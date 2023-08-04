# Superstore-Sales-Analysis

# Introduction
In today's business landscape, data-driven decision-making is pivotal for gaining a competitive edge. Extracting insights from vast datasets empowers informed choices and operational efficiency. This report analyzes the sample superstore dataset, aiming to uncover actionable insights and strategic recommendations.

The dataset mirrors real-world retail complexities, spanning sales, customer behavior, inventory, and promotions. Our exploration sheds light on influential factors, guiding business success.

This report starts with a dataset overview and delves into specific facets, supported by visualizations and statistics. It culminates in actionable recommendations, aligning strategies with data-backed insights for innovation and growth.

Join us on this data journey, uncovering patterns and correlations to drive business strategies. Let's explore valuable insights and transform them into actionable growth plans.

# Activity
Utilizing the provided superstore dataset, our objective is to conduct a thorough analysis and derive valuable business insights in response to the following pivotal questions:

1. **Comprehensive Sales Performance and Profitability by Product Categories:**
   We will delve into the dataset to unravel the holistic sales performance and profitability across diverse product categories. This examination will furnish a deeper understanding of each category's contribution to the overall revenue and profitability of the superstore.

2. **Variation in Sales Figures Across States and Top Revenue-Contributing States:**
   Our analysis will elucidate the fluctuations in sales figures across different states, highlighting those states that significantly bolster the superstore's total revenue. By identifying key revenue contributors, we aim to provide strategic insights for targeted efforts.

3. **Identification of Seasonal Patterns and High-Low Sales Months:**
   Through meticulous examination, we will identify any discernible seasonal patterns ingrained within the sales data. This scrutiny will reveal the months characterized by elevated and diminished sales levels, facilitating the recognition of peak and lean periods.

4. **Customer Distribution across Diverse Regions:**
   Our exploration extends to the distribution of customers across various regions. By discerning the concentration of customers in different areas, we will provide valuable insights that can guide regional strategies and marketing endeavors.

5. **Insights into Customer Segments and Their Impact on Sales and Profits:**
   By dissecting purchasing behaviors, sales patterns, and corresponding profits, we will unlock insights into distinct customer segments. This analysis will shed light on how different segments contribute to the overall success of the superstore.

6. **Identification of Top-Spending Customers and Their Revenue Contribution:**
   Our investigation aims to identify the most prominent spenders among the superstore's customer base. By quantifying their revenue contribution within the specified interval, we will highlight the pivotal role of these customers in driving revenue growth.

Through this rigorous data analysis, we strive to provide actionable insights that empower effective decision-making and strategic planning, fostering enhanced performance and competitiveness for the superstore.

# Skill Demonstrated
1. Data Cleaning
2. Data Manipulation
3. Pivot table
4. Visualisation

# Raw Data
The Sample Superstore Dataset consists of 20 essential columns and an impressive 9994 records. It encompasses crucial parameters that offer invaluable insights into the operations of the superstore business. This dataset provides a comprehensive glimpse into a retail environment, presenting a diverse array of information that mirrors the intricate dynamics of real-world business operations. With multiple dimensions and variables, the dataset serves as a portrayal of a modern retail ecosystem, spanning pivotal aspects such as sales transactions, customer profiles, geographical attributes, product categories, and more.

Each entry within the dataset corresponds to a distinct sales transaction, shedding light on key details such as the products acquired, quantities purchased, pricing structures, and associated costs. Furthermore, customer particulars, including their segments and geographical regions, offer a glimpse into the diverse consumer base that actively engages with the superstore.

One notable feature of the dataset is the inclusion of order dates, which indicate the timing of transactions. This temporal element provides opportunities for analyzing seasonal trends, identifying peak purchase periods, and uncovering patterns that influence consumer buying behaviors.

Additionally, the dataset delves into intricate details concerning shipping modes, elucidating the various choices available to customers for receiving their purchases. This information proves instrumental in evaluating the effectiveness of delivery strategies and gaining insights into customer preferences regarding different shipping methods.

The superstore dataset holds the potential to unveil critical insights across various domains, encompassing realms such as sales analytics, customer behavior assessment, inventory management, and the evaluation of promotional effectiveness. Its diverse array of attributes positions it as a powerful resource for drawing well-founded conclusions, devising strategic plans, and making informed decisions across a spectrum of business dimensions.

# Data Cleaning
To ensure the cleanliness of the dataset, a comprehensive evaluation was initially conducted to address any potential issues. Upon meticulous inspection, it was determined that the dataset exhibited completeness across all rows and columns, with no instances of missing values.

Subsequently, an examination for duplicate rows was undertaken, revealing one duplicate entry. Swift action was taken to rectify this, utilizing Excel's built-in "Remove Duplicates" function, resulting in the prompt elimination of the redundant record.

To confirm the accuracy of data values within each column. It came to light that the order date and ship date values exhibited a combination of date and text data types, potentially compromising the dataset's uniformity. An attempt was made to rectify this by utilizing Excel's "Text to Columns" feature, aiming to convert the entire column to date format. However, it was observed that certain date values were not successfully parsed during this process.

To address this challenge effectively, a decision was made to leverage the capabilities of the R programming language. This involved the utilization of the `as.Date()` function, a fundamental tool for converting string-based entries to standardized date format. The process was implemented as follows: 

```
superstore$OrderDate <- as.Date(superstore$OrderDate, format = "%m/%d/%Y")
```
```
superstore$ShipDate <- as.Date(superstore$ShipDate, format = "%m/%d/%Y")
```
Through this meticulous approach, the order and ship date columns were successfully reformatted, aligning with the desired date data type. This methodological combination of Excel's functionalities and the versatility of R programming ensured the dataset's cleanliness and enhanced its analytical integrity.

# Data Manipulation

To extract insightful value from our dataset and proficiently address the Superstore business inquiries, we will harness the capabilities of pivot tables as a potent analytical and data summarization tool. Here's a comprehensive overview of how we will adeptly employ pivot tables to achieve our objectives:

1. **Comprehensive Sales Performance and Profitability by Product Categories:**
   - A pivot table will be constructed, with the "Category" field placed in the Rows area and the "Sales" and "Profit" fields in the Values area.
   - This arrangement will deliver an illuminating breakdown of sales and profit across distinct categories, facilitating the identification of potential areas for growth.

2. **Variation in Sales Figures Across States and Identification of Top Revenue-Contributing States:**
   - The "State" field will be positioned in the Rows area, with "Sales" in the Values area, enabling a thorough analysis of revenue distribution across states.
   - By scrutinizing this pivot table, we can discern patterns and spotlight states that make substantial revenue contributions to the enterprise.

3. **Identification of Seasonal Patterns and High-Low Sales Months:**
   - To unveil seasonal trends and highlight months with noteworthy sales fluctuations, we will incorporate the "Month" field in the Rows area and "Sales" in the Values area.
   - Given that a specific month column isn't available, we'll derive the month information from the order date column. A formula will be employed for this purpose: ``` =TEXT($B$2:$B$9993, "mmmm") ```
   - This pivot table configuration will empower us to visualize the undulations in monthly sales, aiding the identification of peak sales intervals and potential influencing factors.

4. **Customer Distribution across Diverse Regions:**
   - Our pivot table design will involve the inclusion of the "Region" field in the Rows area, along with "Customer Name" in the Values area.
   - The outcome will present an informative tally of customers within each region, enabling a comprehensive understanding of customer distribution.

5. **Insights into Customer Segments and Their Impact on Sales and Profits:**
   - A pivot table will be fashioned, with the "Segment" field designated for the Rows area and the "Sales" field for the Values area.
   - This arrangement will provide a lucid representation of sales contributions from distinct segments, thereby facilitating the identification of areas primed for growth.

6. **Identification of Top-Spending Customers and Their Revenue Contribution:**
   - For a nuanced comprehension of customer behavior, we will integrate the "Customer Name" field in the Rows area, accompanied by "Sales" in the Values area.
   - This pivot table configuration will empower the segmentation and analysis of customer spending influence, serving as a springboard for precision-targeted marketing and sales initiatives.

Through the dynamic utilization of pivot tables, we are poised to extract profound insights from our sales data, unravel intricate patterns and trends, and empower our decision-making process. Pivot tables stand as an intuitive and user-friendly interface, adept at rapid data manipulation and interpretation, thereby catalyzing informed strategies for the Superstore business.


# Visualisation
1. Our visualization demonstrates that, on average, females exhibit higher BMI, heart rate, blood pressure, cholesterol, and temperature in comparison to males.

To create this visualization, we utilized the "Insert" feature in Excel and selected the column chart as our preferred visualization type. The data source for this visualization was derived from "PivotTable1." After setting up the chart, we carefully formatted it by removing the vertical axes, legend, and gridlines, as well as hiding any unnecessary buttons for a cleaner display.

To highlight the categories with the highest and smallest averages, we employed color-coding. The highest average was emphasized using a green color, while the smallest average was distinguished with a red color.

![]()

2. Our visualization indicates that, on average, males are taller, while females have a higher weight.

To create this visualization, we utilized the "Insert" feature in Excel and selected the column chart as our preferred visualization type. The data source for this visualization was derived from "PivotTable2." After setting up the chart, we carefully formatted it by removing the vertical axes, legend, and gridlines, as well as hiding any unnecessary buttons for a cleaner display.

To highlight the categories with the highest and smallest averages, we employed color-coding. The highest average was emphasized using a green color, while the smallest average was distinguished with a red color.
![]()

3. The visualization reveals that the number of students with blood group B is the highest, while blood group A has the lowest count.

We created this visualization using the "Insert" feature in Excel and selected the column chart as our chosen visualization type. The data source for this visualization was taken from "PivotTable3." To enhance clarity, we formatted the chart by removing vertical axes, the legend, and gridlines, and also hid any unnecessary buttons for a cleaner presentation.

To highlight the categories with the highest and lowest counts, we used color-coding. Blood group B, with the highest count, was represented in green, while blood group A, with the lowest count, was distinguished in red.
![]()

4. The visualization indicates that the number of students who smoke is very small.

We created this visualization using the "Insert" feature in Excel and selected the column chart as our chosen visualization type. The data source for this visualization was taken from "PivotTable4." To improve the clarity of the chart, we formatted it by removing vertical axes, the legend, and gridlines, and also hid any unnecessary buttons.

For highlighting purposes, we utilized green color to represent the category with the highest average, and red color to represent the category with the smallest average.
![]()

5. The visualization reveals that the number of students who have diabetes is also small.

We created this visualization using the "Insert" feature in Excel, opting for the column chart as our preferred visualization type. The data source for this visualization was taken from "PivotTable5." To enhance the clarity of the chart, we formatted it by removing vertical axes, the legend, and gridlines, and also hid any unnecessary buttons.

To emphasize the categories with the highest and smallest averages, we utilized green color to represent the category with the highest average, while red color was used to distinguish the category with the smallest average.
![]()

# Conclusion
This project has significantly expanded my proficiency in utilizing pivot tables, data cleaning, and data visualization techniques. I am eager to apply and further enhance these skills in my future endeavors.

By working on this project, I have gained valuable experience in using pivot tables to summarize and analyze data effectively. Moreover, the process of data cleaning has taught me the importance of handling missing data and ensuring data accuracy for more reliable insights.

Additionally, creating visualizations has been instrumental in presenting complex data in a more accessible and impactful manner. I have learned to choose appropriate chart types, format visualizations for clarity, and use color-coding to highlight key findings.

I am excited about the potential applications of these techniques in various domains, including data analysis, business intelligence, and decision-making. Moving forward, I am eager to explore more advanced features and tools that can further enhance my data handling and visualization capabilities.

Overall, this project has been a valuable learning experience, and I am enthusiastic about applying my newfound skills to tackle more challenging data-related tasks in the future.
