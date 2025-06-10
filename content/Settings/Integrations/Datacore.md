---
{"publish":true,"title":"Datacore","description":"Whether to enable support for the Datacore plugin. Requires Datacore to be installed and enabled.","created":"2025-06-09T20:48:56Z+0200","modified":"2025-06-10T17:42:08Z+0200","tags":["datacore","integration","settings/integrations"],"cssclasses":""}
---


> [!WARNING] Datacore is still in early development
>
> Not all features may work correctly

## Supported features

### Datacore Views

```js title="datacorejsx"
return function View() {
  return <p>Hello!</p>;
}
```

Hello!

### Datacore Lists

```js title="datacorejsx"
return function View() {
  const pages = dc.useQuery('@page and #datacore');
  
  return <dc.List rows={pages} renderer={pages => pages.$link} />;
}
```

- [Datacore](Settings/Integrations/Datacore.md)

### Datacore Tables

```js title="datacorejsx"
return function View() {
  const pages = dc.useQuery("@page and #datacore");

  const COLUMNS = [
    {id: "Name", value: page => page.$link},
    {id: "Tags", value: page => page.$tags}
  ];
  
  return <dc.Table rows={pages} columns={COLUMNS} />
}
```

|Name|Tags|
|---|---|
|[Datacore](Settings/Integrations/Datacore.md)|[#datacore](#datacore), [#integration](#integration), [#settings/integrations](#settings/integrations)|

### Datacore Cards

```js title="datacorejsx"
return function View() {
  return <dc.Card title={"Test"} content={"Testing out a card"} footer={"Hello!"} />;
}
```

<div class="datacore-card"><div class="datacore-card-title">Test</div><div class="datacore-card-inner"><div class="datacore-card-content">Testing out a card</div><div class="datacore-card-footer">Hello!</div></div></div>

### Datacore Callouts

```js title="datacorejsx"
return function View() {
  return <dc.Callout title={"Test"} collapsible={true} open={true}>Hello!</dc.Callout>;
}
```

<blockquote class="callout is-collapsible" data-callout-fold="" data-callout="note"><div class="callout-title"><div class="callout-icon"></div><div class="callout-title-inner">Test</div><div class="fold-callout-icon"></div></div><div class="callout-content"><div class="callout-content-inner">Hello!</div></div></blockquote>

## See also

- [Obsidian Rocks article on Datacore](https://obsidian.rocks/getting-started-with-datacore/), whose query examples are rendered above.
- [Datacore documentation](https://blacksmithgu.github.io/datacore/)


<style>.datacore .callout-content,.datacore.callout{transition:.1s cubic-bezier(.02, .01, .47, 1);margin-top:10px;margin-bottom:10px}.datacore .callout-fold{align-self:center}.datacore-card{display:flex;flex-direction:column;padding:1.2rem;border-radius:.5em;background-color:var(--background-secondary,rgba(0,0,0,0)); min-width: 89%; border: 2px solid var(--table-border-color,var(--gray)); overflow-y: scroll;}.datacore-card-title { margin-bottom: .6em; display: flex; justify-content: space-between; font-size: 1.8em;}.datacore-card-title.centered { justify-content: center !important;}.datacore-card-content,.datacore-card-inner,.datacore-card { transition: all .3s cubic-bezier(.65,.05,.36,1);}.datacore-card-inner { overflow-y: scroll; overflow-x: hidden; max-height: 500px;}.datacore-card .datacore-card-collapser,.datacore-card.is-collapsed .datacore-card-collapser { transition: all .5s cubic-bezier(.65,.05,.36,1);}.datacore-card-content { flex-grow: 1;}.datacore-card-inner { display: flex;}.datacore-card:not(.datacore-card.is-collapsed) .datacore-card-collapser { transform: rotate(180deg);}.datacore-card.is-collapsed .datacore-card-collapser { transform: rotate(0deg) !important;}.datacore-card-collapse,.datacore-card-collapser svg { min-width: 1em; min-height: 1em; fill: currentColor; vertical-align: middle;}.datacore-card.is-collapsed .datacore-card-collapser { transform: rotate(0deg);}.datacore-card .datacore-card-footer { font-size: .7em; text-align: right; padding: 0;}.datacore-list-item-fields{color:var(--text-normal,var(--dark-gray))!important}.datacore-list-item-fields>.datacore-field+.datacore-field{margin-left:.4em}.datacore-field{display:inline-flex;align-items:center;box-sizing:border-box;border-radius:.25em;font-size:.85em;align-items:center}.datacore-field .field-title{flex-grow:0;font-weight:700;height:inherit;display:inline-block}</style>
