# Field Notes — Jekyll thesis website

A responsive, academic-style GitHub Pages template for presenting visual experiments. It uses standard Jekyll, Liquid, CSS, and a small amount of dependency-free JavaScript.

## Run locally

1. Install Ruby and Bundler, then run `bundle install`.
2. Start the development server: `bundle exec jekyll serve --livereload`.
3. Open `http://localhost:4000`.

To validate a production build without a server, run `bundle exec jekyll build`. The generated site will be in `_site/`.

## Publish on GitHub Pages

1. Create a repository named `username.github.io` (or use a project repository).
2. Copy the contents of this folder into the repository.
3. In **Settings → Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`.
4. For a project repository, set `baseurl: "/repository-name"` in `_config.yml`; leave it empty for a user site.

GitHub Pages will build the site with Jekyll. The included `Gemfile` is useful for matching the local Jekyll version; no plugins are required.

## Replace the sample GIFs

Sample files live in `assets/img/` and are intentionally lightweight placeholders. Replace each `.gif` with your own animated GIF, keeping the filename, or update the `gif` field in `_data/experiments.yml`. Add a still poster image (`.png` or `.jpg`) and update the matching `poster` field. Posters are shown when a visitor presses **Pause loop**, because browsers do not provide a native way to pause an animated GIF in an `<img>` element.

Recommended: export a web-optimized GIF under 3–5 MB, with a clear first frame. The image `alt` field in the data file becomes its accessible description.

## Add a new experiment

1. Add a new entry to `_data/experiments.yml` using the existing fields:
   - `number`, `tag`, `year`, `title`, `description`
   - `visible`, `gif`, `poster`, `alt`, `loop`
   - `focus_default` (`context`, `transition`, or `detail`) and `focus_value` (0–100)
2. Place the GIF and poster in `assets/img/`.
3. Rebuild or refresh the local server. The card is generated automatically by the Liquid loop in `index.md`.

The range control changes the focus label and emphasizes one of the two numbered visual prompts. The play button swaps between the animated GIF and its poster; this keeps the interaction portable and backend-free.

## Customization map

- `_config.yml`: site title, description, and GitHub Pages `baseurl`.
- `_data/experiments.yml`: experiment content and media filenames.
- `assets/css/site.css`: colors, typography, grid, and responsive rules.
- `assets/js/site.js`: play/pause and focus-window behavior.
- `_layouts/default.html`: shared header/footer shell.
