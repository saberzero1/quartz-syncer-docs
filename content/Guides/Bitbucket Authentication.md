---
{"publish":true,"title":"Bitbucket Authentication","description":"Guide for setting up authentication with Bitbucket.","created":"2026-01-08T14:00:00Z+0100","modified":"2026-01-08T14:00:00Z+0100","tags":["guides"],"cssclasses":""}
---


## Bitbucket Authentication

### Generating an App Password

1. Go to your [Bitbucket App Passwords page](https://bitbucket.org/account/settings/app-passwords/).
2. Click **Create app password**.
3. Enter a **Label** (e.g., `Quartz Syncer`).
4. Under **Permissions**, select **Write** for the **Repositories** scope.
5. Click **Create**.
6. Copy the generated password immediately.

### Configuring Quartz Syncer

1. Open Obsidian.
2. Open Obsidian's settings and click on **Quartz Syncer** under *Community Plugins*.
3. In the **Git Settings** section, enter your repository's full URL in the **Remote URL** field (e.g., `https://bitbucket.org/username/quartz.git`).
4. Select **Bitbucket** as the **Provider**.
5. Set **Authentication Type** to **Username & Token/Password**.
6. Enter `x-token-auth` in the **Username** field if you are using an App Password. Alternatively, you can use your Bitbucket username.
7. Paste your App Password in the **App Password** field.
