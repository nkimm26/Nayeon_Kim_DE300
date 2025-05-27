## Overview
The goal of this homework is to explore the use of MapReduce and Spark

The main file relies on datasets not provided in this Github. They can be obtained from 

https://raw.githubusercontent.com/mosesyhc/de300-2025sp-class/refs/heads/main/agnews_clean.csv
https://raw.githubusercontent.com/mosesyhc/de300-2025sp-class/refs/heads/main/w.csv
https://raw.githubusercontent.com/mosesyhc/de300-2025sp-class/refs/heads/main/bias.csv
https://raw.githubusercontent.com/mosesyhc/de300-2025sp-class/refs/heads/main/data_for_svm.csv

## Files Included
- 'DE300_HW3.ipynb' - main notebook file
- 'Dockerfile' - used to build Docker image

## Dockerfile
This code connects to my EC2 in a Docker Container. The following steps can be followed to conduct this. The inputs into my Command Prompt to conduct this are also given.

Copy credentials file to EC2 instance: scp -i "C:\Users\nkim0\OneDrive - Northwestern University\NU Classes\DATA_ENG 300.ssh\id_rsa\nkp_key.pem" "C:\Users\nkim0.aws\credentials" ubuntu@13.218.190.214:~/.aws/credentials

Connect to EC2 instances with port tunnel ssh -i "C:\Users\nkim0\OneDrive - Northwestern University\NU Classes\DATA_ENG 300.ssh\id_rsa\nkp_key.pem" -L 8888:localhost:8888 ubuntu@13.218.190.214

Run the container sudo docker run -p 8888:8888
-v ~/.aws:/home/jovyan/.aws
-v /home/ubuntu/Nayeon_Kim_DE300:/home/jovyan/work
my_jupyter

The Dockerfile used can be found under the "Dockerfile" file. This builds a Jupyter Notebook container

## Overview
1. TF-IDF
   - Computes raw Term Frequencies (TF), Document Frequencies (DF), Inverse Document Frequencies (IDF), and normalized TF–IDF scores for each row in agnew_cleans.csv
2. SVM hinge‐loss objective
   - Computes full regularized SVM loss and objective value
   - Uses MapReduce functions to make prediction using provided weights and biases
   
