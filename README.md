# Canon recipes

Recipes for [Canon](https://canoncrm.com). A recipe packages a way of working a deal: what the deal page shows, the rules that watch it, the checks every draft must pass, and the questions research asks. A workspace installs a recipe and tunes its settings for how it sells.

| Recipe | What it's for | Install source |
|---|---|---|
| [Velocity deal](velocity-deal/) | A transactional or SMB deal one rep runs. Ships a deal page, four AI fields, a report, a paused automation and a lead scoring model. | `github:fullstackgtm/canon-recipes/velocity-deal@v2.0.0` |

## Install one

In Canon, an admin or manager opens Settings → Workspace → Recipes → **Install from GitHub** and pastes the install source. Canon pins the commit the tag names, shows the recipe's permissions, settings and eval results, and installs it on your click.

## What a recipe is

Each directory holds:

- `recipe.md`: the recipe, written in markdown. Its frontmatter has the id, the version and the permissions it asks for; a Settings table lists every setting with its default; its headings are the sections it puts on the deal page; and it holds the actions, the prompts, which of Canon's built-in rules run each part, and evals, which are sample calls whose results must hold.
- `dist/recipe.js`, only for a recipe with TypeScript: its code. It runs only in Canon's recipe runtime, an isolate with no network and no secrets, and it returns data. Every write still goes through Canon's own approval and evidence checks.

Velocity deal is markdown only: its rules are Canon's built-ins, set up by its settings and tables, so it has no code.

Versions are git tags. Canon offers an upgrade when a newer tag exists and shows how it changes the settings you've edited before you accept it.
