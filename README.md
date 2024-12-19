# Data Engineering and Modeling Task

---

## Data Engineering

### 1. Overview of Available Data Files:
#### a) **Patient**: Contains demographic information for individuals.
- **Patient_ID**: Anonymous unique identifier for each individual.
- **Gender**: Gender of the individual.  
  - F = Female  
  - M = Male  
- **Birth_year**: The year of birth for the individual.

#### b) **Diagnosis**: Includes diagnosis data for individuals.
- **Patient_ID**: Anonymous unique identifier for each individual.
- **Date_of_service**: Date when the diagnosis was recorded.
- **Diagnosis_code**: Medical code associated with the diagnosis.
- **Diagnosis_code_description**: Description of the medical diagnosis.

#### c) **Pharmacy**: Contains prescription details.
- **Patient_ID**: Anonymous unique identifier for each individual.
- **Date_of_service**: Date when the prescription was filled.
- **NDC**: Code representing the prescribed drug.
- **Days_Supply**: Number of days the prescription covers.
- **Brand_name**: Brand name of the prescribed drug.
- **Generic_name**: Generic name of the prescribed drug.

---

### 2. Questions:
#### a) Determine the number of individuals with at least two recorded diagnosis claims, spaced at least 30 days apart, for specific medical codes within a given time period.
- Relevant medical codes: [Code_1], [Code_2].

#### b) For the individuals identified in **a)**, determine the gender distribution and calculate the number of males aged >= 45 during the same time period.

#### c) Apply a "washout" criterion for the individuals identified in **a)** by checking for any diagnosis or prescription claims recorded at least 6 months prior to the specified study start date. Provide the number of individuals meeting these criteria.

#### d) For individuals meeting the criteria in **c)**, calculate the count and percentage of those using specific drugs during the specified time period:
- Drugs of interest: Drug_A, Drug_B, Drug_C, Drug_D.
- Include results grouped by **Brand_name**.

---

### 3. Deliverables:
- Result datasets.
- Code implementation in either SQL or SAS.

---

## Modeling Task

### 1. Problem Statement:
A client has launched a product and collected survey responses from relevant professionals to understand their decision-making processes. The goal is to analyze survey data to classify professionals based on their treatment decisions:
- **Current User**: Actively using the product.
- **Future User**: Planning to use the product in the future.
- **Non-User**: Do not intend to use the product.

#### Data Description:
- Each row represents an individual survey response.
- Includes basic demographic and professional details, as well as attitudes toward product attributes and familiarity with competing products.

#### Column Details:
- **Familiarity with Competitors**: Scale of 1 to 5.
  - 1: Unaware of the competitor.
  - 5: Very familiar with the competitor.
- **Attitudes Toward Product Attributes**: Scale of 1 to 5.
  - 1: Not at all influential.
  - 5: Extremely influential.

---

### 2. Task:
Develop 1-3 business rules per treatment decision category using data analysis and machine learning methods. For example:
- **Example Rule**: Professionals who specialize in a specific area and are very familiar with Competitor_A are likely to be **Future Users**.

#### Deliverables:
1. Code for data exploration and rule discovery.
2. Brief description of the methodology (1-2 sentences, including at least one machine learning model).
3. Classification rules in bullet points.
4. Confusion matrix with interpretation of results.
5. Layman summary of findings:
   - Include interpretation, sample size, and accuracy for each rule.
   - Example: "The first rule, which is 'Professionals with [specific criteria] are likely to be **Current Users**,' applies to X individuals (Y% of total). Of these, Z% were correctly classified as **Current Users**."
