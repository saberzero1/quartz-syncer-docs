---
{"title":"Setup Guide","description":"Instructions for setting up Quartz Syncer plugin.","created":"04-05-25","date":"05-05-25","publish":true,"PassFrontmatter":true}
---


> [!WARNING]- A GitHub account is required to use Quartz and Quartz Syncer
> You can sign up for free [here](https://github.com/signup).

## Set up Quartz

### Create Quartz GitHub repository

If you haven't set up a Quartz repository on GitHub yet, [click here](https://github.com/new?template_name=quartz&template_owner=jackyzha0) to create it using the Quartz template.

### Configure Quartz settings

#### Configure `quartz.config.ts`

Configure the following settings in the `quartz.config.ts` file:

(Below example only shows a subset of all settings. Please do not remove any settings.)

```ts title="quartz.config.ts" {3,6,12,25ú}
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
> > > [!IMPORTANT] Don't forget to replace `THEME-NAME` with your Obsidian theme of choice
> > > A list of theme options can be [found here](https://github.com/saberzero1/quartz-themes?tab=readme-ov-file#supported-themes).
> >
> > Add the following script as `.github/workflows/deploy.yaml`:
> >
> > ```yaml title=".github/workflows/deploy.yaml" {30}
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
> >       - name: Fetch Quartz Theme
> >         run: curl -s -S https://raw.githubusercontent.com/saberzero1/quartz-themes/master/action.sh | bash -s -- THEME-NAME 
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


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/Guides/Generating-a-fine-grained-access-token#Generating-a-new-fine-grained-access-token" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



## Generating a new fine-grained access token

1. Go to [this page](https://github.com/settings/personal-access-tokens/new) and apply the following settings:
	1. *Token name*: The name to identify this token. I'd recommend something that indicates it is for Quartz Syncer, like `Quartz Syncer token`. ![access-token-name.png](Media/Access%20Token/access-token-name.png)
	2. *Expiration*: When this token will expire. Defaults to 30 days from now. GitHub will send you and email when your token is about to expire. ![access-token-expiration-date.png](Media/Access%20Token/access-token-expiration-date.png)
	3. *Repository access*: Select **Only select repositories** and in the drop-down select your Quartz repository. ![access-token-repository-access.png](Media/Access%20Token/access-token-repository-access.png)
	4. *Permissions*: Click **Repository permissions** to open all options. ![access-token-permissions-options.png](Media/Access%20Token/access-token-permissions-options.png)
	5. Scroll to the **Contents** option and change *Access: No access* to *Access: Read and write*. This will allow Quartz Syncer to manage your Quartz' content folder. ![access-token-contents-permission.png](Media/Access%20Token/access-token-contents-permission.png)
2. Now scroll down and click the button that says **Generate token**. ![access-token-generate-token-button.png](Media/Access%20Token/access-token-generate-token-button.png)
3. A popup with show with the current settings. Click **Generate token** to confirm. ![access-token-confirmation-popup.png](Media/Access%20Token/access-token-confirmation-popup.png)
4. Click the copy button to copy the generated access token. ![access-token-copy-generated-token.png](Media/Access%20Token/access-token-copy-generated-token.png)
5. Open Obsidian.
6. Open Obsidian's settings and click on **Quartz Syncer** under *Community Plugins*.
7. Paste the generated token in the **GitHub token** field. ![access-token-obsidian-settings.png](Media/Access%20Token/access-token-obsidian-settings.png)


</div></div>


## Set up Quartz Syncer

In Obsidian, open `Settings > Community Plugins > Quartz Syncer > Options` and configure the following fields:

- GitHub repo name: the name of your repository on GitHub.
- GitHub username: the name of the GitHub user (or organization) the repository belongs to.
- GitHub token: the generated authentication token to allow Quartz Syncer to manage your Quartz content folder.

> [!EXAMPLE]- Configuration Example
> Using the original Quartz repository as an example:
>
> The repository is hosted at https://github.com/jackyzha0/quartz.
> - *Repository name*: `quartz`
> - *Username*: `jackyzha0`
> - *GitHub token*: generated token. usually starts with `ghp_`.

After setting all three fields, you should get a green checkmark in the Quartz Syncer options. If not, check [[Troubleshooting/Authentication\|the relevant troubleshooting page]] for help.

## That's it

You should now be able to start publishing to Quartz using Quartz Syncer.

For further details, check the [[Usage Guide\|Usage Guide]].
