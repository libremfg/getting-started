# Changelog

## 0.8.0 (2022-01-28)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.7.5...v0.8.0)

This release bumps the minimum required Grafana to >=8.1. Grafana 8 introduces a new theming engine for panel plugins.

- If you're running a Grafana version before 8.0, you should stay with v0.7.5.
- If you're running Grafana 8.1 or above, you should update to v0.8.0.

## 0.7.5 (2022-01-07)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.7.4...v0.7.5)

### Bug fixes

- `experiments` is undefined ([#69](https://github.com/marcusolsson/grafana-gantt-panel/issues/69)) (thanks [@prOOrc](https://github.com/pr00rc)!)

## 0.7.4 (2021-09-05)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.7.3...v0.7.4)

### Bug fixes

- Fix Data Links in Grafana 8.0 ([#49](https://github.com/marcusolsson/grafana-gantt-panel/issues/49))

## 0.7.3 (2021-08-06)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.7.2...v0.7.3)

### Bug fixes

- Cannot read property 'visualization' of undefined ([#38](https://github.com/marcusolsson/grafana-gantt-panel/issues/38))

## 0.7.2 (2021-06-15)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.7.1...v0.7.2)

### Enhancements

- Upgrade grafana-plugin-support dependency

## 0.7.1 (2021-06-15)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.7.0...v0.7.1)

### Enhancements

- Nothing plotted when too many values on y axis ([#32](https://github.com/marcusolsson/grafana-gantt-panel/issues/32))
- Metadata and docs updates
- Upgrade dependencies

## 0.7.0 (2021-05-09)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.6.1...v0.7.0)

### Enhancements

- Color support: You can now configure colors based on text and number fields. Unfortunately, **this bumps the minimum required Grafana version to 7.3.0** ([#26](https://github.com/marcusolsson/grafana-gantt-panel/pull/26))
- Support for data links ([#25](https://github.com/marcusolsson/grafana-gantt-panel/issues/25))
- Improved zoom support
- Option to not display y axis labels ([#30](https://github.com/marcusolsson/grafana-gantt-panel/issues/30))
- Limit task bar height ([#22](https://github.com/marcusolsson/grafana-gantt-panel/pull/22)) (thanks @ymmt07039)

## 0.6.1 (2021-03-07)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.6.0...v0.6.1)

### Enhancements

- Limit Y-axis to relevant values only ([#19](https://github.com/marcusolsson/grafana-gantt-panel/issues/19))

## 0.6.0 (2021-02-18)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.5.0...v0.6.0)

### Enhancements

Adds a new Experiments category with two new features: _Lock to extents_ and _Relative time_:

- **Lock to extents** locks the zoom to fit all tasks from start to finish
- **Relative time** changes the X axis to display the duration from when the first task started

## 0.5.0 (2021-02-16)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.4.0...v0.5.0)

### Enhancements

- Add option to sort tasks by text or by start time ([#15](https://github.com/marcusolsson/grafana-gantt-panel/issues/15))
- Make dimensions clearable ([#12](https://github.com/marcusolsson/grafana-gantt-panel/issues/12))
- Add fallback panel for unsupported Grafana versions
- Add wizard for configuring the query

## 0.4.0 (2021-02-06)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.3.1...v0.4.0)

### Enhancements

- Add labels to tooltip ([#9](https://github.com/marcusolsson/grafana-gantt-panel/issues/9))
- Click-and-drag to change dashboard time interval ([#10](https://github.com/marcusolsson/grafana-gantt-panel/issues/10))

## 0.3.1 (2021-02-02)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.3.0...v0.3.1)

### Bug fixes

- Reduced precision when using strings as time ([#5](https://github.com/marcusolsson/grafana-gantt-panel/issues/5))

## 0.3.0 (2021-01-28)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.2.0...v0.3.0)

### Enhancements

- Null values are interpreted as infinity
- Add duration to tooltip
- Improved styles

## 0.2.0 (2020-01-27)

[Full changelog](https://github.com/marcusolsson/grafana-gantt-panel/compare/v0.1.0...v0.2.0)

### Enhancements

- Allow using string and number fields as time ([#1](https://github.com/marcusolsson/grafana-gantt-panel/issues/1), [#2](https://github.com/marcusolsson/grafana-gantt-panel/issues/2))

## 0.1.0 (2020-01-08)

Initial release. Not fit for production use.
