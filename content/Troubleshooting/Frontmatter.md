---
{"publish":true,"title":"Frontmatter","description":"Troubleshooting issues related to Frontmatter.","created":"2025-05-18T10:31:22.000+02:00","modified":"2025-05-20T20:31:59.193+02:00","tags":["frontmatter"],"cssclasses":""}
---


> [!WARNING] Quartz Syncer passes **all** frontmatter tags by default. Please be mindful when publishing.

> [!INFO] Frontmatter usage
> Frontmatter is a way to add metadata to markdown files in YAML format popularized by Jekyll. You can find the Jekyll docs on frontmatter by [clicking here](https://jekyllrb.com/docs/front-matter/).
>
> Quartz Syncer requires the `publish` tag to be set in order for a note to appear in the publishing dialog.
> > [!EXAMPLE]- Minimum frontmatter required for Quartz Syncer
> >
> > ```markdown
> > ---
> > publish: true
> > ---
> > rest of the note here...
> > ```
