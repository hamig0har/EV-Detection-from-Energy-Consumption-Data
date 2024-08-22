# Electric Vehicle Detection from Energy Consumption Data

## Project Overview

This project aims to detect the presence of Electric Vehicles (EVs) in households based on their energy consumption data. By leveraging a combination of data from Austin and New York, the project explores the application of machine learning techniques to identify patterns in energy usage that correlate with EV charging. The project involves extensive data preprocessing, feature engineering, and model evaluation, with a focus on improving the accuracy and reliability of the predictions.

## Data Sources

- **15-Minute Interval Energy Consumption Data:** Collected from households in Austin and New York, capturing energy usage patterns over time. (PECAN STREET DATAPORT)
- **Metadata:** Provides additional context for the energy consumption data, including information about the households.

## Project Workflow

### 1. **Data Loading and Inspection**
   - **Tools Used:** `pandas`
   - Loaded datasets into pandas DataFrames and inspected the first few rows to understand the structure and content of the data.

### 2. **Data Preprocessing**
   - **Handling Missing Values:** Missing values in the energy consumption columns were imputed with zeros, assuming no consumption or measurement was recorded.
   - **Feature Creation:** Summed the energy values across all consumption columns to create a "total energy consumption" feature.
   - **Labeling Data:** Labeled the data with `1` for households with an EV and `0` for those without, based on known `dataid` values.

### 3. **Feature Engineering**
   - Extracted time-based features such as the hour of the day and whether the data point fell on a weekend, to capture potential patterns related to EV charging behavior.

### 4. **Model Selection and Training**
   - **Model Used:** Random Forest Classifier
   - **Reason for Choice:** Random Forest was selected due to its flexibility, ease of use, and ability to handle both numerical and categorical data effectively.
   - The model was trained on the `total_energy`, `hour`, and `is_weekend` features to predict whether a household has an EV.

### 5. **Model Evaluation**
   - **Metrics:** Accuracy, Precision, Recall, F1-Score, ROC Curve, and AUC were used to evaluate model performance.
   - **Initial Results:** The initial model showed a good balance between precision and recall for the no-EV class, but struggled with the EV class, leading to a need for further refinement.

### 6. **Enhancements**
   - **Combining Datasets:** Merged data from Austin and New York to improve model performance by providing a more diverse dataset.
   - **Improved Results:** The combined dataset led to significant improvements in accuracy, precision, recall, and AUC, particularly for the EV class.

## Key Skills Developed

### 1. **Data Handling and Preprocessing**
   - Mastery in loading and managing large datasets using `pandas`.
   - Experience in handling missing data and creating new features from existing data.

### 2. **Feature Engineering**
   - Skill in extracting and engineering relevant features from raw data, such as time-based features from timestamps.
   - Understanding the importance of domain knowledge in feature selection, especially in time-series data.

### 3. **Machine Learning**
   - Proficiency in training and evaluating machine learning models, particularly Random Forests.
   - Ability to interpret model performance using a range of evaluation metrics, including ROC-AUC.

### 4. **Model Optimization**
   - Experience in improving model performance by combining datasets from different regions to reduce overfitting and enhance generalization.
   - Application of advanced evaluation techniques to assess the effectiveness of model improvements.

## Tools and Technologies Used

- **Programming Language:** Python
- **Libraries:** pandas, numpy, scikit-learn, matplotlib
- **Tools:** Google Colab, Jupyter Notebook

## Project Results

- **Improved Accuracy:** The model's accuracy improved from 0.63 to 0.78 after combining datasets.
- **Enhanced Precision and Recall:** Significant improvements in both precision and recall for the EV class, leading to better identification of households with EVs.
- **ROC-AUC Score:** The AUC increased from 0.64 to 0.82, indicating a much better distinction between classes.

## Next Steps

- **Feature Engineering:** Further refine features, especially those capturing regional differences or specific time-based patterns.
- **Data Imbalance:** Apply techniques like SMOTE or class weighting to address the remaining imbalance in the dataset.
- **Model Experimentation:** Explore more complex models, such as Neural Networks, that can better capture temporal patterns and feature interactions.
- **Incorporate ATCO Data:** Combine the dataset with ATCO data to further enhance the model's capabilities.


