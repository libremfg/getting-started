# Gantt for Grafana

[![Build](https://github.com/marcusolsson/grafana-gantt-panel/workflows/CI/badge.svg)](https://github.com/marcusolsson/grafana-gantt-panel/actions?query=workflow%3A%22CI%22)
[![Release](https://github.com/marcusolsson/grafana-gantt-panel/workflows/Release/badge.svg)](https://github.com/marcusolsson/grafana-gantt-panel/actions?query=workflow%3ARelease)
[![Marketplace](https://img.shields.io/badge/dynamic/json?logo=grafana&color=F47A20&label=marketplace&prefix=v&query=%24.items%5B%3F%28%40.slug%20%3D%3D%20%22marcusolsson-gantt-panel%22%29%5D.version&url=https%3A%2F%2Fgrafana.com%2Fapi%2Fplugins)](https://grafana.com/grafana/plugins/marcusolsson-gantt-panel)
[![Downloads](https://img.shields.io/badge/dynamic/json?logo=grafana&color=F47A20&label=downloads&query=%24.items%5B%3F%28%40.slug%20%3D%3D%20%22marcusolsson-gantt-panel%22%29%5D.downloads&url=https%3A%2F%2Fgrafana.com%2Fapi%2Fplugins)](https://grafana.com/grafana/plugins/marcusolsson-gantt-panel)
[![License](https://img.shields.io/github/license/marcusolsson/grafana-gantt-panel)](LICENSE)
[![Twitter](https://img.shields.io/twitter/follow/marcusolsson?color=%231DA1F2&label=twitter&style=plastic)](https://twitter.com/marcusolsson)

A panel plugin for [Grafana](https://grafana.com) to visualize Gantt charts.

Gantt charts display a list of _tasks over time_, where each task is visualized using a bar with a start and an end time.

## Features

- Identify bottlenecks where one or more tasks are running significantly longer than others
- Compare recurring sets of tasks by grouping them, such as data pipelines that run in regular intervals.
- Display additional metadata from your data source as labels

![Screenshot](https://github.com/marcusolsson/grafana-gantt-panel/raw/main/src/img/dark.png)

## Configuration

This section lists the available configuration options for the Gantt panel.

### Panel options

#### Experiments

By enabling experiments, you can try out new features that we're working on. **Experiments can be unstable and may break your panel**. Use at your own risk.

#### Dimensions

| Option       | Description                                                                                                                                                                                                                                                                                       |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| _Text_       | Name of the field to use for task labels. Defaults to the first string field.                                                                                                                                                                                                                     |
| _Start time_ | Name of the field to use for value. Defaults to the first time field.                                                                                                                                                                                                                             |
| _End time_   | Name of the field to use for value. Defaults to the second time field.                                                                                                                                                                                                                            |
| _Color by_   | Field to use for colors. Defaults to the text field. Color configuration depends on the field type. If the dimension is set to a string field, you can add _color mappings_ for each value. If the dimension is set to a number field, you can instead use field options to configure the colors. |
| _Group by_   | Name of the field to use to group tasks. When grouping tasks, the time interval is set to the start of the first task and the end of the last task in the group.                                                                                                                                  |
| _Labels_     | Fields to use as labels in the tooltip.                                                                                                                                                                                                                                                           |

As some data sources don't yet support time fields, the plugin supports selecting string and number fields as start and end time:

- If you select a string field, values need to be ISO 8601 strings
- If you select a number field, values need to be Unix timestamps in milliseconds

#### Display

| Option           | Description                                                                        |
|------------------|------------------------------------------------------------------------------------|
| _Show Y-axis_    | Toggles the Y-axis.                                                                |
| _Sort by_        | Dimension to sort tasks by.                                                        |
| _Sort order_     | Order in which to sort the tasks.                                                  |
| _Color mappings_ | Configures task color based on the text value based on the **Color by** dimension. |
