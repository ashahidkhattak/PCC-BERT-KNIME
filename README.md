## **Patient Condition Classification with BERT**

**Table of Contents**
1. Raw Data  
2. Data Demographics  
3. KNIME Data Retrieval Workflow  
4. Condition Wise Data (Binary Classes and Multi Classes)  
5. Binary-Class Conditions (0 & 1)  
6. Multi-Class Conditions (0 to 11)  
7. BERT Model Python Code

---

### 1. Raw Data
This dataset is sourced from the [UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/dataset/462/drug+review+dataset+drugs+com). It includes patient reviews on specific drugs, associated conditions, and a 10-star rating reflecting overall patient satisfaction.

**Dataset Characteristics:**
- **Type**: Multivariate, Text
- **Subject Area**: Health and Medicine
- **Associated Tasks**: Classification, Regression, Clustering
- **Feature Type**: Integer
- **Instances**: 215,063
- **Features**: 6

---

### 2. Data Demographics
The Data Demographics Excel file provides a summary of the statistical and mathematical methods used to select the conditions and reviews for training the BERT model. It contains eight sheets, each showcasing a specific method for better evaluation and understanding:

- **Sheet 01: Raw Data of Selected Features**  
  This sheet includes the raw data with six original features, four of which were selected for analysis. These features were used to determine the patient conditions and corresponding reviews that exhibit high-quality behavioral data.

- **Sheet 02: PCS - Patient Condition Sampling**  
  This sheet provides a detailed exploration of patient conditions and their sample counts, obtained through Exploratory Data Analysis (EDA). It outlines the process of selecting 25 conditions for further study using sample mean sampling.

- **Sheet 03: DS - Drug Sampling**  
  This sheet details the drugs associated with each condition, including the sample count, average rating, and total useful count. Based on these metrics, sample mean sampling was applied, followed by judgment sampling to finalize the drugs for each condition.

- **Sheet 04: PCS and DS Overview**  
  This sheet presents a ranking of the patient conditions before and after the demographic analysis, based on the number of samples collected.

- **Sheet 05: Condition and Drug Samples**  
  This sheet summarizes the conditions, associated drugs, and the number of samples selected for further study, offering an overview of the dataset refined for training.

- **Sheet 06: Under Sampling (Binary Class)**  
  This sheet contains the results of the Chi-Square Goodness of Fit Test, conducted on the binary-class dataset. Both the critical value and p-value methods were used to balance the sample sizes, preventing the model from leaning toward bias.

- **Sheet 07: Under Sampling (Multi-Class)**  
  Similar to the binary-class dataset, this sheet includes the Chi-Square Goodness of Fit Test results for the multi-class dataset. The critical value and p-value methods were applied to balance the sample sizes for training.

- **Sheet 08: Final Sample and Review Selection**  
  This sheet lists the final sample counts for both binary and multi-class conditions, as well as the associated drugs. It provides the foundation for retrieving reviews from the raw data, using the KNIME Data Retrieval Workflow for further analysis.

---

### 3. KNIME Data Retrieval Workflow
This KNIME workflow details the process of retrieving and refining data from the raw dataset. Conditions and drugs are selected through data demographics, and the refined data is used for training the BERT model for both binary and multi-class classification tasks.

---

### 4. Condition Wise Data (Binary Classes and Multi Classes)
This folder contains datasets for patient condition classification, including binary and multi-class datasets. The data was processed using the KNIME workflow to create:

**Binary-Class Conditions Datasets**
- 0: Depression  
- 1: Anxiety

**Multi-Class Conditions Datasets**
- 0: Birth Control  
- 1: Depression  
- 2: Pain  
- 3: Anxiety  
- 4: Acne  
- 5: Bipolar Disorder  
- 6: Insomnia  
- 7: Weight Loss  
- 8: Obesity  
- 9: ADHD  
- 10: Bowel Preparation  
- 11: Emergency Contraception

---

### 5. Binary-Class Conditions (0 & 1)
This dataset includes refined data for binary classification of patient conditions. It was created from the "Condition Wise Data (Binary Classes)" retrieved after under-sampling.

---

### 6. Multi-Class Conditions (0 to 11)
This dataset includes refined data for multi-class classification of patient conditions. It was created from the "Condition Wise Data (Multi Classes)" retrieved after under-sampling.

---

### 7. BERT Model Python Code
This Google Colab Notebook (`.ipynb` file) contains the Python code for training the BERT model for both binary and multi-class classification tasks.

**Binary Classification Code Execution:**
- To perform binary classification, use the dataset "Binary-Class Conditions (0 & 1)". Execute all sections, but only run subsections 6.2 and 6.4 in Section 6, and subsection 8.1 in Section 8.

**Multi-Class Classification Code Execution:**
- For multi-class classification, use the dataset "Multi-Class Conditions (0 to 11)". Execute all sections, and in Section 8, run subsection 8.2.
