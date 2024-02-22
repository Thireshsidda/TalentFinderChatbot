# TalentFinderChatbot

## Intelligent App with Azure OpenAI and Neo4j

### In this we will explore how to leverage Azure OpenAI to build and consume a knowledge graph in Neo4j.
For this project we parses data from a public [corpus of Resumes / Curriculum Vitae](https://github.com/florex/resume_corpus) using Azure OpenAI `gpt-3.5 turbo` model. The model will be prompted to recognise and extract entities and relationships. We will then generate Neo4j Cypher queries using them and write the data to a Neo4j database.
We will again use a `gpt-3.5 turbo` model and prompt it to convert questions in english to Cypher - Neo4j's query language, which can be used for data retrieval.


## Setup
To get started, we'll need to set up some resources:

### Step 1- Create OpenAI API key
[Generate an OpenAI API key](create_openai_key/README.md).


### Step 2- Create a conda environment after opening the repository

```bash
conda create -n sensor python=3.7.6 -y
```

```bash
conda activate sensor
```


### Step 3 - Install the requirements
```bash
pip install -r requirements.txt
```


### Step 4 - You will now need to edit that file to reflect your Azure OpenAI and Neo4j credentials. The file has the following variables:

    OPENAI_API_KEY = "" #OPENAI KEY
    OPENAI_API_TYPE = "azure"
    OPENAI_API_VERSION = "2023-03-15-preview"
    OPENAI_API_BASE = ""
    OPENAI_MODEL_NAME = "gpt-3.5-turbo"
    OPENAI_DEPLOYMENT_NAME = "gpt-3.5-turbo"
    NEO4J_URI = "neo4j+s://xxxxx.databases.neo4j.io" # Neo4j URL. Include port if applicable
    NEO4J_USER = "neo4j" # Neo4j User Name
    NEO4J_PASSWORD = "Foo12345678" #Neo4j Password


### Step 5 - Now we can run the app with the command:
```
python TalentFinderChatbot.py
```
