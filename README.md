#  Power BI Project: Kenya Real Estate Data Model
![image](https://github.com/user-attachments/assets/50284f83-d70c-47ef-a527-3dedef197c08)

##  Project Overview
This Power BI project analyzes house sales data in Kenya using a structured data model. It contains multiple `.csv` files:-    
- houses
- owners
- property tax
- utilities  
It combines above multiple datasets into a single interactive dashboard to extract key real estate insights.

## 📁 Files Used
- `houses.csv`: Contains house listings with details like price, size, location.
- `owners_details.csv`: Includes property owner information.
- `property_tax.csv`: Contains tax-related data per property.
- `house_utilities.csv`: Tracks monthly utility costs per house.

##  How to Use This Power BI File
- Open the `housing.pbix` File  
- Launch Power BI Desktop
- Open the provided .pbix file from your local machine
- Explore the Report Pages
- Interact with Filters & Slicers

##  Step-by-Step Instructions
### 1. Load the Data
- Open Power BI Desktop
- Go to Home → Get Data → Text/CSV
- Load the four CSV files listed above
- Rename tables to:  
Houses  
Owners  
Taxes  
Utilities  
### 2. Clean the Data (Recommended)
In Power Query Editor (Transform Data):
- Make sure PropertyID is clean and consistent across all tables
- Remove unwanted characters like KSh, m², and commas using Replace Values
- Convert Price, Size, and TaxRate to numeric formats

### 3. Set Relationships
In Model View, create these relationships:  
| From Table | Column     | To Table | Column     | Relationship | Cardinality | Direction |
| ---------- | ---------- | -------- | ---------- | ------------ | ----------- | --------- |
| Owners     | PropertyID | Houses   | PropertyID | Many-to-One  | Single  |           |
| Taxes      | PropertyID | Houses   | PropertyID | Many-to-One  | Single  |           |
| Utilities  | PropertyID | Houses   | PropertyID | Many-to-One  | Single  |           |
### 4. ERD Diagram
                   +--------------+
                   |   Owners     |
                   |--------------|
                   | OwnerID      |
                   | PropertyID FK|
                   +--------------+
                         |
                         ▼
                   +--------------+
                   |   Houses     |◄────────+
                   |--------------|         |
                   | PropertyID PK|         |
                   +--------------+         |
                         ▲                  |
                +--------+--------+  +------+------+ 
                |     Taxes       |  |  Utilities  |
                |-----------------|  |-------------|
                | PropertyID  FK  |  | PropertyID FK|
                +-----------------+  +--------------+

## Challenges Faced
- 
