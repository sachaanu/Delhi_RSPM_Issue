# Delhi_RSPM_Issue
Delhi Air Quality Index (AQI) / (Respirable Suspended Particulate Matter < 2.5 micrometers) RSPM 2.5 Problem & Predicting the peak using POC on ARIMA/FbProphet

* Introduction to the Phenomenon

## Problem: 
Every year there is horrible air quality in Delhi around Nov-Dec, which contributes to the numerous road accidents due to low visiblity and creates a health hazard for an already polluted city.

RSPM - Respirable Suspended Particulate Matter with size 2.5 micrometers and lower is the main culprit.
There are varied reasons for this phenomenon e.g.:

** Setting of winter-cold air in the lower atmosphere creates a thick blanket which traps pollution.

** Farmers burning left-over crops in-around the same time, adding soot and other particulate matters.

** General pollution from chemicals used in fireworks(this was a huge debate point and Supreme Court of India banned fireworks celebration on Diwali in 2018 - but still the AQI was below breathable and there was no improvement)

Albeit, there are compunding effects from various sources contributing to the detoriation of Air Quality Index of Delhi. Below news links de-lineate the scope of the problem.

New Links:

[Delhi_Harmful_Affect_on Health](https://www.hindustantimes.com/fitness/delhi-air-pollution-what-are-its-harmful-effects-on-health-and-how-to-cope-with-it/story-Ky1d61nVsqrDFKIyEmDzwO.html)

[Delhi_Public_Health_Crisis](https://www.theguardian.com/world/2018/dec/24/delhis-worst-air-pollution-this-year-raises-fear-of-public-health-crisis)

[Living in Delhi is as smoking 45 cigarettes a day](https://qz.com/india/1124049/air-pollution-in-new-delhi-has-the-health-effect-of-smoking-45-cigarettes-a-day/)

## Inference: 
This POC is an effort to predict the peak of the RSPM - Respirable Suspended Particulate Matter in Delhi Air by analyzing the timeseries behaviour.

## Goal: 
If there is model that can analyze the timeseries behaviour and can predcit the worse levels of RSPM correctly on a weekly granualarity, the alerting mechanism can be generated to predict the Air Quality in advance i.e. effectively predicting the RSPM & defining Air Quality Index of Delhi 1 or 2 weeks before the peak.

* Version of Libraries used:

Python version --  3.6.1 

numpy version --  1.14.2

pandas version --  0.22.0

matplotlib version -- 1.14.2

seaborn version --  0.7.1

tensorflow version --  1.5.0

* Source of Data

Data is gathered from the airnow portal, available in csv for a yearly basis.

http://dosairnowdata.org/dos/historical/NewDelhi/2018/NewDelhi_PM2.5_2019_YTD.csv --- YTD_2019
http://dosairnowdata.org/dos/historical/NewDelhi/2018/NewDelhi_PM2.5_2018_YTD.csv --- YTD_2018
http://dosairnowdata.org/dos/historical/NewDelhi/2017/NewDelhi_PM2.5_2017_YTD.csv --- YTD_2017
http://dosairnowdata.org/dos/historical/NewDelhi/2016/NewDelhi_PM2.5_2016_YTD.csv --- YTD_2016
http://dosairnowdata.org/dos/historical/NewDelhi/2015/NewDelhi_PM2.5_2015_YTD.csv --- YTD_2015


## Steps to Create Model

* Sanitizing Data & creating a uniform timeseries
* Observing behaviour and pattern
* Choose optimum Granualarity of data
* Applying log transformation to standardize the scale of the values i.e log transform
* POC on ARIMA with seasonal component with 365 days
* Finalizing the ARIMA specifications e.g. ensuring stationarity
* Comparison with Out of the Box (FbProphet)
* Piting ARIMA vs Fb Prophet over specified paramaters
* Choosing the correct duration and forecast on the test
* Inverse the transformation i.e. un-log the train, test & forecast to compare results on actual scale
* Check for Accuracy and Vizualize the results

## Conclusion

* ARIMA performs better than ARIMA in the problem
* Cusotmized seasonal component helps the model for the accuracy
* Fairly accurate prediction using ARIMA 
* Model can be used to forecast and predict on future peaks in RSPM for Delhi's AQI

## Results of ARIMA seasonal for 9 months as Test/Forecast sample

<img width="867" alt="Delhi_AQI_2" src="https://user-images.githubusercontent.com/26288770/55310970-b12c6080-5416-11e9-9d6d-6e3fcabf4ca2.png">

