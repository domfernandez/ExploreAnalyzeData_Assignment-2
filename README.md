ExploreAnalyzeData_Assignment-2
===============================

The overall goal of this assignment is to explore the National Emissions Inventory database and see what it say about fine particulate matter pollution in the United states over the 10-year period 1999 to 2008.

Fine particulate matter ($PM_{2.5}$) is an ambient air pollutant for which there is strong evidence that it is harmful to human health. In the United States, 
the Environmental Protection Agency (EPA) is tasked with setting national ambient air quality standards for fine PM and for tracking the emissions of this pollutant into the atmosphere. 

Approximatly every 3 years, the EPA releases its database on emissions of $PM_{2.5}$. This database is known as the National Emissions Inventory (NEI). 

You can read more information about the NEI at the EPA National Emissions Inventory web site.

For each year and for each type of PM source, the NEI records how many tons of 
$PM_{2.5}$ were emitted from that source over the course of the entire year. 
The data that you will use for this assignment are for 1999, 2002, 2005, and 2008.

Data: The data for this assignment are available in a single zip file:

Data for this Project is available at:
https://d396qusza40orc.cloudfront.net/exdata%2Fdata%2FNEI_data.zip
... it is  [29Mb]

The zip file contains two files:
- Source_Classification_Code.rds  and
- summarySCC_PM25.rds

The two files are "read" using the readRDS() function in R.
... for example:
NEI <- readRDS("summarySCC_PM25.rds")
SCC <- readRDS("Source_Classification_Code.rds")

They have been un-zipped and placed in the root-directory.

Here are the first few rows of "summarySCC_PM25.rds"

####     fips      SCC Pollutant Emissions  type year
#### 4  09001 10100401  PM25-PRI    15.714 POINT 1999
#### 8  09001 10100404  PM25-PRI   234.178 POINT 1999
#### 12 09001 10100501  PM25-PRI     0.128 POINT 1999
#### 16 09001 10200401  PM25-PRI     2.036 POINT 1999
#### 20 09001 10200504  PM25-PRI     0.388 POINT 1999
#### 24 09001 10200602  PM25-PRI     1.490 POINT 1999

fips: A five-digit number (represented as a string) indicating the U.S. county
SCC: The name of the source as indicated by a digit string 
      (see source code classification table)
Pollutant: A string indicating the pollutant
Emissions: Amount of PM2.5 emitted, in tons
type: The type of source (point, non-point, on-road, or non-road)
year: The year of emissions recorded

"Source_Classification_Code.rds"
Provides a mapping from the SCC digit strings int he Emissions table to the actual name of the $PM_{2.5}$ source. The sources are categorized in a few different ways from more general to more specific and you may choose to explore whatever categories you think are most useful. For example, source �10100101� is known as �Ext Comb /Electric Gen /Anthracite Coal /Pulverized Coal�.
