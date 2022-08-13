# Linear mixed effect models
As part of my bachelor's thesis ("Which determinants influence maize yields in sub-Saharan countries?"), I created linear mixed models and calculated the influence of different variables on maize yields (crop cuts) in Burundi, Kenya, Rwanda, and Tanzania (2016-2020). All datasets and scripts used are included here.

Code and Data for: Processing the OneAcreFund dataset, extracting climate data from raster files, setup and validation of linear mixed effect models 


Date used: 
     CHIRPS: https://www.chc.ucsb.edu/data
     ERA5-Land: https://cds.climate.copernicus.eu/doi/10.24381/cds.e2161bac
     ESA CCI: https://esa-soilmoisture-cci.org/
     OneAcreFund: https://oneacrefund.org/insights-library/?country=4&category=164
     
     
1. Processing OneAcreFund crop cut data: 
-> Removal of incomplete observations, outlier removal, creation of a nitrogen variable, clustering data based on planting/harvesting date

The data processing of the OneAcreFund dataset can be found in:
LME-maize-yields-SSA/code/01_OneAcreFund.Rmd

The creation of the nitrogen variable can be found here: 
LME-maize-yields-SSA/code/05_N_equ.RMD

Clustering can be found here: 
LME-maize-yields-SSA/code/08_Cluster.Rmd


2. Extracting climate data from raster cells for every crop cut and creating timeseries:
The extraction from raster data and creating of timeseries for every crop cut can be found in: 
LME-maize-yields-SSA/code/02_Timeseries.Rmd
-> the finished time series datasets are not uploaded, due to the data volume

Calculating the growing season value for each variable:
LME-maize-yields-SSA/code/03_Growing Season.Rmd
-> results: LME-maize-yields-SSA/data/climate_data/...

Introduction of a variable for heat days:
LME-maize-yields-SSA/code/04_KDD.Rmd
-> results: LME-maize-yields-SSA/data/climate_data/...


3. Merging crop cut data and growth season values and standardization of data + check for collinearity:
LME-maize-yields-SSA/code/06_df_setup.Rmd
-> results: LME-maize-yields-SSA/data/model_data/final_selection_Neq_complete.csv
-> results: LME-maize-yields-SSA/data/model_data/final_selection_Neq_complete_zstand.csv

LME-maize-yields-SSA/code/07_Correlation.Rmd


4. Setup and validate LME-models with different predictor combinations + validation:
LME-maize-yields-SSA/code/09_Model.Rmd
-> results: LME-maize-yields-SSA/data/model_data/rmse_rsq_model.csv
