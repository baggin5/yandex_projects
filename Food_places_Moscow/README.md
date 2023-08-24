# The market of catering establishments in Moscow

## Used tools: 
* `pandas`
* `matplotlib`
* `seaborn`
* `numpy`
* `scipy`
* `datetime`
* `math`
* `plotly`
* `folium`

## Project description

**Investors from the "Shut Up and Take My Money" fund** have decided to open a public catering establishment in Moscow.

**The clients are not sure about the direction of the establishment** (cafe, restaurant, pizzeria, pub, or bar), its location, and pricing.

**A dataset of public catering establishments in Moscow is available, compiled based on data from Yandex Maps and Yandex Business as of the summer of 2022.**

* The information placed in the Yandex Business service could have been added by users or found in publicly available sources. It is purely for reference purposes.

**Dataset Columns:**
**File `moscow_places.csv`**:
* `name` — establishment name;
* `address` — establishment address;
* `category` — establishment category, for example, "cafe," "pizzeria," or "coffee shop";
* `hours` — information about days and hours of operation;
* `lat` — latitude of the geographical point where the establishment is located;
* `lng` — longitude of the geographical point where the establishment is located;
* `rating` — establishment rating based on user ratings in Yandex Maps (highest rating is 5.0);
* `price` — price category in the establishment, for example, "average," "below average," "above average," and so on;
* `avg_bill` — a string that stores the average order cost in the form of a range, for example:
 > "Average bill: 1000–1500 ₽";
 > "Cappuccino price: 130–220 ₽";
 > "Beer glass price: 400–600 ₽".
* `middle_avg_bill` — a number representing the estimated average bill, which is only indicated for values from the `avg_bill` column that start with the substring >"Average bill":
 > If the string contains a price range of two values, the median of these two values will be included in the column.
 > If the string contains a single number — a price without a range, that number will be included in the column.
 > If there is no value or it does not start with the substring "Average bill," the column will be empty.
* `middle_coffee_cup` — a number representing the estimated price of one cup of cappuccino, which is only indicated for values from the `avg_bill` column that start with the substring "Cappuccino price":
 > If the string contains a price range of two values, the median of these two values will be included in the column.
 > If the string contains a single number — a price without a range, that number will be included in the column.
 > If there is no value or it does not start with the substring "Cappuccino price," the column will be empty.
* `chain` — a number expressed as 0 or 1, indicating whether the establishment is part of a chain (there may be errors for small chains):
 * 0 — the establishment is not part of a chain
 * 1 — the establishment is part of a chain
* `district` — administrative district in which the establishment is located, for example:
 * Central Administrative District;
* `seats` — number of seating places.

## Task description

**Task:** Prepare a market research of the public catering industry in Moscow, find interesting features, and present the obtained results that will help in the future to choose a suitable location for investors.

## Overall conclusion
The dataset containing venues in Moscow was analyzed.

**As a result of preprocessing:**

1. A column with street names was created.
2. A categorical column indicating 24/7 operation was added.
3. An upper limit of 250 seating places for the investigated data was defined.
4. Rows without filled columns for operating hours, average check, and seating capacity were removed.
5. Rows with implicit duplicates in the venue name-address pair were eliminated.

**Data analysis revealed:**

1. There are a total of 7 types of venues. The top three types by quantity are cafes, restaurants, and coffee shops.
2. The median seating capacity ranges from 48 to 80.
3. More than 33% of restaurants and cafes are chains. More than half of coffee shops, pizzerias, and bakeries are chains.
4. Leading chain venues include "Shokoladnitsa," "Domino's," "Dodo Pizza," "One Price Coffee," and "Cofix." The majority of popular venues in categories like coffee shops, fast food, and cafes fall into this group. These venues serve as meeting places due to their concentration around urban flows.
5. Venues are primarily concentrated in the central part of the city, with a higher presence of restaurants, cafes, coffee shops, and bars/pubs. Bakeries, pizzerias, canteens, and fast-food places are comparatively less common.
6. If we consider the distribution of categories across city districts, a significant portion is concentrated in the central district, and venues are roughly equally distributed in other districts, except for the Southeastern (ЮВ) and Northwestern (СЗ) administrative districts, where they are less common.
7. Ratings for almost all categories of venues are generally high. The only "outlier" is the fast-food category due to its higher quantity. The central part of the city outperforms others in venue ratings, which is not surprising.
8. Longer streets tend to have more venues. venues are primarily concentrated on busy streets, as foot traffic is essential for profitability.
9. The average check includes rent and other expenses, thus pricier districts have higher average checks. The most expensive districts are Central Administrative District (ЦАО) and Western Administrative District (ЗАО). Less expensive districts are residential or industrial, such as Southeastern (ЮВАО), Southern (ЮВО), and Northern (САО) administrative districts.

**Coffee Shops**

1. A total of 1334 coffee shops were analyzed.
2. Coffee shops are predominantly located in the Central Administrative District (ЦАО), Northern Administrative District (САО), Northeastern Administrative District (СВАО), and Western Administrative District (ЗАО), known for higher or mid-range pricing.
3. The average price of a cup of coffee by districts ranges from 150 to 190 rubles, with an overall city average of 175 rubles.

**Detailed Coffee Shop Opening**

1. Attention should be given to location.
2. The location will influence the coffee price.
3. The client is not afraid of competition.

Based on the three factors for opening a coffee shop: location in the Central Administrative District (any part), Northern Administrative District (САО), Northeastern Administrative District (СВАО), or Western Administrative District (ЗАО) closer to the center. In simpler terms, where foot traffic is high.

Consequently, if the coffee shop is situated closer to the central part of the city, the average coffee price would be around 190 rubles.

Preferred coffee shop size is roughly 40 to 60 seating places.
