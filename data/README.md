# Data

## `game_films.csv`

This TidyTuesday dataset, **Films Based on Video Games**, is scraped from the Wikipedia article [*List of films based on video games*](https://en.wikipedia.org/wiki/List_of_films_based_on_video_games) and curated by Georgios Karamanis. Each row is one film adaptations, with `r ncol(game_films)` variables spanning `r nrow(game_films)` films released since the early 1980s to upcoming titles.

**Source:** [TidyTuesday, 2026-06-09](https://github.com/rfordatascience/tidytuesday/tree/main/data/2026/2026-06-09),

**Dimensions:** 439 rows × 20 columns. One row per film adaptation, released 1986-2028.

| Variable | Description |
|------------------------------------|------------------------------------|
| `category` | Top-level section: Theatrical, Direct-to-video, TV films, Short films, Documentaries |
| `subcategory` | Second-level section (e.g. English, Japanese, Animation); NA if none |
| `title` | Film title |
| `director` | Director(s); multiple separated by " \| " |
| `release_date` | Parsed release date (earliest for regional releases); NA if TBA |
| `release_date_raw` | Original release date string from Wikipedia |
| `air_date_raw` | Original air date string (TV productions); NA otherwise |
| `worldwide_box_office_currency` | Currency symbol of the box office figure |
| `worldwide_box_office` | Worldwide gross, in original currency units |
| `rotten_tomatoes` | Rotten Tomatoes critic score (0-100) |
| `metacritic` | Metacritic score (0-100) |
| `cinema_score` | CinemaScore audience grade (A+ to F) |
| `distributor` | Film distributor(s) |
| `original_game_publisher` | Publisher of the source video game |
| `budget_currency` | Currency symbol of the budget figures |
| `budget_low` | Lower bound of production budget (= `budget_high` if single value) |
| `budget_high` | Upper bound of production budget |
| `domestic_box_office` | Domestic gross (documentary sections) |
| `subject` | Documentary subject (documentary sections only) |
| `network` | Broadcast network (TV productions) |

## `video_game_ratings.csv` *(to be added)*
