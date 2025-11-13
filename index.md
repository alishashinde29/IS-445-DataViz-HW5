# IS-445-DataViz-HW5


## Dataset

The assignment 5 uses the give Illinois Building Inventory dataset(option 1), which contains data about state-owned building inventory i.e. their location, square footage, construction year, agency, and various usage description fields.  
The data is imported directly from the public dataset link using `pandas.read_csv()`.
---

## Plot 1 — The Top Usage Descriptions by Total Square Footage(TSF)

<p>
<iframe src="{{ site.baseurl }}/building_usage_bar.html" width="700" height="450" frameborder="0"></iframe>
</p>

The first chart here shows the ten usage description categories with their highest total building square footage.  
The x-axis on this chart encodes the TSF for each given category, as for the y-axis, it lists the usage descriptions which is again here sorted in descending order.  
I used a bar chart because it clearly shows comparisons between categories.  
Before plotting, I removed rows missing values for “Square Footage” or “Usage Description”, grouped by “Usage Description”, summed the square footage, and selected the top ten categories.  
This aggregation helps me showcase which types of buildings occupy the most physical space within the state inventory.

---

## Plot 2 : Building Size vs Construction Year (Interactive)

<p>
<iframe src="{{ site.baseurl }}/building_year_size_interactive.html" width="750" height="450" frameborder="0"></iframe>
</p>

The second visualization examines how building size relates to construction year, with an interactive dropdown that filters the scatterplot by usage description.  
Here, each data-point represents a building, with the x-axis showcasing the construction year and the y-axis showcasing the building’s square footage.  
The tooltips display uses additional details such as location name, city, agency, and square footage.

On the data side, I removed rows missing “Year Constructed”, “Square Footage”, or “Usage Description”, converted construction years into integers, and filtered out years before 1900 to remove errors and outliers.

For interactivity, I created a dropdown menu using an Altair parameter bound to the “Usage Description” column.  
The plot updates dynamically through a filter expression that selects only buildings matching the chosen category.  
This interactivity reduces visual clutter and allows viewers to focus on trends within a single usage type — such as whether older buildings for that use tend to be larger or smaller.

---

## Links

- [The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/README.csv)  
- [The Analysis Notebook](https://github.com/alishashinde29/IS-445-DataViz-HW5/blob/main/WorkbookHW.ipynb)
