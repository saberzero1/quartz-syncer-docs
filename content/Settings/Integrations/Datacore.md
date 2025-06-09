---
{"publish":true,"title":"Datacore","description":"Whether to enable support for the Datacore plugin. Requires Datacore to be installed and enabled.","created":"2025-06-09T20:48:56Z+0200","modified":"2025-06-09T21:08:20Z+0200","tags":["datacore","integration","settings/integrations"],"cssclasses":""}
---


> [!WARNING] Datacore is still in early development
>
> Not all feature may work correctly

## Supported features

### Datacore Views

```js title="datacorejsx"
return function View() {
  return <p>Hello!</p>;
}
```

<p __self="[object Object]" __source="[object Object]">Hello!</p>

### Datacore Lists

```js title="datacorejsx"
return function View() {
  const pages = dc.useQuery('@page and #datacore');
  
  return <dc.List rows={pages} renderer={pages => pages.$link} />;
}
```

<div class="datacore-list"><ul class="datacore-list datacore-list-unordered"><li class="datacore-list-item"><a aria-label="Datacore"  data-tooltip-position="top" data-href="Settings/Integrations/Datacore.md" href="Settings/Integrations/Datacore.md" class="internal-link">Datacore</a><ul class="datacore-list datacore-list-unordered"></ul></li></ul></div>

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

<div><table class="datacore-table"><thead><tr class="datacore-table-header-row"><th class="datacore-table-header-cell"><div class="datacore-table-header-title">Name</div></th><th class="datacore-table-header-cell"><div class="datacore-table-header-title">Tags</div></th></tr></thead><tbody><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Datacore"  data-tooltip-position="top" data-href="Settings/Integrations/Datacore.md" href="Settings/Integrations/Datacore.md" class="internal-link">Datacore</a></td><td class="datacore-table-cell"><span class="dataview dataview-result-list-span"><span><a href="#datacore" class="tag" target="_blank" rel="noopener nofollow">#datacore</a></span>, <span><a href="#integration" class="tag" target="_blank" rel="noopener nofollow">#integration</a></span>, <span><a href="#settings/integrations" class="tag" target="_blank" rel="noopener nofollow">#settings/integrations</a></span></span></td></tr></tbody></table></div>

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

<div data-callout-fold="+" class="datacore callout is-collapsible"><div class="callout-title"><div class="callout-title-inner">Test</div><div class="callout-fold"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-chevron-down"><path d="m6 9 6 6 6-6"></path></svg></div></div><div class="callout-content">Hello!</div></div>

## See also

- [Obsidian Rocks article on Datacore](https://obsidian.rocks/getting-started-with-datacore/), whose query examples are rendered above.
- [Datacore documentation](https://blacksmithgu.github.io/datacore/)
