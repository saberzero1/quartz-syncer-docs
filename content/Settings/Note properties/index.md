---
publish: true
title: Note properties (frontmatter)
description: Quartz Syncer settings related to note properties or frontmatter.
created: 2025-05-17T15:08:00Z+0200
modified: 2025-05-20T20:31:59Z+0200
tags:
  - settings/frontmatter
cssclasses: ""
---


| Category                                                                                   | Description                                                                                                                         | Default value                             |
| ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- |
| [[Settings/Note properties/Created timestamp keys\|Created timestamp keys]]             | Comma-separated list of keys to look for to determine the created timestamp.                                                        | created, created_at, date                 |
| [[Settings/Note properties/Frontmatter format\|Frontmatter format]]                     | Output format for frontmatter/note properties in published notes.                                                                   | `yaml`                                    |
| [[Settings/Note properties/Include all notes by default\|Include all notes by default]] | Whether to include all as publishable instead of only the notes with the configured publish flag set to true                        | false                                     |
| [[Settings/Note properties/Include all properties\|Include all properties]]             | Whether to include all note properties instead of only note properties that are used by Quartz.                                     | false                                     |
| [[Settings/Note properties/Include created timestamp\|Include created timestamp]]       | Whether to pass a note property to set creation date in Quartz. Required when `defaultDateType` in Quartz is set to "created".      | true                                      |
| [[Settings/Note properties/Include modified timestamp\|Include modified timestamp]]     | Whether to pass a note property to set modification date in Quartz. Required when `defaultDateType` in Quartz is set to "modified". | true                                      |
| [[Settings/Note properties/Include published timestamp\|Include published timestamp]]   | Whether to pass a note property to set publication date in Quartz. Required when `defaultDateType` in Quartz is set to "published". | false                                     |
| [[Settings/Note properties/Publish key\|Publish key]]                                   | What frontmatter key to check for to determine whether a note is visible to Quartz Syncer.                                          | `publish`                                 |
| [[Settings/Note properties/Published timestamp keys\|Published timestamp keys]]         | Comma-separated list of keys to look for to determine the published timestamp.                                                      | published, publishDate, date              |
| [[Settings/Note properties/Updated timestamp keys\|Updated timestamp keys]]             | Comma-separated list of keys to look for to determine the updated timestamp.                                                        | modified, lastmod, updated, last-modified |

