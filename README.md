# Air Temperature (AT) Interpolation

This repository contains Jupyter Notebooks implementing the workflow for AT prediction using a Random Forest regression framework. The approach uses authoritative **[Agenzia Regionale per la Protezione dell'Ambiente (ARPA)](https://www.arpalombardia.it/temi-ambientali/meteo-e-clima/form-richiesta-dati/)** and crowdsourced **[Centro Meteorologico Lombardo (CML)](http://www.centrometeolombardo.com/)** meteorological station data, combined with geospatial and Earth Observation (EO) predictors. The study focuses on **heatwaves (HW)**, estimated from reanalysis data over Italy: [VHR-REA_IT](https://dds.cmcc.it/#/dataset/era5-downscaled-over-italy/hourly).

---

For more details, please refer to the published paper:  
Žgela, M., Vavassori, A., & Brovelli, M. A. (2025). _Predicting Air Temperature Patterns in Milan Using Crowdsourced Measurements and Earth Observation Data_. Remote Sensing, 17(21), 3520.
DOI: **https://doi.org/10.3390/rs17213520**.

---

## Data statement
We relied on high-quality local predictors when available; otherwise, publicly available products were used. Please check the paper for details.
CML data is not publicly available and was made available upon request from the CML Association.

---

## Notebooks replicability
All notebooks besides CML quality control in **2. ARPA and CML preprocessing** can be replicated since raw CML data can't be shared.

---

## Repository Structure
There are five processing notebooks:

1. **CMCC reanalysis download and HW estimation**:
   The research was focused on the periods of extreme heat, i.e. HWs. They were estimated from a spatio-temporal climate reanalysis over Italy.
   This notebook downloads CMCC data and estimates HWs based on the approach proposed by **[Perkins & Alexander (2013)](https://doi.org/10.1175/JCLI-D-12-00383.1)**
   
2. **ARPA and CML preprocessing**:
   CML is a crowdsourced product. Quality control is crucial to ensure reliable comparison between ARPA and CML sensors. ARPA is used as a reference for CML cleaning.
   
3. **CML and ARPA AT extraction**:
   CML and ARPA station data are averaged over selected HWs and prepared for AT interpolation in the next step.
      
4. **AT prediction**:
   The Random Forest machine learning algorithm applied to the selected HW events, generating GeoTIFF rasters of predicted AT.

5. **AT distribution across surface materials**
   Visualise the distribution of predicted AT values across quartiles of surface materials to analyse their potential to intensify or mitigate heat. 
