---
jupyter:
  colab:
  kernelspec:
    display_name: Python 3
    name: python3
  language_info:
    name: python
  nbformat: 4
  nbformat_minor: 0
---

<div class="cell markdown" id="9xZnRXM7x0Cv">

# CUHK-STAT1013: Practical Assignment Part 1: Sharing Your Idea and Data

</div>

<div class="cell markdown" id="9Fy05KAkyJI0">

## Years of World Education by Country dataset background

**Description**:

A country's success and development are greatly influenced by its level
of education. Globally speaking, education has advanced significantly
throughout time, and more people are now obtaining formal education. The
dataset includes data on the typical number of school years in each
nation from 1870 to 2017. For policymakers, academics, and educators to
better comprehend educational trends and their effects on a nation's
growth, it is crucial that they have access to this data.

This DataSet, which can be found at
<https://www.kaggle.com/datasets/fredericksalazar/average-years-of-schooling-since-1870-2017?resource=download>,
provides the average number of years of education for each nation over
the years, from 1870 to 2017, broken down by country.

The collection includes statistics on each nation's average number of
school years from 1870 to 2017 with total 7763 sample size. The
information is set out in four columns:

-   Name of Country: The name of the nation for which the data is given
    may be found in this column.

-   Alpha-3 Country Code: The International Organization for
    Standardization awarded each nation a three-letter code, which is
    listed in this column (ISO).

-   Year of Measurement: The year that the average number of years spent
    in school was determined is listed in this column.

-   Average Years of Schooling: The average number of years spent in
    school in each nation during the specified year is shown in this
    column.

The information may be used to examine historical patterns in
educational trends across nations. Researchers, decision-makers, and
educators may use the data to comprehend the advancements achieved in
education throughout the world and to pinpoint areas in need of
improvement. The information may also be used to compare educational
standards between nations and to comprehend the link between learning
and economic growth.

**Kaggle Link**:
<https://www.kaggle.com/datasets/fredericksalazar/average-years-of-schooling-since-1870-2017?resource=download>

**Sample size**: 7,763

**Feature documentation**:

| Feature                | Class  | Shape | Dtype   |
|:-----------------------|:-------|:------|:--------|
| Entity                 | Tensor |       | string  |
| Code                   | Tensor |       | string  |
| Year                   | Tensor |       | int64   |
| avg_years_of_schooling | Tensor |       | float64 |

</div>

<div class="cell markdown" id="k85zO7zxys4H">

## Hypothesis

-   Tell us what your idea is and why you have chosen to pursue this
    idea.
    -   I propose that there is a correlation between a nation's average
        number of years spent in school and its degree of economic
        growth. I decided to research this concept because I am
        interested in learning more about the link between education and
        a nation's economic prosperity.
-   What two groups you are comparing:
    -   High-income countries and low-income countries are the two
        categories being contrasted. According to their gross national
        income (GNI) per capita, the World Bank categorizes nations as
        high-income or low-income. In 2021, the GNI per capita threshold
        for high-income nations is $12,536; for low-income nations, it
        is $1,035 or less. I will choose three nations for each
        comparison in the assignment.

    -   **G1**: High-income countries: United States of America,
        Switzerland, Japan;

    -   **G2**: Low-income countries: Afghanistan, Central African
        Republic, Sierra Leone
-   What you will be measuring (i.e., what your response variable will
    be)
    -   `avg_years_of_schooling`
-   Is your response variable quantitative rather than categorical?
    -   The response variable will be the average years of schooling in
        each country. This variable is quantitative and continuous.
-   Make a prediction about what kind of difference you expect to see
    between your samples and WHY.
    -   In comparison to low-income countries, high-income countries
        will likely have a greater average number of years spent in
        education. This is true because high-income nations frequently
        invest more money and resources in education and place a higher
        priority on it as a method of promoting economic growth and
        development. However, low-income countries may have a variety of
        difficulties like poverty, a lack of infrastructure, and
        political unrest, all of which can make it difficult for them to
        invest in education and offer their inhabitants a high-quality
        education. Because of this, I anticipate finding a statistically
        significant difference in the average number of years spent in
        school in high-income and low-income countries.
-   Talk about how you will gather your data
    -   The information on educational attainment from various locations
        with We will need to gather information on educational
        attainment from various locations, along with the relevant
        years, in order to accomplish this project. Fortunately, Kaggle,
        an open-source platform that houses statistics from many
        organizations and sources, already has a dataset for average
        years of schooling by country and year. With this URL:
        <https://www.kaggle.com/datasets/fredericksalazar/average-years-of-schooling-since-1870-2017?resource=download>,
        users can get the dataset. Thus, there is no need for us to
        gather any more information.
-   If you had unlimited resources (time, money, staff, etc.) how would
    you collect your data?
    -   If we did not have this dataset and needed to gather data on
        years of world education by country, we could use various
        methods, including:

    -   Online databases: The World Bank, the United Nations
        Educational, Scientific and Cultural Organization, and the
        UNESCO Institute for Statistics are a few online sources that
        offer data on education statistics by nation (UNESCO). Users can
        obtain data from these databases on a range of education
        variables, including years of schooling.

    -   Surveys: Surveys are another way to acquire information on
        education. To get information on each country's population's
        level of education, we may create a survey questionnaire and
        distribute it to a sample of people who are equally
        representative of each nation.

    -   Government statistics: As part of the census or other official
        data collection operations, governments frequently gather
        information on education statistics, particularly the number of
        years spent in school. By getting in touch with the appropriate
        government authorities or using publicly accessible data
        sources, we might receive information from these sources.

</div>

<div class="cell markdown" id="3GOdPWT03PQB">

## Prepare your dataset

</div>

<div class="cell code" execution_count="5"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:206}"
id="mUxJb4hxvpHQ" outputId="a3dfeabb-f3a7-49d1-8359-9f245ee008d9">

``` python
## load dataset

import pandas as pd

df = pd.read_csv('/content/years_of_world_education_by_country.csv', sep=';')
df.head(5)
```

<div class="output execute_result" execution_count="5">

            Entity Code  Year  avg_years_of_schooling
    0  Afghanistan  AFG  1870                    0.01
    1  Afghanistan  AFG  1875                    0.01
    2  Afghanistan  AFG  1880                    0.01
    3  Afghanistan  AFG  1885                    0.01
    4  Afghanistan  AFG  1890                    0.01

</div>

</div>

<div class="cell markdown" id="55xAIxVa3hpQ">

-   Tell us what groups you want to compare in the dataset
    -   **G1** (avg_years_of_schooling \| Entity = United States \|\|
        Switzerland \|\| Japan) vs. **G2** (avg_years_of_schooling \|
        Entity = Afghanistan \|\| Central African Republic \|\| Sierra
        Leone)

</div>

<div class="cell markdown" id="13PdL3ht3902">

-   Print first 5 records of each group, respectively.

</div>

<div class="cell code" execution_count="16"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
id="UNL0WXav3hLj" outputId="aa479f75-85d4-44bd-df60-b7ed7e257334">

``` python
## First 5 records of G1 (High-income countries)
(df[df['Entity'].isin(['United States', 'Switzerland', 'Japan'])]['avg_years_of_schooling']).head(5)
```

<div class="output execute_result" execution_count="16">

    3534    0.42
    3535    0.50
    3536    0.59
    3537    0.70
    3538    1.04
    Name: avg_years_of_schooling, dtype: float64

</div>

</div>

<div class="cell code" execution_count="19"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
id="dhe52HVB4T1O" outputId="22b989ac-4a8f-4019-d6e0-970194500ab1">

``` python
## First 5 records of G2 (Low-income countries)
(df[df['Entity'].isin(['Afghanistan', 'Central African Republic', 'Sierra Leone'])]['avg_years_of_schooling']).head(5)
```

<div class="output execute_result" execution_count="19">

    0    0.01
    1    0.01
    2    0.01
    3    0.01
    4    0.01
    Name: avg_years_of_schooling, dtype: float64

</div>

</div>

<div class="cell code" execution_count="22"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:295}"
id="zEgfWXaKGvNC" outputId="2728fe48-f368-4523-cb0c-adf167b72b7e">

``` python
## Any other data description and visualization you want to add.
import matplotlib.pyplot as plt

country_name = 'United States'
country = df[df['Entity'] == country_name]
y = country['avg_years_of_schooling']
x = country['Year']

plt.plot(x, y)
plt.title('Trend in Years of Schooling for {}'.format(country_name))
plt.xlabel('Year')
plt.ylabel('Average Years of Schooling')
plt.show()
## Open question, be flexible and no example can be provided.
```

<div class="output display_data">

![](4857f0253fd87c831e28b9c0747519d4c1781ee8.png)

</div>

</div>

<div class="cell markdown" id="nWKb_VkjXAjR">

To see the trend in the data on average years of schooling by country
and year, we can plot a line graph with the year on the x-axis and the
average years of schooling on the y-axis. This will allow us to
visualize how the average years of schooling have changed over time for
each country.

Additionally, we can calculate statistical measures such as the mean,
median, and standard deviation of the average years of schooling for
each country over the entire time period covered in the dataset. This
will allow us to quantify the trend in the data and provide a numerical
summary of the changes in average years of schooling over time.

We can also group the countries into different categories based on their
income level, geographic location, or other relevant factors, and
compare the trends in average years of schooling across different
groups. This will allow us to identify any patterns or differences in
the trend of education levels across different groups of countries.

</div>
