# Network Security Project for Phishing Data

## Overview
This project is designed to analyze and detect phishing data using a structured machine learning pipeline. It automates the ingestion, transformation, validation, and potential training of models to identify phishing attempts. The project leverages MongoDB for data storage and Python for data processing and analysis. The modular design ensures scalability and adaptability for future enhancements.

---

## Features

### 1. Data Ingestion
- Reads data from MongoDB collections or CSV files.
- Splits data into training and testing datasets using configurable ratios.
- Exports datasets to CSV files for further processing or analysis.
- Ensures data integrity during ingestion by validating schema and handling missing values.

### 2. Data Transformation
- Preprocesses raw data into formats suitable for machine learning.
- Handles:
  - Missing value imputation.
  - Feature scaling (e.g., normalization or standardization).
  - Encoding categorical variables.
- Saves transformed data for reproducibility.

### 3. Configuration Management
- Centralized configuration for managing:
  - File paths and directories.
  - Database connection details.
  - Pipeline settings (e.g., train-test split ratio, preprocessing parameters).
- Ensures consistency and reduces hardcoding.

### 4. Database Interaction
- Uses MongoDB as the primary database for storing and retrieving data.
- Converts CSV data to JSON format for seamless database insertion.
- Supports CRUD operations for managing datasets in MongoDB.

### 5. Error Handling
- Implements a custom exception mechanism to log and trace errors effectively.
- Ensures that errors are captured with detailed stack traces for debugging.

### 6. Logging
- Tracks the progress and status of various operations, such as data ingestion, transformation, and validation.
- Logs are stored in timestamped files for easy tracking and debugging.

### 7. Testing
- Includes test scripts to:
  - Verify MongoDB connectivity.
  - Validate the integrity of ingested and transformed data.
- Ensures that all components work as expected before deployment.

---

## Project Structure

```
NetworkSecurity/
├── Artifacts/                # Stores outputs from various pipeline stages
│   ├── data_ingestion/       # Ingested data (train/test splits)
│   ├── data_validation/      # Validation reports and validated data
├── Network_data/             # Contains phishing data CSV files
├── data_schema/              # Schema definitions for data validation
│   ├── schema.yaml           # Defines expected data structure
├── logs/                     # Log files for tracking execution
│   ├── <timestamp>.log       # Timestamped log files
├── networksecurity/          # Core project modules
│   ├── components/           # Data ingestion and validation components
│   ├── entity/               # Configuration and artifact entities
│   ├── exception/            # Custom exception handling
│   ├── logging/              # Logging utilities
│   ├── pipeline/             # Pipeline initialization
│   ├── utils/                # Utility functions
├── notebooks/                # Jupyter notebooks for experimentation
├── requirements.txt          # Python dependencies
├── setup.py                  # Project setup configuration
└── README.md                 # Project documentation
```

---

## Installation

### **Step 1: Clone the Repository**
Clone the repository to your local machine:
```bash
git clone https://github.com/ruchagoje/ML-Project-NetworkSecurity.git
```

### **Step 2: Navigate to the Project Directory**
```bash
cd NetworkSecurity
```

### **Step 3: Create and Activate a Virtual Environment**
Create a virtual environment to isolate project dependencies:
```bash
python3 -m venv myenv
source myenv/bin/activate
```

### **Step 4: Install the Required Dependencies**
Install the dependencies listed in `requirements.txt`:
```bash
pip install -r requirements.txt
```

---

## Usage

### **Running the Project**
1. Ensure MongoDB is running and accessible.
2. Update the `.env` file with your MongoDB connection URL.
3. Run the main script to start the pipeline:
   ```bash
   python main.py
   ```

### **Testing**
Run the test script to verify MongoDB connectivity and other components:
```bash
python test_mangodb.py
```

---

## Dataset

### **Description**
The project uses a phishing dataset (`phisingData.csv`) that contains features for identifying phishing attempts. The dataset includes both legitimate and phishing instances, with features that describe the characteristics of URLs, domains, and content.

### **Key Features**
- **URL Length**: Longer URLs may indicate phishing attempts.
- **Special Characters**: Presence of characters like `@`, `//`, or `-` in URLs.
- **Domain Age**: Newly registered domains are more likely to be used for phishing.
- **HTTPS Usage**: Lack of HTTPS may indicate phishing.
- **Keyword Analysis**: Presence of suspicious keywords like "login", "verify", or "update".

### **Preprocessing**
- Handles missing values and outliers.
- Encodes categorical variables.
- Scales numerical features for better model performance.

---

## Future Enhancements

### **1. Machine Learning Models**
- Implement supervised learning models (e.g., Logistic Regression, Random Forest, Gradient Boosting) for phishing detection.
- Evaluate model performance using metrics like accuracy, precision, recall, and F1-score.

### **2. Real-Time Detection**
- Develop a real-time phishing detection system that can analyze URLs or emails as they are received.

### **3. Web Interface**
- Integrate a user-friendly web interface for:
  - Uploading datasets.
  - Visualizing results.
  - Running the pipeline interactively.

### **4. Explainable AI**
- Use tools like SHAP or LIME to explain model predictions and identify key features contributing to phishing detection.

---

## License
This project is licensed under the **MIT License**. See the LICENSE file for details.

---

## Author
- **Rucha Goje**
- GitHub: [ruchagoje](https://github.com/ruchagoje)