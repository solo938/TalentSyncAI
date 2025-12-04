# TalentSyncAI
# TalentSync AI — Resume-Job Matching Engine 🧠

**Cell-by-Cell Google Colab Implementation**

TalentSync AI is an end-to-end AI-powered Resume-Job Semantic Matching System built using Sentence-BERT, spaCy NLP, FAISS vector search, scikit-learn, and custom parsing logic.

This project demonstrates a complete production-style pipeline:
- **Parsing resumes**
- **Extracting skills / education / experience**
- **Embedding job descriptions + resumes**
- **Semantic similarity scoring**
- **Ranking candidate fit**
- **Generating statistical insights**
- **Exporting results**

---

## 🚀 Key Features

### ✅ Semantic Resume–Job Matching
- Uses **Sentence-BERT** (`all-MiniLM-L6-v2`) for high-quality embeddings.
- Computes **cosine similarity** to determine match strength.
- Ranks candidates for each job using **FAISS vector search**.

### ✅ Resume Parsing Engine
Extracts:
- **Skills by category** (Programming, Cloud, ML, Databases, DevOps, etc.)
- **Years of experience** (regex-based analysis)
- **Education qualifications** (Bachelor, Master, PhD, Diploma)
- **Summary preview**
- **Word count**

### ✅ Job Description Embedding
- Converts JD text into embeddings
- Supports bulk job ingestion
- Provides overall similarity matrix

### ✅ Matching Analytics
- **Top-N resume ranking**
- **Best match summary**
- **Similarity matrix** (visualizable in CSV)
- **Statistical metrics**:
  - Mean similarity
  - Standard deviation
  - Max/min match score
  - Score thresholds (>70%, >50%, <50%)

### ✅ Export & Reporting
Saves:
- **Similarity Matrix** → `similarity_matrix.csv`
- **Detailed Matching Table** → `detailed_results.csv`
- Fully compatible with **ATS workflows**

---

## 🛠️ Tech Stack

| Component           | Technology                           |
|---------------------|--------------------------------------|
| Embeddings          | Sentence-BERT (SBERT)                |
| NLP Engine          | spaCy (`en_core_web_sm`)             |
| Vector Search       | FAISS CPU                            |
| ML/Similarity       | Scikit-learn (cosine similarity)     |
| Resume Processing   | PDFPlumber, python-docx              |
| Data Handling       | NumPy, Pandas                        |
| Dashboard-Ready     | Streamlit supported                  |

---

## 📦 Installation (Google Colab)

```bash
!pip install -q sentence-transformers
!pip install -q spacy
!pip install -q faiss-cpu
!pip install -q streamlit
!pip install -q pdfplumber
!pip install -q python-docx
!pip install -q scikit-learn
!pip install -q numpy pandas
```

**Download spaCy model:**

```bash
!python -m spacy download en_core_web_sm
```

---

## 🧩 Core Components

### 1️⃣ ResumeParser Class
Parses resumes and extracts:
- Skills by category
- Experience years
- Education level
- Summaries
- Word count

Uses custom keyword matching + regex rules.

### 2️⃣ SemanticMatcher Class
Performs:
- Resume encoding
- Job encoding
- FAISS vector indexing
- Top-K resume ranking
- Similarity matrix computation
- Single and multi-job scoring

---

## 📊 Outputs Provided

### ✔ Ranked Candidates for Each Job
Includes:
- Name
- Position
- Match percentage
- Visual match bar

### ✔ Similarity Matrix
A 4×4 job-to-resume matrix.

### ✔ Best Match Summary
Top candidate for every job with confidence label:
- **High**
- **Medium**
- **Low**

### ✔ Detailed Matching Table
Columns include:
- Job title
- Company
- Candidate
- Rank
- Match %

### ✔ Statistical Insights
- Total comparisons
- Average match
- Highest/lowest match
- Standard deviation
- Score thresholds

---

## 📁 Exported Files

| File | Description |
|------|-------------|
| `similarity_matrix.csv` | Heatmap-ready similarity matrix |
| `detailed_results.csv` | Full ranked list for all jobs/resumes |

---

## 🧪 Sample Jobs Included

1. **Senior Python Developer** (TechCorp)
2. **Full Stack JavaScript Developer** (WebSolutions)
3. **Machine Learning Engineer** (AI Corp)
4. **DevOps Engineer** (CloudServices)

---

## 🧑‍💻 Sample Resumes Included

1. **John Doe** — Senior Backend Developer
2. **Jane Smith** — Full Stack Developer
3. **Mike Johnson** — Data Scientist
4. **Sarah Williams** — DevOps Engineer

---

## ▶ Running the System

Once resumes and jobs are added:

```python
matcher.add_resumes(sample_resumes, resume_metadata)
matcher.add_jobs(sample_jobs, job_metadata)
matcher.find_top_matches(job_idx=0, top_k=5)
matcher.get_similarity_matrix()
```

---

## 📈 Example Output (Match Summary)

1. **Senior Python Developer** → John Doe → 88.4% (High)
2. **Full Stack JavaScript Developer** → Jane Smith → 91.2% (High)
3. **ML Engineer** → Mike Johnson → 85.7% (High)
4. **DevOps Engineer** → Sarah Williams → 89.9% (High)

---

## 🧱 Future Enhancements

- Streamlit UI dashboard
- RAG-based JD analysis
- PDF/Docx resume ingestion
- Weight-based scoring (skills > experience > education)
- Multi-resume batch indexing
- ATS resume formatting recommender

---

## 🤝 Contributing

Pull requests are welcome!
To contribute:

1. Fork the repo
2. Create a feature branch
3. Submit a PR

---


## ⭐ If you like this project

Please **star** the repository and share feedback!
