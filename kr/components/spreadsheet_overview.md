---
title: Angular Spreadsheet | Grid Controls | Overview | Infragistics |
_description: Use the Spreadsheet control to embed Excel document creation and editing experiences right into your application.
_keywords: Spreadsheet, Ignite UI for Angular, Infragistics
mentionedTypes: ['Spreadsheet']
---

# Angular Angular Spreadsheet

The Angular Spreadsheet is a Angular component that allows visualizing and editing of spreadsheet data. Features include activation, cell editing, conditional formatting, selection, clipboard.

## Demo

<div class="sample-container loading" style="height: 500px">
    <iframe id="spreadsheet-overview-sample-iframe" src='{environment:dvDemosBaseUrl}/excel/spreadsheet-overview' width="100%" height="100%" seamless frameBorder="0" onload="onXPlatSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn"   data-iframe-id="spreadsheet-overview-sample-iframe" data-demos-base-url="{environment:dvDemosBaseUrl}">View on StackBlitz
    </button>


</div>

<div class="divider--half"></div>

## Dependencies

When installing the spreadsheet package, the core and excel package must also be installed.

-   **npm install --save igniteui-angular-core**
-   **npm install --save igniteui-angular-excel**
-   **npm install --save igniteui-angular-spreadsheet**

## Required Modules

The [`IgxSpreadsheetComponent`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxspreadsheetcomponent.html) requires the following modules<!-- Angular, React, WebComponents -->.<!-- end: Angular, React, WebComponents --><!-- Blazor --> to be registered in your application entry point:

-   ExcelModule
-   SpreadsheetModule
    <!-- end: Blazor -->

```ts
import { IgxExcelModule } from 'igniteui-angular-excel';
import { IgxSpreadsheetModule } from 'igniteui-angular-spreadsheet';

@NgModule({
    imports: [
        // ...
        IgxExcelModule,
        IgxSpreadsheetModule,
        // ...
    ]
})
export class AppModule {}
```

<div class="divider--half"></div>

## Usage

Now that the spreadsheet module is imported, next is the basic configuration of the spreadsheet.

```html
<igx-spreadsheet #spreadsheet height="500px" width="100%">
</igx-spreadsheet>
```

> [!NOTE]
>
> In the following code snippet, an external [ExcelUtility](excel-utility.md) class is used to save and load a [`workbook`]({environment:dvApiBaseUrl}/products/ignite-ui-angular/api/docs/typescript/latest/classes/igxspreadsheetcomponent.html#workbook).

The following demonstrates how to load a workbook into the spreadsheet

```ts
import { IgxSpreadsheetComponent } from 'igniteui-angular-spreadsheet';
import { ExcelUtility } from 'ExcelUtility';

// ...
@ViewChild("spreadsheet", { read: IgxSpreadsheetComponent })
public spreadsheet: IgxSpreadsheetComponent;

ngOnInit() {
    const excelFile = '../../assets/Sample1.xlsx';
    ExcelUtility.loadFromUrl(excelFile).then((w) => {
      this.spreadsheet.workbook = w;
    });
  }
```
