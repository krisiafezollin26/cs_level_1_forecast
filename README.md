# cs_level1_forecast pipeline explanation
This repository contains scripts and queries for the Level 1 forecast.

## Setup and Execution Process

Before running the notebooks, please consider the following steps:

1. **Ben_forecasting_utils.py**  
   This script includes various utility functions, such as:
   - `export_df_to_google_sheet`
   - `write_df_to_sheet`
   - `get_intra_month_seasonality`
   
   The functions in this script are used during the first phase of the notebook run in the `Seasonality Extractor.ipynb`.

2. **Seasonality Extractor**  
   - **Notebook**: `Seasonality Extractor.ipynb`  
   - **Important**: Before running this notebook, ensure that you update the Google Sheets ID to match your data source.  
   - This notebook extracts seasonality data and requires the `Ben_forecasting_utils.py` script to function.

3. **Volume Forecaster**  
   - **Notebook**: `Volume Forecaster.ipynb`  
   - **Important**: After running the `Seasonality Extractor`, update the Google Sheets ID (make a copy from the previous week’s data).  
   - This notebook is used to forecast volumes based on the extracted seasonality data.

4. **Rolling_52_automation**  
   - **Notebook**: `Rolling_52_automation.ipynb`  
   - **Important**: This notebook is directly connected to Metabase. Running it will immediately update the forecasted volumes in Metabase. Please exercise caution before executing this notebook to avoid unintended changes.

---

**Note**: Always double-check the Google Sheets ID before running any notebook to ensure that you are working with the correct data.

