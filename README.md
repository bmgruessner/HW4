# HW4-Malaria data in three charts
##Brian Gruessner, 20190404
https://bmgruessner.github.io/HW4/

This vis shows data on malaria mortality in children under five.  It shows the rates of death, by country, form 2000 to 2016, by total
deaths (ufive8), death per 1000 live births (rufive8), and deaths per 100 attributable to malaria (fufive8).  The data was taken from 
UNICEF [1].

To show this multidimensional data, three charts were used in parallel.  The first focuses on country and shows a bar chart of mortality
of countries, based on chosen year and metric.  The second is a line chart of mortality over the years, on a choice of countries and a 
metric.  The final is a parallel coordinates plot that compares metric of chosen countries in a given year.  The first chart is used to 
select countries in the other two, the time chart can be used to select the year for the other two, and the parallel coordinates chart can
select the metric for the other two.

###Design:
-One major challenge in this vis was to handle a large number of categorical variables (countries) at once.  To limit the number of bars in
the bar chart that could fit on the screen at once, countries with no mortality from malaria were excluded.  A wide-ranging rainbow color
scheme was used [2]. even with these features, there were many countries, which could not be reliably color-coded to be individually
discerned.  To improve upon this state in the line To further discern the categories, additional channels were used.  Degree of line 
dashing between close nations was employed in line charts. Finally, to discern similar-looking lines in the line graphs, a highlight
function was used.  Mouseing over on the bar chart highlights bars in all three charts.  This is an effective way to identify and isolate
out lines in the charts by country.

-There was a dilemma between presenting the absolute number of deaths by linear or logarithmic scale.  The log scale is handy for 
presenting overall data, because there is a wide range of mortality depending on country.  In the linear scale, countries with few deaths
have bars that are so small that they cannot be selected.  On the other hand, the linear scale is useful for seeing differences in 
countries with lots of deaths.  Mortality from major sources of death drop by half over the timeline, which is a major victory for medicine,
but looks miniscule on a logarithmic scale.  Therefore, a log scale was used for the bar chart and the linear scale was used for the line
charts.

###Technical:
-An important problem in this homework was formatting of the data.  The line chart did not work without a nesting of the data [3],
(thanks Lane)

-Onclick, mouseover, and mouseoff attributes were used to craft the interactions.  It was a lot of coding.

-Data processing: To filter out countries without mortality, countries with no deaths in the year 2000 were excluded (this was the
deadlist year on record, and there were no major outbreaks in countries that started with no mortality).  For countries that later
had zero mortality, their death rate was changed to 0.5 to prevent problems in my logarithmic scale.

-Time constraints were a limiting factor in this experiment.  Brushing would have been a viable technique to view all countries in
the window view for the bar chart, and would have been implemented given more time.

[1]: UNICEF (2018). Malaria mortality as a cause of death in children under 5. Excel File.  Accessed 4 April 2019, from 
https://data.unicef.org/resources/dataset/malaria/

[2]: Bostock, Mike (2019).  d3-scale.  Github.  Accessed 4 April 2019, from https://github.com/d3/d3-scale

[3]: Bostock, Mike (2018).  Multi-Line Chart. Observable.  Accessed 4 April 2019, from https://observablehq.com/@d3/multi-line-chart 
