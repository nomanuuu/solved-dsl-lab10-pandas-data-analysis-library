Download Link: https://assignmentchef.com/product/solved-dsl-lab10-pandas-data-analysis-library
<br>
The main objective of this laboratory is to put into practice what you have learned on the <a href="https://pandas.pydata.org/">Pandas data </a><a href="https://pandas.pydata.org/">analysis library</a><a href="https://pandas.pydata.org/">.</a> This laboratory will let you carry out a preparatory data exploration analysis on two realworld datasets, to practice with the Pandas data analysis library and its advanced functionalities. If you have any doubts about the Pandas APIs, you can check <a href="http://dbdmg.polito.it/dbdmg_web/wp-content/uploads/2019/12/DSL-Pandas.pdf">the course material</a> or <a href="https://pandas.pydata.org/pandas-docs/stable/">the official documentation</a><a href="https://pandas.pydata.org/pandas-docs/stable/">.</a>

<h1>1          Preliminary steps</h1>

<h2>1.1         Datasets</h2>

<h3>1.1.1         New York Point Of Interest</h3>

The <em>New York Point Of Interest </em>dataset collects a sub-sample of the point of interests (POI) available in the city of New York. It contains the coordinates of each point of interest and the category to which it belongs to, specifying the <em>type </em>of the POI, for each POI <em>category</em>. There are four possible categories of POIs:

<em>amenity</em>, <em>shop</em>, <em>public_transport </em>and <em>highway</em>. The fields available in the dataset are:

<ul>

 <li>@id: a unique id for each point of interest.</li>

 <li>@lat: latitude coordinate of the POI in decimal degrees.</li>

 <li>@lon: longitude coordinate of the POI in decimal degrees.</li>

 <li>amenity name: if the POI category is <em>amenity </em>its type is reported in this field.</li>

 <li>shop: if the POI category is <em>shop </em>its type is reported in this field.</li>

 <li>public_transport: if the POI category is <em>public transport </em>its type is reported in this field.</li>

 <li>highway: if the POI category is <em>highway </em>its type is reported in this field.</li>

</ul>

To identify which are the POIs belonging only to the <em>New York City municipality</em>, a further file is provided. The <em>New York City municipality POIs </em>metadata file is composed by a single column containing the Ids of the POI of interest of the municipality.

Then, a map of the New York municipality is provided as well.

The main dataset is provided in TSV (Tab Separated Values) format. This format is very similar to the CSV one, the only difference is the separator used to split the fields in a row: the separator is a TAB character. You can download a zip containing the three files at: https://github.com/dbdmg/data-science-lab/raw/master/datasets/NYC_POIs.zip

<h3>1.1.2         Flight Delay Data</h3>

This dataset is made available by the <a href="https://www.bts.gov/">Bureau of Transportation Statistics</a> of the United States Department of Transportation.

Measuring the performance of flight carriers (e.g. American Airlines, EasyJet) is extremely important for the transportation department and, for this reason, all the information related to each flight are constantly monitored and collected in huge databases by the Department of Transportation. To the aim of this laboratory, just a small set of information has been extracted.

The dataset contains the Carrier On-Time Performance information collected from 01-01-2017 until 3101-2017 for all the flights in the United States. Each row represents a flight in a specific day. Some of the most useful fields in the dataset are:

<ul>

 <li>FL_DATE: day of the flight in format YYYY-mm-dd.</li>

 <li>TAIL_NUM: aircraft registration number, unique to a single aircraft.</li>

 <li>UNIQUE_CARRIER: flight carrier id.</li>

 <li>FL_NUM: number of the flight.</li>

 <li>ORIGIN: departure airport code.</li>

 <li>DEST: destination airport code.</li>

 <li>CRS_DEP_TIME: scheduled departure time (local time: HHMM) shown in the carriers’ Computerized Reservations Systems (CRS)</li>

 <li>DEP_TIME: actual departure time (local time: HHMM)</li>

 <li>DEP_DELAY: overall delay at departure. Difference in minutes (floating point number) between scheduled and actual departure time. Early departures set to 0.</li>

 <li>CRS_ARR_TIME: scheduled arrival time (local time: HHMM) shown in the carriers’ Computerized Reservations Systems (CRS)</li>

 <li>ARR_TIME: actual arrival time (local time: HHMM)</li>

 <li>ARR_DELAY: overall delay. Difference in minutes (floating point number) between scheduled and actual arrival time. Early arrivals show negative numbers.</li>

 <li>CARRIER_DELAY: delay in minutes (floating point number) caused by the carrier.</li>

 <li>WEATHER_DELAY: delay in minutes (floating point number) caused by the weather.</li>

 <li>NAS_DELAY: delay in minutes (floating point number) caused by the National Air System (NAS).</li>

 <li>SECURITY_DELAY: delay in minutes (floating point number) caused by the security.</li>

 <li>LATE_AIRCRAFT_DELAY: delay in minutes (floating point number) caused by the aircraft.</li>

</ul>

There are some other fields in this dataset. You can explore them, understand what they represents and whether they are significant or not for your analysis. Also, you can navigate <a href="https://www.transtats.bts.gov/DL_SelectFields.asp?Table_ID=236&amp;DB_Short_Name=On-Time">the web page</a> where the data has been collected from.

You can download the dataset at:

https://github.com/dbdmg/data-science-lab/raw/master/datasets/US_FlightDelayData.zip

<h1>2          Exercises</h1>

In this laboratory you have to practice with the <a href="https://pandas.pydata.org/">Pandas</a> data analysis library. Pandas is a very powerful library that provides high-performance, easy-to-use data structures and data analysis tools, allowing to simplify many of the tasks of the data scientist.

<strong>Info: </strong>All the exercises in this laboratory have to be solved using the Pandas library APIs whenever it is possible. Please consider that Pandas provides even plotting APIs, so you can try to solve plotting requests without the use of matplotlib. Further details about the Pandas plotting functionalities are available in the course material or in the DataFrame.plotting <a href="https://pandas.pydata.org/pandas-docs/stable/reference/frame.html#plotting">documentation</a>

<h2>2.1         Data exploration of Point Of Interests</h2>

In this exercise, you will perform a simple data exploration task on the <em>New York Point Of Interest </em>dataset exploiting the Pandas library.

<ol>

 <li>Load the <em>New York Point Of Interest </em>dataset exploiting Pandas APIs. Load the <em>NY Municipality POIs ID </em>metadata as well and filter out from the <em>New York Point Of Interest </em>data the records that do not belong to the New York municipality.

  <ul>

   <li>Which columns have been parsed?</li>

   <li>Which is the type of the data inferred by Pandas?</li>

  </ul></li>

 <li>For each column in the loaded dataset count the number of missing values.

  <ul>

   <li>What did you expect?</li>

   <li>What can you infer from this first analysis?</li>

  </ul></li>

 <li>Now, analyze the distribution of the POI types for each POI category. Point of interest categories are amenity, shop, public_transport and highway. For each of them, plot a histogram showing the distribution of the types of POI. Note that, for certain categories, due to the high number of types, bars and labels could not fit adequately in the figure. Hence, fix a threshold (a percentage one is better) and plot only the most frequent types.</li>

</ol>

To simplify the subsequent analysis, use the retained top frequent POI types also for the following exercises.

<ol start="4">

 <li>Show the points of interest on the New York map for a given category (e.g. amenity). To do so, you have to define a new function (or a new class) that, given the name of the POI category is able to show a scatter plot of the locations of the POI types, onto the New York municipality map, with a different color for each category.

  <ul>

   <li>Are you able to identify areas in which the concentration of a specific POI type is higher then others?</li>

   <li>How can you better characterize the POI distributions?</li>

  </ul></li>

</ol>

<strong>Info: </strong>to display an image on an Axes object, you can use the matplotlib <a href="https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.imshow.html">imshow</a> fuction. Then, you can specify the Axes object as the plotting axes in pandas methods, using the ax argument.

<ol start="5">

 <li>Discretize the POIs by geographical position. Define a new function (or class) that is able to split the geographical position of the POIs using a grid. Once defined the grid over the New York municipality, the function has to assign each POI to the cell to which it belongs to. The result should be a Pandas DataFrame with a new column containing the cell_id for each POI.</li>

 <li>Now you have to identify how many times a POI type is contained in each cell, for each category. Create a new DataFrame containing the cell_id as index, the POI types as columns and the count of the occurrences of each type, in each cell, as values.</li>

 <li>For the categories <em>amenities </em>and <em>shop </em>identify if there exist a correlation between the location of different POI types. Compute the pairwise correlation between the columns of the cell-type DataFrame and show it through a heatmap chart.

  <ul>

   <li>Are you able to identify which are the POI types more correlated between each other? What does it mean?</li>

   <li>Which are the more correlated tuples? Do they belong to the same category?</li>

  </ul></li>

</ol>

<h2>2.2         Data exploration and queries on Flight Delay Data</h2>

In this exercise, you will carry out some data exploration on the <em>Flight Delay </em>dataset. Just as before, you will use the Pandas library to answer different queries, exploiting crucial pandas concepts on indices, slicing types, pivoting and more.

<ol>

 <li>Load the Flight Delay dataset exploiting Pandas APIs.</li>

</ol>

<strong>Info: </strong>take a closer look at the parse_dates argument of the read_csv method. Whenever your data come with timestamps of dates, working with Python’s <a href="https://docs.python.org/3.8/library/datetime.html">datetime</a> structures becomes extremely useful.

<ol start="2">

 <li>Use the info() and describe() methods to analyze how your records are distributed. Before continuing, try to answer the following questions:

  <ul>

   <li>which type does each column have?</li>

   <li>are there any missing values?</li>

   <li>how many unique carriers are present?</li>

   <li>how many unique airports are present?</li>

   <li>from which time interval data were collected?</li>

  </ul></li>

 <li>Filter out all canceled flights.</li>

 <li>Use any pandas method and functionality to answer the following queries:

  <ul>

   <li>how many flights had each carrier operated?</li>

   <li>for each carrier, compute the mean delay considering all possible reasons (due to the carrier, weather, etc.)</li>

  </ul></li>

 <li>Add two new columns to your DataFrame:

  <ul>

   <li>weekday: it is the day of the week expressed as an integer number. Check out Pandas <a href="https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.dt.dayofweek.html#pandas.Series.dt.dayofweek">dayofweek </a></li>

   <li>delaydelta: it is the difference between the arrival delay and the departure one.</li>

  </ul></li>

 <li>Choose one of the visualization tools that you know and inspect the arrival delay as a function of the day of the week. Can you find any correlation?</li>

 <li>Consider the weekend days only, compute, for each carrier, the mean arrival delay. Now consider the working days and compute, for each carrier, the mean arrival time.</li>

</ol>

Then, compare the delays in working days and in weekends for each company.

<ul>

 <li>Are you able to identify companies that are delayed only in weekends or only in working days? Why?</li>

</ul>

<ol start="8">

 <li>Create a Pandas DataFrame with a multi-index composed of the columns: tunique_carrier, origin, dest, fl_date.</li>

 <li>For each flight operated by American Airlines (AA) and Delta Airlines (DL), taken off from the Los Angeles International Airport (LAX) and for each date, display the departure time and delay.</li>

 <li>For each flight that flew in the first week of the month, with LAX as destination airport, compute the mean arrival delay.</li>

 <li>Generate a pivot table containing the number of departed flights for each carrier and for each day of the week and show it.</li>

</ol>

Compute now the pairwise correlation between the carriers and show it on a heatmap.

<ul>

 <li>What does this correlation matrix represent?</li>

 <li>Can you find any carrier with different flight plans?</li>

</ul>

<ol start="12">

 <li>Generate a pivot table containing the average arrival delay, for each carrier and for each day of the week and show it.</li>

</ol>

Compute now the pairwise correlation between the carriers and show it on a heatmap.

<ul>

 <li>What does this correlation matrix represent?</li>

 <li>Can you find any carrier with different delay behaviors?</li>

</ul>

<ol start="13">

 <li>Using a pivot table, for the carriers HA, DL, AA and AS compute the average deltadelay for each day of the week. Then, display the results on a line plot, having a line per carrier and the weekday on the x-axis.</li>

</ol>