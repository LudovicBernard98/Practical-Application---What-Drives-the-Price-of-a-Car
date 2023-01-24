# Practical-Application---What-Drives-the-Price-of-a-Car
 
# This is a practical assignment module 11 exploring regressions on used car prices.

## Overview
In this application, I will explore a dataset from kaggle. The original dataset contained information on 3 million used cars. The provided dataset contains information on 426K cars to ensure speed of processing. My goal is to understand what factors make a car more or less expensive. As a result of my analysis, I should provide clear recommendations to your client -- a used car dealership -- as to what consumers value in a used car.

## Business Understanding
As a business, car dealerships need to build up inventory. To optimize the profitability of the business, it is important for dealerships have a high churn rate of their inventory and maximize the pricing of vehicles. The higher the churn rate the higher the dealerships revenue will be. To achieve such a feat, it is important for the dealers to understand the price at which a used car can be sold. Pricing a used car too high will keep it in their inventory for a longer period of time. Hence, it is important to identify the drivers of value for potential clients to adequatly price each vehicle on the lot.

To adequatly price a vehicle, we will investigate past transactions and explore the various features impacting a the price at which a vehicle was sold. Using a regression model, we can help make inferences about the optimal price at which a car can be sold.

## Summary Findings
After the initial cleaning of the data, I carried out in depth analysis to answer the business question at hand. Most importantly, I focused on various regression models capable of predicting the price of a used vehicle. See jupyter notebook: "https://github.com/LudovicBernard98/Practical-Application---What-Drives-the-Price-of-a-Car/blob/main/prompt_II.ipynb" to view the entire workbook.


Modeling was much more challenging than expected. With hundred of thousands of observations and polynomial features my dataset was very heavy for my computer. I was still able to explore various regression models. Although we could of achieved a higher regression score using the polynomial of degree 4, I settle on a polynomial of degree 3 for two reasons.

1- The gain by increasing the degree of the polynomial was marginal in contrast to gains from increasing the regression to a degree 2 and 3. This leads to a less efficent shift on the graph of accuracy vs overfitting.

2- The degree 4 polynomial would of been very computationally heavy. Additionally, as we increase in polynomial degree the real world inference of such model decreases. For instance, price is not a polynomial degree 4 dependent of types of vehicles or of other features and interactions across features become increasingly hard to track.

Overall, although I performed L1 and L2 normalization/regularization. The gain of such approach were negligeable. Across all models, it was apparent that the features impacting the most the variation of price was the year of the vehicle. Afterwards, variation in price were mostly allocated to the odometer, drive, cylinder and fuel.

Selecting the polynomial of degree 3 as the best predictive model, I would like to offer the following insight: 

To maximize the price at which a vehicle is sold, dealerships should focus in order of importance on:
1- Year of the vehicle -- the younger the better
2- The odometer -- the lower the km the better
3- the drive -- higher value when forward or rear wheel
4- Cylinders -- the bigger the engine the more expensive the car
5- Fuel -- gas has higher value
6- transmission -- an automatic transmission will greatly impact the value of the price
(full list in the figure in the workbook)

By focusing on the 6 attributes to select the vehicles in their inventoy. Dealerships will be able to optimize their inventory. It is important to note that a limitation of this model is the expected profit and inventory turnover. The model does not consider such impacts. Hence, the model would need additional data in this area to offer a proper picture to optimize profits and revenue. For instance, although it is true that the bigger the engine the higher the price. If a dealership only stocks 10 cylinder vehicles, it is unlikely that they will have the clientel to sell these vehicles. This may yield in much lower profits and revenue.


## Next Steps

To offer more insight additional information could be gathered, the dataset could be completed to have less NaN since these were counted as a seperate categor ('missing'). Additionally, providing a listing price vs. the transaction price would give a better understanding to the optimal pricing of vehicles for dealership. Furthemore, days in inventory would be an important metric to track and try to optimize the profit of a dealership.Moreover, logarithmic transformation may yield better results for inferences than a standard polynomial of degree 3 model.