# Data

## `game_films.csv`

This TidyTuesday dataset, **Films Based on Video Games**, is scraped from the Wikipedia article [*List of films based on video games*](https://en.wikipedia.org/wiki/List_of_films_based_on_video_games) and curated by Georgios Karamanis. Each row is one film adaptation, with 20 variables spanning 439 films released since the mid 1980s to upcoming titles.

**Source:** [TidyTuesday, 2026-06-09](https://github.com/rfordatascience/tidytuesday/tree/main/data/2026/2026-06-09)

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

## `video_game_ratings.csv`
**Video Game Sales and Ratings** is a Kaggle dataset pairing video game sales with Metacritic critic and user scores. Used in Question 2 to compare each film's rating against the ratings of its source games when matched by franchise.

**Source:** [Video Game Sales and Ratings](https://www.kaggle.com/datasets/thedevastator/video-game-sales-and-ratings) (Kaggle, thedevastator)
**Dimensions:** 16,928 rows × 17 columns. One row per game-platform release, covering 1980-2020.

| Variable | Description |
|------------------------------------|------------------------------------|
| `Name` | Game title (used to match franchises) |
| `Critic_Score` | Metacritic critic score (0-100); same scale as the films' `metacritic` |
| `User_Score` | Metacritic user score (0-10; stored as text, `"tbd"` where unrated) |
| `Year_of_Release` | Year the game was released |
| `Publisher` | Game publisher |
| `Platform`, `Genre`, `Developer`, `Rating` | Descriptive fields (platform, genre, developer, ESRB rating) |
| `NA_Sales`, `EU_Sales`, `JP_Sales`, `Other_Sales`, `Global_Sales` | Regional and global sales, in millions of units (not used) |
| `Critic_Count`, `User_Count` | Number of critic / user reviews (not used) |

*Only `Name`, `Critic_Score`, and (for a quick peek) `User_Score` feed the analysis.*

## `cpi-data.csv`
U.S. Consumer Price Index (CPI-U, all items), used in Question 1 to convert box office figures into inflation-adjusted 2025 dollars. This is the raw BLS flat file (all CPI series), filtered in code to series `CUUR0000SA0`.

**Source:** [U.S. Bureau of Labor Statistics](https://download.bls.gov/pub/time.series/cu/) — file `cu.data.1.AllItems`
**Format:** Tab-separated. Contains every CPI series; the analysis keeps only `CUUR0000SA0` (all items, U.S. city average, 1982-84 = 100).

| Variable | Description |
|------------------------------------|------------------------------------|
| `series_id` | CPI series identifier (filtered to `CUUR0000SA0`) |
| `year` | Calendar year |
| `period` | Month code (`M01`-`M12`), or `M13` for the annual average |
| `value` | The index value for that series/year/period |
| `footnote_codes` | BLS footnote markers (not used) |
