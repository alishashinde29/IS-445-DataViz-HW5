# IS-445-DataViz-HW5
---
layout: default
title: "Building Inventory Visualizations"
permalink: /building-inventory/
---

## Dataset

For this assignment I used the State of Illinois building inventory dataset.  
It contains information about public buildings, including the agency, location name, city, square footage, year constructed, and several usage description fields.  
I loaded the data directly from the provided URL using `pandas.read_csv` in my notebook.

---

## Plot 1 – Top Usage Descriptions by Total Square Footage

<p>
  <iframe src="/building_usage_bar.html" width="700" height="450" frameborder="0"></iframe>
</p>

This plot shows the top ten usage descriptions ranked by total building square footage.  
The x-axis encodes total square footage as a quantitative variable, and the y-axis encodes usage description as a nominal category.  
I used a bar mark because it makes it easy to compare total space across categories.  
Each bar is colored by usage description, but I turned off the legend since the category names already appear on the y-axis and the colors are mostly decorative.

On the data side, I first dropped rows with missing values for “Square Footage” or “Usage Description”.  
Then I grouped by “Usage Description”, summed the “Square Footage” column, sorted the results in descending order, and kept the ten largest categories.  
This aggregation highlights which types of buildings occupy the most physical space in the inventory and smooths out noise from individual buildings.

---

## Plot 2 – Building Size vs. Construction Year (Interactive)

<p>
  <iframe src="/building_year_size_interactive.html" width="750" height="450" frameborder="0"></iframe>
</p>

The second plot explores how building size relates to construction year for different usage descriptions.  
The x-axis encodes the year constructed as a quantitative variable, and the y-axis encodes square footage.  
Each point represents a single building.  
The color is based on the “Usage Description” field (although only one usage is shown at a time), and the tooltips display the location name, agency name, city, construction year, and square footage so the viewer can inspect individual buildings.

In the notebook, I dropped rows where “Square Footage”, “Usage Description”, or “Year Constructed” were missing.  
I converted “Year Constructed” to integers and kept only buildings from 1900 onwards to avoid obvious outliers or bad values.  
This cleaned table is used as the source for the scatter plot.

For interactivity, I created a dropdown menu bound to a parameter representing the chosen usage description.  
The chart uses this parameter in a filter expression so that only buildings whose “Usage Description” matches the current dropdown value are displayed.  
This interaction makes the visualization clearer because the full dataset has many different usage types; showing everything at once would create a dense cloud of points.  
By focusing on one usage at a time, it is easier to see whether buildings of that type tend to be older or newer and whether they are typically larger or smaller.

---

## Links

- [The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/README.csv)  
- [The Analysis Notebook](Workbook.ipynb.ipynb)