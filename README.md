# Best Foot Forward: An Analysis of Which Shoes Sell
a capstone project by H. Wiley Hill III

## Overview
The [SHOE DATASET](https://www.kaggle.com/datasets/mdwaquarazam/shoe-dataset), posted on Kaggle by an Indian teacher by the name of Waquar Azam, documents various men's shoes sold on Amazon, listing off their brands, prices, and descriptions, as well as how many people bought them and how they were rated.  With this information, it should be possible in theory to determine **which brands at what prices sell the most and get the highest ratings**.

## Files
* notebook_examine_data.ipynb -- A Jupyter notebook containing all my code for reading, analyzing, and processing the data this project was about.
* MEN_SHOES.csv -- The original dataset, exactly as downloaded from the link above.
* MEN_SHOES_BEST.csv -- A cleaned and truncated subset of the previous dataset, showcasing the best shoes in the dataset.
* README.md -- You are here!

## Methodology
### Preprocessing
The preprocessing step was the biggest and most important step.  The data was not ready for analysis as-is, so to prepare it I had to do the following:
* Delete rows with missing data (after deciding that they were a negligible part of the dataset).
* Convert numerical data represented as strings to integers, removing commas in order to do so.
* Rename the columns to be informative and consistent.
* Reposition one column that had been displaced during a previous fix.

I later returned to this step and made some more fixes to the data:
* Delete duplicate rows, dramatically shrinking the dataset.
* Convert the price from Indian rupees to U.S. dollars, and add a new column to hold the result.

### Exploratory Analysis
In order to understand the data, I queried and charted it in various ways, looking for patterns.  Notable steps in this process included:
* Sorting the data by the two dependent variables: rating and number sold.
* Grouping the data by shoe brand, and charting how the different brands fared in terms of average rating and total shoes sold.
* Going out on a limb and charting the length of the shoe description against rating.

Tables and scatter plots depicting the results of these queries can be found throughout the Jupyter notebook.

### Answering the Question
After the exploratory analysis, I returned to the original question.  Although many problems in data analysis require advanced machine learning techniques to tackle, this particular question was too simple and the cleaned dataset too small to warrant them, and so a few queries would suffice.  So I:
* Decided that the "best" shoes in terms of rating and number sold would be the top quartile in both categories.
* Queried the entries that fell into both of those top quartiles.  (If this produced too many or too few results, I would have adjusted the range accordingly.)
* Sorted them by rating (most important), and then by number sold (second most important).
* Wrote a script to print them in a convenient, easily readable format.
* Saved them to a new CSV file for further inspection.
