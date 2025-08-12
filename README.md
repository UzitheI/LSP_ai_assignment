# 🏢 Corporate Intelligence Extractor

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://python.org)
[![LangChain](https://img.shields.io/badge/LangChain-Latest-green)](https://langchain.com)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Gemini](https://img.shields.io/badge/AI-Gemini%202.5-purple)](https://ai.google.dev)

> **Advanced AI-Powered Company Information Mining System**

A sophisticated multi-modal extraction engine that leverages cutting-edge LangChain technology to intelligently parse corporate narratives and extract structured business intelligence. This system employs advanced natural language processing with confidence scoring, data validation, and enhanced analytics.

## 🚀 Features

### Core Capabilities
- **🧠 Smart Entity Recognition** - AI-powered extraction with confidence scoring
- **📅 Multi-format Date Intelligence** - Fuzzy matching with intelligent defaults
- **👥 Founder Name Standardization** - Automated name cleaning and deduplication
- **🎯 Interactive Data Validation** - Real-time quality assessment dashboard
- **📊 Enhanced Analytics** - Industry classification and trend analysis
- **⚡ Real-time Processing** - Progress tracking with visual feedback
- **🏆 Quality Metrics** - Comprehensive extraction confidence scoring

### Advanced Analytics
- **Industry Distribution Analysis** - Automatic business sector categorization
- **Founding Decade Trends** - Historical pattern identification
- **Geographic Intelligence** - Location extraction and mapping
- **Founder Analytics** - Comprehensive statistical insights
- **Company Age Calculations** - Automatic age computation from founding dates

### Multi-Format Export System
- **📄 `company_info.csv`** - Standard format (assignment compliant)
- **📈 `company_info_enhanced.csv`** - Complete dataset with all extracted fields
- **📊 `company_info_quality_report.csv`** - Performance metrics and confidence scores
- **🎯 `company_info_analytics.csv`** - Business intelligence insights and trends

## 🛠️ Technology Stack

- **🐍 Python 3.8+** - Core programming language
- **🦜 LangChain** - AI orchestration framework
- **🧠 Google Gemini 2.5 Flash** - Large language model
- **📊 Pandas** - Data manipulation and analysis
- **🔍 Pydantic** - Data validation and settings management
- **📝 Regular Expressions** - Pattern matching and text processing

## 📋 Prerequisites

Before running this system locally, ensure you have:

1. **Python 3.8 or higher** installed
2. **Google AI Studio API Key** (for Gemini access)
3. **Git** (for cloning the repository)
4. **Jupyter Notebook** environment (VS Code, JupyterLab, or Google Colab)

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/sup-neupane/LSPP-Assignment-AI.git
cd LSPP-Assignment-AI
```

### 2. Set Up Python Environment

#### Option A: Using Virtual Environment (Recommended)
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
# venv\Scripts\activate
```

#### Option B: Using Conda
```bash
# Create conda environment
conda create -n corporate-intel python=3.9
conda activate corporate-intel
```

### 3. Install Dependencies

```bash
# Install required packages
pip install langchain langchain-google-genai pydantic pandas jupyter
```

Or use the requirements file:

```bash
pip install -r requirements.txt
```

### 4. Set Up API Keys

#### Method 1: Environment Variables (Recommended for Local Development)
```bash
# Set your Gemini API key
export GOOGLE_API_KEY="your_gemini_api_key_here"
```

#### Method 2: Create a `.env` file
```bash
# Create .env file in project root
echo "GOOGLE_API_KEY=your_gemini_api_key_here" > .env
```

#### Method 3: For Google Colab
```python
# In Google Colab, use userdata
from google.colab import userdata
os.environ["GOOGLE_API_KEY"] = userdata.get("GEMINI_API_KEY")
```

### 5. Obtain Gemini API Key

1. Visit [Google AI Studio](https://aistudio.google.com/)
2. Sign in with your Google account
3. Create a new API key
4. Copy the API key for use in the system

### 6. Run the System

#### Option A: Jupyter Notebook
```bash
# Start Jupyter Notebook
jupyter notebook

# Open LSPP_AssignmentAI.ipynb
# Run all cells sequentially
```

#### Option B: VS Code
```bash
# Open in VS Code
code .

# Open LSPP_AssignmentAI.ipynb
# Use VS Code's Jupyter extension to run cells
```

#### Option C: Google Colab
1. Upload `LSPP_AssignmentAI.ipynb` to Google Colab
2. Add your Gemini API key to Colab secrets
3. Run all cells

## 📁 Project Structure

```
LSPP-Assignment-AI/
├── LSPP_AssignmentAI.ipynb    # Main extraction system notebook
├── README.md                   # This file
├── requirements.txt            # Python dependencies
├── .env.example               # Environment variables template
├── .gitignore                 # Git ignore rules
└── outputs/                   # Generated output files
    ├── company_info.csv              # Standard format results
    ├── company_info_enhanced.csv     # Complete dataset
    ├── company_info_quality_report.csv # Performance metrics
    └── company_info_analytics.csv    # Business insights
```

## 💻 Local Usage Guide

### Basic Usage

1. **Start the System**
   ```python
   # Initialize the advanced extraction pipeline
   advanced_pipeline = AdvancedCompanyExtractionPipeline(llm)
   ```

2. **Process Text**
   ```python
   # Extract companies from your text
   companies, metrics = advanced_pipeline.process_text_with_analytics(your_text)
   ```

3. **Export Results**
   ```python
   # Generate comprehensive reports
   export_results = export_enhanced_results(companies, metrics, analytics)
   ```

### Advanced Configuration

#### Customize Confidence Thresholds
```python
# Filter by confidence levels
high_confidence = [c for c in companies if c.confidence_score > 0.8]
medium_confidence = [c for c in companies if 0.5 < c.confidence_score <= 0.8]
```

#### Modify Processing Parameters
```python
# Adjust LLM settings
llm = ChatGoogleGenerativeAI(
    model="gemini-2.5-flash-lite",
    temperature=0.3,      # Lower = more deterministic
    max_tokens=None       # Unlimited response length
)
```

#### Custom Industry Classification
```python
industry_keywords = {
    'Your_Industry': ['keyword1', 'keyword2', 'keyword3']
}
```

## 📊 Output Formats

### Standard CSV (`company_info.csv`)
```csv
S.N.,Company Name,Founded in,Founded by
1,Microsoft Corporation,1975-04-04,"Bill Gates, Paul Allen"
2,Apple Inc.,1976-04-01,"Steve Jobs, Steve Wozniak, Ronald Wayne"
```

### Enhanced CSV (`company_info_enhanced.csv`)
```csv
S.N.,Company Name,Founded in,Founded by,Confidence Score,Company Age,Founder Count,Location,Industry
1,Microsoft Corporation,1975-04-04,"Bill Gates, Paul Allen",0.950,49,2,"Albuquerque, New Mexico",Technology
```

### Quality Report (`company_info_quality_report.csv`)
```csv
Metric,Value
Total Companies Extracted,25
Average Confidence Score,87.3%
High-Confidence Extractions,18 (72.0%)
Processing Time (seconds),12.45
```

### Analytics Report (`company_info_analytics.csv`)
```csv
Category,Subcategory,Count,Percentage
Industry,Technology,12,48.0%
Industry,E-commerce,5,20.0%
Founding Decade,1970s,8,32.0%
```

## 🔧 Troubleshooting

### Common Issues

#### API Key Not Working
```bash
# Verify API key is set
echo $GOOGLE_API_KEY

# Test API connection
python -c "import os; from langchain_google_genai import ChatGoogleGenerativeAI; llm = ChatGoogleGenerativeAI(model='gemini-2.5-flash-lite'); print(llm.invoke('Hello').content)"
```

#### Missing Dependencies
```bash
pip install --upgrade langchain langchain-google-genai pydantic pandas
```

#### Memory Issues with Large Texts
```python
# Process in smaller chunks
paragraphs = split_into_paragraphs(large_text)
for chunk in chunks(paragraphs, 10):  
    results = pipeline.process_paragraphs(chunk)
```

#### Rate Limiting
```python
# Increase delay between requests
import time
time.sleep(1.0) 
```

## 🧪 Testing

### Run System Tests
```python
test_dates = ["May 8, 1886", "2009", "August 2008"]
for date in test_dates:
    normalized, confidence = normalize_date_advanced(date)
    print(f"'{date}' → '{normalized}' (confidence: {confidence:.2f})")
```

### Validate Extractions
```python
# Test extraction on sample paragraph
test_paragraph = "Microsoft Corporation was founded on April 4, 1975, by Bill Gates and Paul Allen."
result = extraction_chain.invoke({"paragraph": test_paragraph})
print(result)
```

## 📈 Performance Optimization

### Speed Improvements
- Use batch processing for large documents
- Implement caching for repeated extractions
- Optimize regex patterns for date matching
- Use async processing for concurrent API calls

### Memory Optimization
- Process documents in chunks
- Clear intermediate results
- Use generators for large datasets
- Implement lazy loading for analytics

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit changes (`git commit -am 'Add new feature'`)
4. Push to branch (`git push origin feature/new-feature`)
5. Create Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **LangChain** - For the powerful AI orchestration framework
- **Google AI** - For providing the Gemini 2.5 Flash model
- **Pandas** - For excellent data manipulation capabilities
- **Pydantic** - For robust data validation

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Troubleshooting](#-troubleshooting) section
2. Review the [Issues](https://github.com/sup-neupane/LSPP-Assignment-AI/issues) page
3. Create a new issue with detailed information

## 🎯 Assignment Compliance

This system fully meets all LSPP assignment requirements:

- ✅ **LCEL Framework Implementation** - Advanced chains with RunnableLambda
- ✅ **Paragraph-by-Paragraph Processing** - Individual processing with progress tracking
- ✅ **Company Name Extraction** - Enhanced with confidence scoring
- ✅ **Founding Date Extraction** - Smart normalization (YYYY-MM-DD format)
- ✅ **Founder Information Extraction** - Name standardization and validation
- ✅ **CSV Export** - Standard `company_info.csv` format
- ✅ **Date Intelligence** - Handles incomplete dates with smart defaults
- ✅ **Agentic Workflow** - Multi-stage processing pipeline

### Bonus Features
- 🚀 **Advanced Analytics** - Industry insights and quality metrics
- 🚀 **Confidence Scoring** - AI-powered extraction quality assessment
- 🚀 **Geographic Intelligence** - Location extraction and analysis
- 🚀 **Multi-Format Export** - 4 comprehensive output files

---

**Built with ❤️ using LangChain and Google Gemini AI**
