![instacart](https://github.com/kiranmaiboda/InstaCart-Market-Basket-Analysis/blob/main/images/instacartpic.png)
# <u> InstaCart-Market-Basket-Analysis  -  Capstone Project
# <u> Introduction
  Instacart is an American technology company that operates as a same-day grocery delivery and pick up service in the U.S. and Canada. Customers shop for groceries through the Instacart mobile app or Instacart.com from various retailer partners. The order is shopped and delivered by an Instacart personal shopper.
 # <u> Objectives
 * Analyze the anonymized data of 3 million grocery orders from more than 200,000 Instacart users open sourced by Instacart
* Find out hidden association between products for better cross-selling and upselling
* Build a Machine Learning model to predict which previously purchased product will be in user’s next order
  # <u> Data Description
 * aisles: This file contains different aisles and there are total 134 unique aisles.
 * departments: This file contains different departments and there are total 21 unique departments.

  * orders: This file contains all the orders made by different users. From below analysis, we can conclude following:
    * There are total 3421083 orders made by total 206209 users.
    * There are three sets of orders: Prior, Train and Test. The distributions of orders in Train and Test sets are similar whereas the distribution of orders in Prior set is          different.
    * The total orders per customer ranges from 0 to 100.
    * Based on the plot of 'Orders VS Day of Week' we can map 0 and 1 as Saturday and Sunday respectively based on the assumption that most of the people buy groceries on               weekends.
    * Majority of the orders are made during the day time.
    * Customers order once in a week which is supported by peaks at 7, 14, 21 and 30 in 'Orders VS Days since prior order' graph.
    * Based on the heatmap between 'Day of Week' and 'Hour of Day,' we can say that Saturday afternoons and Sunday mornings are prime time for orders.
 * products: This file contains the list of total 49688 products and their aisle as well as department. The number of products in different aisles and different departments are      different.

* order_products_prior: This file gives information about which products were ordered and in which order they were added in the cart. It also tells us that if the product was       reordered or not.
    * In this file there is an information of total 3214874 orders through which total 49677 products were ordered.
    * From the 'Count VS Items in cart' plot, we can say that most of the people buy 1-15 items in an order and there were a maximum of 145 items in an order.
    * The percentage of reorder items in this set is 58.97%.
 * order_products_train: This file gives information about which products were ordered and in which order they were added in the cart. It also tells us that if the product was         reordered or not.
    * In this file there is an information of total 131209 orders through which total 39123 products were ordered.
    * From the 'Count VS Items in cart' plot, we can say that most of the people buy 1-15 items in an order and there were a maximum of 145 items in an order.
    * The percentage of reorder items in this set is 59.86%.
# <u> Exploratory Data Analysis
  So there are 206,209 customers in total. Out of which, the last purchase of 131,209 customers are given as train set and we need to predict for the rest 75,000 customers.
  
  ![orders](https://github.com/kiranmaiboda/InstaCart-Market-Basket-Analysis/blob/main/images/orders_eachday.png)
  
  * From the above plots is is evident that most of the orders are placed on 0th day and 1st day which may be saturday and sunday respectively followed by lowest orders on 4th day     which may be wednesday.
  * Most of the orders are placed between 10 A.M and 4 P.M

  ![HeatMap](https://github.com/kiranmaiboda/InstaCart-Market-Basket-Analysis/blob/main/images/HeatMap.png)
  
  * In the above heat map we can see that most of the orders are placed on the saturday mornings and sunday evenings.
  
  ![Frequency](https://github.com/kiranmaiboda/InstaCart-Market-Basket-Analysis/blob/main/images/frequency.png)
  
  * In the above bar plot we can say that the spikes in the plot are observed at the intervals of seven and at the end of the month.
  
  ![department](https://github.com/kiranmaiboda/InstaCart-Market-Basket-Analysis/blob/main/images/department_distrubution.png)
  
  * Produce is the largest department. Now let us check the reordered percentage of each department.
  
  ![depaetment_wise](https://github.com/kiranmaiboda/InstaCart-Market-Basket-Analysis/blob/main/images/department_wise.png)
  
  * Personal care has lowest reorder ratio and dairy eggs have highest reorder ratio.
  
  ![reorder](https://github.com/kiranmaiboda/InstaCart-Market-Basket-Analysis/blob/main/images/reorder.png)
  
  * Looks like the products that are added to the cart initially are more likely to be reordered again compared to the ones added later. This makes sense to me as well since we tend to first order all the products we used to buy frequently and then look out for the new products available.
  
  ### Reorder ratio of Day of week Vs Hour of day
  
  ![reorder_ratio](https://github.com/kiranmaiboda/InstaCart-Market-Basket-Analysis/blob/main/images/reorder%20ratio.png)
  
  # <u> ML Models
  I prepared a dataframe which shows all the products user has bought previously, user level features, product level features, asile and department level features, user-product     level features and the information of current order such as order's day-of-week, hour-of-day, etc. The Traget would be 'reordered' which shows how many of the previously            purchased items, user ordered this time.
  
  I relied on XGBoost as it handles large data, can be parallelized and gives feature importance which gives accuracy of 90.46%. Almost every model we use gives us similar accuracy of 90%.
  # <u> Conclusion
  For modelling we got to use Xgboost,logistic,Randomforest and Lightgbm.Both Xgboost and lightgbm are used to improve the accuracy of the model and I conclude that LGBM is slightly more accurate with 90.46% than XG-Boost in this case.
 # <u> Future Improvements
  * To work with the Apriori's theorem which is a common market basket analysis theorem. 
  * Utilize Collaborative filtering to recommend products to a customer.
  
