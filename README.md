# DIANA Project Website

Public website for the DIANA research project.

## How to publish on GitHub Pages

1. Push this `diana-website/` folder (or its contents) to a GitHub repository.
2. Go to **Settings → Pages** in your repository.
3. Under *Source*, select **Deploy from a branch** → choose your branch (e.g. `main`) and set the folder to `/diana-website` (or `/root` if you place the files at the root).
4. Click **Save**. GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/`.

## Adding news

Edit `data/news.json`. Each entry follows this format:

```json
{
  "date": "YYYY-MM-DD",
  "title": "Your news headline",
  "body": "One or two sentences describing the news item.",
  "tag": "Milestone"
}
```

Available tags (or create your own): `Milestone`, `Paper`, `Event`, `Award`, `Press`, `Recruitment`.

## Adding publications

Edit `data/publications.json`. Each entry follows this format:

```json
{
  "year": 2027,
  "authors": "Cappon G., Moretti C., et al.",
  "title": "Full title of the paper",
  "journal": "Journal Name or Conference Proceedings",
  "doi": "10.xxxx/xxxxxxx",
  "type": "Journal Article",
  "note": ""
}
```

Available types: `Journal Article`, `Conference Paper`, `Preprint`, `Software`.

Leave `"doi": ""` if the DOI is not yet assigned. The `"note"` field is optional.

## Local preview

Because news and publications are loaded via `fetch()`, you need a local HTTP server to preview the site (not just opening `index.html` directly in a browser). Run:

```bash
cd diana-website
python3 -m http.server 8000
```

Then open `http://localhost:8000` in your browser.
