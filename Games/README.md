# Patterns that define success of a game

## Used tools: 
* `pandas`
* `matplotlib`
* `seaborn`
* `numpy`
* `scipy`

## Project description

1. It is necessary to **work on the data analysis process** that enables the identification of patterns determining the success of a game.
2. This is required in order to **identify potentially popular products and plan a successful advertising campaign for the year 2017.**


**Dataset and Columns:**
A **dataset** has been compiled from open sources with historical data up until 2016, including:
1. Game sales
2. User and critic reviews
3. Genres and platforms.

**Column Names:**
* `Name` — name of the game;
* `Platform` — gaming platform;
* `Year_of_Release` — year of release;
* `Genre` — game genre;
* `NA_sales` — sales in North America (millions of copies sold);
* `EU_sales` — sales in Europe (millions of copies sold);
* `JP_sales` — sales in Japan (millions of copies sold);
* `Other_sales` — sales in other countries (millions of copies sold);
* `Critic_Score` — critic score (maximum 100);
* `User_Score` — user score (maximum 10);
* `Rating` — rating from the Entertainment Software Rating Board (ESRB), an association that assigns age categories to computer games based on content.

## Overall conclusion

A sample was obtained with historical data on game sales, user and critic reviews, genres, and platforms up until 2016. The sample consists of 16,715 entries.

**The sample had the following issues:**

1. Columns did not have a consistent naming convention (mix of lowercase and uppercase).
2. The columns `Year_of_Release` and `User_Score` had incorrect data types. `int` should have been used for the release year, and `float` for the ratings.
3. Many columns had missing values.

**The following changes were made to the sample:**

1. Column names were changed to have consistent naming conventions, and the `Year_of_Release` column was renamed to `release` for clarity.
2. The formats of the `release` and `user_score` columns were corrected.
3. Ratings with the value `"tbd"` were changed to `NaN` to indicate ratings pending further review.
4. Missing values were filled with "WoR" (Without Rating), and the rating "K-A" was changed to "E".
5. Two rows with missing game titles and genres were deleted.
6. Duplicate games for different platforms were present in the dataframe.
7. Release dates for games might have been lost due to incorrect parsing settings.
8. Review metrics might be missing due to a lack of reviews or incorrect parsing.

**The exploratory data analysis revealed:**

1. There was a sharp increase in the number of games and their sales after 2000, followed by a sharp decline after 2009. This might indicate a shift in focus towards updating and supporting existing games rather than releasing new ones, possibly due to the rise of online gaming and mobile gaming.

**Based on the analysis, the following conclusions were drawn:**

1. The average lifespan of a gaming platform is approximately 10 years.
2. The platforms `PS4` and `XOne` showed promising potential during the selected period (2012-2016).
3. The platforms `PC`, `PS3`, and `X360` also showed promise.
4. Genres with high sales and revenue included `Action`, `Shooter`, and `Sports`.
5. Platform popularity was often tied to the region of their origin.
6. Genre preferences varied by region.

**Several hypotheses were tested and confirmed:**

1. The average user rating for Xbox One and PC platforms is the same.
2. The average user ratings for the `Action` and `Sports` genres are different.
