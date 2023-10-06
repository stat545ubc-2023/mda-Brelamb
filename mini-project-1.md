# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

1.  Load the packages below.

<!-- -->

    library(datateachr)
    library(tidyverse)

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.3     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

1.  Make a repository in the <https://github.com/stat545ubc-2023>
    Organization. You can do this by following the steps found on canvas
    in the entry called [MDA: Create a
    repository](https://canvas.ubc.ca/courses/126199/pages/mda-create-a-repository).
    One completed, your repository should automatically be listed as
    part of the stat545ubc-2023 Organization.

# Instructions

## For Both Milestones

-   Each milestone has explicit tasks. Tasks that are more challenging
    will often be allocated more points.

-   Each milestone will be also graded for reproducibility, cleanliness,
    and coherence of the overall Github submission.

-   While the two milestones will be submitted as independent
    deliverables, the analysis itself is a continuum - think of it as
    two chapters to a story. Each chapter, or in this case, portion of
    your analysis, should be easily followed through by someone
    unfamiliar with the content.
    [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/)
    is a good resource for what constitutes “good code”. Learning good
    coding practices early in your career will save you hassle later on!

-   The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and
6 for overall reproducibility, cleanliness, and coherence of the Github
submission.

# Learning Objectives

By the end of this milestone, you should:

-   Become familiar with your dataset of choosing
-   Select 4 questions that you would like to answer with your data
-   Generate a reproducible and clear report using R Markdown
-   Become familiar with manipulating and summarizing your data in
    tibbles using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

-   *apt\_buildings*: Acquired courtesy of The City of Toronto’s Open
    Data Portal. It currently has 3455 rows and 37 columns.

-   *building\_permits*: Acquired courtesy of The City of Vancouver’s
    Open Data Portal. It currently has 20680 rows and 14 columns.

-   *cancer\_sample*: Acquired courtesy of UCI Machine Learning
    Repository. It currently has 569 rows and 32 columns.

-   *flow\_sample*: Acquired courtesy of The Government of Canada’s
    Historical Hydrometric Database. It currently has 218 rows and 7
    columns.

-   *parking\_meters*: Acquired courtesy of The City of Vancouver’s Open
    Data Portal. It currently has 10032 rows and 22 columns.

-   *steam\_games*: Acquired courtesy of Kaggle. It currently has 40833
    rows and 21 columns.

-   *vancouver\_trees*: Acquired courtesy of The City of Vancouver’s
    Open Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

-   We hope that this project will serve as practice for carrying our
    your own *independent* data analysis. Remember to comment your code,
    be explicit about what you are doing, and write notes in this
    markdown document when you feel that context is required. As you
    advance in the project, prompts and hints to do this will be
    diminished - it’ll be up to you!

-   Before choosing a dataset, you should always keep in mind **your
    goal**, or in other ways, *what you wish to achieve with this data*.
    This mini data-analysis project focuses on *data wrangling*,
    *tidying*, and *visualization*. In short, it’s a way for you to get
    your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr`
package, choose **4** that appeal to you based on their description.
Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

<!-------------------------- Start your work below ---------------------------->

    #1: CHOICE_1 *vancouver_trees*
    #2: CHOICE_2 *building_permits*
    #3: CHOICE_3 *parking_meters*
    #4: CHOICE_4 *apt_buildings*

<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to
*explore* the datasets. Use your knowledge of dplyr to find out at least
*3* attributes about each of these datasets (an attribute is something
such as number of rows, variables, class type…). The goal here is to
have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

    ### EXPLORE HERE ###

    ## CHOICE 1 - *vancouver_trees*

    # To look at the vancouver_trees data set I will use the glimspe() function.
    glimpse(vancouver_trees)

    ## Rows: 146,611
    ## Columns: 20
    ## $ tree_id            <dbl> 149556, 149563, 149579, 149590, 149604, 149616, 149…
    ## $ civic_number       <dbl> 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 7…
    ## $ std_street         <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ genus_name         <chr> "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "…
    ## $ species_name       <chr> "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "C…
    ## $ cultivar_name      <chr> "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICL…
    ## $ common_name        <chr> "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBE…
    ## $ assigned           <chr> "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "…
    ## $ root_barrier       <chr> "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "…
    ## $ plant_area         <chr> "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "…
    ## $ on_street_block    <dbl> 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 7…
    ## $ on_street          <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ neighbourhood_name <chr> "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "…
    ## $ street_side_name   <chr> "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD…
    ## $ height_range_id    <dbl> 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, …
    ## $ diameter           <dbl> 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00…
    ## $ curb               <chr> "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "…
    ## $ date_planted       <date> 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 19…
    ## $ longitude          <dbl> -123.1161, -123.1147, -123.0846, -123.0870, -123.08…
    ## $ latitude           <dbl> 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 4…

    # After using the glimpse function I am curious to see number of unique trees types (by common name) included in the data set.
    dim(distinct(vancouver_trees, common_name))

    ## [1] 634   1

    # Now that I know how many there are, I would like to get an idea of the common names of the trees included in this data set.
    distinct(vancouver_trees, common_name)

    ## # A tibble: 634 × 1
    ##    common_name          
    ##    <chr>                
    ##  1 BRANDON ELM          
    ##  2 JAPANESE ZELKOVA     
    ##  3 JAPANESE SNOWBELL    
    ##  4 AUTUMN APPLAUSE ASH  
    ##  5 HEDGE MAPLE          
    ##  6 CHANTICLEER PEAR     
    ##  7 COLUMNAR NORWAY MAPLE
    ##  8 CRIMEAN LINDEN       
    ##  9 ROSE OF SHARON       
    ## 10 RAYWOOD ASH          
    ## # ℹ 624 more rows

    ## CHOICE 2 - *building_permits*

    ### To get a quick idea of what the columns look like in building_permits I will use the glimpse() function 
    glimpse(building_permits)

    ## Rows: 20,680
    ## Columns: 14
    ## $ permit_number               <chr> "BP-2016-02248", "BU468090", "DB-2016-0445…
    ## $ issue_date                  <date> 2017-02-01, 2017-02-01, 2017-02-01, 2017-…
    ## $ project_value               <dbl> 0, 0, 35000, 15000, 181178, 0, 15000, 0, 6…
    ## $ type_of_work                <chr> "Salvage and Abatement", "New Building", "…
    ## $ address                     <chr> "4378 W 9TH AVENUE, Vancouver, BC V6R 2C7"…
    ## $ project_description         <chr> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA…
    ## $ building_contractor         <chr> NA, NA, NA, "Mercury Contracting Ltd", "08…
    ## $ building_contractor_address <chr> NA, NA, NA, "88 W PENDER ST  \r\nUnit 2069…
    ## $ applicant                   <chr> "Raffaele & Associates DBA: Raffaele and A…
    ## $ applicant_address           <chr> "2642 East Hastings\r\nVancouver, BC  V5K …
    ## $ property_use                <chr> "Dwelling Uses", "Dwelling Uses", "Dwellin…
    ## $ specific_use_category       <chr> "One-Family Dwelling", "Multiple Dwelling"…
    ## $ year                        <dbl> 2017, 2017, 2017, 2017, 2017, 2017, 2017, …
    ## $ bi_id                       <dbl> 524, 535, 539, 541, 543, 546, 547, 548, 54…

    ### I want to find out the number of times there was a building permit application submitted for a "One-Family Dwelling". I do this by using the dplyr() function filter() to filter through the data and count the number of variables labeled "One-Family Dwelling" in the specific_use_category
    dim(filter(building_permits, specific_use_category == "One-Family Dwelling"))

    ## [1] 4571   14

    ### I want to find out the date of the most recent data on building permits being issued in the city of vancouver. To do this I use the dplyr() function arrange(). The arrange() function would typically order the selected column in ascending order but I will also apply the desc() function to the issue_date column, this orders the data so that the most recent date of permit issued is first.
    arrange(building_permits, desc(issue_date))

    ## # A tibble: 20,680 × 14
    ##    permit_number issue_date project_value type_of_work                address   
    ##    <chr>         <date>             <dbl> <chr>                       <chr>     
    ##  1 BP-2019-01569 2020-04-29        15000  Demolition / Deconstruction 3272 W 27…
    ##  2 BP-2019-03180 2020-04-29       250000  Addition / Alteration       3070 W 49…
    ##  3 BP-2019-05369 2020-04-29        15000  Demolition / Deconstruction 4618 W 12…
    ##  4 BP-2020-01078 2020-04-29        20000  Addition / Alteration       1750 E 10…
    ##  5 BP-2020-01213 2020-04-29        31500  Addition / Alteration       1545 W 14…
    ##  6 DB-2019-04360 2020-04-29         2400  Addition / Alteration       4368 WIND…
    ##  7 DB-2019-05041 2020-04-29      1098168. New Building                6149 FREM…
    ##  8 DB-2019-05447 2020-04-29        50000  Addition / Alteration       1854 WILL…
    ##  9 DB-2020-01052 2020-04-29        18000  Addition / Alteration       237 W 26T…
    ## 10 BP-2019-03463 2020-04-29        15000  Demolition / Deconstruction 2735 W 38…
    ## # ℹ 20,670 more rows
    ## # ℹ 9 more variables: project_description <chr>, building_contractor <chr>,
    ## #   building_contractor_address <chr>, applicant <chr>,
    ## #   applicant_address <chr>, property_use <chr>, specific_use_category <chr>,
    ## #   year <dbl>, bi_id <dbl>

    ## CHOICE 3 - *parking_meters*

    ###I am using the glimpse function to view the data. 
    glimpse(parking_meters)

    ## Rows: 10,032
    ## Columns: 22
    ## $ meter_head     <chr> "Twin", "Pay Station", "Twin", "Single", "Twin", "Twin"…
    ## $ r_mf_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_mf_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ r_sa_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_sa_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ r_su_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_su_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ rate_misc      <chr> NA, "$ .50", NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA…
    ## $ time_in_effect <chr> "METER IN EFFECT: 9:00 AM TO 10:00 PM", "METER IN EFFEC…
    ## $ t_mf_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_mf_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ t_sa_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_sa_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ t_su_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_su_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ time_misc      <chr> NA, "No Time Limit", NA, NA, NA, NA, NA, NA, NA, NA, NA…
    ## $ credit_card    <chr> "No", "Yes", "No", "No", "No", "No", "No", "No", "No", …
    ## $ pay_phone      <chr> "66890", "59916", "57042", "57159", "51104", "60868", "…
    ## $ longitude      <dbl> -123.1289, -123.0982, -123.1013, -123.1862, -123.1278, …
    ## $ latitude       <dbl> 49.28690, 49.27215, 49.25468, 49.26341, 49.26354, 49.27…
    ## $ geo_local_area <chr> "West End", "Strathcona", "Riley Park", "West Point Gre…
    ## $ meter_id       <chr> "670805", "471405", "C80145", "D03704", "301023", "5913…

    ### Looking at the tibble that the glimpse() function produced I would like to know more about the different types of meter heads that this data set contains information on. To do this I use the distinct() dplyr function. This function presents the unique types of parking meter heads in a tibble.
    distinct(parking_meters, meter_head)

    ## # A tibble: 7 × 1
    ##   meter_head         
    ##   <chr>              
    ## 1 Twin               
    ## 2 Pay Station        
    ## 3 Single             
    ## 4 Single / Disability
    ## 5 Single Motorbike   
    ## 6 Twin Bay Single    
    ## 7 Twin / Disability

    ### I now know that there are seven different types of meter heads we have data on in this data set. 
    ### I would like to look at information that is specifically for the meter head labeled "twin".
    filter(parking_meters, meter_head == "Twin") 

    ## # A tibble: 8,614 × 22
    ##    meter_head r_mf_9a_6p r_mf_6p_10 r_sa_9a_6p r_sa_6p_10 r_su_9a_6p r_su_6p_10
    ##    <chr>      <chr>      <chr>      <chr>      <chr>      <chr>      <chr>     
    ##  1 Twin       $2.00      $4.00      $2.00      $4.00      $2.00      $4.00     
    ##  2 Twin       $1.00      $1.00      $1.00      $1.00      $1.00      $1.00     
    ##  3 Twin       $2.00      $1.00      $2.00      $1.00      $2.00      $1.00     
    ##  4 Twin       $2.00      $1.00      $2.00      $1.00      $2.00      $1.00     
    ##  5 Twin       $2.00      $3.00      $2.00      $3.00      $2.00      $3.00     
    ##  6 Twin       $4.00      $1.00      $4.00      $1.00      $4.00      $1.00     
    ##  7 Twin       $2.00      $1.00      $2.00      $1.00      $2.00      $1.00     
    ##  8 Twin       $2.00      $1.00      $2.00      $1.00      $2.00      $1.00     
    ##  9 Twin       $2.00      $1.00      $2.00      $1.00      $2.00      $1.00     
    ## 10 Twin       $2.00      $4.00      $2.00      $4.00      $2.00      $4.00     
    ## # ℹ 8,604 more rows
    ## # ℹ 15 more variables: rate_misc <chr>, time_in_effect <chr>, t_mf_9a_6p <chr>,
    ## #   t_mf_6p_10 <chr>, t_sa_9a_6p <chr>, t_sa_6p_10 <chr>, t_su_9a_6p <chr>,
    ## #   t_su_6p_10 <chr>, time_misc <chr>, credit_card <chr>, pay_phone <chr>,
    ## #   longitude <dbl>, latitude <dbl>, geo_local_area <chr>, meter_id <chr>

    ## CHOICE 4 - *apt_buildings*

    ### First I will use the dplyr function glimpse() to view the data set titled apt_buildings
    glimpse(apt_buildings)

    ## Rows: 3,455
    ## Columns: 37
    ## $ id                               <dbl> 10359, 10360, 10361, 10362, 10363, 10…
    ## $ air_conditioning                 <chr> "NONE", "NONE", "NONE", "NONE", "NONE…
    ## $ amenities                        <chr> "Outdoor rec facilities", "Outdoor po…
    ## $ balconies                        <chr> "YES", "YES", "YES", "YES", "NO", "NO…
    ## $ barrier_free_accessibilty_entr   <chr> "YES", "NO", "NO", "YES", "NO", "NO",…
    ## $ bike_parking                     <chr> "0 indoor parking spots and 10 outdoo…
    ## $ exterior_fire_escape             <chr> "NO", "NO", "NO", "YES", "NO", NA, "N…
    ## $ fire_alarm                       <chr> "YES", "YES", "YES", "YES", "YES", "Y…
    ## $ garbage_chutes                   <chr> "YES", "YES", "NO", "NO", "NO", "NO",…
    ## $ heating_type                     <chr> "HOT WATER", "HOT WATER", "HOT WATER"…
    ## $ intercom                         <chr> "YES", "YES", "YES", "YES", "YES", "Y…
    ## $ laundry_room                     <chr> "YES", "YES", "YES", "YES", "YES", "Y…
    ## $ locker_or_storage_room           <chr> "NO", "YES", "YES", "YES", "NO", "YES…
    ## $ no_of_elevators                  <dbl> 3, 3, 0, 1, 0, 0, 0, 2, 4, 2, 0, 2, 2…
    ## $ parking_type                     <chr> "Underground Garage , Garage accessib…
    ## $ pets_allowed                     <chr> "YES", "YES", "YES", "YES", "YES", "Y…
    ## $ prop_management_company_name     <chr> NA, "SCHICKEDANZ BROS. PROPERTIES", N…
    ## $ property_type                    <chr> "PRIVATE", "PRIVATE", "PRIVATE", "PRI…
    ## $ rsn                              <dbl> 4154812, 4154815, 4155295, 4155309, 4…
    ## $ separate_gas_meters              <chr> "NO", "NO", "NO", "NO", "NO", "NO", "…
    ## $ separate_hydro_meters            <chr> "YES", "YES", "YES", "YES", "YES", "Y…
    ## $ separate_water_meters            <chr> "NO", "NO", "NO", "NO", "NO", "NO", "…
    ## $ site_address                     <chr> "65  FOREST MANOR RD", "70  CLIPPER R…
    ## $ sprinkler_system                 <chr> "YES", "YES", "NO", "YES", "NO", "NO"…
    ## $ visitor_parking                  <chr> "PAID", "FREE", "UNAVAILABLE", "UNAVA…
    ## $ ward                             <chr> "17", "17", "03", "03", "02", "02", "…
    ## $ window_type                      <chr> "DOUBLE PANE", "DOUBLE PANE", "DOUBLE…
    ## $ year_built                       <dbl> 1967, 1970, 1927, 1959, 1943, 1952, 1…
    ## $ year_registered                  <dbl> 2017, 2017, 2017, 2017, 2017, NA, 201…
    ## $ no_of_storeys                    <dbl> 17, 14, 4, 5, 4, 4, 4, 7, 32, 4, 4, 7…
    ## $ emergency_power                  <chr> "NO", "YES", "NO", "NO", "NO", "NO", …
    ## $ `non-smoking_building`           <chr> "YES", "NO", "YES", "YES", "YES", "NO…
    ## $ no_of_units                      <dbl> 218, 206, 34, 42, 25, 34, 14, 105, 57…
    ## $ no_of_accessible_parking_spaces  <dbl> 8, 10, 20, 42, 12, 0, 5, 1, 1, 6, 12,…
    ## $ facilities_available             <chr> "Recycling bins", "Green Bin / Organi…
    ## $ cooling_room                     <chr> "NO", "NO", "NO", "NO", "NO", "NO", "…
    ## $ no_barrier_free_accessible_units <dbl> 2, 0, 0, 42, 0, NA, 14, 0, 0, 1, 25, …

    ###Using the distinct() function I can check the different types of facilities available in the apartment buildings.
    distinct(apt_buildings, facilities_available)

    ## # A tibble: 4 × 1
    ##   facilities_available
    ##   <chr>               
    ## 1 Recycling bins      
    ## 2 Green Bin / Organics
    ## 3 Unknown             
    ## 4 Not Available

    ### Now I want to check what the most recent year built is in the data set, to do this I use the arrange() function and order the year_built column in descending order.
    arrange(apt_buildings, desc(year_built)) %>%
      select(year_built)

    ## # A tibble: 3,455 × 1
    ##    year_built
    ##         <dbl>
    ##  1       2019
    ##  2       2019
    ##  3       2019
    ##  4       2019
    ##  5       2019
    ##  6       2018
    ##  7       2018
    ##  8       2018
    ##  9       2018
    ## 10       2017
    ## # ℹ 3,445 more rows

<!----------------------------------------------------------------------------->

1.3 **(1 point)** Now that you’ve explored the 4 datasets that you were
initially most interested in, let’s narrow it down to 1. What lead you
to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->

    ##Data Set Choice & Explanation: 

    ### Of the 4 data sets I chose to explore, I found that the *vancouver_trees* data created the most questions that I would like to answer. I appreciate that this data set has an array of different types of data pertaining to trees in Vancouver - such as date/ year planted and location co-ordinates. Having the common name, along with the genus and species name is also very helpful. A lot of the data in this set allows you to select from more broad terms to very specific. 

<!----------------------------------------------------------------------------->

1.4 **(2 points)** Time for a final decision! Going back to the
beginning, it’s important to have an *end goal* in mind. For example, if
I had chosen the `titanic` dataset for my project, I might’ve wanted to
explore the relationship between survival and other variables. Try to
think of 1 research question that you would want to answer with your
dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->

    # I would like to explore the relationship between different tree species and the locations in which they are found in abundance. 

<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate. If
you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to
dive deeper into your data. All datasets are different and therefore,
not all of these tasks may make sense for your data - which is why you
should only answer *4*.

Make sure that you’re using dplyr and ggplot2 rather than base R for
this task. Outside of this project, you may find that you prefer using
base R functions for certain tasks, and that’s just fine! But part of
this project is for you to practice the tools we learned in class, which
is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.
2.  Create a new variable based on other variables in your data (only if
    it makes sense)
3.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?
4.  Explore the relationship between 2 variables in a plot.
5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…
6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!
7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

2.2 **(4 points)** For each of the 4 exercises that you complete,
provide a *brief explanation* of why you chose that exercise in relation
to your data (in other words, why does it make sense to do that?), and
sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

## Question 2:

    lilac <- filter(vancouver_trees, common_name == "TREE LILAC")
    westlilac <- filter(lilac, neighbourhood_name == "WEST END")
    distinct(westlilac, std_street)

    ## # A tibble: 4 × 1
    ##   std_street  
    ##   <chr>       
    ## 1 ALBERNI ST  
    ## 2 W GEORGIA ST
    ## 3 NICOLA ST   
    ## 4 BROUGHTON ST

## Why I answered question 2:

## I wanted to see how many Lilac trees there are in the data set in a given neighborhood of vancouver and which streets they are located on. To do this I had to create a new variable filtered by trees with the common name Lilac in the data set. I then created a second new variable which I filtered through the old variable ‘lilac’ and only stored lilac trees in the west end neighborhood (in a new variable called ‘westlilac’)

## Question 5:

    pru <- filter(vancouver_trees, genus_name == "PRUNUS" )
    distinct(pru, common_name)

    ## # A tibble: 51 × 1
    ##    common_name              
    ##    <chr>                    
    ##  1 KWANZAN FLOWERING CHERRY 
    ##  2 NIGHT PURPLE LEAF PLUM   
    ##  3 AKEBONO FLOWERING CHERRY 
    ##  4 SCHUBERT CHOKECHERRY     
    ##  5 PISSARD PLUM             
    ##  6 PINK PERFECTION CHERRY   
    ##  7 JAPANESE FLOWERING CHERRY
    ##  8 HIGAN CHERRY             
    ##  9 MAZZARD CHERRY           
    ## 10 RANCHO SARGENT CHERRY    
    ## # ℹ 41 more rows

    pru %>%
      group_by(neighbourhood_name) %>%
    summarise(n = n())

    ## # A tibble: 22 × 2
    ##    neighbourhood_name           n
    ##    <chr>                    <int>
    ##  1 ARBUTUS-RIDGE             1514
    ##  2 DOWNTOWN                   171
    ##  3 DUNBAR-SOUTHLANDS         2554
    ##  4 FAIRVIEW                   635
    ##  5 GRANDVIEW-WOODLAND        1121
    ##  6 HASTINGS-SUNRISE          1932
    ##  7 KENSINGTON-CEDAR COTTAGE  1851
    ##  8 KERRISDALE                1593
    ##  9 KILLARNEY                 1143
    ## 10 KITSILANO                 1194
    ## # ℹ 12 more rows

    distinct(vancouver_trees, diameter) %>%
      select(diameter) %>%
      arrange(desc(diameter))

    ## # A tibble: 520 × 1
    ##    diameter
    ##       <dbl>
    ##  1      435
    ##  2      317
    ##  3      305
    ##  4      182
    ##  5      161
    ##  6      156
    ##  7      151
    ##  8      144
    ##  9      141
    ## 10      131
    ## # ℹ 510 more rows

    filter(pru, diameter > 10)

    ## # A tibble: 19,252 × 20
    ##    tree_id civic_number std_street       genus_name species_name cultivar_name  
    ##      <dbl>        <dbl> <chr>            <chr>      <chr>        <chr>          
    ##  1  155243          501 E KING EDWARD AV PRUNUS     SERRULATA    KWANZAN        
    ##  2  155335          501 E KING EDWARD AV PRUNUS     SERRULATA    KWANZAN        
    ##  3  155971         1795 E 49TH AV        PRUNUS     CERASIFERA   ATROPURPUREUM  
    ##  4  156025         8023 LAUREL ST        PRUNUS     SERRULATA    KWANZAN        
    ##  5  156255          118 W KING EDWARD AV PRUNUS     SERRULATA    KWANZAN        
    ##  6  157379         3350 DUMFRIES ST      PRUNUS     SERRULATA    PINK PERFECTION
    ##  7  157433         4255 LAUREL ST        PRUNUS     CERASIFERA   ATROPURPUREUM  
    ##  8  157434         4255 LAUREL ST        PRUNUS     CERASIFERA   ATROPURPUREUM  
    ##  9  157482         1330 W 8TH AV         PRUNUS     SERRULATA    KWANZAN        
    ## 10  157503          607 W 29TH AV        PRUNUS     SERRULATA    <NA>           
    ## # ℹ 19,242 more rows
    ## # ℹ 14 more variables: common_name <chr>, assigned <chr>, root_barrier <chr>,
    ## #   plant_area <chr>, on_street_block <dbl>, on_street <chr>,
    ## #   neighbourhood_name <chr>, street_side_name <chr>, height_range_id <dbl>,
    ## #   diameter <dbl>, curb <chr>, date_planted <date>, longitude <dbl>,
    ## #   latitude <dbl>

    filter(pru, diameter > 50)

    ## # A tibble: 10 × 20
    ##    tree_id civic_number std_street genus_name species_name cultivar_name
    ##      <dbl>        <dbl> <chr>      <chr>      <chr>        <chr>        
    ##  1   23759          554 W 22ND AV  PRUNUS     SERRULATA    KWANZAN      
    ##  2   43912         1026 W 48TH AV  PRUNUS     SERRULATA    KWANZAN      
    ##  3  128151         1011 E 59TH AV  PRUNUS     CERASIFERA   ATROPURPUREUM
    ##  4  229699         2138 CHARLES ST PRUNUS     SERRULATA    KWANZAN      
    ##  5   50028         1388 W 58TH AV  PRUNUS     CERASIFERA   ATROPURPUREUM
    ##  6   26360         3662 E 25TH AV  PRUNUS     X YEDOENSIS  AKEBONO      
    ##  7   71403         5388 CYPRESS ST PRUNUS     CERASIFERA   ATROPURPUREUM
    ##  8  121759         7707 YUKON ST   PRUNUS     X YEDOENSIS  AKEBONO      
    ##  9  193492         5507 FLEMING ST PRUNUS     CERASIFERA   ATROPURPUREUM
    ## 10   22500          102 W 21ST AV  PRUNUS     LUSITANICA   <NA>         
    ## # ℹ 14 more variables: common_name <chr>, assigned <chr>, root_barrier <chr>,
    ## #   plant_area <chr>, on_street_block <dbl>, on_street <chr>,
    ## #   neighbourhood_name <chr>, street_side_name <chr>, height_range_id <dbl>,
    ## #   diameter <dbl>, curb <chr>, date_planted <date>, longitude <dbl>,
    ## #   latitude <dbl>

## Why I answered question 5:

## I would like to eventually zone in on the cherry trees in this data set, for now I thought I would filter for their genus. I did this by using the dplyr filter() function to search through the column genus\_name for the genus “PRUNUS”.

# After doing so, I thought I would check to see that there are cherry trees in the data set and what their common names are using the distinct() fucntion.

\#Finally to make sure there is an adequate amount of data for the
different neighborhoods I though that I would check the number of trees
in the genus “PRUNUS” by neighborhood.

## Question 1:

    pru %>%
      filter(diameter < 50) %>%
    ggplot(aes (x = diameter)) + 
      geom_histogram(binwidth = 6) 

![](mini-project-1_files/figure-markdown_strict/unnamed-chunk-8-1.png)
\## Why I answered question 1:

### Histograms are a nice way to look at the distribution of a numeric variable, I was curious after filtering for the diameters of trees in the genus prunus in question 5, what the distribution of the variable diameter looks like for the genus prunus under 50 (since 0-50 seems to be where majority of the data points lie).

## Question 7:

    dt_tib <- as_tibble(pru) %>%
    filter(neighbourhood_name == "DOWNTOWN") %>%
      select(date_planted, common_name, neighbourhood_name)

    dt_tib

    ## # A tibble: 171 × 3
    ##    date_planted common_name              neighbourhood_name
    ##    <date>       <chr>                    <chr>             
    ##  1 1995-03-21   RANCHO SARGENT CHERRY    DOWNTOWN          
    ##  2 1995-04-28   RANCHO SARGENT CHERRY    DOWNTOWN          
    ##  3 NA           KWANZAN FLOWERING CHERRY DOWNTOWN          
    ##  4 2008-03-17   RANCHO SARGENT CHERRY    DOWNTOWN          
    ##  5 NA           KWANZAN FLOWERING CHERRY DOWNTOWN          
    ##  6 2011-03-02   RANCHO SARGENT CHERRY    DOWNTOWN          
    ##  7 2012-04-13   RANCHO SARGENT CHERRY    DOWNTOWN          
    ##  8 2012-04-13   RANCHO SARGENT CHERRY    DOWNTOWN          
    ##  9 NA           KWANZAN FLOWERING CHERRY DOWNTOWN          
    ## 10 2012-04-13   RANCHO SARGENT CHERRY    DOWNTOWN          
    ## # ℹ 161 more rows

## Why I answered question 7:

### I wanted to put the trees in genus ‘prunus’ into a new tibble that only showed the ones located in the Downtown neighborhood. I also wanted the columns date\_planted and common\_name, so that I can further use this data to find out how many trees there is no (or <NA>) tree planting date for in this area. This tibble give me options to further explore the genus ‘prunus’ trees in the neighborhood of downtown.

### To do this I created a new tibble with this information and named it dt\_tib.

    <!----------------------------------------------------------------------------->

    # Task 3: Choose research questions 

    **(4 points)** So far, you have chosen a dataset and gotten familiar with it through exploring the data. You have also brainstormed one research question that interested you (Task 1.4).  Now it's time to pick 4 research questions that you would like to explore in Milestone 2! Write the 4 questions and any additional comments below. 

    <!--- *****START HERE***** --->

    ```r
    ### Four Research Question - For Future Exploration:

    # While looking through the vancouver_trees data set many questions crossed my mind, below I have managed to narrow my questions down to four that I hope to answer in the future:

    ##Question 1: How many cherry trees are there vancouver west and vancouver east?

    ##Question 2: Which neighborhood has the highest density of each of the cherry tree species? 

    ##Question 3: Is there a relationship between the location of the cherry trees and their height?

    ##Question 4: Is there a geographical area of vancouver where the city planted more cherry trees? If so, does it differ by decade? 

<!----------------------------->

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1
point deduction if most code runs without error, and 2 points deduction
if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

-   In a sentence or two, explains what this repository is, so that
    future-you or someone else stumbling on your repository can be
    oriented to the repository.
-   In a sentence or two (or more??), briefly explains how to engage
    with the repository. You can assume the person reading knows the
    material from STAT 545A. Basically, if a visitor to your repository
    wants to explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README
files in other projects, you’ll wonder how you ever got by without them!
They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

-   All Rmd files have been `knit`ted to their output md files.
-   All knitted md files are viewable without errors on Github. Examples
    of errors: Missing plots, “Sorry about that, but we can’t show files
    that are this big right now” messages, error messages from broken R
    code
-   All of these output files are up-to-date – that is, they haven’t
    fallen behind after the source (Rmd) files have been updated.
-   There should be no relic output files. For example, if you were
    knitting an Rmd to html, but then changed the output to be only a
    markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point
deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files,
and re-knit each milestone’s Rmd file, so that everything is up to date
and relevant. Then, after your final commit and push to Github, CHECK on
Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You’ve tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
