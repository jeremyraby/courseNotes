# How to Use Tableau Public

[Tableau Tutorial](https://www.javatpoint.com/tableau)

## Definitions

*Alias*: Alias is an alternative that you can assign to a dimension member, to a measurement part or a field.

*Bin*: Bin is a user-defined group of measures in the data source.

*Blue field*: Discrete, countable, indivisible data. People, integers, countries. Generally adds a header to the view. 1 header per field.
- Some data could be either blue or green (discrete or continuous) depending on context.
  - Right click to select Dimension, Attribute, Measure

*Bookmark*: A .tbm document in the bookmarks folder in the Tableau repository that contains a single worksheet. It helps in improving data analysis. Unlike, web browser bookmarks, .tbm files are a compatible way to display various studies quickly.

*Calculated field*: Calculated field is a new field that the user creates derived files by using a formula to modify the existing fields in your data source. It is used to make your work simple and easy.

*Column shelf*: Column shelf is on the top of the workbook. It is used to create the Columns of a data table. The Column shelf provides any numbers of measures and dimensions. When you placed a dimension on the Columns shelf, then Tableau creates headers for the members of that dimension. And when you place a measure on the Columns shelf, Tableau creates quantitative axes for that particular measure.

*Crosstab*: Crosstab is used for a text table view. It uses various text tables to display the numbers associated with dimension members.

*Dashboard*: The dashboard is a combination of several views that are arranged on a single page. In Tableau, dashboards are used to observe and compare a variety of data together, and also it allows interacting with other worksheets.

*Data Pane*: The data pane is on the left side of the workbook displays the fields of the data sources to which Tableau is connected. The fields are further divided into measures and dimensions. The data pane also reflects custom fields such as groups, binned fields, calculations, and many more. You can build views of your data by dragging fields from the data pane onto the various shelves, which is a part of every worksheet.

*Data Source Page*: Data Source is a page where you can set up your data source. This data source page generally consists of four main areas ? join area, left pane, a preview area, and metadata area.

*Dimension*: Qualitative data.

*Extract*: An extract is a saved subset of a data source which is used to improve performance and study offline. The users can create an extract by defining limits and filters that contain the data which you want in the extract.

*Filters Shelf*: Filter shelf is located on the left side of the workbook. Filters shelf is used to exclude the data from a view by filtering it using both dimensions and measures.

*Format Pane*: The Format pane is on the left side of the workbook, and it contains various formatting settings. It controls the entire view of the worksheet, as well as the individual fields in the view.

*Green field*: Continuous, measurable, divisible data. Heights, weights, lengths. Generally adds an axis to the view. 1 axis per field. Placing 1 green field each on the row and column shelf results in a scatterplot with only 1 data point (the sum of the two fields) - break it down by adding blue fields to the marks shelf.
- Tableau *must* aggregate continuous data *before* it will be visualized
  - May be required to determine *how* you want it aggregated before it will populate in the View
- Some data could be either blue or green (discrete or continuous) depending on context.
  - Right click to select Dimension, Attribute, Measure

*Level of Detail expression (LOD)*: The level of detail Expression is a syntax that supports the combination of various dimensions other than the view level. With the help of detail expressions, one can attach multiple dimensions with an aggregate expression.

*Marks*: Marks is a part of the view that visually represents one or more rows in a data source. It can be a line, square, or bar. You can control and alter the size, type, and color of marks.

*Marks Card*: Marks card is on the left side of the worksheet. The user can drag fields to the control mark properties such as color, type, shape, size, label, detail, and tooltip. Refers to how data are displayed in a viz. Data are displayed as "marks."

*Measure*: Quantitative data.

*Pages Shelf*: Page shelf is on the left side of the view. With the help of the page shelf, you can split a view into a sequence of pages based on the values and members in a continuous or discrete field. Adding a field with the pages shelf is similar to adding a field in rows shelf. For each new row, a new page is created.

*Rows shelf*: Row shelf is on the top of the workbook. It is used to create the rows of a data table. The Row shelf provides any numbers of measures and dimensions. When you placed a dimension on the Rows shelf, then Tableau creates headers for the members of that dimension. And when you place a measure on the Rows shelf, Tableau creates quantitative axes for that particular measure.

*Shelves*: The shelves are named areas that are located on the top and left of the view. You can build views by placing fields onto the shelves. Some shelves are only available when you select a particular mark type. For example, The Shape shelf is only open when you choose the specific Shape mark type.

*Workbook*: A workbook is a file with .twb extension that holds one or more worksheets as well as dashboards and stories.

*Worksheet*: The worksheet is a collection of sheets. It's a place where you build views of your data by dragging various fields onto the shelves.

[Menu descriptions can be found here](https://www.javatpoint.com/tableau-desktop-workspace)

[Annotated desktop menus](https://github.com/jeremyraby/courseNotes/blob/main/tableau/desktopFeatures1.jpg)

[Annotated desktop view](https://github.com/jeremyraby/courseNotes/blob/main/tableau/desktopFeatures2.jpg)

## Connecting to Data

Can connect to Excel, text (CSV, TSV), PDF, JSON files and even local databases

For PDFs
- Must have a good table structure
- Follow the dialog box prompts
  - Can search all pages, a single page, or a range of pages
- Can make a cohesive table from a table that spans multiple pages
- Not foolproof, but pretty good
  - and cool as shit!

### Cleaning Data

Tableau can automatically clean up data by checking the Data Interpreter box on the Data Source page.

You can split columns by right-clicking the field name on the Data Source page and following the dialog box prompts. Can be either just "Split" or a "Custom Split".

### Joining Tables

#### Same Field Names

After selecting the data source, the tables (worksheets, if using an Excel file) will appear in the left pane. Drag them to the center ("Drag files here") and Tableau will automatically make connections between the tables (they share common columns). [Here's a pic](https://github.com/jeremyraby/courseNotes/blob/main/tableau/joiningTables.jpg)

#### Different Field Names

If the tables have differing column names, Tableau will show a dashed line between the tables with a red yield sign. You can edit the connection in the lower left relationships pane to set the shared columns from the tables equal to each other. [Here's a pic](https://github.com/jeremyraby/courseNotes/blob/main/tableau/joiningTablesDiffFields.jpg)

## Worksheet Interface

On the data pane (far left), non-numerical data columns are found under the **dimensions** field and numerical data columns are under the **measures** field.
- You can drag and drop measures to dimensions and vice-versa.
Blue highlighted data columns are discrete data and green are continuous.
The analytics tab of the data pane allows you to do cool stuff like add trendlines to scatterplots.

### Making Dashboards

The quickest way to populate fields into a view is to double-click the data field. The graph that is automatically generated in the view depends on which field you select first, eg for geographical data, selecting the geo data first will generate a map view, while selecting numerical data **before** the geo data may generate a bar chart instead.
- Can also `CMD+click` on two different data fields and the Show Me tool will highlight which chart types can be built with those data
  - The chart type highlighted with a red border is what Tableau recommends as being most relevant
- Row shelf = Y axis and Column shelf = X axis

Tableau automatically creates a date hierarchy for any date field. When you drag the date "pill" to the Columns shelf, `YEAR` is defaulted, but clicked the `boxed +` symbol in the left of the pill, you can get smaller time periods (like quarter, etc).

You can adjust the size of the viz using the Size dropdown. Play with it until the entire View can be seen without scrollbars. "Automatic" is a great 'automatic' setting unless you just know how large of a screen will be used to view your viz.

"Actions" in the Dashboard menu allows you to select a data source (worksheet) to act as a filter for all the graphs you have on the dashboard. Several properties can be edited.
- Name
- Target Sheets (which worksheet/data source will be filtered)
- Can add different actions, not just a filter
  - highlight
  - go to url
  - go to sheet
  - change parameter
  - change set values
- Special filters, not seen as 'actions,' can also be set using the dropdown on the top right corner of each view

#### Blue vs Green

**So much** stuff in Tableau is affected by whether the field you're using is discrete (blue) or continuous (green) data.
*Blue*/discrete data will generate headers & *green*/continuous data will generate X/Y axes depending on if they're placed on the Columns (X) or Rows (Y) shelves.

##### Color

Tableau has a max of 20 distinct colors, any more data will use recycled colors
- This will look really messy
- Stick to like 5 distinct colors max

Tableau colors will behave differently for discrete and continuous data
- Discrete data will have different colors for each category
- Continuous data will display as a range of colors eg darker colors for higher profits

##### Filters

Continuous data can be filtered on multiple ranges while discrete data has more limited filtering
- Sliders vs unordered lists

##### Dates

By default, Tableau will aggregate dates to the highest level available
- Right click to see smaller aggregations (month, etc)
- Click the `+` at the left of the pill to add smaller aggregations to the shelf/View
  - Will add what kind of resembles Sparklines to the view
- Can change discrete to continuous by right clicking and scrolling to the second section of date options
  - Creates a "normal looking" timeline

### Data Storytelling

> Expect an underlying story when data show something unexpected, unpleasant, complex, costly, or especially counterintuitive. These situations tend to point to a good data story waiting to be told.

1. Set up
- Start with a hook
  - Is there a sudden change?
  - Are we missing an opportunity?
  - What should we expect going forward?
- Establish the theme of the story
2. Build up
- explain investigation steps
- communicate intermediate findings
- describe analysis
- provide the key finding
  - greatest explanatory power
3. Climax
- Explain the root cause for the hook from the key finding
4. Conclusion
- Discuss cause (if known)
- Call to Action