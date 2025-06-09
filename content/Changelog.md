---
{"publish":true,"title":"Roadmap","description":"Changelog and feature roadmap for Quartz Syncer.","created":"2025-05-16T12:59:31Z+0200","modified":"2025-06-09T20:09:49Z+0200","cssclasses":""}
---


## Upcoming

## Planned

- Excalidraw support.
- Canvas support.
- Built-in Quartz Themes support.
- TTRPG-related plugin support.

## Someday

- Manage Quartz configuration.
- Manage Quartz layout.
- Manage Quartz components.

## Released

### Version 1.6.9

- Fixed MathJax embedding inside callouts and multi-layer embeddings.
- Updated documentation.

### Version 1.6.8

- Fixed DataviewJS queries not always returning correct data.
- Fixed MathJax collapsing to inline queries when embedded.
- Updated documentation.

### Version 1.6.7

- Fixed issues related to alias generation on non-embedded links to blocks or headings.
- Removed redundant `decodeURI` call on blobs.
- Removed redundant function calls in Dataview processor.
- Removed unused utility functions.
- Replaced many CSS rules with Obsidian CSS properties to better integrate with Obsidian themes.
- Fixed grammatical error in embed settings description.
- Expanded settings tabs to show names on desktop.
	- Tablet and mobile still only show name on the active tab.
- Updated dependencies.

### Version 1.6.6

- Re-implemented the settings modal to use built-in Obsidian functionality.
- Settings that are overridden by other settings are now automatically hidden.
- Settings modal will now remember the last settings tab opened, instead of always opening the GitHub tab.
- Added missing heading to the Frontmatter settings tab.
- Removed redundant rendering calls.
- Restructured import statements.

### Version 1.6.5

- Fixed icons in publication center not showing correctly.
- Fixed broken link in project README file.
- Removed unnecessary warning.
- Updated manifest.

### Version 1.6.4

- Fixed embedded math blocks incorrectly parsing to inlined math blocks.
- Moved all inlined styling to CSS classes.
- Changed buttons in publication center to sticky.
	- This makes the buttons always visible at the bottom of the modal, even when displaying larger tree.
- Removed unused code.
- Updated manifest.
- Updated documentation.

### Version 1.6.3

- Fixed mobile folder selector styling.

### Version 1.6.2

- Use Obsidian built-in for rendering Dataviewjs to markdown.

### Version 1.6.1

- Implemented Obsidian built-in folder suggester.
- Removed now-unused popperjs dependency.
- Moved cog loading animation styling to CSS.

### Version 1.6.0

- Fixed embedding issues when embedding blocks.
- Embeddings are now handled by Quartz Syncer instead of Quartz.
	- This behavior can be configured in the settings `Quartz > Apply embeds`.
- Added settings menu for Quartz Themes.
	- This currently does nothing, but will be used for managing and applying Obsidian themes to Quartz.
- Fixed some minor typos.
- Updated documentation.

### Version 1.5.3

- Added note counts to the publication center.
- Added tabbed settings menu.
- Updated documentation.

### Version 1.5.2

- Restored use of `innerHTML` in the Dataview compiler.
	- This only affects `dataviewjs` queries. These are an optional, opt-in component of the Dataview plugin. See [Dataview JavaScript API documentation](https://blacksmithgu.github.io/obsidian-dataview/api/intro/) for details.

### Version 1.5.1

- Addressed Obsidian's automated feedback.

### Version 1.5.0

- Added to Obsidian Community Plugin list.
- Added separate settings for configuring note properties/frontmatter.
- Added option to only pass valid Quartz properties.
	- This can be overridden by setting the new `Include all properties` option.
- Updated publication center headings to better reflect functionality.
- Cleaned up all unused and redundant functions.
- Finished up all of the essential documentation.

### Version 1.4.1

- Fixed links to embedded notes resolving to the wrong URL when deploying from a subfolder.

### Version 1.4.0

- Added support for setting a vault folder as Quartz content folder.
	- This setting is recommended for users with mixed content vaults or users who want to dedicate a specific folder to their Quartz site content.
	- Specific folder can be configured in the plugin settings.
- Added configuration option for specifying publish frontmatter key.
	- The default key is `publish`, matching Obsidian Publish's default key.
	- The frontmatter key is used to expose notes to Quartz Syncer. Any note without the specified key or eith they key set to `false`/unchecked checkbox will not show up in Quartz Syncer.
	- The key should be a boolean/Checkbox (source mode/live-preview mode respectively.)
- Added Obsidian commands for modifying a note's publication status:
	- `Quartz Syncer: Add publish flag`: adds the specified publish flag to the current note frontmatter if not already present and sets it to `true`. This exposes the note to Quartz Syncer.
	- `Quartz Syncer: Remove publish flag`: adds the specified publish flag to the current note frontmatter if not already present and sets it to `false`. This hides the note from Quartz Syncer.
	- `Quartz Syncer: Toggle publication status`: toggles the note's visibility to Quartz Syncer.
- Added support for all embed filetypes that Quartz also supports. This includes the following:
	- Note: `md`
	- Image: `png`, `jpg`, `jpeg`, `gif`, `webp`, `svg`
	- Audio (new): `mp3`, `wav`, `ogg`
	- Video (new): `mp4`, `mkv`, `mov`, `avi`
	- Document (new): `pdf`
- Added a new icon.
- Added this documention website.
- Fixed deleting multiple files in single commit.

### Version 1.3.1

- Fixed Dataview query results not displaying correctly inside nested callouts.

### Version 1.3.0

- Exposed the following options for user configuration in plugin settings view:
	- Pass frontmatter.
	- Image file compression.
	- Use permalink for Quartz URL.
	- Pass note's created date to Quartz.
	- Pass note's last modification date to Quartz.
- Fixed incorrect links to embedded notes.
- Fixed path resolution resolving to wrong path in some cases.

### Version 1.2.0

- Initial beta release as Quartz Syncer.

### Version 1.1.0

- Support for configuring Quartz path.

### Version 1.0.0

- Forked from [Ole Eskild Steensen](https://github.com/oleeskild)'s [Digital Garden plugin](https://github.com/oleeskild/obsidian-digital-garden).

<p __self="[object Object]" __source="[object Object]">You have 51 pages in your vault!</p>

<div><table class="datacore-table"><thead><tr class="datacore-table-header-row"><th class="datacore-table-header-cell"><div class="datacore-table-header-title">Name</div></th><th class="datacore-table-header-cell"><div class="datacore-table-header-title">Publish status</div></th></tr></thead><tbody><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Configuring a specific folder for Quartz content"  data-tooltip-position="top" data-href="Guides/Configuring a specific folder for Quartz content.md" href="Guides/Configuring a specific folder for Quartz content.md" class="internal-link">Configuring a specific folder for Quartz content</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Generating an access token"  data-tooltip-position="top" data-href="Guides/Generating an access token.md" href="Guides/Generating an access token.md" class="internal-link">Generating an access token</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Using an Obsidian theme in Quartz"  data-tooltip-position="top" data-href="Guides/Using an Obsidian theme in Quartz.md" href="Guides/Using an Obsidian theme in Quartz.md" class="internal-link">Using an Obsidian theme in Quartz</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="Guides/index.md" href="Guides/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Access token"  data-tooltip-position="top" data-href="Settings/GitHub/Access token.md" href="Settings/GitHub/Access token.md" class="internal-link">Access token</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Repository name"  data-tooltip-position="top" data-href="Settings/GitHub/Repository name.md" href="Settings/GitHub/Repository name.md" class="internal-link">Repository name</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Username"  data-tooltip-position="top" data-href="Settings/GitHub/Username.md" href="Settings/GitHub/Username.md" class="internal-link">Username</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Vault root folder name"  data-tooltip-position="top" data-href="Settings/GitHub/Vault root folder name.md" href="Settings/GitHub/Vault root folder name.md" class="internal-link">Vault root folder name</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="Settings/GitHub/index.md" href="Settings/GitHub/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Dataview"  data-tooltip-position="top" data-href="Settings/Integrations/Dataview.md" href="Settings/Integrations/Dataview.md" class="internal-link">Dataview</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Excalidraw"  data-tooltip-position="top" data-href="Settings/Integrations/Excalidraw.md" href="Settings/Integrations/Excalidraw.md" class="internal-link">Excalidraw</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="Settings/Integrations/index.md" href="Settings/Integrations/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Include all properties"  data-tooltip-position="top" data-href="Settings/Note properties/Include all properties.md" href="Settings/Note properties/Include all properties.md" class="internal-link">Include all properties</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Include created timestamp"  data-tooltip-position="top" data-href="Settings/Note properties/Include created timestamp.md" href="Settings/Note properties/Include created timestamp.md" class="internal-link">Include created timestamp</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Include modified timestamp"  data-tooltip-position="top" data-href="Settings/Note properties/Include modified timestamp.md" href="Settings/Note properties/Include modified timestamp.md" class="internal-link">Include modified timestamp</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Include published timestamp"  data-tooltip-position="top" data-href="Settings/Note properties/Include published timestamp.md" href="Settings/Note properties/Include published timestamp.md" class="internal-link">Include published timestamp</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Publish key"  data-tooltip-position="top" data-href="Settings/Note properties/Publish key.md" href="Settings/Note properties/Publish key.md" class="internal-link">Publish key</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="Settings/Note properties/index.md" href="Settings/Note properties/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Content folder"  data-tooltip-position="top" data-href="Settings/Quartz/Content folder.md" href="Settings/Quartz/Content folder.md" class="internal-link">Content folder</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Use full image resolution"  data-tooltip-position="top" data-href="Settings/Quartz/Use full image resolution.md" href="Settings/Quartz/Use full image resolution.md" class="internal-link">Use full image resolution</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="Settings/Quartz/index.md" href="Settings/Quartz/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="Settings/Themes/index.md" href="Settings/Themes/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="Settings/index.md" href="Settings/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Setup Guide"  data-tooltip-position="top" data-href="Setup Guide.md" href="Setup Guide.md" class="internal-link">Setup Guide</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Authentication"  data-tooltip-position="top" data-href="Troubleshooting/Authentication.md" href="Troubleshooting/Authentication.md" class="internal-link">Authentication</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Dataview"  data-tooltip-position="top" data-href="Troubleshooting/Dataview.md" href="Troubleshooting/Dataview.md" class="internal-link">Dataview</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Excalidraw"  data-tooltip-position="top" data-href="Troubleshooting/Excalidraw.md" href="Troubleshooting/Excalidraw.md" class="internal-link">Excalidraw</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Frontmatter"  data-tooltip-position="top" data-href="Troubleshooting/Frontmatter.md" href="Troubleshooting/Frontmatter.md" class="internal-link">Frontmatter</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Quartz"  data-tooltip-position="top" data-href="Troubleshooting/Quartz.md" href="Troubleshooting/Quartz.md" class="internal-link">Quartz</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="Troubleshooting/index.md" href="Troubleshooting/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Usage Guide"  data-tooltip-position="top" data-href="Usage Guide.md" href="Usage Guide.md" class="internal-link">Usage Guide</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="Useful resources/index.md" href="Useful resources/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="index.md" href="index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="dataview"  data-tooltip-position="top" data-href="tags/dataview.md" href="tags/dataview.md" class="internal-link">dataview</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="excalidraw"  data-tooltip-position="top" data-href="tags/excalidraw.md" href="tags/excalidraw.md" class="internal-link">excalidraw</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="frontmatter"  data-tooltip-position="top" data-href="tags/frontmatter.md" href="tags/frontmatter.md" class="internal-link">frontmatter</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="guides"  data-tooltip-position="top" data-href="tags/guides.md" href="tags/guides.md" class="internal-link">guides</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="tags/index.md" href="tags/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="integration"  data-tooltip-position="top" data-href="tags/integration.md" href="tags/integration.md" class="internal-link">integration</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="quartz"  data-tooltip-position="top" data-href="tags/quartz.md" href="tags/quartz.md" class="internal-link">quartz</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="resources"  data-tooltip-position="top" data-href="tags/resources.md" href="tags/resources.md" class="internal-link">resources</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="frontmatter"  data-tooltip-position="top" data-href="tags/settings/frontmatter.md" href="tags/settings/frontmatter.md" class="internal-link">frontmatter</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="github"  data-tooltip-position="top" data-href="tags/settings/github.md" href="tags/settings/github.md" class="internal-link">github</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="index"  data-tooltip-position="top" data-href="tags/settings/index.md" href="tags/settings/index.md" class="internal-link">index</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="integrations"  data-tooltip-position="top" data-href="tags/settings/integrations.md" href="tags/settings/integrations.md" class="internal-link">integrations</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="quartz"  data-tooltip-position="top" data-href="tags/settings/quartz.md" href="tags/settings/quartz.md" class="internal-link">quartz</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="themes"  data-tooltip-position="top" data-href="tags/settings/themes.md" href="tags/settings/themes.md" class="internal-link">themes</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="themes"  data-tooltip-position="top" data-href="tags/themes.md" href="tags/themes.md" class="internal-link">themes</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="datacore"  data-tooltip-position="top" data-href="datacore.md" href="datacore.md" class="internal-link">datacore</a></td><td class="datacore-table-cell"><span><ul>
<li dir="auto"></li>
</ul></span></td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Apply embeds"  data-tooltip-position="top" data-href="Settings/Quartz/Apply embeds.md" href="Settings/Quartz/Apply embeds.md" class="internal-link">Apply embeds</a></td><td class="datacore-table-cell">true</td></tr><tr class="datacore-table-row"><td class="datacore-table-cell"><a aria-label="Changelog"  data-tooltip-position="top" data-href="Changelog.md" href="Changelog.md" class="internal-link">Changelog</a></td><td class="datacore-table-cell">true</td></tr></tbody></table></div>
