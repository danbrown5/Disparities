# PRIME_Disparities

This repository contains the R markdown files to perform automated disparity searching on a database of PRIME (Public Hospital Redesign and Incentives in Medi-Cal). These will allow a R-literate analyst to use RStudio and take a database extract of PRIME measures and automate a search for the largest disparities in their served population. 

Use of this file requires a minimal amount of start-up before implementation. The primary input is the database used to calculate PRIME measures. Each row should represent one individual contributing to the measure denominator. The database should include the following variables:
MEASURE_ID: A unique identifier that indicates what PRIME measure this row contributes to
MEASURE_NAME: A text string describing the PRIME measure in more detail
NUMERATOR: An indicator (1/0) variable that is 1 if the individual has the poor outcome and 0 otherwise
TARGET_IS_UP: An indicator of whether the original goal of this measure is up or down
Disparities: A series of factor variables that contain the disparity axes along which you wish to search. The list of variables should be passed to the 'PRIME_Disparities_Analysis_Git.Rmd' file in Row 72, and described in words in rows 38 to 61. 
This data file should be saved as an .RDS file (can be saved from a different format by importing to R and using the saveRDS() function), saved to the same files as the Markdown files and the name placed in the  'PRIME_Disparities_Analysis_Git.Rmd' file in Row 68. In addition, the analyst should include their name and email in rows 4 & 5, and rename the saved file on Row 98.

The output from this file will include:
1) A .pdf file that contains the results from the disparity analysis
2) An .RData file that includes several new objects. Of note - 
  -  table.list - a list of the regression tables from the regression analysis
  -  node.list - a list of the output from the classification tree analysis
  
For any questions or comments, please use the Git platform or contact Dan Brown at dbrown7@cchealth.org.
