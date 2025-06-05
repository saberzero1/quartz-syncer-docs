---
{"publish":true,"title":"Roadmap","description":"Changelog and feature roadmap for Quartz Syncer.","created":"2025-05-16T12:59:31Z+0200","modified":"2025-06-05T16:27:45Z+0200","cssclasses":""}
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

### Version 1.6.8

- Fixed DataviewJS queries not always returning correct data.
- Fixed MathJax collapsing to inline queries when embedded.
- Updated documentations.

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

## Access token

|Name1|Blurb|
|---|---|
|[Access token](Settings/GitHub/Access token.md)|Access token|

## Apply embeds

|Name1|Blurb|
|---|---|
|[Apply embeds](Settings/Quartz/Apply embeds.md)|Apply embeds|

## Authentication

|Name1|Blurb|
|---|---|
|[Authentication](Troubleshooting/Authentication.md)|Authentication|

## Configuring a specific folder for Quartz content

|Name1|Blurb|
|---|---|
|[Configuring a specific folder for Quartz content](Guides/Configuring a specific folder for Quartz content.md)|Configuring a specific folder for Quartz content|

## Content folder

|Name1|Blurb|
|---|---|
|[Content folder](Settings/Quartz/Content folder.md)|Content folder|

## Dataview

|Name3|Blurb|
|---|---|
|[Dataview](Settings/Integrations/Dataview.md)|Dataview|
|[Dataview](Troubleshooting/Dataview.md)|Dataview|
|[Dataview](tags/dataview.md)|Dataview|

## Excalidraw

|Name3|Blurb|
|---|---|
|[Excalidraw](Settings/Integrations/Excalidraw.md)|Excalidraw|
|[Excalidraw](Troubleshooting/Excalidraw.md)|Excalidraw|
|[Excalidraw](tags/excalidraw.md)|Excalidraw|

## Frontmatter

|Name2|Blurb|
|---|---|
|[Frontmatter](Troubleshooting/Frontmatter.md)|Frontmatter|
|[Frontmatter](tags/frontmatter.md)|Frontmatter|

## Frontmatter settings

|Name1|Blurb|
|---|---|
|[Frontmatter settings](tags/settings/frontmatter.md)|Frontmatter settings|

## Generating a fine-grained access token

|Name1|Blurb|
|---|---|
|[Generating a fine-grained access token](Guides/Generating an access token.md)|Generating a fine-grained access token|

## GitHub

|Name1|Blurb|
|---|---|
|[GitHub](Settings/GitHub/index.md)|GitHub|

## GitHub settings

|Name1|Blurb|
|---|---|
|[GitHub settings](tags/settings/github.md)|GitHub settings|

## Guides

|Name2|Blurb|
|---|---|
|[Guides](Guides/index.md)|Guides|
|[Guides](tags/guides.md)|Guides|

## Include all properties

|Name1|Blurb|
|---|---|
|[Include all properties](Settings/Note properties/Include all properties.md)|Include all properties|

## Include created timestamp

|Name1|Blurb|
|---|---|
|[Include created timestamp](Settings/Note properties/Include created timestamp.md)|Include created timestamp|

## Include modified timestamp

|Name1|Blurb|
|---|---|
|[Include modified timestamp](Settings/Note properties/Include modified timestamp.md)|Include modified timestamp|

## Include published timestamp

|Name1|Blurb|
|---|---|
|[Include published timestamp](Settings/Note properties/Include published timestamp.md)|Include published timestamp|

## Integration

|Name1|Blurb|
|---|---|
|[Integration](tags/integration.md)|Integration|

## Integration settings

|Name1|Blurb|
|---|---|
|[Integration settings](tags/settings/integrations.md)|Integration settings|

## Integrations

|Name1|Blurb|
|---|---|
|[Integrations](Settings/Integrations/index.md)|Integrations|

## Note properties (frontmatter)

|Name1|Blurb|
|---|---|
|[Note properties (frontmatter)](Settings/Note properties/index.md)|Note properties (frontmatter)|

## Publish key

|Name1|Blurb|
|---|---|
|[Publish key](Settings/Note properties/Publish key.md)|Publish key|

## Quartz

|Name3|Blurb|
|---|---|
|[Quartz](Settings/Quartz/index.md)|Quartz|
|[Quartz](Troubleshooting/Quartz.md)|Quartz|
|[Quartz](tags/quartz.md)|Quartz|

## Quartz settings

|Name1|Blurb|
|---|---|
|[Quartz settings](tags/settings/quartz.md)|Quartz settings|

## Quartz Syncer Documentation

|Name1|Blurb|
|---|---|
|[Quartz Syncer Documentation](index.md)|Quartz Syncer Documentation|

## Repository Name

|Name1|Blurb|
|---|---|
|[Repository Name](Settings/GitHub/Repository name.md)|Repository Name|

## Resources

|Name1|Blurb|
|---|---|
|[Resources](tags/resources.md)|Resources|

## Roadmap

|Name1|Blurb|
|---|---|
|[Roadmap](Changelog.md)|Roadmap|

## Settings

|Name2|Blurb|
|---|---|
|[Settings](Settings/index.md)|Settings|
|[Settings](tags/settings/index.md)|Settings|

## Setup Guide

|Name1|Blurb|
|---|---|
|[Setup Guide](Setup Guide.md)|Setup Guide|

## Tags

|Name1|Blurb|
|---|---|
|[Tags](tags/index.md)|Tags|

## Themes

|Name2|Blurb|
|---|---|
|[Themes](Settings/Themes/index.md)|Themes|
|[Themes](tags/themes.md)|Themes|

## Themes settings

|Name1|Blurb|
|---|---|
|[Themes settings](tags/settings/themes.md)|Themes settings|

## Troubleshooting

|Name1|Blurb|
|---|---|
|[Troubleshooting](Troubleshooting/index.md)|Troubleshooting|

## Usage Guide

|Name1|Blurb|
|---|---|
|[Usage Guide](Usage Guide.md)|Usage Guide|

## Use full image resolution

|Name1|Blurb|
|---|---|
|[Use full image resolution](Settings/Quartz/Use full image resolution.md)|Use full image resolution|

## Useful resources

|Name1|Blurb|
|---|---|
|[Useful resources](Useful resources/index.md)|Useful resources|

## Username

|Name1|Blurb|
|---|---|
|[Username](Settings/GitHub/Username.md)|Username|

## Using an Obsidian theme in Quartz

|Name1|Blurb|
|---|---|
|[Using an Obsidian theme in Quartz](Guides/Using an Obsidian theme in Quartz.md)|Using an Obsidian theme in Quartz|

## Vault root folder name

|Name1|Blurb|
|---|---|
|[Vault root folder name](Settings/GitHub/Vault root folder name.md)|Vault root folder name|