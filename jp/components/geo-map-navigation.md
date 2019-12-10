---
title: Map |データ可視化ツール|Ignite UI for Angular |マップ ナビゲーション|インフラジスティックス
_description: マップでは、地理座標またはウィンドウ座標を使用して移動できます。
_keywords: map, Ignite UI for Angular, インフラジスティックス
mentionedTypes: ['XamGeographicMap']
_language: ja
---

## コンテンツのナビゲーション

[`IgxGeographicMapComponent`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxgeographicmapcomponent.html) コントロールのナビゲーションは、既定では有効にされており、マップ コンテンツのズームとパンが可能です。ただし、この動作は [`zoomable`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxgeographicmapcomponent.html#zoomable) プロパティを使用して変更できます。マップでは同期ズームのみが許可されていること、つまり、アスペクト比を維持したままマップコンテンツをスケーリングすることを知っておくことが重要です。結果として、マップコンテンツを水平方向にスケーリングせずに垂直方向にスケーリングすることはできません。

### サンプル

<div class="sample-container loading" style="height: 500px">
    <iframe id="geo-map-navigation-iframe" src='{environment:dvDemosBaseUrl}/maps/geo-map-navigation' width="100%" height="100%" seamless frameBorder="0" onload="onXPlatSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn"   data-iframe-id="geo-map-navigation-iframe" data-demos-base-url="{environment:dvDemosBaseUrl}">StackBlitz で表示
    </button>
</div>

<div class="divider--half"></div>

### 地理座標

これらの座標で囲まれた地理的領域内の地図コンテンツをナビゲートします。

-   経度180°E(マイナス) から 180°W(プラス) の緯度
-   南緯 85 度 (マイナス) から北緯 85 度 (プラス)

このコードスニペットは、地理座標を使用してマップをナビゲートする方法を示しています。

### ウィンドウ座標

また、これらの相対座標で区切られたウィンドウ長方形内でマップ コンテンツをナビゲーションできます。

-   水平方向に 0.0 から 1.0 の値
-   垂直方向に 0.0 から 1.0 の値

このコードスニペットは、相対ウィンドウ座標を使用してマップをナビゲートする方法を示しています。

### プロパティ

以下の表は [`IgxGeographicMapComponent`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxgeographicmapcomponent.html) コントロールのナビゲーションで使用できるプロパティをまとめたものです。

| プロパティ名                                                                                                                                                          | プロパティ タイプ | 概要                                                                                                    |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- | ----------------------------------------------------------------------------------------------------- |
| [`windowRect`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxseriesviewercomponent.html#windowrect)                                         | Rect      | 地図コンテンツの表示領域にナビゲーション ウィンドウの新しい位置とサイズを設定します。0、0、1、1 の値で長方形を指定すると、ナビゲーション ウィンドウのマップ コンテンツ全体がズームアウトされます。 |
| [`windowScale`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxgeographicmapcomponent.html#windowscale)                                      | number    | マップ コントロールのナビゲーション ウィンドウの新しいサイズを設定します。WindowRect プロパティに格納されている Width または Height の最小値です。               |
| [`windowPositionHorizontal`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxseriesviewercomponent.html#windowpositionhorizontal)             | number    | マップ コントロールの左端からのナビゲーション ウィンドウのアンカー ポイントの新しい水平位置を設定します。これは WindowRect プロパティの Left に保存された値と等しくなります。     |
| [`windowPositionVertical`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxseriesviewercomponent.html#windowpositionvertical)                 | number    | ナビゲーション ウィンドウのアンカー ポイントの、地図コントロールの上端からの新しい垂直位置を設定します。これは WindowRect プロパティの Top に保存された値と等しくなります。       |
| [`actualWindowRect`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxseriesviewercomponent.html#actualwindowrect)                             | Rect      | マップ コンテンツの表示領域内のナビゲーション ウィンドウの現在の位置とサイズを示します。0、0、1、1の値で長方形を指定すると、ナビゲーション ウィンドウにマップ コンテンツ全体が表示されます。    |
| [`actualWindowScale`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxgeographicmapcomponent.html#actualwindowscale)                          | number    | マップ コントロールのナビゲーション ウィンドウの現在のサイズを示します。 ActualWindowRect プロパティに格納されている Width または Height の最小値と同じです。      |
| [`actualWindowPositionHorizontal`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxseriesviewercomponent.html#actualwindowpositionhorizontal) | number    | マップ コントロールの左端からのナビゲーション ウィンドウのアンカー ポイントの現在の水平位置を示します。ActualWindowRect プロパティの Left に保存された値と等しくなります。    |
| [`actualWindowPositionVertical`](/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxseriesviewercomponent.html#actualwindowpositionvertical)     | number    | マップコントロールの上端からのナビゲーションウィンドウのアンカーポイントの垂直位置を示します。ActualWindowRect プロパティの Top に保存された値と等しくなります。           |