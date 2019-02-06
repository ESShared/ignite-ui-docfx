---
title: Highlighting
_description: The Ignite UI for Category Chart component simplifies the complexities of the data visualization domain into manageable API so that a user can bind a collection of data, a group of collections, and a data property, and let the charting control do the rest.
_keywords: Ignite UI for Angular, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components, Native Angular Components Library, Angular Chart, Angular Chart Control, Angular Chart Example, Angular Grid Component, Angular Chart Component, Angular Category Chart
---

## Highlighting

This topic provides conceptual information about the highlighting features of the `IgxCategoryChart`.

### Demo

<div class="sample-container" style="height: 500px">
    <iframe id="category-chart-highlighting-sample-iframe" src='{environment:demosBaseUrl}/category-chart-highlighting-sample' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<!-- <div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="category-chart-highlighting-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">View on StackBlitz
    </button>
</div> -->
<div class="divider--half"></div>

### Highlight Layers

The `IgxCategoryChart` can enable three types of highlighting when hovering over items.

1.  Series Highlighting will highlight the single data point when the pointer is positioned over it.

2.  Item Highlighting highlights items in a series either by drawing a banded shape at their position or by rendering a marker at their position.

3.  Category Highlighting targets all category axes in the chart. They draw a shape that illuminates the area of the axis closest to the pointer position.

```html
<igx-category-chart
    [dataSource]="data"
    isSeriesHighlightingEnabled="true"
    isCategoryHighlightingEnabled="true"
    isItemHighlightingEnabled="true">
</igx-category-chart>
```
