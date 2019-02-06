---
title: Data Chart Component - Native Angular | Ignite UI for Angular
_description: The Ignite UI for Angular Data Chart component is TODO.
_keywords: Ignite UI for Angular, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components, Native Angular Components Library, Angular Chart, Angular Chart Control, Angular Chart Example, Angular Chart Component, Angular Data Chart
---

## Series Markers

In the `IgxDataChart` control's plot area, markers are visual elements displayed at location of data points. Markers help your end users immediately identify a data point’s even if its values fall between major or minor grid lines.

### Demo

<div class="sample-container" style="height: 300px">
    <iframe id="data-chart-overview-iframe" src='{environment:demosBaseUrl}/data-chart-overview' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<!-- <div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="financial-chart-overview-iframe" data-demos-base-url="{environment:demosBaseUrl}">View on StackBlitz
    </button>
</div> -->

<div class="divider--half"></div>

### Supported Series

Most of chart series support markers and they are listed below:

-   All [Category Series](datachart_series_types_category.md)
-   All [Polar Series](datachart_series_types_polar.md)
-   All [Radial Series](datachart_series_types_radial.md)
-   Some Scatter Series:
    -   [Scatter Bubble Series](datachart_series_types_scatter_bubble.md)
    -   [Scatter Point Series](datachart_series_types_scatter_marker.md)
    -   [Scatter Line Series](datachart_series_types_scatter_marker.md)
    -   [Scatter Spline Series](datachart_series_types_scatter_marker.md)

### Marker Properties

Above series support 12 shapes of markers that you can change using the `MarkerType` property.  Also, you can change fill and stroke using `MarkerBrush` and `MarkerOutline` properties respectively.

This code snippet below demonstrate how to change shape and appearance of markers.

```html
 <igx-data-chart
    [dataSource]="dataSource"
    width="700px"
    height="500px">

    TODO

 </igx-data-chart>
```

<!-- TODO add this section when we add MarkerTemplate

### Marker Templates

You can provide custom shape using the `MarkerTemplate` property.

This code snippet below demonstrate how to create custom  marker with values of data points.


```html
 <igx-data-chart
    [dataSource]="dataSource"
    width="700px"
    height="500px">

    TODO

 </igx-data-chart>
```

```tsx
<IgrColumnSeries name="series1"
    markerTemplate="customMarker" />
``` -->

### Additional Resources

-   [Axis Types](datachart_axis_types.md)
-   [Series Types](datachart_series_types.md)
-   [Series Tooltips](datachart_series_tooltips.md)
