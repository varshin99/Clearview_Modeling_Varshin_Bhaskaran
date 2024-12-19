## Data Engineering

### 1. Introductions to Available Files (Each Tab is a Separate File):
#### a) **Patient**: Patient-level database with patient demographic info.
- **Patient_ID**: Anonymous patient identifier
- **Gender**: The gender of the patient  
  - F = Female  
  - M = Male  
- **Birth_year**: The birth year of the patient

#### b) **Diagnosis**: Contains the dates and types of ICD (diagnosis) codes received by patients.
- **Patient_ID**: Anonymous patient identifier
- **Date_of_service**: Date of service for the diagnosis
- **Diagnosis_code**: ICD code patient received
- **Diagnosis_code_description**: Description of ICD code

#### c) **Pharmacy**: Contains the dates and days of supply of drugs prescribed to patients.
- **Patient_ID**: Anonymous patient identifier
- **Date_of_service**: Date of service (date prescription filled)
- **NDC**: NDC Code for the drug
- **Days_Supply**: Days of supply for the prescription
- **Brand_name**: Brand name associated with the NDC
- **Generic_name**: Generic name associated with the NDC

---

### 2. Questions:
#### a) How many patients have at least two diagnosis (Dx) claims, which can be either the same or different ICD-10 codes, with at least 30 days apart between them (not necessarily consecutive), for any of the following diagnosis codes within the calendar year 2023 (1/1/2023 - 12/31/2023)?
- ICD-10 code: N186, N184

#### b) For patients in **a)**, what is the distribution of gender? How many male patients are aged >= 45 in 2023?

#### c) For the patients identified in **a)**, apply the washout criteria by checking if they have at least one diagnosis (Dx) claim or pharmacy (Rx) claim any time before 6 months prior to the beginning of the study period (1/1/2023). Output the number of patients who meet these criteria.
- Note: 6 months can be calculated as 6*30 = 180 days.

#### d) For patients in **c)**, find the count and percentage of patients who used each of the following drugs within the calendar year 2023 (1/1/2023 - 12/31/2023):
- Drugs: FUROSEMIDE, LISINOPRIL, FARXIGA, ENTRESTO
- Output the patient counts by drug brands (Use **BRAND_NAME** in the Pharmacy table).

---

### 3. Requirements:
The solution should include:
- Result databases
- Code (must be in SQL or SAS)

---

## Modeling

### 1. Problem Statement:
The client has a product already launched in the market and sent a survey to physicians to understand why they would or would not use the product. The aim is to predict physicians' treatment decisions based on the survey responses:
- **Current User**: Physicians currently treating patients with this product
- **Future User**: Physicians planning to treat patients with this product in the future
- **Never Use**: Physicians who will never use this product

#### Data Description:
- Each row represents one physician response.
- Columns include:
  - Basic information about physicians (e.g., location, number of patients treated).
  - Physicians’ sentiments towards product attributes (e.g., importance of product safety, patient age).
  - Familiarity with competitors (e.g., Competitor A, Competitor B).

#### Familiarity of Competitor Columns:
- **1**: I have never heard of this product.
- **2**: I am somewhat familiar with this product.
- **3**: I am familiar with this product.
- **4**: I am quite familiar with this product.
- **5**: I am very familiar with this product.

#### Attitude Columns:
- **1**: Not at all influential
- **2**: Slightly influential
- **3**: Moderately influential
- **4**: Very influential
- **5**: Extremely influential

---

### 2. Task:
Extract 1-3 business rules per treatment decision to classify physicians into **Current User**, **Future User**, or **Never Use**. For example:
- **Example Rule**: Physicians who are Epileptologists and very familiar with Competitor A are likely to be Future Users.

#### Deliverables:
1. Code to explore the data and discover the rules.
2. A general description of the approach (1-2 sentences; must use at least one machine learning model).
3. Rules for physician treatment decision classification (bullet points).
4. Confusion matrix and interpretation of the metric result.
5. A layman summary for the client:
   - Include interpretation, sample size, and accuracy/importance for each rule.
   - Example: *The first rule, which is "XXX are likely to be Current Users," applies to 70 physicians (47% of all physicians). Out of these 70 physicians, 70% were correctly classified as Current Users.*

---
