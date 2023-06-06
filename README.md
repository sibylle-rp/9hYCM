# 20230606 Assignment
The script for the assignment is available in Assignment/Assignment.Rmd  
I used a Rmarkdown file in order to have all the answers and code all in one place.  

## Installation
Clone the repository using the following link: 

The script runs with **R version 4.2.2**  

Please install additionally the following packages: **tidyverse, raster, terra, rnaturalearth, rnaturalearthdata, knitr**  
To do so, you can use the Rstudio IDE or the following function:  

> install.packages(c("tidyverse", "raster", "terra", "rnaturalearth", "rnaturalearthdata", "knitr"))

## Data
You should unzip the zip file from the dropbox into the data folder.  
The data should then be in the Data folder, with the following architecture:  

* GAUL
  * g2015_2005_2.dbf
  * g2015_2005_2.prj
  * g2015_2005_2.sbn
  * g2015_2005_2.sbx
  * g2015_2005_2.shp
  * g2015_2005_2.shx

* NUE_Zhang_et_al_2015
  * Country_NUE_assumption.csv

* SPAM_2005_v3.2
  * SPAM2005V3r2_global_H_TA_WHEA_A.tif
  * SPAM2005V3r2_global_Y_TA_WHEA_A.tif

## Running the Rmd
In order to run the script, simply **open the 9hYCM.rProj** and **open the Assignment.Rmd** file in the Assignment folder.  
Then click on **knit**  
After the code has run, an html file pops up summarising my answers to the assignment. 
The produced rasters, plots, csv and html are saved in the Assignment folder.  

## Answers to additional questions:
The following answers are also written in the HTML file produced by the Assignment.Rmd  

### Question 4/c.
The two largest wheat producers, China and India, as well as Pakistan have a very poor Nitrogen Use Efficiency leading to high Nitrogen losses. On the other hand, France and Russia, which are respectively 4th and 5th largest wheat producers have a better Nitrogen Use Efficiency, leading to smaller Nitrogen losses. Implementing policies to improve the Nitrogen Use Efficiency in China and India could therefore have a significant impact on global Nitrogen losses and related environmental impacts.

### Question 5
One could for example use this analysis to assess the impact of different agricultural management practices on Nitrogen outputs and losses. However, specific Nitrogen information for each agricultural practice would be needed. The underlying assumptions, such as the 2% Nitrogen in harvested wheat yield would need to be refined. Furthermore, yield and harvesting area data for multiple years would have to be obtained (to avoid drawing conclusions based on a year that might be affected by extreme weather conditions). From my understanding this type of analysis could be performed and refined by the EPIC Model. 

The Nitrogen cycle could also be integrated into the GLOBIOM model, which, by combining it to supply and demand data, could allow to see the impact of different nitrogen mitigation options on food security, as it has been done in [Chang, J. et al 2021](https://www.nature.com/articles/s43016-021-00366-x).

### Question 6
Regarding the units of the SPAM raster data, I used the same units as the units described in the technical documents (Table 2-1). 
Regarding the Production data calculations, I assumed that the yield data refers to the tonnes produced per harvested area, and not per physical area, also based on the SPAM technical documents.
Comparing the results with FAOSTAT data confirmed both of these assumptions.

For the calculation of the production per country, I manually added correspondences(in the script) between "USA" and "United States of America", and "Russian Federation" and "Russian Fed" in order to match the NUE to the top 10 producing countries. If the analysis would be performed on a larger data set, a proper concordance table should be implemented. 

Additionally, when comparing the total production before and after the allocation per country, a difference of 0.7% is observed. This is probably due to the way the extraction is performed in the extract function. Due to time constraint and runtime limitation, this has not been further investigated. However, for some countries this could potentially lead to increased errors.
