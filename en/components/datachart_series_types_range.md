---
title: Data Chart Component - Native Angular | Ignite UI for Angular
_description: The Ignite UI for Angular Data Chart component is TODO.
_keywords: Ignite UI for Angular, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components, Native Angular Components Library, Angular Chart, Angular Chart Control, Angular Chart Example, Angular Chart Component, Angular Data Chart
---

## Range Series

This topic explains various types of range series in the `IgxDataChart` control. range series is a group of chart series that take two numeric data columns and render them as collection of data points stretched in horizontal orientation (e.g. `IgxRangeAreaSeriesComponent`)

### Demo

<div class="sample-container" style="height: 300px">
    <iframe id="data-chart-type-range-series-iframe" src='{environment:demosBaseUrl}/data-chart-type-range-series' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<!-- <div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="financial-chart-type-range-series-iframe" data-demos-base-url="{environment:demosBaseUrl}">View on StackBlitz
    </button>
</div> -->

<div class="divider--half"></div>

### Types of Range Series

The following table lists all types of range series and their descriptions:

| Series Name                     | Description                                                                                                                                                |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `IgxRangeAreaSeriesComponent`   | Displays filled region/area between pairs of High/Low values of data points. Categories are arranged horizontally and values – vertically.                 |
| `IgxRangeColumnSeriesComponent` | Displays discrete data in separate columns between High/Low values of data points. Categories are arranged horizontally and values are plotted vertically. |

### Required Axes

The `IgxDataChart` control provides various types of axes but only the following types of axes can be used with range series.

| Series Type                     | YAxis Type                 | XAxis Type                                                                           |
| ------------------------------- | -------------------------- | ------------------------------------------------------------------------------------ |
| `IgxRangeAreaSeriesComponent`   | `IgxNumericYAxisComponent` | `IgxCategoryXAxisComponent`, `IgxOrdinalTimeXAxisComponent`, `IgxTimeXAxisComponent` |
| `IgxRangeColumnSeriesComponent` | `IgxNumericYAxisComponent` | `IgxCategoryXAxisComponent`, `IgxOrdinalTimeXAxisComponent`, `IgxTimeXAxisComponent` |

### Required Data

Range series have the following data requirements:

-   The data source must be an array or a list of data items
-   The data source must contain at least one data item otherwise the chart will not render the range series.
-   All data items must contain at least one label data column (string or date time) which should be mapped to the `Label` property of the category axis (e.g. `IgxCategoryXAxisComponent`)
-   All data items must contain at least two numeric data column which should be mapped using the `HighMemberPath` and `LowMemberPath` properties of range series (e.g. `IgxRangeAreaSeriesComponent`)

You can use the [SampleRangeData](datachart_data_sources_range.md) as data source which meets above data requirements.

```typescript
this.state = { dataSource: SampleRangeData.create() }
```

### Required Modules

<!-- Angular -->

In order to use range series, you need to import the following modules in your app during load and register data chart modules:

```typescript
// axis' modules:
TODO Angular
// category series' modules:
TODO Angular
// data chart's modules:
TODO Angular
```

### Code Example

This code demonstrates how to create an instance of data chart with `IgxRangeColumnSeriesComponent` and bind it to the data source.

```html
 <igx-data-chart
    [dataSource]="dataSource"
    width="700px"
    height="500px">

    TODO

 </igx-data-chart>
```

Note that you can also use above code to create `IgxRangeAreaSeriesComponent` by replacing `IgxRangeColumnSeriesComponent`.

### Additional Resources

-   [Axis Types](datachart_axis_types.md)
-   [Axis Locations](datachart_axis_locations.md)
-   [Axis Sharing](datachart_axis_sharing.md)
-   [Chart Legend](datachart_chart_legends.md)
-   [Series Markers](datachart_series_markers.md)
-   [Series Requirements](datachart_series_requirements.md)
-   [Series Types](datachart_series_types.md)
