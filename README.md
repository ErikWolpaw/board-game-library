# Board Game Library

A single-page browser for our board game collection — filter by player count,
search by title or publisher, see which games are *best* at tonight's headcount.

**Live site:** https://erikwolpaw.github.io/board-game-library/

## Files

- `index.html` — the whole site. No build step, no dependencies, no server.
- `games.csv` — the catalog. One row per physical box; boxes of the same game
  share a `title` and get grouped into one card.

## Updating

Edit `games.csv` and commit it. The page fetches the CSV at load time, so a new
copy is all it takes — `index.html` never needs to change to add games.

### Columns

| Column | Meaning |
|---|---|
| `title` | Groups boxes together. Rows sharing a title become one card. |
| `subtitle_or_edition` | Edition or box name, shown under the title. |
| `type` | `base game`, `expansion`, or `storage box`. |
| `in_storage` | `yes` hides the game from the default "On the shelf" view. |
| `min_players` / `max_players` | Drives the player-count filter. |
| `best_players` | From the BGG community poll. `4`, `4-5`, or `"2, 4"` for split results. |
| `bgg_id` | Links the card title to BoardGameGeek. |
| `bgg_year`, `poll_votes` | Shown as context; `poll_votes` flags a thin poll. |
| `notes` | Provenance — what the spine actually said, judgment calls made. |

Player counts and "best at" figures come from
[BoardGameGeek](https://boardgamegeek.com) community polls.
