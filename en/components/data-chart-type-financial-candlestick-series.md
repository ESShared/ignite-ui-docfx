---
title: Angular Data Chart | Data Visualization Tools | Financial Candle | Infragistics
_description: Use Infragistics' Angular charts control to create financial candlestick charts. Learn about our Ignite UI for Angular graph types!
_keywords: Angular charts, data chart, financial candlestick, Ignite UI for Angular, Infragistics
mentionedTypes: ['XamDataChart', 'FinancialPriceSeries','PriceDisplayType','CategoryXAxis']
---

# Angular Financial Candlestick Chart

The Ignite UI for Angular financial price chart in [`Candlestick`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/enums/pricedisplaytype.html#candlestick) mode is used to plot stock prices, and show the stock’s high, low, open and close prices for each day. Each data point is plotted as a vertical column with vertical lines on both the top and bottom. The vertical line indicates the span between high and low values of an investment. The top of the vertical line indicates the highest price during a session and the bottom of the vertical line indicates the lowest price during a session. The vertical columns indicate the span between the opening and closing values of an investment. The columns are filled using series’ [`brush`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxseriescomponent.html#brush) when there is positive value and using the series' [`negativeBrush`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxfinancialseriescomponent.html#negativebrush) when there is negative value between the opening and closing values.

## Angular Financial Candlestick Chart Example

<div class="sample-container loading" style="height: 400px">
    <iframe id="data-chart-type-financial-candlestick-series-iframe" src='{environment:dvDemosBaseUrl}/charts/data-chart-type-financial-candlestick-series' width="100%" height="100%" seamless frameBorder="0" onload="onXPlatSampleIframeContentLoaded(this);" alt="Angular Financial Candlestick Chart Example"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="data-chart-type-financial-candlestick-series-iframe" data-demos-base-url="{environment:dvDemosBaseUrl}">View on StackBlitz
    </button>


</div>

<div class="divider--half"></div>

## Required Axes

The Angular data chart component provides various types of axes but all financial series can only use the [`IgxNumericYAxisComponent`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxnumericyaxiscomponent.html) as Y-Axis and [`IgxCategoryXAxisComponent`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxcategoryxaxiscomponent.html), [`IgxOrdinalTimeXAxisComponent`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxordinaltimexaxiscomponent.html), or [`IgxTimeXAxisComponent`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxtimexaxiscomponent.html) as X-Axis.

## Required Data

Financial series, indicators, and overlays have the following data requirements:

-   The data source must be an array or a list of data items
-   The data source must contain at least one data item otherwise the data chart will not render the financial series.
-   All data items must contain at least one data column (string or date time) which should be mapped to the [`label`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxaxiscomponent.html#label) property of the financial axis (e.g. [`IgxCategoryXAxisComponent`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxcategoryxaxiscomponent.html))
-   All data items must contain 5 numeric data column which should be mapped using properties of a financial series: [`openMemberPath`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxfinancialseriescomponent.html#openmemberpath), [`highMemberPath`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxfinancialseriescomponent.html#highmemberpath), [`lowMemberPath`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxfinancialseriescomponent.html#lowmemberpath), [`closeMemberPath`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxfinancialseriescomponent.html#closememberpath), [`volumeMemberPath`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxfinancialseriescomponent.html#volumememberpath)

You can use the [SampleFinancialData](data-chart-data-sources-financial.md) as data source which meets above data requirements.

```ts
public dataSource: any[] = SampleFinancialData.create();
```

## Required Modules

The financial series requires the following modules<!-- Angular, React, WebComponents -->.<!-- end: Angular, React, WebComponents --><!-- Blazor --> to be registered in your application entry point:

-   DataChartCoreModule
-   DataChartFinancialModule
-   DataChartFinancialCoreModule
-   DataChartFinancialIndicatorsModule
-   DataChartInteractivityModule
    <!-- end: Blazor -->

```ts
// axis' modules:
import { IgxNumericYAxis } from 'igniteui-angular-charts';
import { IgxCategoryXAxis } from 'igniteui-angular-charts';
// series' modules:
import { IgxFinancialPriceSeries } from 'igniteui-angular-charts';
import { IgxBollingerBandsOverlay } from 'igniteui-angular-charts';
import { IgxMedianPriceIndicator } from 'igniteui-angular-charts';
// data chart's modules:

import { IgxDataChartCoreModule } from 'igniteui-angular-charts';
import { IgxDataChartCategoryModule } from 'igniteui-angular-charts';
import { IgxFinancialPriceSeriesModule } from 'igniteui-angular-charts';

// in app.module.ts file
@NgModule({
    imports: [
        // ...
        IgxDataChartCoreModule,
        IgxDataChartCategoryModule,
        IgxFinancialPriceSeriesModule,
        // ...
    ]
})
```

## Code Example

This code demonstrates how to create an instance of data chart with [`IgxFinancialPriceSeriesComponent`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxfinancialpriceseriescomponent.html), [`IgxBollingerBandsOverlayComponent`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxbollingerbandsoverlaycomponent.html), and [`IgxMedianPriceIndicatorComponent`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxmedianpriceindicatorcomponent.html). Note these series use the same X-Axis and Y-Axis but you can use multiple axes and assign them to different series. Refer to the [Axis Sharing and Multiple Axes](data-chart-axis-sharing.md) topic for more info.

```html
 <igx-data-chart
    [dataSource]="dataSource"
    width="700px"
    height="500px">
    <igx-category-x-axis name="xAxis" label="Date"></igx-category-x-axis>
    <igx-numeric-y-axis  name="yAxis"></igx-numeric-y-axis>
    <igx-bollinger-bands-overlay
        name="series1"
        xAxisName="xAxis"
        yAxisName="yAxis"
        lowMemberPath="Low"
        highMemberPath="High"
        openMemberPath="Open"
        closeMemberPath="Close"
        volumeMemberPath="Volume">
    </igx-bollinger-bands-overlay>

    <igx-financial-price-series
        name="series2"
        xAxisName="xAxis"
        yAxisName="yAxis"
        displayType="Candlestick"
        lowMemberPath="Low"
        highMemberPath="High"
        openMemberPath="Open"
        closeMemberPath="Close"
        volumeMemberPath="Volume">
    </igx-financial-price-series>

    <igx-median-price-indicator
        name="series3"
        xAxisName="xAxis"
        yAxisName="yAxis"
        displayType="Line"
        lowMemberPath="Low"
        highMemberPath="High"
        openMemberPath="Open"
        closeMemberPath="Close"
        volumeMemberPath="Volume">
    </igx-median-price-indicator>
 </igx-data-chart>
```

### Additional Resources

-   [Axis Types](data-chart-axis-types.md)
-   [Axis Sharing](data-chart-axis-sharing.md)
-   [Chart Legend](data-chart-legends.md)
-   [Series Annotations](data-chart-series-annotations.md)
-   [Series Highlighting](data-chart-series-highlighting.md)
-   [Series Markers](data-chart-series-markers.md)
-   [Series Tooltips](data-chart-series-tooltips.md)
-   [Series Trendlines](data-chart-series-trendlines.md)
-   [Series Types](data-chart-series-types.md)
