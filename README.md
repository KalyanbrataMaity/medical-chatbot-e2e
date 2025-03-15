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

