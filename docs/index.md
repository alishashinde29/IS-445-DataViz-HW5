# Homework 5 - Data Visualization
# IS-445-DataViz-HW5

## Dataset

This project uses the Illinois Building Inventory dataset, which contains information about state-owned buildings including their location, agency, square footage, construction year, and various usage description fields.  
The data was imported directly from the public dataset link using `pandas.read_csv()` in the analysis notebook.

---

## Plot 1 — Top Usage Descriptions by Total Square Footage

<p>

<iframe src="{{ 'building_usage_bar.html' | relative_url }}" width="900" height="450"></iframe>

### Description, encodings, color choices, transformations

The first visualization depicts the 10 usage description categories with the highest total building square footage from the dataset.  
The x-axis encodes the total square footage for each given category, as for the y-axis lists the usage descriptions sorted in descending order.  
I used a bar chart because it clearly shows comparisons between these categories.  
And before plotting, I removed rows missing values for “Square Footage” or “Usage Description”, grouped by “Usage Description”, summed the square footage, and selected the top ten categories.  
This aggregation helps reveal which types of buildings occupy the most physical space within the state inventory.


---

## Plot 2: UFO Sightings Over Time by Shape (Interactive)

<iframe src="{{ 'building_year_size_interaction.html' | relative_url }}" width="900" height="500"></iframe>

### Description, encodings, color choices, transformations

The second visualization scatter plot examines how the building size relates to construction year, with an interactive dropdown that filters the scatterplot by usage description.  
Each point shown represents a building of the university, with the x-axis showing the construction year and the y-axis showing the building’s square footage.  
Tooltips display additional details such as agency, location name, city, and square footage.

On the data side, I removed rows missing “Year Constructed”, “Square Footage”, or “Usage Description”, converted construction years into integers, and filtered out years before 1900 to remove errors and outliers.


---

## Interactivity

For interactivity, I created a dropdown menu using an Altair parameter bound to the “Usage Description” column.  
The plot updates dynamically through a filter expression that selects only buildings matching the chosen category.  
This interactivity reduces visual clutter and allows viewers to focus on trends within a single usage type, such as whether older buildings for that use tend to be larger or smaller.


---

## Links

- **The Data**  
  [Dataset Link](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv)

- **The Analysis Notebook**  
 - [The Analysis Notebook](https://github.com/alishashinde29/IS-445-DataViz-HW5/blob/main/WorkbookHW.ipynb)


