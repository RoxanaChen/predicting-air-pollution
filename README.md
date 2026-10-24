# Predicting Annual Air Pollution

## Overview
This project explores how accurately we can predict a location's annual average air pollution (measured by PM2.5, fine airborne particulate matter with a diameter of 2.5 micrometers or less) from monitor, land-use, population, and demographic data. Air pollution monitors are sparse and mostly located in cities, so rural areas are under-measured, and predictive models can estimate pollution where there are no monitors. As an extension, we asked whether a simpler model with fewer predictors could perform as well as a full model or not.

## Data
Public data from the [OpenCaseStudies "Predicting Annual Air Pollution"](https://www.opencasestudies.org/ocs-bp-air-pollution/) project (Wright et al., 2020), which can be downloaded with the `OCSdata` R package. It contains 2008 annual average PM2.5 from 876 EPA monitors in the U.S., plus 48 features from NASA, the U.S. Census, and the National Center for Health Statistics: satellite aerosol measurements, a chemical-model pollution estimate, road length, emissions, population density, urbanization, education, and poverty.

## Methods
* Wrangled and explored the data in R (tidyverse, ggplot2), including a map of monitor locations and a correlation plot
* Split the data into 2/3 training and 1/3 testing sets and used 4-fold cross-validation
* Built a random forest regression model with tidymodels, then ranked predictors by importance and refit smaller models using only the top 10 and top 5 predictors

## Key Findings
The full model predicted annual PM2.5 on test data with an RMSE of 1.72 µg/m³ (R² of approximately 0.61). The top-10 model had an RMSE of 1.85 and the top-5 model 1.92, so a much simpler model lost only a small amount of accuracy.

## Files
- `data/` - data folder
  - `pm25_data.csv`: air pollution data
- `pred_air_pollution.Rmd`: R Markdown file with the full code and analysis
- `pred_air_pollution.html`: rendered report

## Team
Group project by Roxana Chen, Jiayi Xue, Sehee Kim, Jorge Ramos, Nick Liu
