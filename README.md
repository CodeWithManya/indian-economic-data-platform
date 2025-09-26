# EconoData India - AI-Powered Economic Data Platform

## 🎯 Project Overview

EconoData India is a revolutionary one-stop platform that aggregates all Indian economic indicators and datasets, making them accessible and understandable for undergraduate students. Unlike complex platforms like CMIE and CEIC, our solution combines real-time data aggregation with AI-powered insights to democratize economic education in India.

**Built for FutureStack25 GenAI Hackathon** 🚀

## ✨ Key Features

- **Real-time Data Aggregation**: Automatically fetches and updates economic indicators from RBI, MOSPI, and other government sources
- **AI-Powered Blog Generation**: Creates student-friendly explanations of complex economic trends using Cerebras + Llama
- **Interactive Dashboards**: Intuitive visualizations with trend analysis and historical context
- **Mobile-First Design**: Responsive interface optimized for students on-the-go
- **Natural Language Queries**: Ask questions like "Why is inflation rising?" and get AI-generated explanations
- **Educational Context**: Every indicator includes "What does this mean?" explanations

## 🛠 Technology Stack

### Sponsor Technologies
- **🧠 Cerebras API**: Ultra-fast AI inference (20x faster than GPUs) for real-time economic analysis
- **🦙 Meta Llama 3.1**: Advanced language model for natural language processing and content generation
- **🐳 Docker**: Containerization for seamless deployment and scalability

### Core Technologies
- **Backend**: FastAPI with Python 3.11
- **Frontend**: Next.js 14 with TypeScript
- **Database**: PostgreSQL with TimescaleDB extension
- **Visualization**: Recharts for interactive charts
- **Styling**: Tailwind CSS for responsive design
- **Scheduling**: APScheduler for automated data updates

## 🏗 Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Data Pipeline │────│   PostgreSQL    │────│   Backend API   │
│   (RBI, MOSPI)  │    │   (TimeSeries)  │    │   (FastAPI)     │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                                        │
┌─────────────────┐    ┌─────────────────┐             │
│  AI Services    │────│  Cerebras +     │─────────────┘
│  (Blog Gen)     │    │  Llama 3.1      │
└─────────────────┘    └─────────────────┘             │
                                                        │
                       ┌─────────────────┐             │
                       │   Frontend      │─────────────┘
                       │   (Next.js)     │
                       └─────────────────┘
```

## 🚀 Quick Start

### Prerequisites
- Docker Desktop
- Node.js 18+
- Python 3.11+
- Git

### Environment Setup
1. Clone the repository:
```bash
git clone https://github.com/yourusername/econodata-india.git
cd econodata-india
```

2. Copy environment variables:
```bash
cp .env.example .env
```

3. Add your API keys to `.env`:
```env
CEREBRAS_API_KEY=your_cerebras_key_here
LLAMA_API_KEY=your_llama_key_here
DATABASE_URL=postgresql://user:pass@db:5432/econodata
```

### Running with Docker (Recommended)
```bash
# Build and start all services
docker compose up --build

# Access the application
Frontend: http://localhost:3000
Backend API: http://localhost:8000
API Docs: http://localhost:8000/docs
```

### Running Locally (Development)
```bash
# Start PostgreSQL
docker run --name postgres -e POSTGRES_PASSWORD=password -p 5432:5432 -d postgres

# Backend
cd backend
pip install -r requirements.txt
uvicorn main:app --reload --port 8000

# Frontend
cd frontend
npm install
npm run dev

# Data Pipeline
cd data-pipeline
pip install -r requirements.txt
python scheduler.py
```

## 📊 API Endpoints

### Data Endpoints
- `GET /indicators` - List all available economic indicators
- `GET /indicators/{id}/data` - Get time-series data for specific indicator
- `GET /indicators/{id}/data?start=2024-01-01&end=2024-12-31` - Data with date range

### AI-Powered Features
- `POST /blogs/generate` - Generate AI blog post from latest economic data
- `GET /blogs` - List all generated blog posts
- `POST /ai/explain` - Get AI explanation of specific economic trend

### Example Response
```json
{
  "indicator": "gdp_growth",
  "name": "GDP Growth Rate",
  "description": "Quarterly GDP growth rate (YoY %)",
  "data": [
    {
      "date": "2024-09-30",
      "value": 7.2,
      "source": "MOSPI"
    }
  ]
}
```

## 🎓 Educational Features

### For Students
- **Simplified Language**: Complex economic terms explained in plain English
- **Visual Learning**: Interactive charts with hover explanations
- **Context Cards**: "Why this matters" sections for each indicator
- **Assignment Helper**: Easy data export for academic projects
- **Mobile Optimized**: Study anywhere, anytime

### AI-Generated Content
- **Weekly Summaries**: "This Week in Indian Economy"
- **Trend Analysis**: "Understanding Current Inflation Trends"
- **Career Context**: "How GDP Growth Affects Job Opportunities"
- **Comparative Studies**: "India vs Global Economic Performance"

## 🧪 Testing

```bash
# Backend tests
cd backend
pytest tests/ -v

# Frontend tests
cd frontend
npm test

# Integration tests
docker compose -f docker-compose.test.yml up --abort-on-container-exit
```

## 📈 Data Sources

- **Reserve Bank of India (RBI)**: Monetary policy, banking statistics
- **Ministry of Statistics (MOSPI)**: GDP, inflation, employment data
- **Data.gov.in**: Government economic datasets
- **Economic Adviser Office**: Industrial production, trade data

## 🎯 Target Impact

### Problem Solved
- **40+ million Indian undergraduate students** struggle with expensive, complex economic data platforms
- Current solutions like CMIE cost ₹50,000+ annually
- No student-friendly interface for economic data analysis

### Our Solution Impact
- **Free access** to comprehensive economic data
- **AI-powered explanations** make complex data understandable
- **Mobile-first design** reaches students across India
- **Real-time updates** ensure latest information for research

## 🏆 Hackathon Achievements

### Sponsor Technology Integration
- **Cerebras**: Lightning-fast inference for real-time economic analysis (2,500+ tokens/sec)
- **Llama 3.1**: Multilingual content generation (English/Hindi) with 128K context
- **Docker**: Seamless containerization enabling easy deployment and scaling

### Judging Criteria Excellence
- **Potential Impact**: Democratizing economic education for millions of Indian students
- **Creativity**: First AI-powered, student-centric economic data platform in India
- **Technical Implementation**: Sophisticated AI pipeline with real-time data integration
- **User Experience**: Intuitive, mobile-first design with educational focus

## 🚀 Future Roadmap

### Phase 2 Features
- **Regional Language Support**: Tamil, Bengali, Gujarati interfaces
- **University Partnerships**: Integration with academic curricula
- **Advanced AI Features**: Predictive economic modeling
- **Community Platform**: Student discussion forums and study groups

### Scaling Plans
- **Multi-country Expansion**: South Asian economic data aggregation
- **Premium Features**: Advanced analytics for researchers
- **API Marketplace**: Third-party developer ecosystem

## 👥 Team

- **Economics & Backend**: Data pipeline architecture, economic analysis, AI integration
- **UI/UX & Frontend**: Student-centric design, responsive interfaces, user experience optimization

## 📄 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## 🙏 Acknowledgments

- **FutureStack25 Hackathon** for the opportunity to build impactful AI solutions
- **Cerebras** for providing world's fastest AI inference capabilities
- **Meta** for open-source Llama models enabling accessible AI
- **Docker** for containerization technology enabling seamless deployment
- **Indian Government** for open data initiatives making this platform possible

## 📞 Contact

- **Demo Video**: [YouTube Link](https://youtube.com/demo)
- **Live Platform**: [econodata-india.tech](https://econodata-india.tech)
- **GitHub**: [Repository](https://github.com/yourusername/econodata-india)

---

*Built with ❤️ for Indian students during FutureStack25 GenAI Hackathon*

**#FutureStack25 #AI4Education #EconomicData #StudentFirst**
