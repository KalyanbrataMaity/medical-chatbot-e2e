# medical chatbot end to end using Generative AI

# How to run?
### Steps:

Clone the repository

```bash
Project repo: https://github.com/
```

### STEP 01: Create a conda environment after opening the repository
```bash
conda create -n medibot python=3.10 -y
```

```bash
conda activate medibot
```


# STEP 02: install requirements
```bash
pip install -r requirements.txt
```

# Create a .env file in the root directory and add your Pinecone & openai credentials as follows:
```bash
PINECONE_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
OPENAI_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

```bash
# run the following command to store embeddings to pinecone
python vectorstore.py
```

```bash
# Finally run the following command
python app.py
```

Now, open localhost


## Techstack Used:
* Python
* Langchain
* Flask
* GPT
* Pinecone


### AWS CI/CD deployment with Github Actions

1. Login to AWS console
2. Create IAM user for deployment
```bash
# with specific access
1. EC2 access: it is virtual machine
2. ECR: Elastic Container registry to save your docker image in aws


# Description: About the deployment
1. Build docker image of the source code
2. Push your docker image to ECR
3. Lauch your EC2
4. Pull your image from ECR to EC2
5. Launch your docker image in EC2

# Policy:
1. AmazonEC2ContainerRegistryFullAccess
2. AmazonEC2FullAccess
```

3. Create ECR repo to store/save docker image
```bash
- Save the URI: 195275673646.dkr.ecr.ap-south-1.amazonaws.com/medical-chatbot
```

4. Create EC2 machine (Ubuntu)

5. Open EC2 and install docker in EC2 machine:
```bash
# optional
sudo apt-get update -y

sudo apt-get upgrade

# required
curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
```

6. Configure EC2 as self-hosted runner:
```bash
setting > actions > runner > new self hosted runner > choose os > then run command one by one
```

7. Setup github secrets:
* AWS_ACCESS_KEY_ID
* AWS_SECRET_ACCESS_KEY
* AWS_DEFAULT_REGION
* ECR_REPO
* PINECONE_API_KEY
* OPENAI_API_KEY
