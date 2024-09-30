# **Optimizing Query Performance in E-commerce Databases**

## **Project Overview**
In this project, I designed a comprehensive benchmarking system to evaluate the performance of SQL queries on an e-commerce database under different optimization scenarios. The project explores how database indexing strategies, both system-managed and user-defined, affect the execution time of queries. This study uses a large e-commerce dataset that simulates real-world transactions, enabling insights into performance improvements achievable through efficient database structuring.

---

## **Motivation**
As e-commerce platforms handle millions of transactions, the efficiency of database queries becomes critical for system performance. Understanding how database indices influence query execution times can lead to more efficient database management, especially in data-heavy environments. My goal was to create a scalable solution that evaluates query performance across different database sizes and index optimization strategies.

---

## **Data and Setup**

**Dataset**:  
The project uses the Brazilian e-commerce dataset from Kaggle, consisting of the following key tables:
- **Customers**: Contains customer IDs and postal codes.
- **Sellers**: Contains seller IDs and postal codes.
- **Orders**: Contains order IDs and customer IDs.
- **Order_items**: Contains order details (order IDs, item IDs, product IDs, and seller IDs).

**Database Sizes**:
- **small.db**: ~10k customers, ~500 sellers, ~10k orders, ~2k order items.
- **medium.db**: ~20k customers, ~750 sellers, ~20k orders, ~4k order items.
- **large.db**: ~33k customers, ~1k sellers, ~33k orders, ~10k order items.

Three versions of the database were created to measure performance across varying sizes, each enforcing the required primary and foreign key constraints.

---

## **Project Structure**

### **Queries Evaluated**  
The project evaluated four key queries:
1. **Query 1**: Count the number of orders with more than one item placed by customers from a specific postal code.
2. **Query 2**: Extend Query 1 by adding a condition to count orders that exceed the average number of items.
3. **Query 3**: Rewrite Query 2 without using views.
4. **Query 4**: Identify the number of unique seller postal codes for a random customer with more than one order.

These queries reflect typical e-commerce operations like customer behavior analysis and order management.

---

## **Problem Statement**
The core objective of the project was to assess the impact of database indexing on the performance of four key queries commonly used in e-commerce platforms. Specifically, the project analyzed:
- **Uninformed**: No indices or key constraints; auto-indexing is disabled.
- **Self-Optimized**: Primary/foreign keys are set; SQLite auto-indexing is enabled.
- **User-Optimized**: Custom indices created on frequently queried columns for optimization.

---

## **Files and Scripts**
Each query is executed 50 times across the three database sizes and indexing scenarios. Execution times are averaged and visualized in charts.

- `Q1.py`: Executes Query 1 and collects performance data.
- `Q2.py`: Executes Query 2 (using a view) and collects performance data.
- `Q3.py`: Executes Query 3 (without a view) and collects performance data.
- `Q4.py`: Executes Query 4 and collects performance data.

Charts are generated for each query to visualize query execution time (in milliseconds) under each scenario and database size.

---

## **Results**
The performance results for each query show a significant difference depending on the indexing scenario:
- **Uninformed Scenario**: Slowest execution due to full table scans.
- **Self-Optimized Scenario**: Moderate performance improvements from SQLite’s auto-indexing.
- **User-Optimized Scenario**: Fastest query execution due to targeted indices.

Each query's performance was visualized in stacked bar charts to show runtime differences across different database sizes and indexing strategies.

---

## **Visualizations**
The project generates performance charts for each query, comparing the execution times for the three database sizes under each indexing strategy. The charts provide a visual representation of how the use of indices can dramatically reduce query execution time in large databases.

- `Q1_chart.png`
- `Q2_chart.png`
- `Q3_chart.png`
- `Q4_chart.png`

---

## **Technologies Used**
- **SQLite**: For database management and running queries.
- **Python**: For scripting, executing queries, collecting data, and generating charts.
- **Matplotlib**: For visualizing query performance.

---

## **Conclusion**
This project provided valuable insights into the importance of database optimization in high-traffic e-commerce environments. User-defined indices significantly improved the performance of complex queries, demonstrating the effectiveness of database tuning for large datasets. This research can be extended to other types of databases and queries, providing a basis for developing scalable, high-performance e-commerce platforms.

---

## **How to Run the Project**
1. Download the project files.
2. Place the datasets in the same directory as the Python scripts.
3. Run each Python script (`Q1.py`, `Q2.py`, `Q3.py`, `Q4.py`) to execute the queries on the databases and generate performance charts.

---

## **Acknowledgements**
This project is based on research into query performance optimization using SQLite. The dataset was sourced from Kaggle’s [Brazilian E-commerce Dataset](https://www.kaggle.com/olistbr/brazilian-ecommerce).

---

