# Documentation for Python Scripts

## Handling Multiple CSV Files in a Directory

### ISS Filter Out Files.py

**Purpose:**  
This script is designed to preprocess multiple CSV files within a directory, filtering each for specific rows that contain labels indicating key network attacks such as DDoS, DoS, Recon, and Mirai. This approach is crucial for efficiently processing large datasets that are split across multiple files.

**Contents:**
- **Importing Libraries:** Uses `pandas` for data manipulation, and `os` for path operations.
- **Data Loading and Processing:** Iterates over each CSV file in the specified directory, loads the file, filters necessary rows, and saves the filtered data back to a new file.
- **Data Filtering:** Applies a filter to each dataframe to retain only rows with specified attack types.
- **Data Saving:** Outputs the filtered data to new CSV files with a modified naming scheme to distinguish them from the originals.

**Script Execution Steps:**
1. **Environment Setup:** Ensure Python, Pandas, and other necessary libraries are installed. If not already installed, use pip: `pip install pandas`
2. **Directory Setup**: Ensure the script's directory path is correctly set to the folder containing your CSV files for example `CICIoT2023`folder containing `.csv` files.
3. **Running the Script:** Execute the script from your command line or terminal: `python ISS_Filter_out_files.py`.
4. **Output:** Check the directory for new files starting with `filtered_ .csv` to verify that the data has been processed correctly, and created with the expected filtered data.

## 2. ISS Main Code.py

**Purpose:**  
This script is responsible for reading the preprocessed data from multiple CSV files, training a simple Random Forest classifier, and evaluating its performance. This is a continuation of the workflow where the preprocessed data (filtered in the previous step) is utilized for model training and testing, exemplifying a complete machine learning pipeline in the context of IDS for network security.

**Contents:**
- **Importing Libraries:** Uses `pandas` for data handling and `sklearn` for machine learning tasks.
- **Data Loading:** Iterates over each filtered CSV file in the directory, loads the data, and aggregates it if necessary for training.
- **Feature Preparation:** Separates features and labels from the aggregated dataset, splits the data into training and testing subsets.
- **Model Training:** Initializes a Random Forest classifier and fits it to the training data, optimizing for parameters such as number of trees and depth where applicable.
- **Model Evaluation:** Evaluates the trained model on the testing set and prints out a detailed classification report that includes metrics such as accuracy, precision, recall, and F1-score.

**Script Execution Steps:**
1. **Environment Setup:** Ensure all required libraries (`pandas`, `sklearn`) are installed. These can be installed via pip if not already available: `pip install pandas sklearn`.
2. **Script Placement:** Ensure the script is in the same directory as the `filtered_ .csv` or adjust the script to include the correct file path.
3. **Running the Script:** Execute the script using Python from your command line or terminal: `python ISS_main_code.py`.
4. **Review Output:** After execution, review the console output for the classification report, which evaluates the model's performance.
"""
