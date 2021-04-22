
This is a process to track advertised pricing for mortgage lenders (only tracking online lenders or lenders that advertise online) on 
an hourly basis. The reason it's tracked hourly is that some lenders change prices at peak hours to remain competetive. I wanted to 
know at what point of the month/day/hour would I be able to get the best offer for a purchase/refi. The process takes a snapshot of the 
prices and calculates changes in the following dimensions:
```
1. lender name - name of the lender
2. mortgage type - purchase/refinance
3. state
4. purchase price - price of the house / outstanding UPB
5. down payment - 10%/20%/30%
6. credit score bins - 580-619, 620-639, ..., 720-739, 740+
7. term of the loan - 30 yr, 20 yr,..., 3/1 arm,..., 10/1 arm
8. rate bin - rates in increments of .125
```

Changes are tracked in the following pricing variables:
```
1. apr
2. upfront costs
3. points
4. monthly payments
```

Using the snapshot data, I wanted to create an hour time series for all lenders/products tracking changes in points. This repo
contains a sample file for 2 states for 30 days time series data tracking changes in points:

|column|description|sample_data |
|:-----|:----------|:----------:|
|date|Date when data was collected from online lending sources|2021-01-24|
|month|Month of date column|1|
|week|Week of date column|3|
|hour|hour of date column|3|
|mortgage_type|type of mortgage (purchase vs refinance)|Purchase|
|z_state|State where data is adertised|KY|
|rate_desc|Type of mortgage product (e.g. 3/1 Arm or 30 Yr Fixed)|30 Yr Fixed|
|ltv|Loan to value on the offer|0.8|
|credit_score|Credit score on the offer|750|
|loan_amount|Loan amount bin on the offer|250000|
|lender_name|Lender name|AimLoan.com|
|rate_bin|Advertised online interest rates binned by increments of 0.125|2.5|
|load_datetime|Date/time when data was pullled and interpolated points were calculated|2021-02-23 23:17:45.991494+00|
|points_orig|Original points advertised online||
|points_stg1|Interpolated points (combination of actual 'points_orig' and synthetic interpolated data)|1.699|
|daily_weights|# of times a lender advertised that day|1|
|weekly_weights|#  of times a lender advertised that week|1|
|monthly_weights|# of times a lender advertised that month|3|
