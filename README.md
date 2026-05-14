# Data Mining

A localhost-based data mining project for collecting and organizing research papers about organic thermoelectric polymers.

## Goal

Build an ethical pipeline that can search papers, collect metadata, check legal open-access availability, download allowed PDFs, extract text/tables, extract useful polymer properties, and export a clean dataset.

## Workflow

Search keyword → Collect metadata → Check open-access status → Download legal PDFs → Extract text/tables → Extract polymer properties → Export dataset

## Project Structure

Data-Mining/
├── README.md
├── requirements.txt
├── .env
├── .gitignore
├── data/
│   ├── raw_pdfs/
│   ├── parsed_text/
│   ├── extracted_tables/
│   └── exports/
├── database/
│   ├── papers.db
│   └── schema.sql
├── logs/
│   ├── downloader.log
│   ├── failed_downloads.csv
│   └── pipeline_runs.log
├── app/
│   ├── main.py
│   ├── config.py
│   ├── routes/
│   ├── services/
│   ├── models/
│   ├── templates/
│   └── static/
├── notebooks/
├── scripts/
└── tests/

## Folder Purpose

app/ = localhost FastAPI web app  
routes/ = web pages and button actions  
services/ = main data mining logic  
models/ = data structures for papers and extracted values  
templates/ = HTML pages for localhost  
static/ = CSS and JavaScript  
data/ = PDFs, extracted text, tables, and final exports  
database/ = stores paper metadata and extraction results  
logs/ = tracks downloads, failures, and pipeline activity  
notebooks/ = experiments and analysis  
scripts/ = run pipeline steps from terminal  
tests/ = check if the code works correctly  

## Localhost

The project will run at:

http://localhost:8000

The localhost dashboard will let the user search papers, view results, check open-access status, download legal PDFs, parse papers, and export datasets.

## Installation

Create virtual environment:

python -m venv venv

Activate it on Windows:

venv\Scripts\activate

Activate it on Mac/Linux:

source venv/bin/activate

Install packages:

pip install -r requirements.txt

Run the app:

uvicorn app.main:app --reload

Open:

http://localhost:8000

## Main Tools

Python = main programming language  
FastAPI = localhost web app  
SQLite = database  
OpenAlex = paper metadata search  
Crossref = DOI metadata  
Unpaywall = legal open-access checking  
PyMuPDF = PDF text extraction  
pdfplumber = table extraction  
Pandas = data cleaning and export  

## Ethical Rules

This project only downloads papers from legal sources such as open-access publisher pages, preprint servers, institutional repositories, and university-accessible resources.

It does not support bypassing paywalls, illegal paper repositories, or unauthorized scraping.

## Target Data

The final dataset aims to include:

title  
doi  
year  
journal  
polymer  
dopant  
solvent  
conductivity  
seebeck_coefficient  
power_factor  
zt  
temperature  
film_preparation_method  

## Final Output

The final exported dataset will be saved in:

data/exports/organic_te_dataset.csv