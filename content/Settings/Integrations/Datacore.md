---
{"publish":true,"title":"Datacore","description":"Whether to enable support for the Datacore plugin. Requires Datacore to be installed and enabled.","created":"2025-06-09T20:48:56Z+0200","modified":"2025-08-07T09:14:15Z+0200","tags":["datacore","integration","settings/integrations"],"cssclasses":""}
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
|[[Settings/Integrations/Datacore\|Datacore]]|<a href="tags/datacore" class="tag-link">datacore</a>, <a href="tags/integration" class="tag-link">integration</a>, <a href="tags/settings/integrations" class="tag-link">settings/integrations</a>|

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

## Advanced

<!--
<div class="carousel-container"><div class="carousel" mask="true"><article><img src="" /><h2>Auto Card Link</h2><div><p>Whether to enable support for the Auto Card Link plugin. Requires Auto Card Link to be installed and enabled.</p><a href="/Settings/Integrations/Auto Card Link.md" class="internal-link">Link</a></div></article><article><img src="" /><h2>Dataview</h2><div><p>Whether to enable support for the Dataview plugin. Requires Dataview to be installed and enabled.</p><a href="/Settings/Integrations/Dataview.md" class="internal-link">Link</a></div></article><article><img src="" /><h2>Excalidraw</h2><div><p>Whether to enable support for the Excalidraw plugin. Feature is currently disabled.</p><a href="/Settings/Integrations/Excalidraw.md" class="internal-link">Link</a></div></article><article><img src="" /><h2>Fantasy Statblocks</h2><div><p>Whether to enable support for the Fantasy Statblocks plugin. Requires Fantasy Statblocks to be installed and enabled.</p><a href="/Settings/Integrations/Fantasy Statblocks.md" class="internal-link">Link</a></div></article><article><img src="" /><h2>Datacore</h2><div><p>Whether to enable support for the Datacore plugin. Requires Datacore to be installed and enabled.</p><a href="/Settings/Integrations/Datacore.md" class="internal-link">Link</a></div></article></div><style>
	.carousel-container {
	  place-items: center;
	  display: flex;
	}
	.carousel {
	  --items: 5;
	  --carousel-duration: 40s;
	  @media (width &gt; 600px) {
		--carousel-duration: 30s;
	  }
	  --carousel-width: min(80vw,
		1200px);
	  /* note - it will "break" if it gets too wide and there aren't enough items */
	  --carousel-item-width: 280px;
	  --carousel-item-height: 450px;
	  --carousel-item-gap: 2rem;
	  --clr-cta: rgb(0, 132, 209);
	  position: relative;
	  width: var(--carousel-width);
	  height: var(--carousel-item-height);
	  overflow: clip;
	  &amp;[mask] {
		/* fade out on sides */
		mask-image: linear-gradient(to right,
			transparent,
			black 10% 90%,
			transparent);
	  }
	  &amp;[reverse]&gt;article {
		animation-direction: reverse;
	  }
	  /* hover pauses animation */
	  &amp;:hover&gt;article {
		animation-play-state: paused;
	  }
	}
	.carousel&gt;article {
	  position: absolute;
	  top: 0;
	  left: calc(100% + var(--carousel-item-gap));
	  width: var(--carousel-item-width);
	  height: var(--carousel-item-height);
	  display: grid;
	  grid-template-rows: 200px auto 1fr auto;
	  gap: 0.25rem;
	  border: 1px solid light-dark(rgba(0 0 0 / 0.25), rgba(255 255 255 / 0.15));
	  padding-block-end: 1rem;
	  border-radius: 10px;
	  background: light-dark(white, rgba(255 255 255 / 0.05));
	  color: light-dark(rgb(49, 65, 88), white);
	  /* animation */
	  will-change: transform;
	  animation-name: marquee;
	  animation-duration: var(--carousel-duration);
	  animation-timing-function: linear;
	  animation-iteration-count: infinite;
	  animation-delay: calc(var(--carousel-duration) / var(--items) * 1 * var(--i) * -1);
	  
	  &amp;:nth-child(1) {
	  --i: 0;
	}
  
	  &amp;:nth-child(2) {
	  --i: 1;
	}
  
	  &amp;:nth-child(3) {
	  --i: 2;
	}
  
	  &amp;:nth-child(4) {
	  --i: 3;
	}
  
	  &amp;:nth-child(5) {
	  --i: 4;
	}
  
	  &amp;:nth-child(6) {
	  --i: 5;
	}
  
	  &amp;:nth-child(7) {
	  --i: 6;
	}
  
	}
	.carousel img {
	  width: 100%;
	  height: 100%;
	  object-fit: cover;
	  border-radius: 10px 10px 0 0;
	}
	.carousel&gt;article&gt;*:not(img) {
	  padding: 0 1rem;
	}
	.carousel&gt;article&gt;div {
	  grid-row: span 2;
	  display: grid;
	  grid-template-rows: subgrid;
	  font-size: 0.8rem;
	}
	.carousel&gt;article h2 {
	  font-size: 1.2rem;
	  font-weight: 300;
	  padding-block: 0.75rem 0.25rem;
	  margin: 0;
	}
	.carousel&gt;article p {
	  margin: 0;
	}
	.carousel&gt;article a {
	  text-decoration: none;
	  text-transform: lowercase;
	  border: 1px solid var(--clr-cta);
	  color: light-dark(var(--clr-cta), white);
	  border-radius: 3px;
	  padding: 0.25rem 0.5rem;
	  place-self: start;
	  transition: 150ms ease-in-out;
	  &amp;:hover,
	  &amp;:focus-visible {
		background-color: var(--clr-cta);
		color: white;
		outline: none;
	  }
	}
	@keyframes marquee {
	  100% {
		transform: translateX(calc((var(--items) * (var(--carousel-item-width) + var(--carousel-item-gap))) * -1));
	  }
	}
  </style></div>
-->

## See also

- [Obsidian Rocks article on Datacore](https://obsidian.rocks/getting-started-with-datacore/), whose query examples are rendered above.
- [Datacore documentation](https://blacksmithgu.github.io/datacore/)


<style>.datacore-card{display:flex;flex-direction:column;padding:1.2rem;border-radius:.5em;background-color:var(--background-secondary,rgba(0,0,0,0)); min-width: 89%; border: 2px solid var(--table-border-color,var(--gray)); overflow-y: auto;}.datacore-card-title { margin-bottom: .6em; display: flex; justify-content: space-between; font-size: 1.8em;}.datacore-card-title.centered { justify-content: center !important;}.datacore-card-content,.datacore-card-inner,.datacore-card { transition: all .3s cubic-bezier(.65,.05,.36,1);}.datacore-card-inner { overflow-y: auto; overflow-x: hidden; max-height: 500px;}.datacore-card .datacore-card-collapser,.datacore-card.is-collapsed .datacore-card-collapser { transition: all .5s cubic-bezier(.65,.05,.36,1);}.datacore-card-content { flex-grow: 1;}.datacore-card-inner { display: flex;}.datacore-card:not(.datacore-card.is-collapsed) .datacore-card-collapser { transform: rotate(180deg);}.datacore-card.is-collapsed .datacore-card-collapser { transform: rotate(0deg) !important;}.datacore-card-collapse,.datacore-card-collapser svg { min-width: 1em; min-height: 1em; fill: currentColor; vertical-align: middle;}.datacore-card.is-collapsed .datacore-card-collapser { transform: rotate(0deg);}.datacore-card .datacore-card-footer { font-size: .7em; text-align: right; padding: 0;}</style>
