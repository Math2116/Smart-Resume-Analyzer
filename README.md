# 🧠 Smart Resume Analyzer

An AI-powered resume analysis tool that streamlines early-stage hiring by automatically comparing candidate resumes with job descriptions to generate **ATS-style scores**, **matched/missing skills**, and **human-like improvement suggestions**.

---

## 🚀 Features
- 📄 **Resume Parsing** — Uses **Apache Tika** to extract clean text from PDF/DOCX resumes.  
- 🧩 **NLP Processing** — Powered by **Apache OpenNLP** for tokenization, POS tagging, and entity recognition to identify key skills and experience.  
- 📊 **Scoring Engine** — Computes **cosine similarity** on TF-IDF/keyword vectors, with rule-based weighting for exact matches and experience hints.  
- 💡 **Smart Suggestions** — Optionally integrates **OpenAI API** to produce personalized, natural improvement tips (with safe prompt handling).  
- 💾 **Persistence Layer** — Stores results and logs in **SQLite** for portability.  
- 🧱 **Backend** — Developed in **Java (Maven project)** with **JUnit** tests and **Log4j** structured logging.  
- 🌐 **Frontend** — Simple and responsive **HTML/CSS/JavaScript** UI for file uploads and report visualization.  
- 🐳 **Deployment** — Fully **containerized with Docker** for consistent builds and deployments.

---

## ⚙️ Tech Stack
| Layer | Technology |
|--------|-------------|
| Frontend | HTML, CSS, JavaScript |
| Backend | Java (Spring or Core Java Service) |
| Libraries | Apache Tika, Apache OpenNLP |
| Database | SQLite |
| Testing | JUnit |
| Logging | Log4j |
| Build Tool | Maven |
| Containerization | Docker |
| IDE | IntelliJ IDEA |

---

## 🧪 How It Works
1. **Upload a resume** (PDF/DOCX) and **paste a job description**.  
2. **Apache Tika** extracts plain text from the file.  
3. **OpenNLP** processes the text to identify skills, entities, and experience phrases.  
4. The **scoring module** matches extracted skills with the job description using **TF-IDF** and **cosine similarity**.  
5. **Matched and missing skills** are displayed with an overall **ATS compatibility score**.  
6. Optionally, the **OpenAI API** generates natural-language suggestions to improve the resume.  
7. **Results are stored** in SQLite for audit or analysis.

---

## 🧰 Build and Run
```bash
# Clone the repository
git clone https://github.com/yourusername/smart-resume-analyzer.git
cd smart-resume-analyzer

# Build the Maven project
mvn clean install

# Run the service
java -jar target/smart-resume-analyzer.jar

# (Optional) Build Docker image
docker build -t smart-resume-analyzer .
docker run -p 8080:8080 smart-resume-analyzer
