---
publish: true
title: Setup Guide
description: Instructions for setting up Quartz Syncer plugin.
created: 2025-05-05T12:00:00Z+0200
modified: 2026-01-08T17:16:24Z+0100
tags:
  - guides
---

> [!WARNING] Set up Quartz first
> This plugin manages Quartz content from Obsidian. Please set up Quartz on your Git provider before continuing.

## Choose Your Git Provider

Quartz Syncer supports any Git provider. Choose your provider for complete setup instructions:

| Provider | Guide | Hosting |
|----------|-------|---------|
| **GitHub** | [[GitHub Setup]] | GitHub Pages (built-in) |
| **GitLab** | [[GitLab Setup]] | GitLab Pages (built-in) |
| **Codeberg** | [[Codeberg Setup]] | Codeberg Pages (built-in) |
| **Bitbucket** | [[Bitbucket Setup]] | Netlify, Cloudflare, Vercel |
| **Other** | See [Generic Setup](#generic-setup) below | Varies |

Each guide covers:

1. Creating a Quartz repository
2. Configuring automatic deployment
3. Generating an access token
4. Configuring Quartz Syncer

## Generic Setup

For Git providers not listed above, follow these general steps:

### 1. Create a Quartz Repository

Create a new repository on your Git provider (start from the [official Quartz template](https://github.com/new?template_name=quartz\&template_owner=jackyzha0) on GitHub, then import or mirror it to your provider of choice).

### 2. Configure Hosting

```bash
git clone https://<provider>/<user>/<repo>.git
cd <repo>
npm ci
```

### 2. Run the Quartz Setup Wizard

Quartz v5 ships an interactive setup command that writes `quartz.config.yaml` and installs all required plugins for you:

```bash
npx quartz create
```

Pick a template (`default`, `obsidian`, `ttrpg`, or `blog`), set your base URL, and choose how Quartz should treat your content folder. The `obsidian` template is recommended when publishing from an Obsidian vault.

> [!TIP] Non-interactive setup
> You can pass flags to skip the prompts: `npx quartz create --template obsidian --strategy new --baseUrl <your-site.example.com>`. See the [`quartz create` reference](https://quartz.jzhao.xyz/cli/create) for the full flag list.

### 3. Configure Hosting

Set up a CI/CD pipeline to build and deploy Quartz. The v5 build process **must** install plugins before building:

```bash
npm ci
npx quartz build
# Deploy the 'public' folder to your hosting service
```

Popular hosting options:

- [Netlify](https://netlify.com)
- [Cloudflare Pages](https://pages.cloudflare.com)
- [Vercel](https://vercel.com)

See the [Quartz hosting documentation](https://quartz.jzhao.xyz/hosting) for more options.

### 4. Generate an Access Token

Create a personal access token (or app password) with **write** access to your Quartz repository. The exact steps vary by provider — see the provider-specific guide linked above, or consult your provider's documentation.

### 5. Configure Quartz Syncer

In Obsidian, go to **Settings** > **Community Plugins** > **Quartz Syncer** and configure:

| Setting | Value |
|---------|-------|
| **Remote URL** | `https://<provider>/<user>/<repo>.git` |
| **Branch** | Your repository's default branch (typically `v5`) |
| **Provider** | Select your provider or "Custom" |
| **Authentication Type** | Username & Token/Password |
| **Username** | Your username (or `oauth2` for some providers) |
| **Access Token** | Your generated token |

A green checkmark indicates a successful connection.

## Configure Quartz

After setting up your repository and Quartz Syncer, configure Quartz itself:

### `quartz.config.ts`

Update these key settings in `quartz.config.ts`:

```ts
const config: QuartzConfig = {
  configuration: {
    pageTitle: "Your Site Title",
    baseUrl: "your-site.example.com", // Without https://
    defaultDateType: "modified", // or "created", "published"
  },
  plugins: {
    transformers: [
      Plugin.CrawlLinks({ markdownLinkResolution: "shortest" }),
      // Should match your Obsidian link settings
    ],
  },
}
```

## That's It

You're ready to publish notes to Quartz using Quartz Syncer.

For usage instructions, see the [[Usage Guide]].
