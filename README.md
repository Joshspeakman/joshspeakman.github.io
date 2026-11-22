# joshspeakman.github.io

Source for [joshspeakman.github.io](https://joshspeakman.github.io): apps, websites, games and game restoration work.

It's one static page (`index.html`) with no build step. A GitHub Actions workflow deploys it on every push to `master`.

## Release details

Each project shows its newest release (prereleases count, drafts don't), the date it came out and its stars. Projects with no release show when they were last updated. Nothing on the page needs editing when you publish a release:

- **Every 15 minutes** the workflow reads every public repo from the GitHub API into `data/repos.json`. It deploys only when something has changed.
- **When the page opens**, it shows that file first and then asks GitHub for every repo's last push. Publishing a release pushes its tag, so any repo on the page pushed since the file was made gets its releases read again: at most five, newest first. A new release usually shows up within about a minute of publishing for anyone who opens the page. If GitHub doesn't answer (it allows a visitor 60 requests an hour), the page keeps what the file says.
- A release that doesn't push a new tag (renaming one, or publishing a draft on an existing tag) shows up on the next 15-minute refresh.

To give a card release details, add `<span class="live" data-repo="REPO"></span>`. A download link with `data-dl="REPO"` reads "Download the beta", "Download the alpha" or "Download" to match that repo's newest release.

GitHub turns off scheduled workflows in a public repo after 60 days with no activity in it. The page still finds new releases on its own; to restart the refresh, enable the workflow again in the Actions tab.

## Editing

To add a restoration project, edit the `PORTS` list near the bottom of `index.html`. Each entry gets the tags Native Apple Silicon and Custom launcher; set `gfx` (for example `"Metal"`) and `drag: true` (a drag-and-drop app in the release) to add those two. Its badge shows the name of the repo's newest release; `status` is only what it says until that loads. List every title the port covers (each game, expansion or collection) in `games`; they show as an "Includes" row, so someone searching for any one of them finds the card. Leave out titles the port doesn't support. Screenshots live in `assets/img`. Colours, fonts and animation timings are the variables at the top of the stylesheet.

The page runs in four groups: apps, web work, restoration, games. The four cards under the hero (and the header links) show one group at a time; `?show=apps`, `?show=web`, `?show=restoration` or `?show=games` opens the page already filtered, and a link to a specific card always shows everything.
