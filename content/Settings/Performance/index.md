---
publish: true
title: Performance
description: Quartz Syncer settings related to performance.
created: 2025-06-12T22:41:01Z+0200
modified: 2026-04-01T17:15:09Z+0200
tags:
  - settings
  - settings/performance
---

| Category                                                                                      | Description                                                                                                                                 | Default value |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| [[Settings/Performance/Enable caching\|Enable caching]]                                       | Whether to cache note compilation results to greatly improve performance.                                                                   | true          |
| [[Settings/Performance/Persist cache after unload\|Persist cache after unload]]               | Whether to persist the cache when the plugin is unloaded. This is useful for users that start Obsidian with the plugin disabled.            | false         |
| [[Settings/Performance/Synchronize cache between devices\|Synchronize cache between devices]] | Prevents caching inconsistencies by storing a serialized copy of the cache to the `data.json`. This allows for consistency between devices. | true          |
