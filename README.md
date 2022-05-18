# Flights-Customer-Satisfaction-Classification
## Customer Satisfaction 

### Data definition: 

Airline customers satisfaction dataset consists of 1 csv file. This data contains the records of the flight information with 25 features for each flight and 103904 rows. So, it is needed first to list the features (Columns) to explore the data and for better understanding. The features can be split into two parts, Numerical features, and categorical features. Numerical features are the features that contain numbers as data. Categorical features that contain data divided into groups. The first two features are the ID and the index so it will be ignored. “Gender” whether male or female, “Customer type” whether loyal or disloyal, “type of travel” whether personal or business, “Class” whether eco plus, business or eco and the last categorical features is the “satisfaction” the most important because it is the target class for analysis and classification model. The numerical features are 'Age', 'Flight Distance', 'Inflight Wi-Fi service', 'Departure/Arrival time convenient', 'Ease of Online booking', 'Gate location', 'Food and drink', 'Online boarding', 'Seat comfort', 'Inflight entertainment', 'On-board service', 'Leg room service', 'Baggage handling', 'Check-in service', 'Inflight service', 'Cleanliness', 'Departure Delay in Minutes', 'Arrival Delay in Minutes'. 

### STATISTICAL ANALYSIS: 

Female travelers outnumber male passengers by 52727. 50% of the flights in this data were not delayed because the median number of delays is 0. Flight delays average 15 minutes, with a standard variation of 38 minutes.  

### General Visualization: 

As shown in the plot below the number of travelers of female and male is almost the same. 

![1](https://user-images.githubusercontent.com/96385070/168953338-fc8cb308-78c1-429a-8b49-9d4581ede93a.png)
 
The number of loyal customers is clearly higher than disloyal customers. 

![2](https://user-images.githubusercontent.com/96385070/168953411-a41b8bf2-7312-4249-bb9f-8e7a5c369f8d.png)


The number of business travels is much higher than personal travel. 

![3](https://user-images.githubusercontent.com/96385070/168953443-5e31f6c4-8a04-4d8c-9156-45ef3511768d.png)

Business class and eco class is almost the same but the eco plus class is clearly lower than the other two classes. 

![4](https://user-images.githubusercontent.com/96385070/168953481-06f730ca-d927-414c-98df-dff649fc6144.png)

It is shown the neutral or dissatisfied class is little more than satisfied but does not consider as unbalanced data. 
 
![5](https://user-images.githubusercontent.com/96385070/168953503-b2d07ffa-07ae-4c04-a243-f70699ca6d55.png)

### Extracting useful insights: 

![6](https://user-images.githubusercontent.com/96385070/168953548-3be6962d-d1c3-45db-902c-b5bbc2651377.png)

As shown in above plots, males and females are the same number of dissatisfied. Disloyal customers are more dissatisfied the loyal customers. Personel Travel customers are hugely dissatisfied and business travelers are very satisfied. The eco class customers are insanely dissatisfied, the business class customers are highly satisfied and a high number of customers in the eco plus class are dissatisfied. 

 ### Conclusion of insights: 

- Men and women appear to be equally worried about the same factors, hence gender does not appear to have a significant impact in satisfaction. 

- Although this airline has a large number of loyal customers, dissatisfaction is prevalent regardless of loyalty. The airline will have to work hard to keep its loyal customers. 

- Business travelers appear to be happier with their flights than personal Travellers. 

- People in business class appear to be the most satisfied, while those in economy class appear to be the least satisfied. 

![7](https://user-images.githubusercontent.com/96385070/168953781-31b7f440-89ed-41c7-922f-6a074a0fff6b.JPG) 

In comparison to Eco and Eco plus, business class customers have been given superior evaluations for all services supplied. As a result, the class of travel should play a significant role in overall satisfaction. 

![8](https://user-images.githubusercontent.com/96385070/168953826-1b3f0977-36ca-4096-84ae-9c96145e6769.png)

As shown, there is a direct correlation between in-flight entertainment and satisfaction. 

![9](https://user-images.githubusercontent.com/96385070/168953852-47807169-f343-41e7-b4e2-b718940371b9.png)

As shown, there is a direct correlation between seat comfort and satisfaction. 

![10](https://user-images.githubusercontent.com/96385070/168953867-eeef6105-d67f-4146-8aaf-ea7dccb7ffab.png)

Travelers between the ages of 38 and 60 are more satisfied than customers of other ages. 
 
![11](https://user-images.githubusercontent.com/96385070/168953901-8895334a-e9ed-4690-b57d-d0d5bd22a13b.png)

The arrival and departure delays follow a linear relationship. 

![12](https://user-images.githubusercontent.com/96385070/168953935-25183a8e-b2a4-4f44-9f52-2e3a12948d3a.png)

The most essential point from this plot is that the greater the trip distance, the more passengers are willing to accept a short delay in departure. As a result, departure delays are less of an issue for long-distance flights; however, short-distance travelers do not appear to be concerned about departure delays. 

### Feature selection: 

![13](https://user-images.githubusercontent.com/96385070/168954953-9835bd43-d9a1-47fd-b23c-df1382e645c4.png)

Features like Flight Distance, Departure/Arrival time convenient, Gate location, Departure Delay in Minutes and Arrival Delay in Minutes have very low impact on customer satisfaction and the correlation is weak. So, it’s going to drop those features to decrease model complexity. 

### Model training: 

The first Model is Logistic regression and the model trained twice. The first train was using scaling method and the second train without any scaling method. The difference between them was very small and unnoticeable. But in confusion matrix the scaled data has slightly overfit, so it’s used the unscaled data. 

![scaled](https://user-images.githubusercontent.com/96385070/168954803-b827b37a-99c2-451b-8627-be022be8e021.JPG)
Scaled 
![unscaled](https://user-images.githubusercontent.com/96385070/168954841-ffc893f9-7db0-47e1-ac4b-f5c8082124ce.JPG)
Unscaled 

The second model was (KNN) K nearest neighbor. To identify the suitable number of K, there’s a loop iterate from 10 to 18 to choose the best value of K. 

![16](https://user-images.githubusercontent.com/96385070/168955003-2453a2a7-7f4e-41b1-8d4b-c0c80a5d32c4.JPG)

As shown below the best K value is 11. 

The third model is the Decision tree classifier. It uses a loop to set the best depth for the tree from to 20 to 30. 

![19](https://user-images.githubusercontent.com/96385070/168955058-08bceba1-3f27-452f-86ff-46f63ab3e28b.JPG)
 
As shown the best depth is 25. 

### Model Evaluation: 

#### Logistic Regression 
![14](https://user-images.githubusercontent.com/96385070/168956038-bf8b2660-9eb0-4a85-8821-94f696fda3d0.png)
![unscaled](https://user-images.githubusercontent.com/96385070/168954841-ffc893f9-7db0-47e1-ac4b-f5c8082124ce.JPG)

#### KNN 
![18](https://user-images.githubusercontent.com/96385070/168956299-c8550aa4-059b-465c-bf67-11fa6d7e6ed4.JPG)

#### Decision Tree 
![20](https://user-images.githubusercontent.com/96385070/168955113-cb4ffac3-5284-451b-9165-a4114ea34b2f.png)

#### Random Forest 
![21](https://user-images.githubusercontent.com/96385070/168955132-0ae11827-eaa6-48ff-afd6-cd9dd1f94e80.JPG)
 
#### XGBoost 
![22](https://user-images.githubusercontent.com/96385070/168955148-7c6d3789-8c77-446c-9223-0c421b0da5aa.png)
![23](https://user-images.githubusercontent.com/96385070/168955173-3dee5d93-dae9-4a48-ad3e-69eb72e27984.JPG)
![24](https://user-images.githubusercontent.com/96385070/168955187-7be1ee0f-c06b-42c2-a2a0-7ff18597c54f.JPG)
![final](https://user-images.githubusercontent.com/96385070/168955197-09340b7f-1b28-4526-957d-f231aa430a14.png)

### The best model is the XGBoost 
