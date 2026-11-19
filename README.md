# joshspeakman.github.io

Source for [joshspeakman.github.io](https://joshspeakman.github.io): apps, websites, games and game restoration work.

It's one static page (`index.html`) with no build step. A GitHub Actions workflow deploys it on every push and once a day, pulling fresh stars, release tags and update dates from the GitHub API into `data/repos.json`.

To add a restoration project, edit the `PORTS` list near the bottom of `index.html`; the hero shelf is the `SHELF` list right below it. Screenshots live in `assets/img`.
