# 🚀 ATS Resume Analyzer - AI-Powered Resume Optimization

An intelligent ATS (Applicant Tracking System) resume analyzer that helps job seekers optimize their resumes for better visibility and higher match scores with job descriptions.

## ✨ Features

### 📄 **Resume Analysis**
- **Multi-format Support**: Upload PDF, DOCX, and TXT files
- **Smart Parsing**: Automatic extraction of contact info, skills, and experience
- **ATS Compliance Scoring**: Comprehensive 0-100 score with detailed breakdown
- **AI-Powered Feedback**: Advanced analysis using Google Gemini AI

### 🎯 **Job Matching**
- **Real-time Matching**: Compare your resume against any job description
- **Keyword Analysis**: Identify matched and missing critical keywords
- **Role Detection**: Automatically detect suitable job roles based on your skills
- **Match Percentage**: Get precise compatibility scores

### 📊 **Visual Analytics**
- **Interactive Charts**: Beautiful visualizations of your resume performance
- **Performance Heatmap**: Color-coded analysis of different resume sections
- **Score Breakdown**: Detailed insights into rule-based and LLM scoring
- **Progress Tracking**: Monitor improvements over time

### 🎨 **Modern UI/UX**
- **Glassmorphic Design**: Stunning modern interface with smooth animations
- **Responsive Layout**: Works perfectly on desktop, tablet, and mobile
- **Interactive Elements**: Hover effects, transitions, and micro-interactions
- **Professional Styling**: Clean, modern aesthetic with gradient accents

## 🛠️ Tech Stack

### Frontend
- **React 18** - Modern component-based UI
- **Vite** - Lightning-fast development and build tool
- **Chart.js** - Interactive data visualizations
- **Modern CSS** - Glassmorphic design with animations

### Backend
- **FastAPI** - High-performance Python web framework
- **Google Gemini API** - Advanced AI for resume analysis
- **scikit-learn** - Machine learning for text matching
- **pdfplumber** - PDF text extraction
- **python-docx** - DOCX file parsing

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- Node.js 16+
- Google Gemini API Key

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/resume_analyser-main.git
cd resume_analyser-main
```

2. **Backend Setup**
```bash
cd SCV
pip install -r requirement.txt
```

3. **Environment Configuration**
```bash
# Copy the example environment file
cp ../.env.example .env

# Edit .env and add your Gemini API key
# Get your API key from: https://makersuite.google.com/app/apikey
```

4. **Start Backend Server**
```bash
python server.py
```
Backend runs on `http://localhost:8000`

5. **Frontend Setup**
```bash
cd ../frontend
npm install
npm run dev
```
Frontend runs on `http://localhost:5173`

## 📖 Usage Guide

### 1. **Upload Your Resume**
- Click "Choose File" and select your resume (PDF/DOCX/TXT)
- Click "Upload & Parse" to analyze your resume
- View your ATS compliance score and detailed feedback

### 2. **Review ATS Analysis**
- **Total Score**: Overall ATS compliance (0-100)
- **Rule-Based Score**: Structured analysis (70 points max)
- **LLM Score**: AI-powered evaluation (30 points max)
- **Detailed Breakdown**: Section-by-section performance metrics

### 3. **Job Description Matching**
- Paste a job description in the text area
- Click "Analyze Match" to compare with your resume
- View match percentage and keyword analysis
- Identify missing critical skills to add

### 4. **Optimize Your Resume**
- Review AI feedback for improvement suggestions
- Add missing keywords identified in job matching
- Use the performance heatmap to strengthen weak sections
- Re-upload to track improvements

## 🏗️ Project Structure

```
resume_analyser-main/
├── SCV/                     # Backend API
│   ├── server.py            # FastAPI application
│   ├── ats_scorer.py        # ATS scoring logic
│   ├── matcher.py           # Job description matching
│   ├── llm_wrapper.py       # Gemini AI integration
│   ├── requirement.txt      # Python dependencies
│   └── utils/               # Parsing utilities
│       ├── extract.py       # File text extraction
│       ├── parse_resume.py  # Resume parsing
│       └── nlp_utils.py     # NLP processing
├── frontend/                # React application
│   ├── src/
│   │   ├── App.jsx         # Main application component
│   │   ├── ATSCharts.jsx   # Chart visualizations
│   │   └── App.css         # Styling
│   ├── package.json        # Node dependencies
│   └── index.html          # HTML template
├── .env.example            # Environment variables template
└── README.md              # This file
```

## 🔧 API Endpoints

### Upload Resume
```http
POST /upload
Content-Type: multipart/form-data

Response:
{
  "name": "John Doe",
  "contact": {
    "emails": ["john@example.com"],
    "phones": ["+1234567890"],
    "links": ["linkedin.com/in/johndoe"]
  },
  "extracted_skills": ["Python", "React", "Machine Learning"],
  "extracted_keywords": ["software engineer", "developer"],
  "ats_score": {
    "total_score": 85,
    "rule_based_score": 60,
    "llm_score": 25,
    "grade": "A",
    "llm_feedback": "Detailed AI feedback..."
  }
}
```

### Job Matching
```http
POST /match
Content-Type: application/json

{
  "resume_text": "Your resume content...",
  "jd_text": "Job description content..."
}

Response:
{
  "score": 0.75,
  "missing_keywords": {
    "critical": ["Docker", "Kubernetes"],
    "good": ["AWS", "GraphQL"],
    "optional": ["TypeScript", "Redis"]
  },
  "matched": {
    "critical": ["Python", "React"],
    "good": ["JavaScript", "Node.js"]
  },
  "detected_roles": ["Full Stack Developer", "Software Engineer"]
}
```

## 🎯 ATS Scoring Breakdown

### Rule-Based Scoring (70 points)
- **Contact Information** (10 points): Email, phone, LinkedIn
- **Resume Sections** (15 points): Proper section structure
- **Skills Section** (10 points): Well-defined skills list
- **Resume Length** (10 points): Optimal page count
- **Bullet Points** (15 points): Quantified achievements
- **Action Verbs** (10 points): Strong action words

### LLM Evaluation (30 points)
- **Content Quality**: Professionalism and clarity
- **Keyword Optimization**: ATS-friendly terminology
- **Achievement Focus**: Results-oriented content
- **Industry Standards**: Compliance with best practices

## 🌟 Advanced Features

### Performance Heatmap
Visual representation of your resume's performance across different sections:
- 🟢 **High Performance** (80-100%): Strong sections
- 🟡 **Medium Performance** (50-79%): Room for improvement
- 🔴 **Low Performance** (0-49%): Needs attention

### AI Feedback Categories
- **Content Quality**: Writing style and professionalism
- **Structure & Format**: Organization and readability
- **Keyword Optimization**: ATS-friendly terminology
- **Achievement Focus**: Quantified results and impact

### Role Detection
Automatically identifies potential job roles based on your skills:
- Software Engineer
- Data Scientist
- Product Manager
- DevOps Engineer
- And many more...

## 🔒 Environment Variables

Create a `.env` file in the `SCV` directory:

```env
# Google Gemini API Key
GEMINI_API_KEY=your_gemini_api_key_here

# Server Configuration
PORT=8000
HOST=localhost

# CORS Settings
CORS_ORIGINS=http://localhost:5173,http://localhost:3000

# File Upload Settings
MAX_FILE_SIZE=10485760  # 10MB
UPLOAD_DIR=uploads
OUTPUT_DIR=outputs

# LLM Settings
LLM_MODEL=gemini-1.5-flash
LLM_TEMPERATURE=0.3
LLM_MAX_TOKENS=1000
```

## 🐛 Troubleshooting

### Common Issues

1. **"LLM evaluation unavailable"**
   - Ensure your Gemini API key is correctly set in `.env`
   - Check your internet connection
   - Verify API key validity

2. **"Upload failed"**
   - Check if backend server is running on port 8000
   - Ensure file format is supported (PDF/DOCX/TXT)
   - Check file size (max 10MB)

3. **"Error connecting to backend"**
   - Verify backend server is running
   - Check CORS settings
   - Ensure correct port configuration

### Debug Mode
Enable debug logging by setting:
```python
import logging
logging.basicConfig(level=logging.DEBUG)
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow PEP 8 for Python code
- Use ESLint for JavaScript/React code
- Add tests for new features
- Update documentation

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Google Gemini** - For providing powerful AI capabilities
- **FastAPI** - For the excellent web framework
- **React** - For the amazing UI library
- **Chart.js** - For beautiful data visualizations



**🚀 Start optimizing your resume today and land your dream job!**
