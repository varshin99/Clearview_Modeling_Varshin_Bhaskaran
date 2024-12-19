NOTICE OF CONFIDENTIALITY
This take-home test, including attachments, is confidential and only for the sole use of the 
intended recipient. Any disclosure, copying, sharing to the public or distribution of the 
contents are prohibited.
Data Engineering
1) Introductions to available files (each tab is a separate file):
a) Patient: Patient-level database with patient demographic info.
i) Patient_ID: Anonymous patient identifier
ii) Gender: the gender of the patient
(1) F = Female 
(2) M = Male
iii) Birth_year: The birth year of the patient
b) Diagnosis: Contains the dates and types of ICD (diagnosis) codes received by patients
i) Patient_ID: Anonymous patient identifier
ii) Date_of_service: Date of service for the diagnosis
iii) Diagnosis_code: ICD code patient received
iv) Diagnosis_code_description: Description of ICD code
c) Pharmacy: Contains the dates and days of supply of drugs prescribed to patients
i) Patient_ID: Anonymous patient identifier
ii) Date_of_service: Date of service (date prescription filled)
iii) NDC: NDC Code for the drug
iv) Days_Supply: Days of supply for the prescription
v) Brand_name: Brand name associated with the NDC
vi) Generic_name: Generic name associated with the NDC
2) Questions:
a) How many patients have at least two diagnosis (Dx) claims, which can be either the same or 
different ICD-10 codes, with at least 30 days part between them (not necessarily 
consecutive), for any of following diagnosis codes within the calendar year 2023 (1/1/2023 
- 12/31/2023)? 
2
Confidential
2024 | ClearView Internal | Varshin
ClearView - Company Confidential 
i) ICD-10 code: N186, N184
b) For above patients in a), what is distribution of gender? How many male patients with age 
>= 45 at 2023?
c) For the patients identified in a), apply the washout criteria by checking if they have at least 
one diagnosis (Dx) claim or pharmacy (Rx) claim any time before 6 months prior to the 
beginning of study period (1/1/2023). Output the number of patients who meet these 
criteria.
i) Note: 6 months can be calculated as 6*30 = 180 days
d) For patients in c), find # and % of patients used each drug of FUROSEMIDE, LISINOPRIL, 
FARXIGA, ENTRESTO within calendar year 2023 (1/1/2023 - 12/31/2023)? 
i) Output the patient counts by drug brands
ii) Use BRAND_NAME in Pharmacy table
3) Candidate’s solution should include both the result databases and code (Must be SQL or 
SAS)
Modeling
1) Problem statement:
o The client has a product already launched in the market, they sent a survey to the 
related physicians to listen to their opinion of why they would or would not decide to 
use the product
o The client is seeking a way to predict physician’s treatment decisions based off the 
survey, aiming to understand why physicians are currently treating patients with this 
product, plan to treat patients with this product in the future, or will never treat 
patients with this product
o Each row is represented as one physician response. The survey contains the basic 
information of physicians (i.e., where the physician works at, how many related patients 
the physician has treated) and the physicians’ sentiments towards the product 
attributes (i.e., how strongly the product safety will impact on the treatment decision, 
how strongly the patient age will impact on the treatment)
3
Confidential
2024 | ClearView Internal | Varshin
ClearView - Company Confidential 
For those Familiarity of Competitor columns (e.g., Familiarty_CompetitorA): 
1: I have never heard of this product; 
2: I am somewhat familiar with this product;
3: I am familiar with this product; 
4: I am quite familiar with this product;
5: I am very familiar with this product
For those attitudes columns (e.g., Importance_Product_Safety):
1: Not at all influential;
2: Slightly influential;
3: Moderately influential;
4: Very influential;
5: Extremely influential
o We would like to ask you to extract some business rules (1-3 rules per treatment 
decision) to classify physician’s treatment decisions (i.e., Current user vs. Future 
user vs. Physicians never use the drug). An example of a set of rules would be 
“Physicians who are Epileptologist and very familiar with Competitor A are likely to be 
Future User.”
2) In the response email, the following should be provided:
o The code to explore the data and discover the rules
o A general description of your approach (only 1-2 sentences, must use at least one 
machine learning model) and the rules (bullet points) for physician’s decision
classification 
o The overall confusion matrix and the interpretation of the metric result you selected
o A layman deliverable summary for the client, please include the interpretation, sample 
size and the accuracy/importance for each rule.
For example, the first rule, which is XXX are likely to be Current User, 70 physicians fit 
this rule (47% of all physicians), and out of those 70 physicians, 70% can be correctly 
assigned as Current User
