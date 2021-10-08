# Libre Event Editor Table Panel

This panel gives users the ability to list downtime reasons and edit them to assign a reason and comment. Users can also split event to correctly capture downtime information. This panel is part of [Libre](https://github.com/Spruik/Libre). This plugin interfaces to the Libre core GraphQL server. This panel is targeted at Grafana v8.x.x only.

![Panel](./docs/ScreenRecording.gif)

## Installation

The easiest way to get started with this plugin is to [download the latest release](https://github.com/Spruik/Libre-Event-Editor-Table-Panel/releases/latest/download/libre-event-editor-table-panel.zip), unzip into grafana plugin directory and restart grafana.

Download the latest release

```shell
$ wget https://github.com/Spruik/Libre-Event-Editor-Table-Panel/releases/latest/download/libre-event-editor-table-panel.zip
Resolving github.com (github.com)... 140.82.114.4
...
2020-06-24 20:47:59 (1.08 MB/s) - 'libre-event-editor-table-panel.zip' saved [90150]
```

Unzip into your Grafana plugin directory

```shell
$ unzip libre-event-editor-table-panel.zip -d /var/lib/grafana/plugins
Archive: libre-event-editor-table-panel.zip
...
inflating: /var/lib/grafana/libre-event-editor-table-panel/utils.js.map
```

Restart Grafana

```shell
$ service grafana-server restart
 * Stopping Grafana Server
 * Starting Grafana Server
```

## Usage

In order to get the most out of this panel:

1. Add dashboard variables for *Site*, *Area* and *Line* from the database. For example:
```
| Variable | Definition                                                                                                      |
|----------|-----------------------------------------------------------------------------------------------------------------|
| $Site    | query{
   queryEquipment(filter:{not:{has:parent},and:{not:{isActive:false}}}){
      __text: name
      __value: id
   }
}                                                                                  |
| $Area    | query{
   getEquipment(id:"$site"){
      children(filter:{not:{isActive:false}}){
         __text: label
         __value: id
      }
   }
}                                         |
| $Line    |query{
   getEquipment(id:"$area"){
      children(filter:{not:{isActive:false}}){
         __text: label
         __value: id
      }
   }
} |
```
2. Add the following 4 queries to the panel

Equipment
```   graphql
   query {
   getEquipment(id:"${line}"){
      id
      name
   }
}
```
Events
```graphql
query{
  getEquipment(id:"${line}"){
    id
    label
    Events:eventsByField(filter:{filterField:"packMLStatus",filterValue:"Execute",from:"${__from:date:iso}",to:"${__to:date:iso}"}){
      packMLStatus
      startDateTime
      endDateTime
      duration
      reasonCategoryCode
      reasonCode
      reasonText
    }
  }
}
```
Reasons
```graphql
query{
  getEquipment(id:"$line"){
    id
    label
    Reasons:reasonListWithOverrides(filter:{not:{has:parent}}){
      id
      isActive
      class
      label
      text
      parent{id}
      standardValue
      category{code}
    }
  }
}
```
ReasonsWithParents
```graphql
query{
  getEquipment(id:"$line"){
    id
    label
    Reasons:reasonListWithOverrides(filter:{has:parent}){
      id
      isActive
      class
      label
      text
      parent{id}
      standardValue
      category{code}
    }
  }
}
```


### Add/Edit Reason

Click the event in the table, select a category and reason. Type in a comment and click save.

### Split Reason

Click the event in the table, select a category and reason. Type in a comment and click split. Drag the slider to the correct time to split the event. Alternatively use the edit button, type in the desired timestamp and click save. Use the left/right select to choose which side of the split event to apply the currently selected category, reason and comment too. Click save to split the event.

## Contributing

For any issue, there are fundamentally three ways an individual can contribute:

- By opening the issue for discussion: For instance, if you believe that you have uncovered a bug in, creating a new issue in the [GitHub issue tracker](https://github.com/Spruik/Libre-Event-Editor-Table-Panel/issues) is the way to report it.
- By helping to triage the issue: This can be done either by providing supporting details (a test case that demonstrates a bug), or providing suggestions on how to address the issue.
- By helping to resolve the issue: Typically, this is done either in the form of demonstrating that the issue reported is not a problem after all, or more often, by opening a Pull Request that changes some bit of something in the panel in a concrete and reviewable manner.

## Change log

- 2.0.0 Rebuild in react to suit Grafana v8.x.x
- 1.0.1 Documentation Update
   - Fix subtitle & project path
   - Remove unused grunt config

- 1.0.0 Initial Public Release
## Learn more

- [Build a panel plugin tutorial](https://grafana.com/tutorials/build-a-panel-plugin)
- [Grafana documentation](https://grafana.com/docs/)
- [Grafana Tutorials](https://grafana.com/tutorials/) - Grafana Tutorials are step-by-step guides that help you make the most of Grafana
- [Grafana UI Library](https://developers.grafana.com/ui) - UI components to help you build interfaces using Grafana Design System
