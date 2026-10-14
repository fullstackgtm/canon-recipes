# Canon recipes

Recipes for [Canon](https://canoncrm.com). A recipe packages a way of working a deal: what the deal page shows, the rules that watch it, the checks every draft must pass, and the questions research asks. A workspace installs a recipe and tunes its settings for how it sells.

| Recipe | What it's for | Install source |
|---|---|---|
| [Velocity deal](velocity-deal/) | A transactional or SMB deal one rep runs: get a reply from the champion, show the fit, close. | `github:fullstackgtm/canon-recipes/velocity-deal@v1.0.0` |

## Install one

In Canon, an admin or manager opens Settings → Workspace → Recipes → **Install from GitHub** and pastes the install source. Canon pins the commit the tag names, shows the recipe's permissions, settings and eval results, and installs it on your click.

## What a recipe is

Each directory holds:

- `canon-recipe.json`: the manifest. It has the recipe's id and version, the permissions it asks for, its settings with their defaults, the sections it puts on the deal page, and evals, which are sample calls whose results must hold.
- `dist/recipe.js`: the recipe's code. It runs only in Canon's recipe runtime, an isolate with no network and no secrets, and it returns data. Every write still goes through Canon's own approval and evidence checks.
- `README.md`: the settings and evals in plain words.

Versions are git tags. Canon offers an upgrade when a newer tag exists and shows how it changes the settings you've edited before you accept it.
