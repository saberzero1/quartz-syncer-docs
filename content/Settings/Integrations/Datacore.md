---
{"publish":true,"title":"Datacore","description":"Whether to enable support for the Datacore plugin. Requires Datacore to be installed and enabled.","created":"2025-06-09T20:48:56Z+0200","modified":"2025-06-10T21:16:47Z+0200","tags":["datacore","integration","settings/integrations"],"cssclasses":""}
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

- [[Settings/Integrations/Datacore\|Datacore]]

### Datacore Tables

```js title="datacorejsx"
return function View() {
  const pages = dc.useQuery("@page and #datacore");

  const COLUMNS = [
    {id: "Name", value: page => page.$link},
    {id: "Tags", value: page => page.$tags}
  ];
  
  return <dc.Table rows={pages} columns={COLUMNS} />;
}
```

|Name|Tags|
|---|---|
|[[Settings/Integrations/Datacore\|Datacore]]|<a href="tags/datacore" class="internal tag-link">datacore</a>, <a href="tags/integration" class="internal tag-link">integration</a>, <a href="tags/settings/integrations" class="internal tag-link">settings&sol;integrations</a>|

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


<style>.datacore-card{display:flex;flex-direction:column;padding:1.2rem;border-radius:.5em;background-color:var(--background-secondary,rgba(0,0,0,0)); min-width: 89%; border: 2px solid var(--table-border-color,var(--gray)); overflow-y: auto;}.datacore-card-title { margin-bottom: .6em; display: flex; justify-content: space-between; font-size: 1.8em;}.datacore-card-title.centered { justify-content: center !important;}.datacore-card-content,.datacore-card-inner,.datacore-card { transition: all .3s cubic-bezier(.65,.05,.36,1);}.datacore-card-inner { overflow-y: auto; overflow-x: hidden; max-height: 500px;}.datacore-card .datacore-card-collapser,.datacore-card.is-collapsed .datacore-card-collapser { transition: all .5s cubic-bezier(.65,.05,.36,1);}.datacore-card-content { flex-grow: 1;}.datacore-card-inner { display: flex;}.datacore-card:not(.datacore-card.is-collapsed) .datacore-card-collapser { transform: rotate(180deg);}.datacore-card.is-collapsed .datacore-card-collapser { transform: rotate(0deg) !important;}.datacore-card-collapse,.datacore-card-collapser svg { min-width: 1em; min-height: 1em; fill: currentColor; vertical-align: middle;}.datacore-card.is-collapsed .datacore-card-collapser { transform: rotate(0deg);}.datacore-card .datacore-card-footer { font-size: .7em; text-align: right; padding: 0;}</style>
