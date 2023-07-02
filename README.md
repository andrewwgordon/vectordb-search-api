# QDrant Vector Database API
FastAPI based API for Semantic Search using QDrant Vector Database
## Overview
Adapted from [QDrant tutorial](https://qdrant.tech/documentation/tutorials/neural-search/) using [Startips-List dataset](https://www.startups-list.com/) as a corpus.
## Requirements
Python >=3.10.x
Docker >=20.x
## Installation
```bash
git clone [this repositiory]
cd vectordb-search-api
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
mkdir data
cd data
wget https://storage.googleapis.com/generall-shared-data/startups_demo.json
cd ..
docker pull qdrant/qdrant
docker run -d -p 6333:6333 \
    -v $(pwd)/qdrant_storage:/qdrant/storage \
    qdrant/qdrant
```
## Build the Model
```bash
python model_build.py
```
## Upload the Data to the Vector Database
```bash
python data_upload.py
```
### Run the API Service
```bash
python api_service.py
```
