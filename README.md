# Air Temperature Interpolation with Random Forests

This repository contains Jupyter Notebooks implementing the workflow for air temperature (AT) interpolation using a Random Forest regression framework.  
The approach leverages authoritative **ARPA** and crowdsourced **CML** meteorological station data, combined with geospatial and Earth Observation (EO) predictors.  
The study focuses on **heatwaves (HW)**, estimated from reanalysis data over Italy: [VHR-REA_IT](https://dds.cmcc.it/#/dataset/era5-downscaled-over-italy/hourly).

For more details, please refer to the published paper:  
*"Predicting air temperature patterns in Milan using crowdsourced measurements and Earth Observation data"*,  
_Remote Sensing_, DOI: **XXX**.

---

## Prerequisites
To replicate the methodology, you will need:
- A set of predictors prepared on a common grid  
- A station network well distributed across the study area  

---

## Repository Structure
The notebooks are organized into three main steps:

1. **CMCC reanalysis download and HW estimation**  
2. **ARPA and CML preprocessing**  
3. **Air Temperature (AT) interpolation**
