# What drives the price of a car

## Overview

From a business perspective, we are tasked with identifying key drivers for used car prices. In the CRISP-DM overview, we are asked to convert this business framing to a data problem definition. Using a few sentences, reframe the task as a data task with the appropriate technical vocabulary.

Basically, we have been provided a dataset that contains 426K sales transactions of used cars (minimized from 3 million to avoid resource exhuastion).  The objective for the data scientist is to understand what characteristics of used cars that were previously sold can be used to predict a future sales price.  This type of prediction will help the car dealership (a.k.a. the client) to choose inventory and to more or less accurately price chosen inventory.

## Business Understanding

Car dealerships build inventory up and then sell used cars as quickly as possible to make money. It is important for dealerships have a high turnover rate of their inventory.  In order to have a high inventory turnover rate, dealerships must adequately price their inventory so that it sells as quickly as possible and, at the same time, acheives the highest profit margin.  To acheive this goal it is important for the dealers to understand the price at which a used car can be sold. Pricing a used car too high will keep it in their inventory for a longer period of time. Hence, it is important to identify the drivers of value for potential clients to adequatly price each vehicle on the lot.

To adequatly price a vehicle, we will investigate past transactions and explore the various features pertaining to previously sold vehicles and the features which impact the sales price the most. Using a regression model, we can make inferences about the optimal price at which a car can be sold.

## Summary Findings

The following conclusions can be given to the client:

To build inventory that will produce the highest turnover with regards to the sale of used vehicles, dealerships should obtain vehicles with the following attributes:

- Vehicles manufactured recently (within the last 5 years)
- Vehicles not driven or used very frequently (low odometer readings)
- Vehicles with forward or rear wheel drive
- Vehicles with engines of a certain size (7 cylinders)
- Vehicles with Automatic transmission

Note, vehicles of varying engine sizes (cylinders) should be accumulated in the dealership's inventory in order to accomodate potential customers looking for a particular engine size.

The feature 'year' seems to be the most influential independent variable when predicting the price of a car. The optimal Ridge model (polynomial degree 3) using alpha 10 seems to be the best model to use for price prediction of a used car producing a margin of error of +/- $4,360.

The year of the used car has the most influence on predicting the price. Again, odometer, drive, cylinders and fuel seem to have about the same influence when predicting the price of a used car. Also, automatic transmission seem to be preferred to other types of trammissions.

## Next Steps

The data needs to be entered correctly to avoid missing values.  The features whose percentage of missing values was greater than 20% had the missing values replaced with the string "missing" which created an additional category after encoding.  Columns/features with larger than 20% missing values should be considered to be dropped in a subsequent iteration.