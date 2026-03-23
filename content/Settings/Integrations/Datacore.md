---
publish: true
title: Datacore
description: Whether to enable support for the Datacore plugin. Requires Datacore to be installed and enabled.
created: 2025-06-09T20:48:56Z+0200
modified: 2026-01-08T13:30:00Z+0100
tags:
  - datacore
  - integration
  - settings/integrations
---

> [!WARNING] Datacore is still in early development
>
> Not all features may work correctly

## Cache behavior

Files containing Datacore queries are automatically detected and flagged as containing dynamic content. These files are always recompiled when you open the Publication Center, ensuring query results reflect the current state of your vault.

The output is then compared against the published version—if the compiled result is identical, the file won't appear as changed.

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

- [[Settings/Integrations/Datacore|Datacore]]

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
|[[Settings/Integrations/Datacore|Datacore]]|<a href="tags/datacore" class="tag-link">datacore</a>, <a href="tags/integration" class="tag-link">integration</a>, <a href="tags/settings/integrations" class="tag-link">settings/integrations</a>|

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
