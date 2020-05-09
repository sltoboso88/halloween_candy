README
================
Sandra Tobon
2020-05-09

<center>

# <span style="color: orange;"> HALLOWEEN DATA </span>

![](http://justfunfacts.com/wp-content/uploads/2018/01/candies.jpg)

</center>

## What is the dataset about?

Every year around the world but mainly in USA and Canada, is a poll that
ask people if they **Join**, **Despair** or **Meh**, some general
candies; the grade of conecction that they have with specifics famous
person; some question about cultural and publicity things, and some
personal questions.

For this exercise we used only the information about the candies. The
main objective of the project was clean the data and found some useful
information from the data.

If you want more information about the data set, it is avaible
[here](https://www.scq.ubc.ca/so-much-candy-data-seriously/)

## Tools used in this project

  - **Language**: R  
  - **Libraries**:
      - tidyverse  
      - janitor  
      - readxl  
      - here  
      - readr  
      - styler

## Data before the cleaning process

The raw data were in three different excel files, one for each year
(2015, 2016 and 2017), with the answers of the poll for the
corresponding year. The year with most records is 2015 with 5630
records.

The problem with the data from 2015 is that year the only options for
describing the candies were Join and Despair. Also they didn’t ask for
the gender and the country from which people answered the survey.

## Data clean proccess

  - Clean the age column: in the survey the people were allowed from
    entering letters  
  - Clean the country column (2016 -2017): for this were very helpfull
    the states and city columns  
  - Select the columns for the analysis: how we said above we only
    needed the columns referring to gender, country, age, trick or
    treating yourself, and candies preferences  
  - Pivot longer: candies and the preferences. This helped to do the
    analysis in R, because R works better with vectors
  - Add a year column in each data set, so we could identify them when
    we merged all the data frames  
  - Add gender and country columns in the 2015 data set. Those columns
    we fill with “Not ask”, with the purpose of making possible the
    union of data sets and work with them together  
  - Unit the 3 data sets  
  - Filter some information without relation to a real candies, for
    instances “Cash, or other forms of legal tender” or “Hugs (actual
    physical hugs)”

## Interesting conclusions after analyzing the data

  - The total number of different candies were part of the survey during
    the three years were 120

  - The average age of people who are or aren’t going out to trick or
    treating themsel are:

| trick\_themself | average\_age |
| :-------------- | -----------: |
| No              |           42 |
| Yes             |           37 |

  - The candies revived the most of joy, despair and meh, during the
    three years and regardless of the answer “Any full-sized candy bar”,
    because actually is the answer with most revived in the category of
    Joy, are:

| candies\_food     | preference\_candies | total\_votes |
| :---------------- | :------------------ | -----------: |
| Broken glow stick | DESPAIR             |          755 |
| Kit Kat           | JOY                 |          713 |
| Lollipops         | MEH                 |          461 |

<center>

![](https://straightforward.design/wp-content/uploads/2018/11/Starburst-Standard-Set-Visual-v3.jpg)

</center>

  - The number of people rated Starburst as Despair 351

For the rest of the analysis we assumed that when the people answered
despair was -1 for the candy, joy was +1 and meh was 0.

  - The most popular candy by this rating system for each gender in the
    dataset, during the three years and regardless of the answer “Any
    full-sized candy bar”, because actually is the answer with the best
    rating for women and men, are:

| gender             | candies\_food | total\_prefence |
| :----------------- | :------------ | --------------: |
| Female             | Kit Kat       |             202 |
| Female             | Lindt Truffle |             202 |
| I’d rather not say | Kit Kat       |              33 |
| Male               | Kit Kat       |             249 |
| Other              | Twix          |              26 |

  - The most popular candy by this rating system for each year in the
    dataset, regardless of the answer “Any full-sized candy bar”,
    because actually is the answer with the best rating each year, are:

| year | candies\_food | total\_prefence |
| ---: | :------------ | --------------: |
| 2017 | Kit Kat       |             287 |
| 2016 | Kit Kat       |             220 |
| 2015 | Kit Kat       |              45 |

  - The most popular candy by this rating system for USA, Canada, UK and
    the other countries in the dataset, regardless of the answer “Any
    full-sized candy bar”, because is the answer with the best rating in
    USA, Canada and the other countries, are:

| country | candies\_food                | total\_prefence |
| :------ | :--------------------------- | --------------: |
| USA     | Kit Kat                      |             314 |
| Canada  | Tolberone something or other |             124 |
| Other   | Kit Kat                      |              45 |
| UK      | Rolos                        |              32 |
| UK      | Tolberone something or other |              32 |
