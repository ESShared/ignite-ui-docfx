---
title: Layout Manager Directive
_description: Only Ignite UI for Angular Layout Manager directive provides various styles of responsive and fluid user interfaces.
_keywords: Ignite UI for Angular, UI controls, Angular widgets, web widgets, UI widgets, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components Library, Angular Layout Manager component, Angular Layout Manager controls
---

# Layout Manager
<p class="highlight">The Ignite UI for Angular Layout Directive allows developers to specify a layout direction for any children of the container it is applied to. Layout can flow vertically or horizontally, with controls for wrapping, justification, and alignment.</p>
<div class="divider"></div>

## Angular Layout Manager Example
<div class="divider--half"></div>

<div class="sample-container loading" style="height: 580px">
    <iframe id="layout-sample-iframe" src='{environment:demosBaseUrl}/layouts/layout-sample' width="100%" height="100%" seamless="" frameborder="0" onload="onSampleIframeContentLoaded(this);" alt="Angular Layout Manager Example"></iframe>
</div>
<p style="margin: 0;padding-top: 0.5rem">Like this sample? Get access to our complete Angular toolkit and start building your own apps in minutes. <a class="no-external-icon mchNoDecorate trackCTA" target="_blank" href="https://www.infragistics.com/products/ignite-ui-angular/download" data-xd-ga-action="Download" data-xd-ga-label="Ignite UI for Angular">Download it for free.</a></p>
<div>
<button data-localize="codesandbox" disabled class="codesandbox-btn" data-iframe-id="layout-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on codesandbox</button>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="layout-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider--half"></div>

## Usage

Use the [**igxLayout**]({environment:angularApiUrl}/classes/igxlayoutdirective.html) directive on a container element to specify the layout direction for its children:

<div class="divider--half"></div>

### Horizontally with Row direction

Use [`igxLayoutDir`]({environment:angularApiUrl}/classes/igxlayoutdirective.html#dir)`="row"`.
<div class="sample-container loading" style="height: 180px">
    <iframe id="layout-direction-row-iframe" src='{environment:demosBaseUrl}/layouts/layout-direction-row' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="codesandbox" disabled class="codesandbox-btn" data-iframe-id="layout-direction-row-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on codesandbox</button>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="layout-direction-row-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider--half"></div>

### Vertically with Column direction

Use [`igxLayoutDir`]({environment:angularApiUrl}/classes/igxlayoutdirective.html#dir)`="column"`.
<div class="sample-container loading" style="height: 300px">
    <iframe id="layout-direction-column-iframe" src='{environment:demosBaseUrl}/layouts/layout-direction-column' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="codesandbox" disabled class="codesandbox-btn" data-iframe-id="layout-direction-column-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on codesandbox</button>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="layout-direction-column-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider--half"></div>

**Note**: Reverse order using [`igxLayoutReverse`]({environment:angularApiUrl}/classes/igxlayoutdirective.html#reverse)`="true"`.

<div class="divider--half"></div>

### Customize the order of the elements
Customize the order of the element by using `igxFlexOrder`.

<div class="sample-container loading" style="height: 110px">
    <iframe id="layout-custom-order-iframe" src='{environment:demosBaseUrl}/layouts/layout-custom-order' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="codesandbox" disabled class="codesandbox-btn" data-iframe-id="layout-custom-order-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on codesandbox</button>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="layout-custom-order-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider--half"></div>

### Change element spacing

Use [`igxLayoutJustify`]({environment:angularApiUrl}/classes/igxlayoutdirective.html#justify)`="space-between | space-around"`.
<div class="sample-container loading" style="height: 180px">
    <iframe id="layout-content-space-iframe" src='{environment:demosBaseUrl}/layouts/layout-content-space' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="codesandbox" disabled class="codesandbox-btn" data-iframe-id="layout-content-space-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on codesandbox</button>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="layout-content-space-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider--half"></div>

### Position elements along the main axis
Use [`igxLayoutJustify`]({environment:angularApiUrl}/classes/igxlayoutdirective.html#justify)`="flex-start | center | flex-end"` to specify the elements position along the main axis according to your preferences.
<div class="sample-container loading" style="height: 180px">
    <iframe id="layout-justify-content-iframe" src='{environment:demosBaseUrl}/layouts/layout-justify-content' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="codesandbox" disabled class="codesandbox-btn" data-iframe-id="layout-justify-content-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on codesandbox</button>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="layout-justify-content-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider--half"></div>

### Position elements along the cross axis
Use [`igxLayoutItemAlign`]({environment:angularApiUrl}/classes/igxlayoutdirective.html#itemalign)`="flex-start | center | flex-end"` to specify the elements position along the cross axis according to your preferences.
<div class="sample-container loading" style="height: 400px">
    <iframe id="layout-align-items-iframe" src='{environment:demosBaseUrl}/layouts/layout-align-items' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="codesandbox" disabled class="codesandbox-btn" data-iframe-id="layout-align-items-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on codesandbox</button>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="layout-align-items-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider--half"></div>

### You can also wrap elements 
Use [`igxLayoutWrap`]({environment:angularApiUrl}/classes/igxlayoutdirective.html#wrap)`="wrap"`.
<div class="sample-container loading" style="height: 180px">
    <iframe id="layout-wrap-iframe" src='{environment:demosBaseUrl}/layouts/layout-wrap' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="codesandbox" disabled class="codesandbox-btn" data-iframe-id="layout-wrap-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on codesandbox</button>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="layout-wrap-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

**Note**: The [`igxLayout`]({environment:angularApiUrl}/classes/igxlayoutdirective.html) directive affects the flow directions for that
container's **immediate** children.
<div class="divider--half"></div>

## Nesting
Use the [`igxFlex`]({environment:angularApiUrl}/classes/igxflexdirective.html) directive for elements inside an [`igxLayout`]({environment:angularApiUrl}/classes/igxlayoutdirective.html) parent to control specific flexbox properties.
<div class="divider--half"></div>


## API References
<div class="divider--half"></div>

* [IgxLayoutDirective]({environment:angularApiUrl}/classes/igxlayoutdirective.html)
* [IgxFlexDirective]({environment:angularApiUrl}/classes/igxflexdirective.html)