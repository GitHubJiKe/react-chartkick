# React Chartkick

Create beautiful JavaScript charts with one line of React

[See it in action](https://www.chartkick.com/react)

Supports [Chart.js](http://www.chartjs.org/), [Google Charts](https://developers.google.com/chart/), and [Highcharts](http://www.highcharts.com/)

## Charts

Line chart

```jsx
<LineChart data={{"2017-01-01": 11, "2017-01-02": 6}} />
```

Pie chart

```jsx
<PieChart data={[["Blueberry", 44], ["Strawberry", 23]]} />
```

Column chart

```jsx
<ColumnChart data={[["Sun", 32], ["Mon", 46], ["Tue", 28]]} />
```

Bar chart

```jsx
<BarChart data={[["Work", 32], ["Play", 1492]]} />
```

Area chart

```jsx
<AreaChart data={{"2017-01-01": 11, "2017-01-02": 6}} />
```

Scatter chart

```jsx
<ScatterChart data={[[174.0, 80.0], [176.5, 82.3]]} xtitle="Size" ytitle="Population" />
```

Geo chart - *Google Charts*

```jsx
<GeoChart data={[["United States", 44], ["Germany", 23], ["Brazil", 22]]} />
```

Timeline - *Google Charts*

```jsx
<Timeline data={[["Washington", "1789-04-29", "1797-03-03"], ["Adams", "1797-03-03", "1801-03-03"]]} />
```

Multiple series

```jsx
data = [
  {"name":"Workout", "data": {"2017-01-01": 3, "2017-01-02": 4}},
  {"name":"Call parents", "data": {"2017-01-01": 5, "2017-01-02": 3}}
];

// and
<LineChart data={data} />
```

### Say Goodbye To Timeouts

Make your pages load super fast and stop worrying about timeouts. Give each chart its own endpoint.

```jsx
<LineChart data="/stocks" />
```

### Options

Id, width, and height

```jsx
<LineChart id="users-chart" width="800px" height="500px" />
```

Min and max values

```jsx
<LineChart min={1000} max={5000} />
```

`min` defaults to 0 for charts with non-negative values. Use `null` to let the charting library decide.

Colors

```jsx
<LineChart colors={["#b00", "#666"]} />
```

Stacked columns or bars

```jsx
<ColumnChart stacked={true} />
```

Discrete axis

```jsx
<LineChart discrete={true} />
```

Label (for single series)

```jsx
<LineChart label="Value" />
```

Axis titles

```jsx
<LineChart xtitle="Time" ytitle="Population" />
```

Straight lines between points instead of a curve

```jsx
<LineChart curve={false} />
```

Show or hide legend

```jsx
<LineChart legend={true} />
```

Specify legend position

```jsx
<LineChart legend="bottom" />
```

Donut chart

```jsx
<PieChart donut={true} />
```

Refresh data from a remote source every `n` seconds

```jsx
<LineChart refresh={60} />
```

You can pass options directly to the charting library with:

```jsx
<LineChart library={{backgroundColor: "#eee"}} />
```

See the documentation for [Google Charts](https://developers.google.com/chart/interactive/docs/gallery), [Highcharts](http://api.highcharts.com/highcharts), and [Chart.js](http://www.chartjs.org/docs/) for more info.

### Data

Pass data as an array or object

```jsx
<PieChart data={{"Blueberry": 44, "Strawberry": 23}} />
<PieChart data={[["Blueberry", 44], ["Strawberry", 23]]} />
```

Times can be a `Date`, a timestamp, or a string (strings are parsed)

```jsx
<LineChart data={[[new Date(), 5], [1368174456, 4], ["2017-01-01 00:00:00 UTC", 7]]} />
```

### Download Charts

*Chart.js only*

Give users the ability to download charts. It all happens in the browser - no server-side code needed.

```jsx
<LineChart download={true} />
```

Set the filename

```jsx
<LineChart download="boom" />
```

**Note:** Safari will open the image in a new window instead of downloading.

## Installation

Run

```sh
npm install chartkick react-chartkick --save
```

And import the chart types you want

```es6
import { LineChart, PieChart } from 'react-chartkick';
```

### Chart.js

Run

```sh
npm install chart.js --save
```

And add

```es6
window.Chart = require('chart.js');
```

### Google Charts

Include

```html
<script src="https://www.gstatic.com/charts/loader.js"></script>
```

### Highcharts

Run

```sh
npm install highcharts --save
```

And add

```javascript
window.Highcharts = require('highcharts');
```

### Without NPM

Include the charting library

```html
<script src="https://unpkg.com/chart.js@2.7.1/dist/Chart.bundle.js"></script>
```

And then the Chartkick libraries

```html
<script src="https://unpkg.com/chartkick@2.2.4"></script>
<script src="https://unpkg.com/react-chartkick@0.1.4"></script>
```

## Contributing

Everyone is encouraged to help improve this project. Here are a few ways you can help:

- [Report bugs](https://github.com/ankane/react-chartkick/issues)
- Fix bugs and [submit pull requests](https://github.com/ankane/react-chartkick/pulls)
- Write, clarify, or fix documentation
- Suggest or add new features

To get started with development, run:

```sh
git clone https://github.com/ankane/react-chartkick.git
cd react-chartkick
yarn
npm run build
```
