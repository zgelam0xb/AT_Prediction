# Air Temperature Interpolation

This repository contains Jupyter Notebooks implementing the workflow for air temperature (AT) interpolation using a Random Forest regression framework. The approach uses authoritative **[ARPA](https://www.arpalombardia.it/temi-ambientali/meteo-e-clima/form-richiesta-dati/)** and crowdsourced **[CML](http://www.centrometeolombardo.com/)** meteorological station data, combined with geospatial and Earth Observation (EO) predictors. The study focuses on **heatwaves (HW)**, estimated from reanalysis data over Italy: [VHR-REA_IT](https://dds.cmcc.it/#/dataset/era5-downscaled-over-italy/hourly).

---

For more details, please refer to the published paper:  
*"Predicting air temperature patterns in Milan using crowdsourced measurements and Earth Observation data"*,  
_Remote Sensing_, DOI: **XXX**.

---

## Data statement
We relied on high-quality local predictors when available; otherwise, European or global products were used. Please check the paper for details.
CML data is not publicly available and was made available upon request from the CML Association.

---

## Notebooks replicability
All notebooks besides CML quality control in **2. ARPA and CML preprocessing** can be replicated since raw CML data can't be shared.

---

## Repository Structure
The notebooks are organised into three main steps:

1. **CMCC reanalysis download and HW estimation**:
   The research was focused on the periods of extreme heat, i.e. HWs. They were estimated from a spatio-temporal climate reanalysis over Italy.
   This notebook downloads CMCC data and estimates HWs based on the approach proposed by **[Perkins & Alexander (2013)](https://doi.org/10.1175/JCLI-D-12-00383.1)**
   
2. **ARPA and CML preprocessing**:
   CML is a crowdsourced product. Quality control is crucial to ensure reliable comparison between ARPA and CML sensors. ARPA is used as a reference for CML cleaning.
   
3. **CML and ARPA AT extraction**:
   CML and ARPA station data is averaged over selected HWs and prepared for AT interpolation in the next step.
      
4. **Air Temperature (AT) interpolation**:
   The Random Forest machine learning algorithm applied to the selected HW events, generating GeoTIFF rasters of predicted AT.
