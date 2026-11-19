# joshspeakman.github.io

Source for [joshspeakman.github.io](https://joshspeakman.github.io): apps, websites, games and game restoration work.

It's one static page (`index.html`) with no build step. A GitHub Actions workflow deploys it on every push and once a day, pulling fresh stars, release tags and update dates from the GitHub API into `data/repos.json`.

To add a restoration project, edit the `PORTS` list near the bottom of `index.html`. Each entry gets the tags Native Apple Silicon and Custom launcher; set `gfx` (for example `"Metal"`) and `drag: true` (a drag-and-drop app in the release) to add those two. Screenshots live in `assets/img`. Colours, fonts and animation timings are the variables at the top of the stylesheet.

The page runs in four groups: apps, web work, restoration, games. The four cards under the hero (and the header links) show one group at a time; `?show=apps`, `?show=web`, `?show=restoration` or `?show=games` opens the page already filtered, and a link to a specific card always shows everything.

The previous version of this site is on the `legacy-portfolio` branch.
