## Overview
The goal of this homework is to explore the MIMIC-III patient database through relational and non-relational databases.

The main file relies on datasets not provided in this Github. They can be obtained from https://mit-lcp.github.io/mimic-schema-spy/relationships.html

## Files Included
- 'DE300_HW2.ipynb' - main notebook file
- 'Dockerfile' - used to build Docker image
- 'Written Analysis DE300 HW2.pdf' - analysis of dataset

## Datasets Used
The following subset of the tables provided in the MIMIC-III database are used:

- ADMISSIONS.csv
- ICUSTAYS.csv
- PATIENTS.csv
- PROCEDURES_ICD.csv
- D_ICD_PROCEDURES.csv
- DRGCODES.csv
- PRESCRIPTIONS.csv 

## Cassandra Keyspace
This code connects to a Cassandra keyspace through my EC2 in a Docker Container.
The following steps can be followed to conduct this. The inputs into my Command Prompt to conduct this are also given.

1. Copy credentials file to EC2 instance:
scp -i "C:\Users\nkim0\OneDrive - Northwestern University\NU Classes\DATA_ENG 300\.ssh\id_rsa\nkp_key.pem" "C:\Users\nkim0\.aws\credentials" ubuntu@44.193.81.140:~/.aws/credentials

2. Connect to EC2 instances with port tunnel
ssh -i "C:\Users\nkim0\OneDrive - Northwestern University\NU Classes\DATA_ENG 300\.ssh\id_rsa\nkp_key.pem" -L 8888:localhost:8888 ubuntu@44.193.81.140

3. Run the container
sudo docker run -p 8888:8888 \
  -v ~/.aws:/home/jovyan/.aws \
  -v /home/ubuntu/Nayeon_Kim_DE300:/home/jovyan/work \
  my_jupyter

The Dockerfile used can be found under the "Dockerfile" file. This builds a Jupyter Notebook container.

## Queries
Part 1 focuses on conducting analysis with relational databases through SQL queries
- Each question in the Jupyter notebook provides the SQL query, brief explanation of the query, resulting table, and summary of my findings

Part 2 focuses on conducting the same analysis as part 1 but through Cassandra and data manipulation
- Each question designs a Cassandra table, uploads data into the table, and extracts data

The analysis questions are:
1. Create a summary of type of drugs and their total amount used by ethnicity. Report the top usage in each ethnicity group. You may have to make certain assumptions in calculating their total amount.
2. Create a summary of procedures performed on patients by age groups (<=19, 20-49, 50-79, >80). Report the top three procedures, along with the name of the procedures, performed in each age group.
3. How long do patients stay in the ICU? Is there a difference in the ICU length of stay among gender or ethnicity?

   
No copies of the AWS crendentials file is stored on any publicly accessible location, nor is the file in any way shared with anyone outside of DATA_ENG 300 (Spring 2025).
