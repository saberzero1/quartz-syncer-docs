---
{"publish":true,"title":"GitLab Authentication","description":"Guide for setting up authentication with GitLab.","created":"2026-01-08T14:00:00Z+0100","modified":"2026-01-08T14:00:00Z+0100","tags":["guides"],"cssclasses":""}
---


## GitLab Authentication

### Generating a Personal Access Token

1. Go to your [GitLab Personal Access Tokens page](https://gitlab.com/-/user_settings/personal_access_tokens).
2. Click **Add new token**.
3. Enter a **Token name** (e.g., `Quartz Syncer`).
4. Under **Select scopes**, check the **write_repository** scope.
5. Click **Create personal access token**.
6. Copy the generated token immediately.

### Configuring Quartz Syncer

1. Open Obsidian.
2. Open Obsidian's settings and click on **Quartz Syncer** under *Community Plugins*.
3. In the **Git Settings** section, enter your repository's full URL in the **Remote URL** field (e.g., `https://gitlab.com/username/quartz.git`).
4. Select **GitLab** as the **Provider**.
5. Set **Authentication Type** to **Username & Token/Password**.
6. Enter `oauth2` in the **Username** field if you are using a Personal Access Token. Alternatively, you can use your GitLab username.
7. Paste your Personal Access Token in the **Access Token** field.
