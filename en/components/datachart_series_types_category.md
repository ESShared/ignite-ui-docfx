---
title: Data Chart Component - Native Angular | Ignite UI for Angular
_description: The Ignite UI for Angular Data Chart component is TODO.
_keywords: Ignite UI for Angular, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components, Native Angular Components Library, Angular Chart, Angular Chart Control, Angular Chart Example, Angular Chart Component, Angular Data Chart
---

## Category Series

This topic explains various types of category series in the `IgxDataChart` control. Category series is a group of the simplest and most common form of chart series that take data and render it as collection of data points stretched along a horizontal line (e.g. `IgxColumnSeriesComponent`) or vertical line (e.g. `BarSeries`).

### Demo

<div class="sample-container" style="height: 300px">
    <iframe id="data-chart-type-category-series-iframe" src='{environment:demosBaseUrl}/data-chart-type-category-series' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<!-- <div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="financial-chart-type-category-series-iframe" data-demos-base-url="{environment:demosBaseUrl}">View on StackBlitz
    </button>
</div> -->

<div class="divider--half"></div>

### Types of Category Series

The following table lists all types of category series and their descriptions:

| Series Name                    | Description                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `IgxAreaSeriesComponent`       | Displays a set of evenly placed points connected by a line below which area is filled in. Categories are arranged horizontally and values – vertically.                                                                                                                                                                                                                                      |
| `BarSeries`                    | Displays discrete data in separate rows. Unlike other series, categories are arranged vertically and values are plotted horizontally. In other words, this series is like `IgxColumnSeriesComponent` but rotated 90 degrees clockwise.                                                                                                                                                       |
| `IgxColumnSeriesComponent`     | Displays discrete data in separate columns. Categories are arranged horizontally and values are plotted vertically. Used for showing the changes in a data series over time or for comparing multiple items.                                                                                                                                                                                 |
| `IgxLineSeriesComponent`       | Displays a set of evenly placed points connected by straight lines. Used for showing data or information that changes continuously over time. Useful when emphasizing the relationship between the points is required.                                                                                                                                                                       |
| `IgxPointSeriesComponent`      | Displays markers at locations of data points without connecting them by lines. Shape of these markers can be changed using `markerType` property                                                                                                                                                                                                                                             |
| `IgxSplineSeriesComponent`     | Displays a set of evenly placed points connected by smooth lines that are generated using spline interpolation for improved presentation of data.                                                                                                                                                                                                                                            |
| `IgxSplineAreaSeriesComponent` | Same as the `IgxAreaSeriesComponent` type with the added feature of spline interpolation and smoothing for improved presentation of data.                                                                                                                                                                                                                                                    |
| `IgxStepLineSeriesComponent`   | Same as the `IgxLineSeriesComponent` type, except that the values are connected by continuous vertical and horizontal lines forming a step-like progression instead of a straight line tracing the shortest path between points.                                                                                                                                                             |
| `IgxStepAreaSeriesComponent`   | Same as the `IgxStepLineSeriesComponent` type, except that the area below values is filled out instead of continuous vertical and horizontal lines forming a step-like progression for the changes between data points.                                                                                                                                                                      |
| `IgxWaterfallSeriesComponent`  | Displays a set of points as vertical columns that show the difference between values of consecutive data points. The columns are color coded for distinguishing between positive and negative changes in value. Categories are arranged horizontally and values are plotted vertically. Used for showing the changes in a consecutive data points over time or for comparing multiple items. |

### Required Axes

The `IgxDataChart` control provides various types of axes but only the following types of axes can be used with category series.

| Series Type                    | YAxis Type                 | XAxis Type                                                                           |
| ------------------------------ | -------------------------- | ------------------------------------------------------------------------------------ |
| `BarSeries`                    | `CategoryYAxis`            | `IgxNumericXAxisComponent`                                                           |
| `IgxAreaSeriesComponent`       | `IgxNumericYAxisComponent` | `IgxCategoryXAxisComponent`, `IgxOrdinalTimeXAxisComponent`, `IgxTimeXAxisComponent` |
| `IgxColumnSeriesComponent`     | `IgxNumericYAxisComponent` | `IgxCategoryXAxisComponent`, `IgxOrdinalTimeXAxisComponent`, `IgxTimeXAxisComponent` |
| `IgxLineSeriesComponent`       | `IgxNumericYAxisComponent` | `IgxCategoryXAxisComponent`, `IgxOrdinalTimeXAxisComponent`, `IgxTimeXAxisComponent` |
| `IgxSplineSeriesComponent`     | `IgxNumericYAxisComponent` | `IgxCategoryXAxisComponent`, `IgxOrdinalTimeXAxisComponent`, `IgxTimeXAxisComponent` |
| `IgxSplineAreaSeriesComponent` | `IgxNumericYAxisComponent` | `IgxCategoryXAxisComponent`, `IgxOrdinalTimeXAxisComponent`, `IgxTimeXAxisComponent` |
| `IgxStepAreaSeriesComponent`   | `IgxNumericYAxisComponent` | `IgxCategoryXAxisComponent`, `IgxOrdinalTimeXAxisComponent`, `IgxTimeXAxisComponent` |
| `IgxStepLineSeriesComponent`   | `IgxNumericYAxisComponent` | `IgxCategoryXAxisComponent`, `IgxOrdinalTimeXAxisComponent`, `IgxTimeXAxisComponent` |
| `IgxWaterfallSeriesComponent`  | `IgxNumericYAxisComponent` | `IgxCategoryXAxisComponent`, `IgxOrdinalTimeXAxisComponent`, `IgxTimeXAxisComponent` |

### Required Data

Category series have the following data requirements:

-   The data source must be an array or a list of data items
-   The data source must contain at least one data item otherwise the chart will not render the category series.
-   All data items must contain at least one data column (string or date time) which should be mapped to the `Label` property of the category axis (e.g. `IgxCategoryXAxisComponent`)
-   All data items must contain at least one numeric data column which should be mapped using the `ValueMemberPath` property of a category series (e.g. `IgxLineSeriesComponent`)

You can use the [SampleCategoryData](datachart_data_sources_category.md) as data source which meets above data requirements.

```typescript
this.state = { dataSource: SampleCategoryData.create() }
```

### Required Modules

<!-- Angular -->

In order to use category series, you need to import the following modules in your app during load and register data chart modules:

```typescript
// axis' modules:
TODO Angular
// category series' modules:
TODO Angular
// data chart's modules:
TODO Angular
```

### Code Example - Column Series

This code demonstrates how to create an instance of data chart with `IgxColumnSeriesComponent` and bind it to the data source.

```html
 <igx-data-chart
    [dataSource]="dataSource"
    width="700px"
    height="500px">

    TODO

 </igx-data-chart>
```

### Code Example - Bar Series

Note that you can also use above code to create other type of category series by replacing `IgxColumnSeriesComponent` with name of series that you want to render. However, the `BarSeries` is an exception from this rule because it requires different types of axes. This code demonstrates how to create an instance of data chart with `BarSeries` and bind it to the data source.

```html
 <igx-data-chart
    [dataSource]="dataSource"
    width="700px"
    height="500px">

    TODO

 </igx-data-chart>
```

### Additional Resources

-   [Axis Types](datachart_axis_types.md)
-   [Axis Locations](datachart_axis_locations.md)
-   [Axis Sharing](datachart_axis_sharing.md)
-   [Chart Legend](datachart_chart_legends.md)
-   [Series Markers](datachart_series_markers.md)
-   [Series Requirements](datachart_series_requirements.md)
-   [Series Types](datachart_series_types.md)
