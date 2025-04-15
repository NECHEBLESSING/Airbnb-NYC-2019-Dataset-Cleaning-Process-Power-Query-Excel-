# Airbnb-NYC-2019-Dataset-Cleaning-Process-Power-Query-Excel-

### Overview 
This dataset contains information on Airbnb listings in New York City, collected in 2019. The cleaning process focuses on preparing the data for analysis by removing inaccuracies, handling missing values, and filtering out outliers.

#### Step-by-Step Cleaning Workflow
1. ## Load the Dataset
##### ToolUsed:
- Excel Workbook
- Load the CSV file into via Excel Workbook Data > Get Data > From File > From CSV.
**Excel Workbook provides an efficient and structured approach for transforming and cleaning data in Excel.2. Remove Unnecessary Columns**
  
2. ## Removed Columns:
**These columns are either redundant, too detailed for basic analysis, or contain too many missing values**
- host_id
- latitude, longitude (not used in basic analysis)
- calculated_host_listings_count
- last_review (contains many nulls; optional to remove)
   
3. ## Rename Columns for Clarity
The following Names were changed to Improves readability and professionalism in reports/dashboards.

- name → Listing Title
- neighbourhood_group → Borough
- neighbourhood → Neighborhood 
- room_type → Room Type 
- reviews_per_month → Reviews/Month 

4. ## Handle Missing Values
**Column Affected:** reviews_per_month Changed Reviews/Month
- Replace null with 0
- A missing value likely indicates no reviews yet, which logically means zero.
- Other Columns Checked for Null Are ~ name ~, ~ host_name ~,~ price ~
- Rows with null values in these key fields were removed because These are the essential fields for meaningful listing analysis.
  
5. ## Remove Price Outliers
- $0 listings are unrealistic or test/demo data.
- Prices above $1000 are extremely rare and skew averages.
- This step helps maintain meaningful pricing distributions.
  
6. ## Ensure Correct Data Types
 Ensures accuracy in sorting, calculations, and visuals.
- price → Decimal Number
- minimum_nights → Whole Number
- reviews_per_month → Decimal Number
- availability_365 → Whole Number
## Outcome
The cleaned dataset is more reliable for:
- Average price analysis
- Availability and occupancy metrics
- Neighborhood trends
- Room type comparisons



