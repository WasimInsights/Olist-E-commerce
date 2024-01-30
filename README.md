
# Olist E-commerce-Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/a09b1900-189b-4dc5-988d-e54633ea024a/ReportSectionef0d17b75c4d6da856ba?experience=power-bi

## Problem Statement

Weekday Vs Weekend (order_purchase_timestamp) Payment Statistics

Number of Orders with review score 5 and payment type as credit card.

Average number of days taken for order_delivered_customer_date for pet_shop

Average price and payment values from customers of sao paulo city

Relationship between shipping days (order_delivered_customer_date - order_purchase_timestamp) Vs review scores.


Customer Satisfaction: The project has identified that almost 57% of customers are neutral or dissatisfied, while around 43% are satisfied. This indicates a significant opportunity for service improvement.

Operational Efficiency: The project has also found that the average delay in both arrival and departure is 15 minutes. This suggests a need for strategies to reduce these delays and enhance operational efficiency.

The Dashboard is divided in 3 sections 
1) Sales insight.
2) Logistics analysis.
3) Customer satisfaction. 


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present except column named "Arrival Delay".
- Step 5 : For calculating average delay time, null values were not taken into account as only less than 1% values are null in this column(i.e column named "Arrival Delay") 
- Step 6 : In the report view, under the view tab, theme was selected.
- Step 7 : Since the data contains various ratings, thus in order to represent ratings, a new visual was added using the three ellipses in the visualizations pane in report view. 
- Step 8 : Visual filters (Slicers) were added for four fields named "Payment mode", "Product category", "State" & "Year".
- Step 9 : Three card visuals were added to each dashboard
           Using visual level filter from the filters pane, basic filtering was used & null values were unselected for consideration into average calculation.
           
           Although, by default, while calculating average, blank values are ignored.
- Step 10 : An advanced visual was also added to the report design area representing customer's sentiments. While creating this visual, field named "weekdays & weekends" was also added to the Legends bucket, thus number of customers are also seggregated according their purchase timimngs. 
- Step 11 : Ratings Visual was used to represent different ratings mentioned below,

  (a) Payment mothods.

  (b) Dilivery sattus.
  
  (c) Product quality
  
  
In our dataset, Some parameters were assigned value 0, representing those parameters are not applicable for some customers.

All these values have been ignored while calculating average rating for each of the parameters mentioned above.

- Step 12 : In the report view, under the insert tab, two text boxes were added to the canvas, in one of them name of the airlines was mentioned & in the other one company's tagline was written.
- Step 13 : In the report view, under the insert tab, using shapes option from elements group a rectangle was inserted & similarly using image option company's logo was added to the report design area. 
- Step 14 : Calculated column was created in which, customers were grouped into various groups as per time of day. similarly delivery performance was aslo categorised as on time and delayed based on actual dilivery time and estimated time.


        
- Step 15 : New measure was created to find total count of distinct orders.

Following DAX expression was written for the same,
        
        total orders = COUNT(olist_orders[order_ID])
        
A card visual was used to represent count of customers.

![Screenshot 2024-01-30 095542](https://github.com/WasimInsights/Test/assets/158030674/90deb434-d6ce-47e1-88c6-e7cc9f96624c)

        
 - Step 16 : New measure was created to find total revenue,
 
 Following DAX expression was written to find % of customers,
 
         Total Revenue = SUM(olist_order_payments_dataset[payment_value]
 
 A card visual was used to represent this amount
 
 Snap of Total Revenue generated
 
![Screenshot 2024-01-30 094903](https://github.com/WasimInsights/Test/assets/158030674/ebb32fc4-6503-446f-958c-24ff537314b4)

 
 - Step 17 : New measure was created for an advanced visual in third dashboard 
 
 Following are 2 DAX expression was written to find total distance,
 
         Emot = IF([Total review score]>403000,"wink",IF([Total review score]>200000,"laugh",IF([Total review score]>180000,"worried","angry")))
         Action = IF([Total review score]>403000,"yuhoo",IF([Total review score]>200000,"superperfect",IF([Total review score]>180000,"thinkinghmm","angryfrustrated")))
    
 A advance visual was used to represent this customer sentiments.
 
 
![Screenshot 2024-01-30 101137](https://github.com/WasimInsights/Test/assets/158030674/92452923-1221-44c4-b027-70d49d62db6d)
 
# Snapshot of Dashboard (Power BI DESKTOP)
 ## Sales Dashboard

![Screenshot 2024-01-18 134300](https://github.com/WasimInsights/Test/assets/158030674/5bda3336-e84e-44bf-bdb6-a69b70f3e711)

## Logistics Dashboard

![Screenshot 2024-01-30 124722](https://github.com/WasimInsights/Test/assets/158030674/22f07bef-bdc9-439b-a283-02768fded21c)

## Customers Dashboard

![Screenshot 2024-01-18 134400](https://github.com/WasimInsights/Test/assets/158030674/954fc12f-aef4-40e8-95c3-47f0beb48220)

# Insights

A three page report was created on Power BI Desktop.

Following inferences can be drawn from the dashboard;

### [1] Total Number orders = 1,12,280

   Total weekdays orders = 86,778 (77.28 %)

   Total weekends orders = 25,502 (22.71 %)
   
   "Order update! 📦

Weekdays are buzzing with 86,778 orders, making up 77.28% of the total 🗓️

Weekends aren’t too shabby either with 25,502 orders, accounting for 22.71% of the total 🎉"


           thus, higher number of orders are on weekdays.
           

  
  while calculating average rating, null values have been ignored as they were not relevant for some customers. 
  
  These ratings will change if different visual filters will be applied.  
  
  ### [2] Logistics Delay 
  
      a) Average delay in arrival(minutes) - 15.09
      b) Average delay in departure(minutes) - 14.71

We’re spread across **4,110** distinct cities 🏙️.

We have a presence in **27** states 🗺️.

We’ve generated a total revenue of **$2.256M** from freight 💰.

Average delay will change if different visual filters will be applied.


 ### [3] Some other insights
 
 ### Product performance (2017-2018)
 
"Revenue update! 💰
- **Health & Beauty** is glowing with a total revenue of **$1.44M** from **8,791 orders** 💅

- **Watches & Gifts** clocked in a total revenue of **$1.31M** from **5,691 orders** 🎁

- **Bed & Bath Tables** made a splash with a total revenue of **$1.26M** from **9,412 orders** 🛏️"
 
         thus, maximum revenue generated by Health & Beauty.
 
 ### State wise Sales
 
 1)  **São Paulo** state just dropped a cool **$2.17M** in revenue 💰.
 
 2)  **Rio de janeiro** state just dropped a cool **$1.15M** in revenue 💰.
 
 3)  **Belo horizonte** state just dropped a cool **$0.42M** in revenue 💰.
 
 4)  **Brasilia** state just dropped a cool **$0.35M** in revenue 💰.

 
         “Thus, ‘São Paulo’ is leading the game with the highest revenue. That’s impressive! 💰🚀”

         
### Customer Type

1) “**Morning** time peeps make up **36.8%** of our customers. 🌞”

2) “**Afternoon** time? That’s **25.38%** of our customers. 🌤️”

3) “**Evening** time customers? We’ve got **18.93%** of them. 🌆”

4) “**Night owls** represent **18.88%** of our customers. 🌙”
       
       "“Thus, 'morning time' customers are leading the pack. Rise and shine! 🌞"

### Review score

* On **weekdays**, **77 %** of customers are loving us with a **4.9** review score 📈

* On **weekends**, we’ve got a solid **4.3** review score from **23 %** of customers 🙌

        “So, our customers are really vibing with us on weekdays. That’s awesome! 🎉 But hey, let’s not forget about the weekends. We need to ramp up our game to increase customer traffic then as well. Let’s brainstorm some cool ideas to make their weekend experiences with us just as enjoyable! 💡”

# Reccomendations
“Level Up! 🚀 Your Ultimate Guide to Crushing Sales Goals in 2024! 💰📈”

![Screenshot 2024-01-30 125300](https://github.com/WasimInsights/Test/assets/158030674/742c0580-34c4-4094-8c1a-0342845e413b)

“And that’s a wrap! 🎬 We’ve journeyed through data, crunched numbers, and unlocked insights. But remember, this is just the beginning. The real magic happens when these insights are put into action. So, let’s gear up and get ready to conquer the market with our newfound knowledge. Here’s to making waves in 2024! 🚀💡”
