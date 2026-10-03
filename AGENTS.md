# Reports

This repo hosts reports as static HTML pages served by GitHub Pages. Reports are published on every push to main.

## Adding a report

1. Pick a descriptive slug for your report. The slug should be meaningful on its own without additional context — a reader scanning the directory should understand what the report covers from the slug alone. `stallion-chunked-transfer-encoding` and `ponycheck-shrink-research` are good; `pr-42` and `api-review` are not.

2. Create `r/<slug>/index.html` with your report content. The report is a self-contained HTML file. Different reports may have different visual styles — there is no single required template.

3. Update `r/index.html` to include your report under the appropriate category. Add a list item with a link and a one-line description:

```html
<ul class="report-list">
  <li>
    <a href="slug/">Report title</a>
    <div class="report-desc">One-line description.</div>
  </li>
</ul>
```

A report can appear in more than one category. If the category doesn't exist yet, confirm with the user before adding it, then add a new `<section>` for it with an `id`, an `<h2>` heading, and a `<ul class="report-list">`. Add a corresponding nav link in the `<nav>` sidebar.

4. Squash all changes into a single commit and push to main. Each report addition or update should be one commit. The report will be live at `https://ponylang.github.io/reports/r/<slug>/` after the deploy workflow runs.

## Updating a report

Edit the report's `index.html` in place, squash into a single commit, and push. The deploy rebuilds on every push to main.

## Structure

```
r/
  index.html              # categorized index of all reports
  some-report/
    index.html            # a report
  another-report/
    index.html            # another report
.github/workflows/
  deploy.yml              # GitHub Pages deployment
```
