# Taxi_demand_prediction_NYC_project

Since the project data is very high, I have done this Project in Kaggle, please find it in the below link -

### https://www.kaggle.com/dasarimohana/nyc-taxi-demand-by-dasari-mohana

### Context
The yellow taxi trip records include fields capturing pick-up and drop-off dates/times, pick-up and drop-off locations, trip distances, itemized fares, rate types, payment types, and driver-reported passenger counts. The data used in the attached datasets were collected and provided to the NYC Taxi and Limousine Commission (TLC) by technology providers authorized under the Taxicab & Livery Passenger Enhancement Programs (TPEP/LPEP).                                                                           

## Data Source
<p>
Ge the data from : http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml (2015/2016 data)
The data used in the attached datasets were collected and provided to the NYC Taxi and Limousine Commission (TLC) 

The data is also provided in Kaggle

   Kaggle Data Link : https://www.kaggle.com/vishnurapps/newyork-taxi-demand
</p>

## Information on taxis:

<h5> Yellow Taxi: Yellow Medallion Taxicabs</h5>
<p> These are the famous NYC yellow taxis that provide transportation exclusively through street-hails. The number of taxicabs is limited by a finite number of medallions issued by the TLC. You access this mode of transportation by standing in the street and hailing an available taxi with your hand. The pickups are not pre-arranged.</p>

<h5> For Hire Vehicles(FHVs): </h5>
<p> FHV transportation is accessed by a pre-arrangement with a dispatcher or limo company. These FHVs are not permitted to pick up passengers via street hails, as those rides are not considered pre-arranged. </p>

<h5> Green Taxi: Street Hail Livery (SHL) </h5>
<p>  The SHL program will allow livery vehicle owners to license and outfit their vehicles with green borough taxi branding, meters, credit card machines, and ultimately the right to accept street hails in addition to pre-arranged rides. </p>

<h4>Note:</h4>
In this notebook I am considering only the yellow taxis for the time period between Jan - Mar 2015 & Jan - Mar 2016

# Data Collection:
- I have collected all yellow taxi trips data from jan-2015 to dec-2016(Will be using only 2015 data) 
- I have used dask library to read the data due to its large size
<table>
<tr>
<th> file name </th>
<th> file name size</th>
<th> number of records </th>
<th> number of features </th>
</tr>
<tr>
<td> yellow_tripdata_2016-01 </td>
<td> 1. 59G </td>
<td> 10906858 </td>
<td> 19 </td>
</tr>

<tr>
<td> yellow_tripdata_2016-02 </td>
<td> 1. 66G </td>
<td> 11382049 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2016-03 </td>
<td> 1. 78G </td>
<td> 12210952 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2016-04 </td>
<td> 1. 74G </td>
<td> 11934338 </td>
<td> 19 </td>
</tr>

<tr>
<td> yellow_tripdata_2016-05 </td>
<td> 1. 73G </td>
<td> 11836853 </td>
<td> 19 </td>
</tr>

<tr>
<td> yellow_tripdata_2016-06 </td>
<td> 1. 62G </td>
<td> 11135470 </td>
<td> 19 </td>
</tr>

<tr>
<td> yellow_tripdata_2016-07 </td>
<td> 884Mb </td>
<td> 10294080 </td>
<td> 17 </td>
</tr>

<tr>
<td> yellow_tripdata_2016-08 </td>
<td> 854Mb </td>
<td> 9942263 </td>
<td> 17 </td>
</tr>

<tr>
<td> yellow_tripdata_2016-09 </td>
<td> 870Mb </td>
<td> 10116018 </td>
<td> 17 </td>
</tr>

<tr>
<td> yellow_tripdata_2016-10 </td>
<td> 933Mb </td>
<td> 10854626 </td>
<td> 17 </td>
</tr>
<tr>
<td> yellow_tripdata_2016-11 </td>
<td> 868Mb </td>
<td> 10102128 </td>
<td> 17 </td>
</tr>
<tr>
<td> yellow_tripdata_2016-12 </td>
<td> 897Mb </td>
<td> 10449408 </td>
<td> 17 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-01 </td>
<td> 1.84Gb </td>
<td> 12748986 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-02 </td>
<td> 1.81Gb </td>
<td> 12450521 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-03 </td>
<td> 1.94Gb </td>
<td> 13351609 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-04 </td>
<td> 1.90Gb </td>
<td> 13071789 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-05 </td>
<td> 1.91Gb </td>
<td> 13158262 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-06 </td>
<td> 1.79Gb </td>
<td> 12324935 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-07 </td>
<td> 1.68Gb </td>
<td> 11562783 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-08 </td>
<td> 1.62Gb </td>
<td> 11130304 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-09 </td>
<td> 1.63Gb </td>
<td> 11225063 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-10 </td>
<td> 1.79Gb </td>
<td> 12315488 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-11 </td>
<td> 1.65Gb </td>
<td> 11312676 </td>
<td> 19 </td>
</tr>
<tr>
<td> yellow_tripdata_2015-12 </td>
<td> 1.67Gb </td>
<td> 11460573 </td>
<td> 19 </td>
</tr>
</table>


## Data Cleaning:
1. Univariate analysis of the data is performed wherein all erroneous data was removed.
2. As a part of the data cleaning phase we check if the pick-up and dropoff latitude and longitude fall within NYC and remove the ones that don’t.
3. I also removed outliers based on fare prices, Trip Duration, Speed and Distance travelled.

## Data-Preperation:

#### 1. Clustering/Segmentation

As a part of our solution is to predict the pickups in a region within some time interval, we need to derive regions and time intervals from data.Lets begin with dividing NYC into K clusters using the latitude and longitude of pickups. Using K-Means clustering, we cluster the pick-up points into different regions. From the data, we observe that a taxi can cover up to 2 miles in 10 minutes. Therefore, we want the inner cluster distance to be greater than 2 miles but not lesser than 0.5   miles. The optimal K value must meet this constraint. We tried a range of different cluster values from 30 to 70 clusters. After trying a different range of clusters, we observed that when the number of clusters is 40.

#### 2. Time Binning:

Every region is split into 10-minute interval, which corresponds to one time bin, i.e. each time bin has 10 minute. However, in the data we have time in the format “YYYY-MM-DD HH:MM:SS which are converted to Unix time format so as to retrieve time in minute/hour format. Number of possible 10 min interval bins : 4464 bins

#### 3. Smoothing:

Now that the data is divided into 10-minute interval bins, each bin should contain at least one pickup. There are chances that a time bin may contain zero pick-ups leading to ratio feature error and division by zero therefore we need to smoothed these values

#### 4. Time series and Fourier Transforms:

In theory, any waveform can be represented as the sum of infinite sine waves. Each sine wave has some amplitude and frequency. We can see that the number of pickups in a month in every cluster form a repeating pattern. We do not know the frequency of the repeating pattern. Our pattern cannot be represented by a single frequency as it’s aperiodic. Instead, it is composed of infinite sine wave with each sine wave having a frequency. Fourier transform lets us represent our pattern from time domain (number of pickups per time) to frequency domain(can be viewed as number pickup bins with highest number of pickups).

## MODELING
### Baseline models:

The first step to solving our business problem begins with baseline model. We will walk you through the process of discovering the right baseline model which gave us the best result.

1. Moving Averages

2. Weighted Moving Averages

3. Exponential Moving Averages

### Feature Engineering:

After doing all the data cleaning and preparation and baseline modelling, we now have an arsenal of features which would help build a good predication model. We see that, from baseline modeling, how Exponential weighted moving averages gives the best forecasting among the rest. We will use this as a feature while building the regression model along with others we got from data preparation stage.

## REGRESSION MODELS
#### Test and train split:

For test and train split by time, we take 3 months of 2016 pickup data and split it such that for every region we have 70% data in train and 30% in the test. As this is a time-series problem, we have to split our train and test data on the basis of time.

1. LINEAR REGRESSION

2. RANDOM FOREST REGRESSION

3. XGBOOST REGRESSOR

## MODEL EVALUATION

    Error Metric Matrix (Tree Based Regression Methods) -  MAPE
    --------------------------------------------------------------------------------------------------------
    Baseline Model -                             Train:  0.1487    |  Test:  0.1422
    Exponential Averages Forecasting -           Train:  0.1412    |  Test:  0.1349
    Linear Regression -                          Train:  0.1421    |  Test:  0.1348
    Random Forest Regression -                   Train:  0.0987    |  Test:  0.1333
    XgBoost Regression -                         Train:  0.1385    |  Test:  0.1328
    --------------------------------------------------------------------------------------------------------

# Conclusion:

- I have built a total of 5 regression models using the pickup_densities. Some models used the time series property while the other models ignored it and was treated as a proper regression problem.

- We can see that XGBoost performed based on TEST_MAPE was better than other models. Linear Regression was able to achieve similar values as XGBoost. 

- Here Random Forest Regression performs well on Train data and not good on test data which makes it overfit.Therefore, I choose XGBoost to avoid overfitting.

- Some of the more important features used by these models are pickupdensity(P(t-1),P(t-2)...) followed by Exponential Moving Averages using the previous pickup densities(predicted).

- Using these predictions, the Yellow taxi owners can decide where to station themselves during their hours of least pickup.
