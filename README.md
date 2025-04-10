# NYC Taxi (Work in Progress)

This is an early-stage project where I'm exploring New York City yellow taxi trip data from January 2024.  
We want to find patterns in how people use taxis — where and when trips happen, how long they take, and more.

**Project Goal:**  
Predict the average amount of money spent on a casual taxi ride in NYC for each region, given a specific date and hour — so that taxi drivers can better understand when and where to operate.

**Data source:**  
- NYC Taxi & Limousine Commission: https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page  
- Data dictionary: https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf

---

## 1. Data Exploration

- Reviewed all 19 available features  
- Identified which features can be dropped (e.g., irrelevant or suspicious ones like negative payments)  
- Checked data types and looked for inconsistencies  
- Started thinking about features we might want to add

---

## 2. Cleaning & Prepering

- Filtered for January 2024 only  
- Dropped irrelevant or invalid rows  
- Fixed data types (e.g., datetime fields, location IDs)  
- Cleaned up payment information
- Grouped the data by pickup datetime and location  
- Calculated total fare amount and number of rides for each group  
- Created a new dataset to serve as input for modeling

---

## 3. First Benchmark Model

- Ran a simple Decision Tree Regressor  
- Tried two depths — both performed similarly
- 
**Features used in this version:**
- Pickup location
- Day and hour
- Mean fare amount
- Number of rides

## Current Issues

- The model isn’t predicting high values  
- The model predicts low valuse (close to zero) 
- Need to isolate and investigate very low-value cases  
- Might require better aggregation or different target definitions  

---


## 4. Feature Engineering

- Added the following new features:
  - Weekend/weekday indicator
  - Day of the week
  - Late-night / early-morning connection


## Next Steps

- Retrain the model with the new features 
- Evaluate performance changes and track errors  
- Try more models 
- Visualize predictions vs. actuals over time and space  
- Possibly revisit aggregation strategy (e.g., dropoff vs. pickup)  
