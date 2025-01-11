**Dominos \- Predictive Purchase Order System**

### **1\. Executive Summary**

* Business Problem: Dominos wants to optimize its inventory by predicting future sales and generating purchase orders to avoid both overstocking and stockouts. The goal is to forecast pizza sales and calculate the required quantities of ingredients, ensuring optimal stock levels.  
* Solution: This project involves building a time series forecasting model to predict future sales and creating a purchase order for the ingredients based on the predicted sales. This solution helps Dominos streamline its inventory management, minimize waste, and reduce costs.

### **2\. Business Use Cases**

* Inventory Management: The system helps Dominos maintain optimal stock levels by forecasting future demand and aligning inventory with sales predictions.  
* Cost Reduction: By avoiding over-ordering, the solution reduces waste from expired or unused ingredients.  
* Sales Forecasting: Accurate predictions of future sales help with planning promotions and aligning supply chain operations.  
* Supply Chain Optimization: Streamlined ordering processes reduce disruptions in the supply chain by ensuring the right amount of ingredients are available at the right time.

### 

### **3\. Data Overview**

* **Sales Data**: Historical pizza sales data, including:  
  * `Order Date`, `Pizza Name`, `Quantity Sold`, `Total Price`, `Pizza Category`, and `Ingredients`.  
* **Ingredients Data**: Ingredient details for each pizza type, including:  
  * `Pizza Name`, `Pizza Ingredients`, `Quantity Needed (grams)` per pizza.  
* **Predicted Sales Data**: Sales forecast data for the next 7 days, including:  
  * `Date`, `Predicted Quantity`.

### **4\. Technical Approach**

#### **4.1 Data Preprocessing and Exploration**

* **Data Cleaning**: Removed duplicates, handled missing values, and formatted the data.  
* **Exploratory Data Analysis (EDA)**: Conducted visual analysis to identify sales trends and seasonality.  
* **Feature Engineering**: Generated new features such as `day_of_week`, `order_month`, and `order_week` to capture seasonal trends and improve the forecasting model.

#### **4.2 Model Development**

* **Model Selection**: Chose Facebook's **Prophet** model for time series forecasting due to its ability to handle seasonal trends and missing data.  
* **Model Training**: Trained the model using historical sales data to predict sales for the next 7 days.  
* **Model Evaluation**: Evaluated the model using **Mean Absolute Percentage Error (MAPE)** to ensure prediction accuracy.

#### **4.3 Forecasting**

* **Weekly Sales Forecast**: The model predicted the number of pizzas sold for the next 7 days based on historical trends and seasonality.

### **5\. Ingredient Calculation**

* **Step 1**: For each day’s predicted sales, calculate the total number of pizzas to be sold.  
* **Step 2**: For each pizza type, multiply the predicted quantity by the ingredient quantities (in grams) specified in the ingredient dataset.  
* **Step 3**: Aggregate the total quantity of each ingredient needed for the entire 7-day period.

#### **Example Calculation:**

If **155 pizzas** are predicted to be sold on January 1st, and each pizza requires:

* **40 grams** of Barbecued Chicken, then the total requirement is: 155×40=6200 grams of Barbecued Chicken155 \\times 40 \= 6200 \\, \\text{grams of Barbecued Chicken}155×40=6200grams of Barbecued Chicken

This calculation is repeated for each day and aggregated for the 7-day period.

### **6\. Purchase Order Creation**

* Based on the total ingredient quantities required for the predicted sales, a **Purchase Order** is generated to provide a comprehensive list of the ingredients needed for the week.  
* The columns included in the purchase order:  
  * **Ingredient**: The name of the ingredient (e.g., Barbecued Chicken, Tomatoes).  
  * **Total Quantity Needed (grams)**: The total amount of each ingredient required.  
  * **Units**: The measurement unit (e.g., grams).  
  * **Order Date**: The date when the purchase order was generated.

Ingredient        Ingredient Usage    Units             Date                   

Barbecued 

Chicken                    6200.0           Grams       2016-01-01

Red Peppers            2325.0           Grams       2016-01-01

Green Peppers        3100.0           Grams       2016-01-01  Tomatoes                 4650.0           Grams       2016-01-01         Red Onions              9300.0           Grams       2016-01-01

### **7\. Results**

* **Predicted Sales**: Accurate prediction of pizza sales for the next 7 days.  
* **Ingredient Requirements**: Clear calculation of the total ingredient quantities needed to meet the forecasted sales, allowing for efficient inventory management.  
* **Purchase Order**: A detailed, ready-to-use purchase order that lists the required ingredients for the predicted sales period.

### **8\. Business Impact**

* **Optimized Inventory Management**: The solution ensures that the right amount of ingredients is stocked, reducing the likelihood of overstocking or stockouts.  
* **Reduced Costs**: By aligning ingredient orders with predicted sales, Dominos can minimize waste from unused ingredients, lowering costs.  
* **Better Decision-Making**: Accurate sales forecasts allow Dominos to plan promotions and manage supply chains more effectively, improving overall business operations.

### **9\. Future Work**

* **Explore Additional Forecasting Models**: Test other models like ARIMA, LSTM to compare performance.  
* **Extend Prediction Period**: Predict sales and create purchase orders for longer periods, such as a month.


### **11\. Tools and Technologies Used**

* **Python**: For data analysis, modeling, and report generation.  
* **Pandas**: For data manipulation and cleaning.  
* **Prophet**: For time series forecasting.  
* **Matplotlib/Seaborn**: For visualizing data trends and forecast results.  
* **Excel/CSV**: For generating the final purchase order.

### **12\. References**

* **Facebook Prophet**: Time series forecasting model.  
* **Pandas Documentation**: Data manipulation library.  
* **Python**: General-purpose programming language.

### **Conclusion**

The **Dominos Predictive Purchase Order System** project effectively predicts future pizza sales and automates the generation of ingredient purchase orders. This solution optimizes inventory, reduces costs, and ensures the smooth operation of Dominos' supply chain.
