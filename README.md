# Highstock Dart wrapper library
[![GitHub release](https://img.shields.io/github/release/instrumentisto/highstock.svg)](https://github.com/instrumentisto/highstock)

Library that allows to use Highstock chart library in Dart applications.


## Installation

Include highstock.js in your project from package asset, CDN or as bower dependency.

```html
<script src="http://code.highcharts.com/stock/4.2.4/highstock.js"></script>
```


## Usage

Instantiate Highstock chart library with container to render chart into:

```dart
var chart = new HighstockChart(new StockChartOptions()
  ..chart = (new Chart()
    ..renderTo = querySelector('#payments_chart')));
```

You can add some data to chart before rendering:

```dart
var chart = new HighstockChart(new StockChartOptions()
  ..chart = (new Chart()
    ..renderTo = querySelector('#payments_chart'))
  ..series = [new LineSeries()
    ..name = 'Demo'
    ..type = 'line'
    ..data = [0, 2, 1]]);
```

... or after rendering:

```dart
var chart = new HighstockChart(new StockChartOptions()
  ..chart = (new Chart()
    ..renderTo = querySelector('#payments_chart'))
  ..series = [new LineSeries()
    ..name = 'Demo'
    ..type = 'line']);
chart.series[0].setData([0, 2, 1], true, false, false);
```


## Structure

Class hierarchy is the same as in highstock library.  
Each option is mapped to the related class, so if you want to tune chart title, 
you should use Title class, for legend - Legend class etc.
