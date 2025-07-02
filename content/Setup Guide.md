---
{"publish":true,"title":"Setup Guide","description":"Instructions for setting up Quartz Syncer plugin.","created":"2025-05-18T10:31:22.000+02:00","modified":"2025-05-31T13:01:58.884+02:00","tags":["guides"],"cssclasses":""}
---


> [!WARNING]- A GitHub account is required to use Quartz and Quartz Syncer
> You can sign up for free [here](https://github.com/signup).

> [!WARNING] Set up Quartz first
> This plugin manages Quartz content from Obsidian. Please set up Quartz if you have not already. See instructions below.
>

## Set up Quartz

### Create Quartz GitHub repository

If you haven't set up a Quartz repository on GitHub yet, [click here](https://github.com/new?template_name=quartz&template_owner=jackyzha0) to create it using the Quartz template.

### Configure Quartz settings

#### Configure `quartz.config.ts`

Configure the following settings in the `quartz.config.ts` file:

(Below example only shows a subset of all settings. Please do not remove any settings.)

```ts title="quartz.config.ts" {3,6,12,25}
const config: QuartzConfig = {
  configuration: {
    pageTitle: "Quartz 4",
    // Change to your desired site title
    ...
    baseUrl: "quartz.jzhao.xyz",
    // Change to your site URL without https://.
    // This is your own domain,
    // or "<github-user-name>.github.io/<repository-name>" when using GitHub Pages.
    // See below for details
    ...
    defaultDateType: "modified",
    // Change to tell Quartz what date to display on notes
    // Valid options:
    // "created", use when the note was created.
    // "modified", use when the note was last modified.
    // "published", use when the note was published.
    // See Quartz docs for details.
    ...
    }
  }
  plugins: {
    transformers: [
      ...
      Plugin.CrawlLinks({ markdownLinkResolution: "shortest" }),
      // Sets how Quartz should resolve links between notes.
      // Should match the settings you use in Obsidian.
      // Valid options:
      // "shortest"
      // "relative"
      // "absolute"
      ...
    ]
    ...
  }
}
```

#### Configure automatic deployment

If you haven't already, set up Quartz to automatically deploy on push:

> [!INFO] GitHub Pages setup (recommended)
> In your GitHub repository, go to `Settings > Pages` and set `Source` to "GitHub Actions".
>
> Next, add one of the following deploy scripts:
> > [!EXAMPLE]- Option 1: Default Quartz
> > For using Quartz without adding an Obsidian Theme.
> >
> > Add the following script as `.github/workflows/deploy.yaml`:
> >
> > ```yaml title=".github/workflows/deploy.yaml"
> > name: Deploy Quartz site to GitHub Pages
> > 
> > on:
> >   push:
> >     branches:
> >       - v4
> > 
> > permissions:
> >   contents: read
> >   pages: write
> >   id-token: write
> > 
> > concurrency:
> >   group: "pages"
> >   cancel-in-progress: false
> > 
> > jobs:
> >   build:
> >     runs-on: ubuntu-22.04
> >     steps:
> >       - uses: actions/checkout@v4
> >         with:
> >           fetch-depth: 0 # Fetch all history for git info
> >       - uses: actions/setup-node@v4
> >         with:
> >           node-version: 22
> >       - name: Install Dependencies
> >         run: npm ci
> >       - name: Build Quartz
> >         run: npx quartz build
> >       - name: Upload artifact
> >         uses: actions/upload-pages-artifact@v3
> >         with:
> >           path: public
> >  
> >   deploy:
> >     needs: build
> >     environment:
> >       name: github-pages
> >       url: ${{ steps.deployment.outputs.page_url }}
> >     runs-on: ubuntu-latest
> >     steps:
> >       - name: Deploy to GitHub Pages
> >         id: deployment
> >         uses: actions/deploy-pages@v4
> > ```
>
> > [!EXAMPLE]- Option 2: Quartz with Quartz Themes
> > For using an Obsidian Theme with Quartz.
> >
> > > [!IMPORTANT] Don't forget to replace `THEME_NAME` with your Obsidian theme of choice
> > > A list of theme options can be [found here](https://github.com/saberzero1/quartz-themes?tab=readme-ov-file#supported-themes).
> >
> > Add the following script as `.github/workflows/deploy.yaml`:
> >
> > ```yaml title=".github/workflows/deploy.yaml" {8-9, 32-33}
> > name: Deploy Quartz site to GitHub Pages
> > 
> > on:
> >   push:
> >     branches:
> >       - v4
> > 
> > env:
> >   THEME_NAME: tokyo-night
> > 
> > permissions:
> >   contents: read
> >   pages: write
> >   id-token: write
> > 
> > concurrency:
> >   group: "pages"
> >   cancel-in-progress: false
> > 
> > jobs:
> >   build:
> >     runs-on: ubuntu-22.04
> >     steps:
> >       - uses: actions/checkout@v4
> >         with:
> >           fetch-depth: 0 # Fetch all history for git info
> >       - uses: actions/setup-node@v4
> >         with:
> >           node-version: 22
> >       - name: Install Dependencies
> >         run: npm ci
> >       - name: Fetch Quartz Theme
> >         run: curl -s -S https://raw.githubusercontent.com/saberzero1/quartz-themes/master/action.sh | bash -s -- $THEME_NAME 
> >       - name: Build Quartz
> >         run: npx quartz build
> >       - name: Upload artifact
> >         uses: actions/upload-pages-artifact@v3
> >         with:
> >           path: public
> >  
> >   deploy:
> >     needs: build
> >     environment:
> >       name: github-pages
> >       url: ${{ steps.deployment.outputs.page_url }}
> >     runs-on: ubuntu-latest
> >     steps:
> >       - name: Deploy to GitHub Pages
> >         id: deployment
> >         uses: actions/deploy-pages@v4
> > ```

For other options, see the [Quartz docs on hosting](https://quartz.jzhao.xyz/hosting).

## Generating a fine-grained access token

1. Go to [this page](https://github.com/settings/personal-access-tokens/new) and apply the following settings:
 1. *Token name*: The name to identify this token. I'd recommend something that indicates it is for Quartz Syncer, like `Quartz Syncer token`. ![[Media/Access Token/access-token-name.png]]
 2. *Expiration*: When this token will expire. Defaults to 30 days from now. GitHub will send you an email when your token is about to expire. ![[Media/Access Token/access-token-expiration-date.png]]
 3. *Repository access*: Select **Only select repositories** and in the drop-down select your Quartz repository. ![[Media/Access Token/access-token-repository-access.png]]
 4. *Permissions*: Click **Repository permissions** to open all options. ![[Media/Access Token/access-token-permissions-options.png]]
 5. Scroll to the **Contents** option and change *Access: No access* to *Access: Read and write*. This will allow Quartz Syncer to manage your Quartz' content folder. ![[Media/Access Token/access-token-contents-permission.png]]
2. Now scroll down and click the button that says **Generate token**. ![[Media/Access Token/access-token-generate-token-button.png]]
3. A popup with show with the current settings. Click **Generate token** to confirm. ![[Media/Access Token/access-token-confirmation-popup.png]]
4. Click the copy button to copy the generated access token. ![[Media/Access Token/access-token-copy-generated-token.png]]
5. Open Obsidian.
6. Open Obsidian's settings and click on **Quartz Syncer** under *Community Plugins*.
7. Paste the generated token in the **GitHub token** field. ![[Media/Access Token/access-token-obsidian-settings.png]]


## Set up Quartz Syncer

In Obsidian, open `Settings > Community Plugins > Quartz Syncer > Options` and configure the following fields:

- GitHub repo name: the name of your repository on GitHub.
- GitHub username: the name of the GitHub user (or organization) the repository belongs to.
- GitHub token: the [[Guides/Generating an access token#Generating a fine-grained access token\|generated authentication token]] to allow Quartz Syncer to manage your Quartz content folder.

> [!EXAMPLE]- Configuration Example
> Using the original Quartz repository as an example:
>
> The repository is hosted at <https://github.com/jackyzha0/quartz>.
>
> - *Repository name*: `quartz`
> - *Username*: `jackyzha0`
> - *GitHub token*: generated token. usually starts with `github_pat_` or `ghp_`.

After setting all three fields, you should get a green checkmark in the Quartz Syncer options. If not, check [[Troubleshooting/Authentication\|the relevant troubleshooting page]] for help.

## That's it

You should now be able to start publishing to Quartz using Quartz Syncer.

For further details, check the [[Usage Guide]].
