---
{"excalidraw-plugin":"parsed","tags":["excalidraw"],"title":"Excalidraw","description":"Quartz Syncer settings related to integration with Excalidraw plugin.","publish":true,"PassFrontmatter":true}
---

const file = dv.page("Settings/Integrations/Excalidraw.excalidraw.md").file;

const ea = ExcalidrawAutomate;
ea.reset()

const scene = await ea.getSceneFromFile(file)
ea.copyViewElementsToEAforEditing(scene.elements)

await ea.createPNG()
  .then((png) => {
      const data = URL.createObjectURL(png);
      dv.span(`<img src=${data}>`)
    });
