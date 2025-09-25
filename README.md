# UNIMIB SNOWIT PROJECT
This project is prepared using the package manager PDM (https://pdm-project.org/).<br>
It is recommended to use a virtual environment, it is used Conda (https://docs.anaconda.com/free/miniconda/miniconda-install/).<br>
It is recommended to use an IDE for developing your code, it is used Visual Studio Code (https://code.visualstudio.com/).<br>

To setup the project (after installed pdm and conda) follow these step:
1. Create an environment and activate it
    ```
    conda create -n <ENV NAME> python=3.12
    conda activate <ENV NAME>
    ```
2. Go to the project folder where the pyproject.toml is and run
    ```
    cd <PATH PROJECT FOLDER>\unimib_snowit_project
    pdm install
    ```

## Project Structure

The main project folder is **`unimib_snowit_project/`**, which contains the following subfolders:

- `data_input/`  
- `data_loaded/`  
- `notebooks/`  
- `models/`  

Below the details of each folder.

---

## Notebooks

The `notebooks/` folder contains 10 Jupyter notebooks that guide the data pipeline, modeling and analysis phases.  
They are designed to be executed in order, from **01** to **10**.

1. **01_read&clean_data**  
   - Loads raw data from `data_input/`.  
   - Performs data checks (uniqueness of primary keys, consistency checks).  
   - Stores cleaned data in `data_loaded/`.  

2. **02_handling_missing_data**  
   - Loads data from `data_loaded/`.  
   - Performs further cleaning and missing values imputation.  
   - Saves updated datasets back to `data_loaded/`.  

3. **03_EDA**  
   - Exploratory Data Analysis (EDA): descriptive statistics, distributions, correlations.  

4. **04_RFM_between**  
   - RFM analysis of customers for the entire 2024–2025 season.  
   - Model is saved in `models/rfm_between_2025-2026`.  

5. **05_RFM_within**  
   - RFM analysis of customers for the first half of the 2024–2025 season.  
   - Model is saved in `models/rfm_within_2024-2025`.  

6. **06_churn_analysis_between**  
   - Builds a churn model between seasons.  
   - Used to predict churners on unlabeled data for the upcoming season 2025–2026.  
   - Predictions dataset is saved in `models/predicted_2025-2026_between_churn_df`.  

7. **07_churn_analysis_within**  
   - Builds a churn model within the same season.  
   - Since future data for 2025–2026 is not available, it uses labeled data from 2024–2025.  
   - Predictions with ground truth are saved in `models/predicted_2024-2025_within_churn_df`.  

8. **08_sentiment_analysis**  
   - Sentiment analysis model built on customer reviews.  
   - Predictions on unlabelled data are saved in `models/predicted_sentiment`.
   - Note: reviews are **decontextualized** from the business problem; they serve only as a NLP exercise.  

9. **09_between_2025-2026_marketing_campaign**  
   - Merges predicted churners with their RFM categories on **unlabeled data** for the next season (2025–2026).  
   - Marketing Campaign

10. **10_within_2024-2025_marketing_campaign**  
   - Merges predicted churners with their RFM categories on **labeled data** from the first half of season 2024–2025.  
   - Marketing Campaign



