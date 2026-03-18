# 🚀 N.O.V.A. - Networked Onboarding Virtual Assistant

**Organization:** Code Yodha Technologies  
**Repository:** Code-Yodha-NOVA/nova-system  
**Version:** 2.1.0  
**Status:** Active Development 🟢

---

## 📋 Overview

N.O.V.A. is an intelligent **AI-powered developer onboarding platform** that transforms how new developers join and integrate into teams. It provides personalized guidance, knowledge management, and collaborative features all in one unified workspace.

**Core Mission:** Reduce developer onboarding time from 2-3 weeks to 3-4 days through intelligent AI assistance and centralized knowledge management.

---

## ⭐ Key Features

### 1. 🤖 Nova Chatbot
- Intelligent AI assistant powered by Groq LLM
- Answers onboarding questions with context awareness
- Fetches project README directly from GitHub
- Creates GitHub issues from chat
- Searches knowledge base for answers
- Multi-turn conversations

### 2. 📚 Knowledge Base
- 3-tier knowledge management system
- RAG (Retrieval-Augmented Generation) powered
- Full-text search capability
- Internal documentation library
- Searchable templates and examples
- Always up-to-date information

### 3. 🛣️ My Path - Personalized Onboarding
- AI-detects developer persona (Backend/Frontend/DevOps/etc)
- Custom checklist based on role
- Step-by-step guidance
- Progress tracking dashboard
- Adaptive learning paths
- Milestone celebrations

### 4. 💬 Team Forum
- Discussion platform for developers
- Create discussion threads about challenges
- Get solutions from teammates
- Upvote helpful answers
- Build searchable knowledge base
- Category organization (Setup, Debugging, Architecture, Tools, Best Practices)

### 5. 🔗 GitHub Integration
- Fetch repository README in chat
- View open issues and pull requests
- Create GitHub issues directly from N.O.V.A.
- Track project progress
- Monitor team activity
- Real-time GitHub data sync

### 6. 📊 Progress Dashboard
- Onboarding completion percentage
- Time spent on each section
- Resources accessed count
- Knowledge gained metrics
- Next steps recommendations

---

## 🚀 Quick Start

### Prerequisites

```
✓ Python 3.9 or higher
✓ Node.js 16 or higher  
✓ GitHub personal access token
✓ Groq API key (for LLM features)
✓ Git
```

### Installation

#### 1. Backend Setup

```bash
# Clone repository
git clone https://github.com/Code-Yodha-NOVA/nova-system.git
cd nova-system/backend

# Create virtual environment
python -m venv .venv

# Activate virtual environment
# On macOS/Linux:
source .venv/bin/activate

# On Windows:
.venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Create .env file with your credentials
cat > .env << EOF
GITHUB_TOKEN=ghp_your_github_token_here
GITHUB_ORG=Code-Yodha-NOVA
GITHUB_REPO=nova-system
GROQ_API_KEY=gsk_your_groq_key_here
EOF

# Start the backend server
python main.py
# Server will run on http://localhost:8000
```

#### 2. Frontend Setup

```bash
# Navigate to frontend
cd ../frontend

# Install dependencies
npm install

# Start development server
npm run dev
# Frontend will run on http://localhost:3000
```

#### 3. Access the Application

```
Open your browser: http://localhost:3000
Start your onboarding journey! 🚀
```

---

## 🏗️ Architecture

### System Overview

```
┌─────────────────────────┐
│    Frontend (React)     │
│   localhost:3000        │
└────────────┬────────────┘
             │ HTTP/REST
             │
┌────────────▼─────────────┐
│  Backend (FastAPI)       │
│  localhost:8000          │
└───┬────────┬────────┬────┘
    │        │        │
    ▼        ▼        ▼
  Groq    GitHub   ChromaDB
 (LLM)    (API)    (Vector)
```

### Technology Stack

**Frontend:**
- Next.js 14 - React framework with file-based routing
- React 18 - UI component library
- TypeScript - Type-safe JavaScript
- Tailwind CSS - Utility-first CSS framework
- Lucide React - Beautiful icon library

**Backend:**
- FastAPI - Modern Python web framework
- Python 3.9+ - Programming language
- Pydantic - Data validation library
- PyGithub - GitHub API client
- Uvicorn - ASGI application server

**AI/ML:**
- Groq API - Large Language Model (LLM) inference
- LangGraph - Agent orchestration framework
- ChromaDB - Vector database for embeddings
- Sentence Transformers - Text embedding model

**Integration:**
- GitHub API - Repository and issue management
- SMTP - Email notifications
- Jira - Project tracking (optional)
- Slack - Workspace notifications (optional)

---

## 💻 Usage Examples

### Ask Nova About the Project

```
You: "Show me the README"

Nova: 📖 Project README
      ▼ Overview
      ▼ Key Features  
      ▼ Quick Start
      ▼ Architecture
      ▼ API Endpoints
      ▼ Troubleshooting

(Click to expand any section)
```

### Get Onboarding Guidance

```
You: "How do I get started?"

Nova: Based on your role, here's your personalized checklist:
      ✓ Clone repository
      ✓ Set up environment
      ✓ Run tests
      ✓ Read architecture docs
      ✓ Set up local database
      
      You've completed 2/5 tasks (40%)
```

### Create a GitHub Issue

```
You: "Create issue: Add authentication to API"

Nova: ✅ Issue #145 created!
      
      Title: Add authentication to API
      Status: Open
      Labels: enhancement
      
      View on GitHub: [link]
```

### Ask the Team Forum

```
You: "How do I set up PostgreSQL?"

Nova: Found similar discussions:
      
      • PostgreSQL Setup (by Vikram) - 12 upvotes
      • Database Configuration Guide (by Sofia) - 8 upvotes
      
      Create new thread or view existing?
```

---

## 📡 API Endpoints

### Chat API

```http
POST /api/chat/message
Content-Type: application/json

{
  "content": "Show me the README"
}

Response:
{
  "type": "readme",
  "title": "📖 Project README",
  "content": "# N.O.V.A...",
  "sections": [...]
}
```

### GitHub API

```http
GET /api/github/readme
→ Fetch repository README

GET /api/github/issues?state=open
→ List open issues

POST /api/github/issues
→ Create new issue

GET /api/github/pull-requests
→ List pull requests
```

### Forum API

```http
GET /api/forum/threads
→ Get discussion threads

POST /api/forum/threads
→ Create thread

POST /api/forum/threads/{id}/comments
→ Add comment

POST /api/forum/threads/{id}/vote
→ Upvote/downvote thread
```

### Search API

```http
GET /api/search?q=authentication
→ Search knowledge base

GET /api/knowledge-base
→ Get all resources
```

---

## 🧪 Features in Detail

### Smart Persona Detection

When you first open N.O.V.A., it asks about your role:
- **Backend Developer** - Focus on APIs, databases, server logic
- **Frontend Developer** - Focus on UI, components, styling
- **DevOps Engineer** - Focus on deployment, CI/CD, infrastructure
- **Product Manager** - Focus on features, requirements, roadmap
- **Designer** - Focus on UI/UX, design systems, prototypes

Based on your selection, you get a customized onboarding path.

### Multi-Tier Knowledge Management

**Tier 1: Public Knowledge**
- FAQs and getting started guides
- Best practices and conventions
- General development guidelines
- Public documentation

**Tier 2: Internal Knowledge**  
- Company-specific workflows
- Team processes and standards
- Project-specific architecture
- Internal guidelines

**Tier 3: Templates**
- Email templates
- Document templates
- Code snippet templates
- Issue templates

### Real-time GitHub Integration

- Fetches README from your GitHub repository
- Creates issues that appear in GitHub
- Shows live pull request status
- Displays repository statistics
- Links issues to forum discussions

---

## 🔧 Configuration

### Environment Variables

Create `.env` file in backend root:

```env
# GitHub Integration (Required)
GITHUB_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxxxx
GITHUB_ORG=Code-Yodha-NOVA
GITHUB_REPO=nova-system

# Groq AI (Required)
GROQ_API_KEY=gsk_xxxxxxxxxxxxxxxxxxxxxx

# SMTP Email (Optional)
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
SMTP_USERNAME=your-email@gmail.com
SMTP_PASSWORD=your-app-password

# Database (Optional - Production)
DATABASE_URL=postgresql://user:password@localhost:5432/nova_db
REDIS_URL=redis://localhost:6379/0

# Server Settings
SERVER_HOST=0.0.0.0
SERVER_PORT=8000
ENVIRONMENT=development
```

### Getting API Keys

#### GitHub Personal Access Token

1. Go to: https://github.com/settings/tokens
2. Click "Generate new token (classic)"
3. Name it: `Nova Development`
4. Select scopes:
   - ✅ `repo` - Full control of private repositories
   - ✅ `read:org` - Read organization data
   - ✅ `read:user` - Read user profile data
5. Generate and copy the token
6. Paste into `.env`

#### Groq API Key

1. Visit: https://console.groq.com/keys
2. Click "Create API Key"
3. Copy the key
4. Paste into `.env`

---

## 📁 Project Structure

```
nova-system/
│
├── frontend/                    # React + Next.js Frontend
│   ├── src/
│   │   ├── app/
│   │   │   ├── chat/           # Chat interface
│   │   │   ├── my-path/        # Onboarding journey
│   │   │   ├── knowledge-base/  # Search & docs
│   │   │   ├── forum/          # Team discussions
│   │   │   ├── github/         # GitHub integration
│   │   │   └── layout.tsx      # Root layout
│   │   │
│   │   ├── components/         # Reusable components
│   │   │   ├── SidebarLayout.tsx
│   │   │   ├── ChatMessage.tsx
│   │   │   └── ...
│   │   │
│   │   └── context/            # React contexts
│   │       ├── ChatContext.tsx
│   │       └── AuthContext.tsx
│   │
│   └── package.json
│
├── backend/                     # FastAPI Backend
│   ├── main.py                 # Entry point
│   │
│   ├── agent/                  # AI Agent workflows
│   │   ├── persona_agent.py   # Persona detection
│   │   ├── chat_agent.py      # Chat logic
│   │   └── issue_creator.py   # Issue creation
│   │
│   ├── routes/                 # API endpoints
│   │   ├── chat_routes.py
│   │   ├── forum_routes.py
│   │   ├── github_routes.py
│   │   └── search_routes.py
│   │
│   ├── tools/                  # Utilities
│   │   ├── github_service.py
│   │   ├── embeddings.py
│   │   └── chat_handler.py
│   │
│   ├── models/                 # Data models
│   │   ├── forum.py
│   │   ├── github.py
│   │   └── knowledge.py
│   │
│   └── requirements.txt
│
├── docs/                        # Documentation
│   ├── SETUP.md
│   ├── ARCHITECTURE.md
│   └── API.md
│
└── README.md
```

---

## 🗺️ Roadmap

### Phase 1 - Current (March 2026)
✅ Chat interface with LLM  
✅ Knowledge base with RAG  
✅ My Path onboarding  
✅ Team forum  
✅ GitHub README fetching  
✅ Issue creation from chat  

### Phase 2 - Next (April 2026)
🔄 Pull request previews in chat  
🔄 Code diff viewing  
🔄 Database persistence (PostgreSQL)  
🔄 User authentication  
🔄 Email notifications  

### Phase 3 - Coming (May 2026)
📈 GitHub Actions integration  
📈 Advanced search (Elasticsearch)  
📈 Real-time collaboration  
📈 Performance analytics  
📈 Mobile app (iOS/Android)  

### Phase 4 - Future (Q3 2026)
🚀 Enterprise SSO  
🚀 Custom branding  
🚀 Advanced permissions  
🚀 Audit logs  
🚀 API rate limiting  

---

## 🐛 Troubleshooting

### Backend Issues

**Problem: "ModuleNotFoundError"**
```bash
Solution: Install dependencies
pip install -r requirements.txt
```

**Problem: "GitHub API 401 Unauthorized"**
```bash
Solution: Check GitHub token
1. Verify token in .env
2. Token must have 'repo' scope
3. Regenerate if expired
```

**Problem: "Cannot connect to Groq API"**
```bash
Solution: Check Groq API key
1. Verify key in .env
2. Key must start with 'gsk_'
3. Check internet connection
```

### Frontend Issues

**Problem: "Cannot reach backend"**
```bash
Solution: Ensure both are running
1. Backend: python main.py (on :8000)
2. Frontend: npm run dev (on :3000)
3. Check firewall settings
```

**Problem: "Dark mode not working"**
```bash
Solution: Clear cache
1. Press Ctrl+Shift+Delete
2. Clear all cache
3. Refresh page
4. Restart npm dev server
```

**Problem: "Styles look broken"**
```bash
Solution: Rebuild CSS
1. Stop npm dev server (Ctrl+C)
2. Delete .next folder
3. Run: npm run dev again
```

### Database Issues

**Problem: "Cannot connect to PostgreSQL"**
```bash
Solution: Check database URL
1. Verify DATABASE_URL in .env
2. Check PostgreSQL is running
3. Verify credentials are correct
```

---

## 🤝 Contributing

We welcome contributions! Here's how:

### 1. Fork the Repository
```bash
git clone https://github.com/Code-Yodha-NOVA/nova-system.git
cd nova-system
```

### 2. Create a Feature Branch
```bash
git checkout -b feature/YourFeature
```

### 3. Make Your Changes
```bash
# Edit files, test locally
npm run dev     # Frontend
python main.py  # Backend
```

### 4. Commit and Push
```bash
git add .
git commit -m "Add YourFeature"
git push origin feature/YourFeature
```

### 5. Create Pull Request
- Go to GitHub repository
- Click "New Pull Request"
- Describe your changes
- Submit for review

---

## 📞 Support

- **Email:** support@codeyodha.com
- **GitHub Issues:** [Report a bug](https://github.com/Code-Yodha-NOVA/nova-system/issues)
- **Slack:** [Code Yodha Community](https://codeyodha.slack.com)
- **Documentation:** [Full Docs](https://docs.codeyodha.com)

---

## 📄 License

This project is proprietary software developed by **Code Yodha Technologies**.

For licensing inquiries: `legal@codeyodha.com`

---

## 👥 Team

- **Swayam Mankar** - Lead Developer & Architect
- **Code Yodha Team** - Contributors & Advisors

### Special Thanks

- Groq for LLM infrastructure
- GitHub for API access
- ChromaDB team for vector database
- FastAPI and React communities

---

## 📊 Project Statistics

```
Total Lines of Code:    12,500+
Frontend Components:    40+
Backend Endpoints:      25+
API Documentation:      Complete
Test Coverage:          75%+
Active Development:     Yes ✓
```

---

## 🌟 Why N.O.V.A?

**Before N.O.V.A.:**
- New developers take 2-3 weeks to onboard
- Repetitive questions asked multiple times
- Important information scattered across platforms
- Context switching between tools
- Inconsistent guidance

**With N.O.V.A.:**
- Developers onboard in 3-4 days
- Instant answers to common questions
- Centralized knowledge in one app
- Consistent, AI-powered guidance
- Better team productivity

---

## 🎯 Vision

**Year 1:** Be the #1 developer onboarding platform in the market

**Long-term:** Every developer, everywhere, has instant access to team knowledge and intelligent guidance

---

## 📅 Recent Updates

### v2.1.0 (March 18, 2026)
- ✅ Added GitHub README fetching
- ✅ Improved chat interface
- ✅ Dark mode support
- ✅ Forum UI redesign
- 🐛 Bug fixes and optimizations

### v2.0.0 (February 2026)
- ✅ GitHub integration
- ✅ LangGraph agent system
- ✅ ChromaDB knowledge base
- ✅ Forum with voting system

### v1.0.0 (January 2026)
- ✅ Initial MVP release
- ✅ Chat interface
- ✅ My Path onboarding
- ✅ Knowledge base search

---

## 📝 Notes

- This README is regularly updated
- Latest version: March 18, 2026
- See [CHANGELOG.md](./CHANGELOG.md) for detailed updates
- Join our community for announcements

---

**Made with ❤️ by Code Yodha Technologies**

**N.O.V.A. - Making Developer Onboarding Intelligent** 🚀
