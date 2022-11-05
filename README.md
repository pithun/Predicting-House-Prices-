# Predicting-House-Prices-

## 📜 Description
An ML task from a competition on [Machine hack](https://machinehack.com/) with comprehensive EDA and Model building to predict house prices. The dataset had some 
abstract datapoint which cause the models to have a very high RMSE. 

I ended the competition with rank of 13th. 
![machine_hack](https://user-images.githubusercontent.com/57589300/200123975-50d7bf34-8e8f-4e37-94eb-5e1b6ed77755.jpg)

## 📓 Dataset
Train: 134683 rows x 21 columns 

Test: 57722 rows x 20 columns

Data description:

'Property_ID', = Unique id of the property

'room',  No. of rooms available

'layout_type',  ['BHK' 'RK']

'property_type', = ['Apartment' 'Studio Apartment' 'Independent Floor' 'Independent House' 'Villa' 'Penthouse']

'locality',  = Overall Locality description

'price', = Rent in INR

'area', = in Square Feet

'furnish_type', ['Semi-Furnished' 'Furnished' 'Unfurnished']

'bathroom',: No. of Bathrooms

'city', : ['Ahmedabad' 'Bangalore' 'Chennai' 'Delhi' 'Hyderabad' 'Kolkata' 'Mumbai' 'Pune']

'parking_spaces',: 1 or 0  : 1 = Yes, 0 = No

'floor',: Floor from 0 to 20

'pet_friendly', : 1 or 0  : 1 = Yes, 0 = No

'power_backup', : 1 or 0  : 1 = Yes, 0 = No

'washing_machine',: 1 or 0  : 1 = Yes, 0 = No

'air_conditioner', : 1 or 0  : 1 = Yes, 0 = No

'geyser/solar',: 1 or 0  : 1 = Yes, 0 = No

'security_deposit', Amount of security Deposit

'neighborhood', : Nearest Metro/Bus/Mall in meters

'CCTV/security' : CCTV available 1 or 0  : 1 = Yes, 0 = No

'lift': 1 or 0  : 1 = Yes, 0 = No

Task: Regression

Data Type: Continuous and Categorical

## 💡 Motivation and Context

It's fascinating to easily predict prices of houses using basic regression models. This repo contains basic implemetation of concepts like using datascience 
libraries (numpy, pandas, etc.), data preprocessing (applying log transformation to normalize data distribution) and use of machine learning algorithms.

## Approach
### 1. Data Cleaning
- Missing Value Check: There was no missing values in the dataset
- Duplicate Check: There was no duplicate entry in the dataset
- Consistency Check: Values in the locality was inconsistent as we had misspeled similar words e.g Amru**taha**lli' and 'Amru**thaha**lli
- Validity Check: We had some abstract values as shown below.
![validity](https://user-images.githubusercontent.com/57589300/200125691-b8506ebd-7116-4d41-a22a-da1a28dcc599.jpg)

### 2. EDA
Most of the houses in the dataset was from mumbai

![city_distr](https://user-images.githubusercontent.com/57589300/200125947-5edeae68-87c9-4037-84ab-7f6103400c70.jpg)

Having removed outliers, we see the average price of houses with different number of rooms and bathrooms

![room_bathroom](https://user-images.githubusercontent.com/57589300/200126062-600bf074-7249-48b6-bff4-d75150ee2acf.jpg)

### 3. Feature Engineering 
The security deposit which is an amount of money that a renter pays when beginning to rent property (such as an apartment) and that can be used to pay for any damage that the renter causes to the property was skewed so I applied a log transformation to normalize the distribution.

#### skewed
![sec_skewed](https://user-images.githubusercontent.com/57589300/200125343-272664ea-51d1-4a91-a1d9-916111938b29.jpg)

#### log transformed
![sec_logt](https://user-images.githubusercontent.com/57589300/200125361-8b4d9c67-049f-4974-a04e-3b85c6ee4a7e.jpg)

The city was integer encoded as distribution of houses from some cities were higher than others.

![distribution](https://user-images.githubusercontent.com/57589300/200125874-18faff09-55af-4e41-8837-36c0b7a11bdf.jpg)


## 🧰 Technologies used

- Pandas
- Numpy
- Matplotlib
- Scikit-learn
- Tensorflow
- Python

🔧 Algorithms Implemented - (RMSE)
- LGBMRegressor - 28541
- XGBRegressor - 27810
- LinearRegression - 34631
- Ridge Regression - 34666
- Neural Network - 28106
