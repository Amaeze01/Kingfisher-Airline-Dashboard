# Kingfisher Airlines Dashboard Analysis

## Problem Statement

This dashboard provides Kingfisher airlines with a comprehensive analysis of customer satisfaction and service efficiency. It highlights critical areas where improvements can be made based on customer ratings and operational metrics, such as flight delays. This tool allows airlines to address dissatisfaction (57% of customers are neutral or dissatisfied) and identify opportunities to reduce delays (average delay of 15 minutes for arrivals and departures). By leveraging this data, kingfisher airlines can make informed decisions to improve service quality, enhance customer experience, and reduce operational inefficiencies.

## How I Plan on Solving the Problem
To address the problem, I will create a comprehensive dashboard using Power BI. The dataset will first be cleaned and preprocessed to ensure data quality. Key metrics like customer satisfaction ratings, average delay times, and customer demographics will be analyzed. Through Power BI’s interactive visuals and filters, the dashboard will provide actionable insights, enabling the airline to identify improvement areas in service, such as reducing delays and enhancing customer satisfaction. This will guide the airline's efforts in making informed decisions to improve overall performance.

## Methodology
### Data Preparation: 
- Step 1: Imported a CSV dataset into Power BI.
- Step 2: Used power query editor for profiling and ensuring data quality (checked for column distribution, quality, and profiling on the entire dataset).
- Step 3: Handled null values in the "Arrival Delay" column, which had less than 1% missing data, ensuring accurate analysis without biasing delay metrics.
### Visual Design and Reporting
- Step 4: Applied a custom theme to the report through the view tab for a consistent visual style.
- Step 5: Added a new visual to represent customer ratings using the ellipses in the visualizations pane.
- Step 6: Integrated slicers for "Class," "Customer Type," "Gate Location," and "Type of Travel" to filter data dynamically.
- Step 7: Added two card visuals to display average departure and arrival delays, filtering out null values for accurate average calculations.
           
           Although, by default, while calculating average, blank values are ignored.
- Step 8: A bar chart was also added to the report design area representing the number of satisfied & neutral/unsatisfied customers. While creating this visual, field named "Gender" was also added to the legends bucket, thus number of customers are also seggregated according the gender. 
- Step 9: Ratings visual was used to represent different ratings mentioned below,

  (a) Baggage Handling

  (b) Check-in Services
  
  (c) Cleanliness
  
  (d) Ease of online booking
  
  (e) Food & Drink
  
  (f) In-flight Entertainment

  (g) In-flight Service
  
  (h) In-flight wifi service
  
  (i) Leg Room service
  
  (j) On-board service
  
  (k) Online boarding
  
  (l) Seat comfort
  
  (m) Departure & arrival time convenience
  
In the dataset, certain parameters were assigned a value of 0 to indicate non-applicability for some customers. These values were excluded from the calculation of average ratings for each parameter.
- Step 10: Two text boxes were added to the report canvas, one displaying the airline's name and the other the company’s tagline.
- Step 11: A rectangle shape and the company logo were inserted into the design area.
- Step 12: A calculated column was created to categorize customers into different age groups.

For creating new column following DAX expression was written;
       
        Age Group = 
        
        if(airline_passenger_satisfaction[Age]<=25, "0-25 (25 included)",
        
        if(airline_passenger_satisfaction[Age]<=50, "25-50 (50 included)",
        
        if(airline_passenger_satisfaction[Age]<=75, "50-75 (75 included)",
        
        "75-100 (100 included)")))
        
Picture of the calculated new column ,

![Snap_1](https://user-images.githubusercontent.com/102996550/174089602-ab834a6b-62ce-4b62-8922-a1d241ec240e.jpg)

        
- Step 13: New measure was created to find total count of customers.

The following DAX expression was written for the same,
        
        Count of Customers = COUNT(airline_passenger_satisfaction[ID])
        
A card visual was used to represent count of customers.

![Snap_Count](https://user-images.githubusercontent.com/102996550/174090154-424dc1a4-3ff7-41f8-9617-17a2fb205825.jpg)

        
 - Step 14: New measure was created to find  % of customers,
 
 The following DAX expression was written to find % of customers,
 
         % Customers = (DIVIDE(airline_passenger_satisfaction[Count of Customers], 129880)*100)
 
 A card visual was used to represent this perecntage.
 
 Snap of % of customers who preferred business class
 
 ![Snap_Percentage](https://user-images.githubusercontent.com/102996550/174090653-da02feb4-4775-4a95-affb-a211ca985d07.jpg)

 
 - Step 15: New measure was created to calculate total distance travelled by flights & a card visual was used to represent total distance.
 
 The following DAX expression was written to find total distance,
 
         Total Distance Travelled = SUM(airline_passenger_satisfaction[Flight Distance])
    
 A card visual was used to represent this total distance.
 
 
 ![Snap_3](https://user-images.githubusercontent.com/102996550/174091618-bf770d6c-34c6-44d4-9f5e-49583a6d5f68.jpg)
 
 ### Publishing
 - Step 16: The final report was published to Power BI Service, enabling interactive data exploration and sharing across the organization.



 
 # Kingfisher Airline Dashboard (Power BI DESKTOP)

![Dashboard_upload](https://user-images.githubusercontent.com/102996550/174074051-4f08287a-0568-4fdf-8ac9-6762e0d8fa94.jpg)

# Insights
### Customer Satisfaction:
1. #### Satisfaction Rates:
- 43% of customers are satisfied, while 57% are neutral or dissatisfied, highlighting a significant opportunity for service improvements.
- Female customers showed slightly higher satisfaction levels (21.76%) compared to male customers (21.68%).
### Service Ratings:
2. #### Service Quality:
- In-flight services received moderate ratings (e.g., 3.36 / 5 for in-flight entertainment, 3.44 / 5 for seat comfort).
- In-flight WiFi was rated the lowest (2.81 / 5), indicating an area for significant improvement.
3. #### Delay Metrics:
- Average arrival delay: 15.09 minutes.
- Average departure delay: 14.71 minutes.
### Customer Segmentation:
4. #### Class of Travel:
- Business class accounted for 47.87% of travelers, followed by economy class at 44.89%.
5. #### Age Groups:
- Most customers (52.44%) fall in the 25-50 age group, providing insights into target demographics for customer engagement strategies.
6. #### Customer Type:
- 81.69% of customers were returning, highlighting loyalty but also providing an opportunity to convert more first-time flyers (18.31%) into repeat customers.
7. #### Type of Travel:
- 69.06% of customers were traveling for business purposes, while 30.94% traveled for personal reasons, reinforcing the importance of focusing on business travelers.
### Conclusion
The Kingfisher Airlines Dashboard provides actionable insights into key performance indicators like customer satisfaction, service quality, and operational efficiency. By addressing areas such as in-flight WiFi and delays, airlines can improve their services, ultimately enhancing the customer experience. The dashboard’s interactive features, including segment filters, enable data-driven decision-making to reduce inefficiencies, retain customers, and increase satisfaction across various demographic groups.

