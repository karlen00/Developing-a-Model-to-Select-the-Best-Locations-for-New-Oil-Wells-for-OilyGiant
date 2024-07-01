# README

## Project: Developing a Model to Select the Best Locations for New Oil Wells for OilyGiant

### Project Description
You are working at the mining company OilyGiant. Your task is to find the best locations to develop 200 new oil wells.

To complete this task, you need to follow these steps:
1. Read the file with parameters collected from oil wells in the selected region: oil quality and reserve volume.
2. Create a model to predict the reserve volume in new wells.
3. Select the oil wells with the highest estimated values.
4. Choose the region with the highest total profit from the selected oil wells.

You have sample oil data from three regions. The parameters of each oil well in these regions are known. Develop a model to help you select the region with the highest profit margin. Remember to use bootstrapping to analyze potential profit and risk.

### Project Instructions
1. **Download and Prepare the Data:**
   - Explain the procedures you perform.

2. **Train and Test Models for Each Region in `geo_data_0.csv`:**
   - 2.1. Split the data into training and validation sets with a 75:25 ratio.
   - 2.2. Train the model and make predictions for the validation set.
   - 2.3. Save predictions and correct answers for the validation set.
   - 2.4. Display the average predicted volume and RMSE of the model.
   - 2.5. Analyze the results.
   - 2.6. Repeat steps 2.1-2.5 for the files `geo_data_1.csv` and `geo_data_2.csv`.

3. **Prepare for Profit Calculation:**
   - 3.1. Store all values needed for profit calculation in separate variables.
   - 3.2. With an investment of 100 million for 200 oil wells, each well should produce at least 500 thousand USD to avoid losses (equivalent to 111.1 units). Compare this amount with the average volume in each region.
   - 3.3. Provide conclusions regarding the preparations for profit calculation.

4. **Create a Function to Calculate Profit from Selected Oil Wells and Model Predictions:**
   - 4.1. Write a function to calculate profit from a set of selected oil wells and model predictions: Select 200 wells with the highest predicted values from each of the 3 regions (csv files).
   - 4.2. Summarize the target volume based on these predictions. Save predictions for 200 wells in each of the 3 regions.
   - 4.3. Present your conclusions: recommend a region suitable for oil well development and justify your choice. Calculate the profit for the accepted volume.

5. **Calculate Risk and Profit for Each Region:**
   - 5.1. Using the predictions saved in step 4.2, use bootstrapping with 1,000 samples to find the profit distribution.
   - 5.2. Find the average profit, 95% confidence interval, and the risk of loss. Loss is negative profit, calculated as a probability and then expressed as a percentage.
   - 5.3. Present your conclusions: recommend a region suitable for oil well development and justify your choice. Does this choice align with your previous recommendation in step 4.3?

### Data Description
Geological exploration data for the three regions is stored in several files:
- `geo_data_0.csv` (download dataset)
- `geo_data_1.csv` (download dataset)
- `geo_data_2.csv` (download dataset)

Each observation contains:
- `id` — unique ID of the oil well
- `f0`, `f1`, `f2` — three features of the region point (the specific meaning is not important, but the features themselves are crucial)
- `product` — reserve volume in the oil well (1 unit = 1,000 barrels)

### Conditions:
- Only linear regression can be used to train the model (others are not predictable enough).
- The budget for developing 200 oil wells is 100 million dollars.
- One barrel of crude oil produces revenue of $4.5. Therefore, the revenue from one unit of product is $4,500 (reserve volume is in thousands of barrels).
- After analyzing the risks, retain only regions with a loss risk of less than 2.5%. Among all that meet the criteria, choose the region with the highest average profit.
