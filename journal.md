# 11/10/2023 
The issue with downscaling a timeseries for precipiation is that there are no existing data to train on. The precipitation for one day measures the total precipitation in one day. I cannot assume that the precipitation for an hour is just total precipitation/24. This is pretty tricky to do especially without any physical models. The parameters for this problem are: 
Input: Daily total precipitation, hourly temperature measurement 
Model: Decision tree. 
Output: Hourly total precipiation 

# 10/23/2023 
- cloned project
- set up api key for retrieving CDS' ERA5 dataset 
- Created specific project objective

I think it would be good to train on windspeed, K index (thunderstorm), 2 m temperature, cloud base height, surface pressure, total cloud cover, total precipitation, vertical integral of temperature. 

Input: (2 m temperature, Surface Pressure, vertical integral of temperature, total cloud cover, cloud base height, K index total precipiation, month of year (1-12)) * decorrelation distance * decorrelation distance * decorrelation time (days)

a T by (7*M*N*dT) matrix. 

Output: Total precipitation by the hour. 