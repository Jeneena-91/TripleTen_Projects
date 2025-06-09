# Instacart Customer Shopping Patterns – EDA Project

## Project Overview

This project focuses on exploratory data analysis (EDA) of a modified version of the Instacart dataset. Instacart is a popular grocery delivery platform that allows customers to place orders online. The goal of this project is to clean and analyze the data to gain insights into customer shopping behaviors, including **shopping times, item popularity, reorder trends, and user engagement**.

This analysis simulates real-world data problems where datasets are imperfect and assumptions need to be tested and validated using data.

---

## Datasets Used

- `instacart_orders.csv`: Contains order-level information (user, time, day, etc.)
- `order_products.csv`: Contains product-level information for each order
- `products.csv`: Contains product names and corresponding IDs
- `aisles.csv`: Maps aisle IDs to aisle names
- `departments.csv`: Maps department IDs to department names

---

## Project Objectives

### Data Preprocessing

- Verified and corrected data types
- Identified and addressed missing and duplicate values
- Explained causes and handling strategies for missing/duplicate data

###  Exploratory Data Analysis (EDA)

#### A. **Basic Behavioral Trends**
- Verified `order_hour_of_day` and `order_dow` value ranges
- Visualized shopping frequency by hour and day of the week
- Analyzed wait times between orders

#### B. **User and Product-Level Insights**
- Compared shopping hour distributions on Wednesdays vs Saturdays
- Analyzed order counts per customer
- Identified top 20 most frequently ordered products

#### C. **Advanced Analysis (Selected Tasks)**
- Analyzed number of items per order
- Identified top 20 most frequently reordered products
- Calculated reorder proportion per product and per user
- Identified most common first items added to carts

---

## Key Findings

- **Shopping Trends**: Most orders occur between **10 AM and 4 PM**. Weekends, particularly **Saturday and Sunday**, show higher activity than weekdays.
- **Reorder Behavior**: A significant portion of purchases are reorders, reflecting recurring shopping needs (e.g. milk, bananas).
- **Order Volume**: Most customers order fewer than 10 items per purchase.
- **Popular Products**: Bananas, organic strawberries, and other staple items are among the most frequently ordered and reordered.

---

## Technologies Used

- **Python** – Main programming language
- **Pandas** – Data cleaning and manipulation
- **NumPy** – Numerical operations
- **Matplotlib & Seaborn** – Data visualization
- **Jupyter Notebook** – Interactive exploration and documentation
- **Git & GitHub** – Version control and code collaboration

---


