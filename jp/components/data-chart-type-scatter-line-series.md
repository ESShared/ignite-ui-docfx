---
title: Data Chart |可視化ツール|Ignite UI for Angular |Infragistics |散布図 - 折れ線
_description: 同じプロット領域に視覚要素の複数インスタンスを表示するデータ チャートを作成し、複合チャートビューを作成します。
_keywords: data chart, Ignite UI for Angular, Infragistics
mentionedTypes: ['XamDataChart', 'ScatterLineSeries']
_language: ja
---

## 散布折れ線チャート

Ignite UI for Angular 散布折れ線チャートは、デカルト (x, y) 座標系を使用してデータをプロットする散布図のグループに属します。このシリーズは、直線で接続されたマーカーのコレクションとしてレンダリングされ、各マーカーにはデカルト座標系での位置を決定する X/Y の数値のペアがあります。

[`IgxScatterLineSeriesComponent`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxscatterlineseriescomponent.html) は、不均等な間隔またはデータのクラスターに注意を促します。予測結果の収集データの標準偏差を強調表示し、科学データや統計データをプロットするためによく使用されます。[`IgxScatterLineSeriesComponent`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxscatterlineseriescomponent.html) は、データを時系列に整理して X 軸と Y 軸にプロットします (バインド前にデータが時系列に並んでいなくても)。

### サンプル

<div class="sample-container loading" style="height: 500px">
    <iframe id="data-chart-type-scatter-line-series-iframe" src='{environment:dvDemosBaseUrl}/charts/data-chart-type-scatter-line-series' width="100%" height="100%" seamless frameBorder="0" onload="onXPlatSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="data-chart-type-scatter-line-series-iframe" data-demos-base-url="{environment:dvDemosBaseUrl}">StackBlitz で表示
    </button>
</div>

<div class="divider--half"></div>

### 軸の要件

Angular データ チャート コンポーネントはさまざまなタイプの軸を提供しますが、[`IgxScatterLineSeriesComponent`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxscatterlineseriescomponent.html) で使用できるのは以下のタイプの軸のみです。

-   [`IgxNumericXAxisComponent`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxnumericxaxiscomponent.html)
-   [`IgxNumericYAxisComponent`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxnumericyaxiscomponent.html)

### データの要件

[`IgxScatterLineSeriesComponent`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxscatterlineseriescomponent.html) には以下のデータ要件があります。

-   データソースはデータ項目の配列またはリストである必要があります。
-   データソースはデータ項目を少なくとも 1 つ含む必要があります。含まない場合はチャートに散布シェイプ シリーズを描画しません。
-   すべてのデータ項目には、[`xMemberPath`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxscatterbasecomponent.html#xmemberpath) と [`yMemberPath`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxscatterbasecomponent.html#ymemberpath)  プロパティにマップされる 2 つの数値データ列を含める必要があります。

上記データ要件を満たすデータソースとして [SamplePolarData](data-chart-data-sources-stats.md) を使用できます。

```ts
public dataSource: any[] = SampleScatterStats.getCountries();
```

### モジュールの要件

[`IgxScatterLineSeriesComponent`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxscatterlineseriescomponent.html) は以下のモジュールを要求します。

```ts
// axis' modules:
import { IgxNumericYAxis } from "igniteui-angular-charts/ES5/igx-numeric-y-axis";
import { IgxNumericXAxis } from "igniteui-angular-charts/ES5/igx-numeric-x-axis";
// series' modules:
import { IgxScatterLineSeries } from "igniteui-angular-charts/ES5/igx-scatter-line-series";
import { MarkerType } from "igniteui-angular-charts/ES5/MarkerType";
// data chart's modules:

import { IgxDataChartCoreModule } from "igniteui-angular-charts/ES5/igx-data-chart-core-module";
import { IgxDataChartScatterCoreModule } from "igniteui-angular-charts/ES5/igx-data-chart-scatter-core-module";
import { IgxDataChartScatterModule } from "igniteui-angular-charts/ES5/igx-data-chart-scatter-module";

@NgModule({
    imports: [
        // ...
        IgxDataChartCoreModule,
        IgxDataChartScatterCoreModule,
        IgxDataChartScatterModule,
    ]
})
export class AppModule { /* ... */ }
```

### コード例

このコードは、[`IgxScatterLineSeriesComponent`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxscatterlineseriescomponent.html) を使用して Ignite UI for Angular データ チャートのインスタンスを作成し、それをデータ ソースにバインドする方法を示します。

```html
 <igx-data-chart
    [dataSource]="dataSource"
    width="700px"
    height="500px">
    <igx-numeric-x-axis name="xAxis" isLogarithmic="true"></igx-numeric-x-axis>
    <igx-numeric-y-axis name="yAxis" isLogarithmic="true"></igx-numeric-y-axis>
    <igx-scatter-line-series
        name="series1"
        xAxisName="xAxis"
        yAxisName="yAxis"
        xMemberPath="Population"
        yMemberPath="GdpTotal">
    </igx-scatter-line-series>
 </igx-data-chart>
```

### シリーズの外観

[マーカー](data-chart-series-markers.md) プロパティを使用してマーカーの外観をカスタマイズできます。マーカーごとに [`brush`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxseriescomponent.html#brush) と [`thickness`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxseriescomponent.html#thickness) のビジュアルを変更することもできます。以下のこのコードスニペットは、これらのプロパティの使用方法を示しています。

```html
<igx-scatter-line-series
 name="series1"
 brush="Purple"
 markerType="Square"
 markerBrush="White"
 markerOutline="Blue"
 thickness="2">
</igx-scatter-line-series>
```

```ts
const series1 = new IgxScatterLineSeries({ name: "series1" });
series1.markerType = MarkerType.Square;
series1.markerBrush = "White";
series1.markerOutline = "Blue";
series1.brush = "Purple";
series1.thickness = 2;
```

### その他のリソース

-   [軸のタイプ](data-chart-axis-types.md)
-   [軸の共有](data-chart-axis-sharing.md)
-   [チャート凡例](data-chart-legends.md)
-   [シリーズ マーカー](data-chart-series-markers.md)
-   [シリーズのツールチップ](data-chart-series-tooltips.md)
-   [シリーズ トレンドライン](data-chart-series-trendlines.md)
-   [シリーズ タイプ](data-chart-series-types.md)