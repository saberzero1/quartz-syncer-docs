---
{"publish":true,"title":"Codeberg Authentication","description":"Guide for setting up authentication with Codeberg.","created":"2026-01-08T14:00:00Z+0100","modified":"2026-01-08T14:00:00Z+0100","tags":["guides"],"cssclasses":""}
---


## Codeberg Authentication

Codeberg is powered by Gitea. You can use a standard Personal Access Token to authenticate.

### Generating an Access Token

1. Log in to your Codeberg account.
2. Go to your [Settings > Applications page](https://codeberg.org/user/settings/applications).
3. Under **Manage Access Tokens**, enter a **Token Name** (e.g., `Quartz Syncer`).
4. Click **Generate Token**.
5. Copy the generated token immediately.

### Configuring Quartz Syncer

1. Open Obsidian.
2. Open Obsidian's settings and click on **Quartz Syncer** under *Community Plugins*.
3. In the **Git Settings** section, enter your repository's full URL in the **Remote URL** field (e.g., `https://codeberg.org/username/quartz.git`).
4. Select **Gitea / Codeberg** as the **Provider**.
5. Set **Authentication Type** to **Username & Token/Password**.
6. Enter your Codeberg username in the **Username** field.
7. Paste your Access Token in the **Access Token** field.
