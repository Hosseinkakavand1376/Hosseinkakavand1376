# Documentation for Python Scripts

## 1. ISS Filter Out Files.py

**Purpose:**  
This script preprocesses the CIC-IoT2023 dataset by filtering out specific rows that contain labels indicating key types of network attacks relevant to our study: DDoS, DoS, Recon, and Mirai attacks. This is critical for focusing the dataset on scenarios pertinent to our intrusion detection model training.

**Contents:**
- **Importing Libraries:** Uses the pandas library, essential for data manipulation and analysis.
- **Data Loading:** Loads the dataset from a CSV file named `CIC-IoT2023.csv`.
- **Data Filtering:** Filters rows based on the presence of specific substrings ('DDoS', 'DoS', 'recon', 'Mirai') in the 'Label' column.
- **Data Saving:** Saves the filtered dataset to a new CSV file, `filtered_CIC-IoT2023.csv`, excluding rows that do not correspond to the attacks of interest.

**Script Execution Steps:**
1. **Environment Setup:** Ensure that Python and Pandas are installed on your system. If Pandas is not installed, you can install it via pip: `pip install pandas`.
2. **Script Placement:** Place the script in the same directory as the `CIC-IoT2023.csv` dataset file, or modify the script to include the path to the dataset.
3. **Running the Script:** Execute the script using Python from your command line or terminal: `python ISS_Filter_out_files.py`.
4. **Output:** Check the directory for the `filtered_CIC-IoT2023.csv` file to ensure it has been created with the expected filtered data.

## 2. ISS Main Code.py

**Purpose:**  
The main code is tasked with reading the preprocessed data, training a Random Forest classifier, and evaluating its performance based on the dataset that has been filtered by the first script. This script exemplifies the model development and initial training phase in the machine learning workflow for IDS.

**Contents:**
- **Importing Libraries:** Utilizes `sklearn` for machine learning tasks, including model training and evaluation, and `pandas` for handling the dataset.
- **Data Loading:** Reads the filtered data from `filtered_CIC-IoT2023.csv`.
- **Feature Preparation:** Separates features and labels, and splits the data into training and testing subsets.
- **Model Training:** Initializes a Random Forest classifier, fits it to the training data.
- **Model Evaluation:** Predicts labels for the test set and prints out a classification report that includes key metrics such as accuracy, precision, recall, and F1-score.

**Script Execution Steps:**
1. **Environment Setup:** Ensure all required libraries (`pandas`, `sklearn`) are installed. If not, they can be installed via pip: `pip install pandas sklearn`.
2. **Script Placement:** Ensure the script is in the same directory as the `filtered_CIC-IoT2023.csv` or adjust the script to include the correct file path.
3. **Running the Script:** Execute the script using Python from your command line or terminal: `python ISS_main_code.py`.
4. **Review Output:** After execution, review the console output for the classification report, which evaluates the model's performance.
"""
