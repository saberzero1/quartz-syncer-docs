---
{"publish":true,"title":"Datacore","description":"Whether to enable support for the Datacore plugin. Requires Datacore to be installed and enabled.","created":"2025-06-09T20:48:56Z+0200","modified":"2025-06-10T09:31:11Z+0200","tags":["datacore","integration","settings/integrations"],"cssclasses":""}
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

<p>Hello!</p>

### Datacore Lists

```js title="datacorejsx"
return function View() {
  const pages = dc.useQuery('@page and #datacore');
  
  return <dc.List rows={pages} renderer={pages => pages.$link} />;
}
```

<div class="datacore-list"><ul class="datacore-list datacore-list-unordered"><li class="datacore-list-item"><a class="internal-link" href="Settings/Integrations/Datacore.md" data-href="Settings/Integrations/Datacore.md" data-tooltip-position="top" rel="noopener" aria-label="Datacore" target="_blank">Datacore</a><ul class="datacore-list datacore-list-unordered"></ul></li></ul></div>

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

<div><table class="datacore-table"><thead><tr class="datacore-table-header-row"><th class="datacore-table-header-cell"><div class="datacore-table-header-title">Name</div></th><th class="datacore-table-header-cell"><div class="datacore-table-header-title">Tags</div></th></tr></thead><tbody><tr class="datacore-table-row"><td class="datacore-table-cell"><a class="internal-link" href="Settings/Integrations/Datacore.md" data-href="Settings/Integrations/Datacore.md" data-tooltip-position="top" rel="noopener" aria-label="Datacore" target="_blank">Datacore</a></td><td class="datacore-table-cell"><span class="dataview dataview-result-list-span"><span><a rel="noopener nofollow" class="tag" href="#datacore" target="_blank">#datacore</a></span>, <span><a rel="noopener nofollow" class="tag" href="#integration" target="_blank">#integration</a></span>, <span><a rel="noopener nofollow" class="tag" href="#settings/integrations" target="_blank">#settings/integrations</a></span></span></td></tr></tbody></table></div>

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

<div class="datacore callout is-collapsible" data-callout-fold="+"><div class="callout-title"><div class="callout-title-inner">Test</div><div class="callout-fold"><svg class="svg-icon lucide-chevron-down" stroke-linejoin="round" stroke-linecap="round" stroke-width="2" stroke="currentColor" fill="none" viewBox="0 0 24 24" height="24" width="24" xmlns="http://www.w3.org/2000/svg"><path d="m6 9 6 6 6-6"/></svg></div></div><div class="callout-content">Hello!</div></div>

## See also

- [Obsidian Rocks article on Datacore](https://obsidian.rocks/getting-started-with-datacore/), whose query examples are rendered above.
- [Datacore documentation](https://blacksmithgu.github.io/datacore/)



<style>.datacore .callout-content,.datacore.callout{transition:.1s cubic-bezier(.02, .01, .47, 1);margin-top:10px;margin-bottom:10px}.datacore .callout-fold{align-self:center}.datacore-card{display:flex;flex-direction:column;padding:1.2rem;border-radius:.5em;background-color:var(--background-secondary,rgba(0,0,0,0); min-width: 89%; border: 2px solid var(--table-border-color,var(--gray)); overflow-y: scroll;}.datacore-card-title { margin-bottom: .6em; display: flex; justify-content: space-between; font-size: 1.8em;}.datacore-card-title.centered { justify-content: center !important;}.datacore-card-content,.datacore-card-inner,.datacore-card { transition: all .3s cubic-bezier(.65,.05,.36,1);}.datacore-card-inner { overflow-y: scroll; overflow-x: hidden; max-height: 500px;}.datacore-card .datacore-card-collapser,.datacore-card.is-collapsed .datacore-card-collapser { transition: all .5s cubic-bezier(.65,.05,.36,1);}.datacore-card-content { flex-grow: 1;}.datacore-card-inner { display: flex;}.datacore-card:not(.datacore-card.is-collapsed) .datacore-card-collapser { transform: rotate(180deg);}.datacore-card.is-collapsed .datacore-card-collapser { transform: rotate(0deg) !important;}.datacore-card-collapse,.datacore-card-collapser svg { min-width: 1em; min-height: 1em; fill: currentColor; vertical-align: middle;}.datacore-card.is-collapsed .datacore-card-collapser { transform: rotate(0deg);}.datacore-card .datacore-card-footer { font-size: .7em; text-align: right; padding: 0;}.datacore-list-item-fields{color:var(--text-normal,var(--dark-gray))!important}.datacore-list-item-fields>.datacore-field+.datacore-field{margin-left:.4em}.datacore-field{display:inline-flex;align-items:center;box-sizing:border-box;border-radius:.25em;font-size:.85em;align-items:center}.datacore-field .field-title{flex-grow:0;font-weight:700;height:inherit;display:inline-block}</style>
