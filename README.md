# Data Mining

A localhost-based scientific literature mining pipeline for collecting, organizing, and extracting data from organic thermoelectric polymer research papers.

---

# Goal

Build an ethical and scalable pipeline that can:

- Search scientific papers
- Collect metadata
- Check legal open-access availability
- Download allowed PDFs
- Extract text and tables
- Extract thermoelectric polymer properties
- Export a structured dataset

---

# Workflow

```text
Search Keyword
      ↓
Collect Metadata
      ↓
Check Open-Access Status
      ↓
Download Legal PDFs
      ↓
Extract Text and Tables
      ↓
Extract Polymer Properties
      ↓
Export Final Dataset
```

---

# Project Structure

```text
Data-Mining/
│
├── README.md
├── requirements.txt
├── .env
├── .gitignore
│
├── data/
│   ├── raw_pdfs/
│   ├── parsed_text/
│   ├── extracted_tables/
│   └── exports/
│
├── database/
│   ├── papers.db
│   └── schema.sql
│
├── logs/
│   ├── downloader.log
│   ├── failed_downloads.csv
│   └── pipeline_runs.log
│
├── app/
│   ├── main.py
│   ├── config.py
│   │
│   ├── routes/
│   │   ├── search_routes.py
│   │   ├── download_routes.py
│   │   ├── parse_routes.py
│   │   └── export_routes.py
│   │
│   ├── services/
│   │   ├── openalex_service.py
│   │   ├── crossref_service.py
│   │   ├── unpaywall_service.py
│   │   ├── downloader.py
│   │   ├── pdf_parser.py
│   │   ├── table_parser.py
│   │   └── extractor.py
│   │
│   ├── models/
│   │   ├── paper.py
│   │   └── extraction.py
│   │
│   ├── templates/
│   │   ├── index.html
│   │   ├── results.html
│   │   ├── paper.html
│   │   └── dashboard.html
│   │
│   └── static/
│       ├── style.css
│       └── script.js
│
├── notebooks/
│   ├── 01_metadata_exploration.ipynb
│   ├── 02_pdf_text_extraction.ipynb
│   └── 03_property_analysis.ipynb
│
├── scripts/
│   ├── run_metadata_search.py
│   ├── run_oa_check.py
│   ├── run_downloader.py
│   ├── run_parser.py
│   └── run_full_pipeline.py
│
└── tests/
    ├── test_openalex.py
    ├── test_unpaywall.py
    ├── test_downloader.py
    └── test_parser.py
```

---

# Folder Purpose

| Folder/File | Purpose |
|---|---|
| `app/` | Main localhost FastAPI web application |
| `routes/` | Handles web requests and user actions |
| `services/` | Core data mining and extraction logic |
| `models/` | Data structures for papers and extracted properties |
| `templates/` | HTML pages for the localhost dashboard |
| `static/` | CSS and JavaScript frontend files |
| `data/` | Stores PDFs, parsed text, tables, and exports |
| `database/` | SQLite database and schema |
| `logs/` | Download and pipeline logs |
| `notebooks/` | Research experiments and analysis |
| `scripts/` | Run pipeline steps manually |
| `tests/` | Unit tests for validation |

---

# Localhost Dashboard

The project runs locally at:

```text
http://localhost:8000
```

The dashboard allows users to:

- Search scientific papers
- View metadata
- Check open-access status
- Download legal PDFs
- Parse papers
- Extract scientific properties
- Export datasets

---

# Installation

## Create Virtual Environment

```bash
python -m venv venv
```

## Activate Virtual Environment

### Windows

```bash
venv\Scripts\activate
```

### Mac/Linux

```bash
source venv/bin/activate
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Running the Application

```bash
uvicorn app.main:app --reload
```

Open in browser:

```text
http://localhost:8000
```

---

# Main Technologies

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| FastAPI | Localhost backend framework |
| SQLite | Database storage |
| OpenAlex API | Metadata collection |
| Crossref API | DOI metadata |
| Unpaywall API | Legal open-access checking |
| PyMuPDF | PDF text extraction |
| pdfplumber | Table extraction |
| Pandas | Data cleaning and export |

---

# Ethical Data Mining

This project only downloads papers from legal sources such as:

- Open-access publisher pages
- Institutional repositories
- Author accepted manuscripts
- Preprint servers
- University-accessible resources

This project does not support:

- Bypassing paywalls
- Illegal paper repositories
- Unauthorized scraping
- Violating publisher terms

---

# Target Extracted Data

```text
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
```

---

# Final Output

Example final dataset:

```text
data/exports/organic_te_dataset.csv
```

https://chatgpt.com/c/6a053606-1468-838d-be8c-82119b85a2c4