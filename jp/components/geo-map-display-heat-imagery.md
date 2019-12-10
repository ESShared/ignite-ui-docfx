---
title: Map |データ可視化ツール|Ignite UI for Angular |ヒート画像マップ|インフラジスティックス
_description: マップを使用すると、ヒート画像マップを表示できます。詳細については、サンプルおよび使用方法を参照してください。
_keywords: map, Ignite UI for Angular, infragistics
mentionedTypes: ['XamGeographicMap', 'ShapefileConverter']
_language: ja
---

## ヒート画像の表示

Ignite UI for Angular マップ コントロールには、Shape ファイルをタイル シリーズにロードして地理空間データをロードすることにより、ShapeDataSource によって生成される ShapeFileRecords を使用して、ヒートマップ画像を表示する機能があります。

このトピックを読み進めるための前提条件として、[シェープ ファイルを地理的データにバインディング](geo-map-binding-shp-file.md)をお読みください。

### サンプル

<div class="sample-container loading" style="height: 500px">
    <iframe id="geo-map-display-heat-imagery-iframe" src='{environment:dvDemosBaseUrl}/maps/geo-map-display-heat-imagery' width="100%" height="100%" seamless frameBorder="0" onload="onXPlatSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn"   data-iframe-id="geo-map-display-heat-imagery-iframe" data-demos-base-url="{environment:dvDemosBaseUrl}">StackBlitz で表示
    </button>
</div>

<div class="divider--half"></div>

`ShapeDataSource` がそのシェイプ ファイルを読み込むと、そのデータを ShapeFileRecord オブジェクトに変換します。これらのオブジェクトは、`ShapeDataSource` の `GetPointData()` メソッドから取得でき、`TileGenerator` プロパティに割り当てられた [`HeatTileGenerator`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html) で [`TileGeneratorMapImagery`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/tilegeneratormapimagery.html) オブジェクトを使用してヒートマップを作成するために使用できます。この [`TileGeneratorMapImagery`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/tilegeneratormapimagery.html) は、`TileImagery` ソースとして地理タイルシリーズで使用できます。

[`HeatTileGenerator`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html) オブジェクトは、[`xValues`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#xvalues)、[`yValues`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#yvalues)、[`values`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#values) の 3 つの値パスを持つように機能します。これらの使用方法の例として、人口に関する情報を持つ形状ファイルの場合、[`xValues`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#xvalues) を経度、[`yValues`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#yvalues) を緯度、[`values`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#values) を人口データとみなすことができます。これらの各プロパティは、`number[]` を取得します。

ヒートマップ機能を使用する際の地理的タイルシリーズの表示は、[`minimumColor`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#minimumcolor) プロパティと [`maximumColor`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#maximumcolor) プロパティを [`HeatTileGenerator`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html) の [`values`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#values) プロパティに割り当てるコレクションの最小値と最大値に対応する色を記述する「rgba」文字列に設定することでカスタマイズできます。これをさらにカスタマイズするには、ジェネレーターの `ScaleColors` プロパティを設定して、色を説明する文字列のコレクションを含めます。これにより、[`HeatTileGenerator`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html) に、マップに表示される値に使用する色がわかります。[`blurRadius`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#blurradius)、[`maxBlurRadius`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#maxblurradius)、[`useBlurRadiusAdjustedForZoom`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#useblurradiusadjustedforzoom) プロパティを使用して、`ScaleColors` コレクション内の色が一緒にぼやける方法をカスタマイズすることもできます。

[`HeatTileGenerator`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html) は対数スケールも使用できます。これを使用する場合は、[`useLogarithmicScale`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#uselogarithmicscale) プロパティを `true` に設定できます。

### Web Worker

また、[`HeatTileGenerator`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html) は、Web Worker が、別のスレッドでシェイプ ファイルからタイル イメージをロードする際の重いリフティングをサポートしています。これにより、ヒートマップ機能を使用する際に地理マップのパフォーマンスが大幅に向上します。ジェネレーターでWebワーカーを使用するには、[`useWebWorkers`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#usewebworkers) プロパティを `true` に設定し、[`webWorkerInstance`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/heattilegenerator.html#webworkerinstance) プロパティを Web Worker のインスタンスに設定できます。

<!-- Angular -->

```ts
// heatworker.worker.ts
import { HeatTileGeneratorWebWorker } from "igniteui-angular-core/ES5/HeatTileGeneratorWebWorker";

const worker: Worker = self as any;
worker.onmessage = HeatTileGeneratorWebWorker.onmessage;
HeatTileGeneratorWebWorker.postmessage = heatWorkerPostMessage;
function heatWorkerPostMessage() {
  (self as any).postMessage.apply(self, Array.prototype.slice.call(arguments));
}
HeatTileGeneratorWebWorker.start();
export default {} as typeof Worker & (new () => Worker);
```

### 依存関係

<!-- Angular -->

```ts
import { HeatTileGenerator } from "igniteui-angular-core/ES5/igx-heat-tile-generator";
import { ShapeDataSource } from "igniteui-angular-core/ES5/igx-shape-data-source";
import { IgxGeographicMapComponent } from "igniteui-angular-maps/ES5/igx-geographic-map-component";
import { TileGeneratorMapImagery } from "igniteui-angular-maps/ES5/igx-tile-generator-map-imagery";
```

### ヒートマップの作成

以下のコードスニペットは、人口ベースのヒートマップを Ignite UI for Angular マップ コンポーネントに表示する方法を示しています。

<!-- Angular -->

```html
<igx-geographic-map #map width="100%" height="calc(100% - 60px)">
    <igx-geographic-tile-series name="heatTiles" [tileImagery]="tileImagery"></igx-geographic-tile-series>
</igx-geographic-map>
```

```ts
@ViewChild("map", { static: true })
public map: IgxGeographicMapComponent;
public data: any[];
public tileImagery: TileGeneratorMapImagery;
// ...
constructor() {
    this.data = this.initData();

    this.tileImagery = new TileGeneratorMapImagery();

    const con: ShapeDataSource = new ShapeDataSource();
    con.importCompleted.subscribe((s, e) => {
        const data = con.getPointData();
        const lat: number[] = [];
        const lon: number[] = [];
        const val: number[] = [];
        for (let i = 0; i < data.length; i++) {
            const item = data[i];
            for (let j = 0; j < item.points.length; j++) {
                const pointsList = item.points[j];
                for (let k = 0; k < pointsList.length; k++) {
                    lat.push(pointsList[k].y);
                    lon.push(pointsList[k].x);
                }
            }
            const value = item.fieldValues["POP_2010"];
            if (value >= 0) {
                val.push(value);
            } else {
                val.push(0);
            }
        }

        const gen = new HeatTileGenerator();
        gen.xValues = lon;
        gen.yValues = lat;
        gen.values = val;
        gen.blurRadius = 6;
        gen.maxBlurRadius = 20;
        gen.useBlurRadiusAdjustedForZoom = true;
        gen.minimumColor = "rgba(100,255, 0, 0.3922)";
        gen.maximumColor = "rgba(255, 255, 0, 0.9412)";
        gen.useGlobalMinMax = true;
        gen.useGlobalMinMaxAdjustedForZoom = true;
        gen.useLogarithmicScale = true;
        gen.useWebWorkers = true;
        gen.webWorkerInstance = new Worker("../heatworker.worker", { type: "module" });
        gen.scaleColors = [
            "rgba(0, 0, 255, 64)",
            "rgba(0, 255, 255, 96)",
            "rgba(0, 255, 0, 160)",
            "rgba(255, 255, 0, 180)",
            "rgba(255, 0, 0, 200)"
        ];

        this.tileImagery.tileGenerator = gen;
    });
    con.shapefileSource = "assets/Shapes/AmericanCities.shp";
    con.databaseSource  = "assets/Shapes/AmericanCities.dbf";
    con.dataBind();
}
```