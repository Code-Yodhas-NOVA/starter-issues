# 📖 N.O.V.A. - Networked Onboarding Virtual Assistant

**Organization:** Code Yodha Technologies  
**Repository:** Code-Yodha-NOVA/nova-system  
**Version:** 2.1.0  
**Status:** Active Development 🟢

---

## 🎯 Overview

**N.O.V.A.** is an intelligent **AI-powered developer onboarding platform** that transforms how new developers join and integrate into your team. Instead of switching between tools, asking in Slack, and searching documentation, developers get everything they need in one unified workspace.

### What Problems Does It Solve?

```
❌ WITHOUT N.O.V.A.:
- New dev joins → confused about setup
- Asks 5 people same question → wasted time
- Searches documentation → outdated info
- Creates wrong issue → context confusion
- Onboarding takes 2-3 weeks

✅ WITH N.O.V.A.:
- New dev opens app → guided onboarding
- Asks Nova → instant, personalized answer
- Smart knowledge base → always up-to-date
- Creates issue in chat → syncs with GitHub
- Onboarding takes 3-4 days
```

---

## ⭐ Key Features

### 1. 🤖 Nova - AI Chatbot
Intelligent assistant that understands context and helps developers:
- Answer onboarding questions
- Fetch project README
- Create GitHub issues
- Search knowledge base
- Provide code examples

**Try asking Nova:**
- "Show me the project README"
- "How do I set up the environment?"
- "Create an issue: Bug in login form"
- "What's our API design pattern?"

### 2. 📚 Knowledge Base
3-tier knowledge management system:
- **Tier 1 (Public):** FAQs, Getting Started, Best Practices
- **Tier 2 (Internal):** Developer Personas, Checklists, Guidelines
- **Tier 3 (Templates):** Email templates, Document templates, Code snippets

Powered by **RAG** (Retrieval-Augmented Generation) for accurate, contextual answers.

### 3. 🛣️ My Path - Personalized Onboarding
Smart onboarding journey tailored to each developer:
- **Persona Detection:** Backend, Frontend, DevOps, etc.
- **Custom Checklist:** Role-specific tasks
- **Progress Tracking:** See what you've completed
- **Adaptive Guidance:** Get help when you need it

### 4. 💬 Team Forum
Discussion platform for developers to:
- Ask questions about implementation
- Share solutions to common problems
- Build institutional knowledge
- Get help from teammates
- Upvote helpful answers

### 5. 🔗 GitHub Integration
Direct integration with your GitHub organization:
- View open issues and pull requests
- **Create issues directly from chat**
- **Fetch README and documentation**
- Track project progress
- Monitor team activity

### 6. 📊 Progress Dashboard
Visual onboarding metrics:
- Completed vs. total checklist items
- Time spent on each section
- Resources accessed
- Knowledge gained

---

## 🚀 Quick Start

### Prerequisites

```
Python:     3.9 or higher
Node.js:    16.0 or higher
GitHub:     Personal access token
API Keys:   Groq API, (Optional: SMTP, Jira)
```

### Installation (5 minutes)

#### Backend Setup

```bash
# 1. Navigate to backend
cd nova-onboarding/backend

# 2. Create virtual environment
python -m venv .venv

# 3. Activate virtual environment
# On macOS/Linux:
source .venv/bin/activate

# On Windows:
.venv\Scripts\activate

# 4. Install dependencies
pip install -r requirements.txt

# 5. Create .env file
cat > .env << EOF
GITHUB_TOKEN=ghp_your_token_here
GITHUB_ORG=Code-Yodha-NOVA
GITHUB_REPO=nova-system
GROQ_API_KEY=gsk_your_key_here
EOF

# 6. Start backend server
python main.py
# Server runs at: http://localhost:8000
```

#### Frontend Setup

```bash
# 1. Navigate to frontend
cd nova-onboarding/frontend

# 2. Install dependencies
npm install

# 3. Start development server
npm run dev
# Frontend runs at: http://localhost:3000
```

#### Access the Application

```
Open browser: http://localhost:3000
Start onboarding now! 🚀
```

---

## 🏗️ Architecture

### System Design

```
┌─────────────────────────┐
│    User Browser         │
│   (localhost:3000)      │
│                         │
│  ┌─────────────────┐   │
│  │   React App     │   │
│  │  - Chat UI      │   │
│  │  - Forum        │   │
│  │  - My Path      │   │
│  │  - Knowledge    │   │
│  └────────┬────────┘   │
└───────────┼─────────────┘
            │ HTTP/REST
            │ JSON
            ▼
┌─────────────────────────┐
│  FastAPI Backend        │
│ (localhost:8000)        │
│                         │
│  Routes:                │
│  ├─ /api/chat          │
│  ├─ /api/forum         │
│  ├─ /api/github        │
│  ├─ /api/search        │
│  └─ /api/knowledge     │
└────┬────────┬────────┬──┘
     │        │        │
     ▼        ▼        ▼
  Groq API  GitHub  ChromaDB
  (LLM)     (API)   (Vector)
```

### Tech Stack

**Frontend:**
- ✅ Next.js 14 (Framework)
- ✅ React 18 (UI Library)
- ✅ TypeScript (Type Safety)
- ✅ Tailwind CSS (Styling)
- ✅ Lucide React (Icons)

**Backend:**
- ✅ FastAPI (Web Framework)
- ✅ Python 3.9+ (Language)
- ✅ Pydantic (Validation)
- ✅ Uvicorn (ASGI Server)
- ✅ PyGithub (GitHub API)

**AI/ML:**
- ✅ Groq API (LLM)
- ✅ LangGraph (Agent Orchestration)
- ✅ ChromaDB (Vector Database)
- ✅ Sentence Transformers (Embeddings)

**Integrations:**
- ✅ GitHub API (Issues, PRs, README)
- ✅ SMTP (Email)
- ✅ Jira (Issue Tracking)
- ✅ Slack (Notifications)

**Database (Production):**
- ✅ PostgreSQL (Persistent Data)
- ✅ Redis (Caching)

---

## 💻 How to Use

### Chat with Nova

**Example: Fetch README**

```
You:   "Show me the README"
Nova:  [Fetches from GitHub]
       [Displays formatted content]
       [Shows key sections]
       ✅ Done!
```

**Example: Create Issue**

```
You:   "Create issue: Add authentication to API"
Nova:  [Creates GitHub issue]
       [Returns issue #123]
       [Shows confirmation]
       ✅ Issue created!
```

**Example: Ask Question**

```
You:   "How do I run tests?"
Nova:  [Searches knowledge base]
       [Retrieves relevant docs]
       [Provides step-by-step answer]
       ✅ Question answered!
```

### Start Your Onboarding Path

1. Open "My Path" tab
2. Nova detects your role (Backend/Frontend/DevOps)
3. Get personalized checklist
4. Complete tasks in order
5. Track progress with dashboard

### Join Team Forum

1. Find relevant discussions
2. Read solutions to common problems
3. Ask your own questions
4. Upvote helpful answers
5. Build knowledge together

---

## 📡 API Endpoints

### Chat API

**Send Message to Nova**
```http
POST /api/chat/message
Content-Type: application/json

{
  "content": "Show me the README"
}

Response:
{
  "type": "github_response",
  "data": {
    "type": "readme",
    "content": "# N.O.V.A...",
    "sections": [...]
  }
}
```

**Create Issue from Chat**
```http
POST /api/chat/create-issue
Content-Type: application/json

{
  "title": "Add authentication",
  "description": "Implement JWT-based auth"
}

Response:
{
  "type": "issue_created",
  "issue_id": 123,
  "url": "https://github.com/Code-Yodha-NOVA/nova-system/issues/123"
}
```

### GitHub API

**Fetch README**
```http
GET /api/github/readme

Response:
{
  "name": "README.md",
  "content": "# N.O.V.A...",
  "sections": [
    {"title": "Overview", "content": "..."},
    {"title": "Quick Start", "content": "..."}
  ],
  "last_updated": "2026-03-18T10:30:00Z"
}
```

**List Issues**
```http
GET /api/github/issues?state=open

Response:
{
  "state": "open",
  "count": 5,
  "issues": [
    {
      "id": 1,
      "title": "Setup PostgreSQL",
      "state": "open",
      "author": "vikram",
      "labels": ["database"]
    }
  ]
}
```

**Create Issue**
```http
POST /api/github/issues
Content-Type: application/json

{
  "title": "Feature request",
  "description": "Please add X",
  "labels": ["enhancement"],
  "assignees": ["vikram"]
}

Response:
{
  "id": 126,
  "title": "Feature request",
  "url": "https://github.com/Code-Yodha-NOVA/nova-system/issues/126"
}
```

**List Pull Requests**
```http
GET /api/github/pull-requests

Response:
{
  "count": 3,
  "pull_requests": [
    {
      "id": 45,
      "title": "Fix forum search",
      "state": "open",
      "author": "maya",
      "additions": 156,
      "deletions": 42
    }
  ]
}
```

### Forum API

**Get Threads**
```http
GET /api/forum/threads?category=Setup

Response:
{
  "count": 5,
  "threads": [
    {
      "id": "thread_001",
      "title": "PostgreSQL Connection Issues",
      "author": "vikram",
      "upvotes": 12,
      "comments_count": 4
    }
  ]
}
```

**Create Thread**
```http
POST /api/forum/threads
Content-Type: application/json

{
  "title": "How to set up Redis?",
  "content": "I'm confused about...",
  "category": "Setup"
}

Response:
{
  "id": "thread_123",
  "title": "How to set up Redis?",
  "url": "http://localhost:3000/forum/thread_123"
}
```

### Knowledge Base API

**Search Documentation**
```http
GET /api/search?q=authentication

Response:
{
  "results": [
    {
      "title": "JWT Authentication Guide",
      "content": "...",
      "relevance": 0.95
    }
  ]
}
```

---

## 🔧 Configuration

### Environment Variables

Create `.env` in backend directory:

```env
# GitHub Integration
GITHUB_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxxxx
GITHUB_ORG=Code-Yodha-NOVA
GITHUB_REPO=nova-system

# Groq AI
GROQ_API_KEY=gsk_xxxxxxxxxxxxxxxxxxxxxx

# Email (Optional)
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
SMTP_USERNAME=your-email@gmail.com
SMTP_PASSWORD=your-app-password

# Database (Production)
DATABASE_URL=postgresql://user:pass@localhost/nova_db
REDIS_URL=redis://localhost:6379/0

# Server
SERVER_HOST=0.0.0.0
SERVER_PORT=8000
ENVIRONMENT=development
```

### Getting API Keys

#### GitHub Personal Access Token

1. Go to: https://github.com/settings/tokens
2. Click "Generate new token (classic)"
3. Name: `Nova Development`
4. Select scopes:
   - ✅ `repo` (full control)
   - ✅ `read:org` (read organization data)
   - ✅ `read:user` (read user profile)
5. Copy token and add to `.env`

#### Groq API Key

1. Go to: https://console.groq.com/keys
2. Click "Create API Key"
3. Copy the key
4. Add to `.env`

---

## 📁 Project Structure

```
nova-onboarding/
│
├── frontend/                          # React + Next.js
│   └── src/
│       ├── app/
│       │   ├── chat/page.tsx         # Chat interface
│       │   ├── my-path/page.tsx      # Onboarding journey
│       │   ├── knowledge-base/page.tsx # Search & docs
│       │   ├── forum/page.tsx        # Team discussions
│       │   ├── github/page.tsx       # GitHub integration
│       │   └── layout.tsx            # Root layout
│       │
│       ├── components/
│       │   ├── SidebarLayout.tsx     # Navigation
│       │   ├── ChatMessage.tsx       # Message display
│       │   ├── ThreadCard.tsx        # Forum thread
│       │   └── GitHubReadmeDisplay.tsx # README viewer
│       │
│       └── context/
│           ├── ChatContext.tsx       # Chat state
│           └── AuthContext.tsx       # Auth state
│
├── backend/                           # FastAPI + Python
│   ├── main.py                       # Entry point
│   │
│   ├── agent/                        # LangGraph workflows
│   │   ├── persona_agent.py         # Role detection
│   │   ├── chat_agent.py            # Chat logic
│   │   └── issue_creator.py         # Issue creation
│   │
│   ├── routes/                       # API endpoints
│   │   ├── chat_routes.py           # Chat API
│   │   ├── forum_routes.py          # Forum API
│   │   ├── github_routes.py         # GitHub API
│   │   └── search_routes.py         # Search API
│   │
│   ├── tools/                        # Utilities & services
│   │   ├── github_service.py        # GitHub integration
│   │   ├── chat_github_service.py   # Chat + GitHub
│   │   └── embeddings.py            # Vector embeddings
│   │
│   ├── models/                       # Data schemas
│   │   ├── forum.py                 # Forum data
│   │   ├── github.py                # GitHub data
│   │   └── knowledge.py             # Knowledge data
│   │
│   └── data/                         # Knowledge files
│       ├── faqs.json                # FAQ documents
│       ├── guidelines.md            # Best practices
│       └── templates/               # Document templates
│
└── docs/                              # Documentation
    ├── SETUP.md                      # Setup guide
    ├── ARCHITECTURE.md               # System design
    └── API.md                        # API documentation
```

---

## 🧪 Features Roadmap

### Phase 1 (Current - March 2026)
✅ **Core Onboarding**
- Chatbot with LLM integration
- Knowledge base with RAG
- Forum for team discussions
- GitHub issue creation
- **README fetching from chat**

### Phase 2 (April 2026)
🔄 **Enhanced GitHub Integration**
- Pull request previews
- Code diff viewing
- Branch management
- Deployment tracking
- Issue templates

### Phase 3 (May 2026)
📈 **Advanced Features**
- GitHub Actions status
- Advanced search (Elasticsearch)
- Real-time notifications
- Performance analytics
- Mobile app (iOS/Android)

### Phase 4 (Q3 2026)
🚀 **Enterprise Features**
- Single sign-on (SSO)
- Custom branding
- Advanced permissions
- Audit logs
- SLA monitoring

---

## 🐛 Troubleshooting

### Chat Not Responding

**Problem:** Nova doesn't respond to messages

**Solutions:**
1. Check backend is running: `http://localhost:8000`
2. Check Groq API key is valid in `.env`
3. Check browser console for errors (F12)
4. Restart backend: `python main.py`

### Cannot Fetch README

**Problem:** "Show me the README" returns error

**Solutions:**
1. Verify GitHub token: `echo $GITHUB_TOKEN`
2. Check token has `repo` scope
3. Verify org name: `Code-Yodha-NOVA`
4. Verify repo exists: `nova-system`
5. Try mock data first: `USE_MOCK_DATA=True`

### GitHub API 404 Errors

**Problem:** GitHub endpoints return 404

**Solutions:**
```bash
# Check token is valid
curl -H "Authorization: token ghp_xxx" https://api.github.com/user

# Check org exists
curl https://api.github.com/orgs/Code-Yodha-NOVA

# Check repo exists
curl https://api.github.com/repos/Code-Yodha-NOVA/nova-system
```

### Knowledge Base Returns No Results

**Problem:** Search returns empty results

**Solutions:**
1. Check documents in `backend/data/`
2. Re-index documents: `python -m tools.ingest`
3. Check ChromaDB is running
4. Verify embeddings model is downloaded

### Dark Mode Not Working

**Problem:** Dark mode toggle doesn't work

**Solutions:**
1. Clear browser cache: `Ctrl+Shift+Delete`
2. Restart frontend: `npm run dev`
3. Check Tailwind config has dark mode
4. Check system dark mode setting

---

## 📚 Learning Resources

### Documentation
- [Full API Documentation](./docs/API.md)
- [Architecture Guide](./docs/ARCHITECTURE.md)
- [Setup Instructions](./docs/SETUP.md)

### Tutorials
- Getting Started (3 min video)
- Chat Basics (5 min video)
- Forum Usage (5 min video)
- GitHub Integration (8 min video)

### Examples
- [Chat with README](./examples/chat_readme.md)
- [Create GitHub Issue](./examples/create_issue.md)
- [Ask Knowledge Question](./examples/ask_knowledge.md)

---

## 🤝 Contributing

We welcome contributions! Here's how:

### 1. Fork the Repository
```bash
git clone https://github.com/Code-Yodha-NOVA/nova-system.git
cd nova-system
```

### 2. Create Feature Branch
```bash
git checkout -b feature/AmazingFeature
```

### 3. Make Changes
```bash
# Edit files, test locally
npm run dev  # Frontend
python main.py  # Backend
```

### 4. Commit & Push
```bash
git add .
git commit -m "Add AmazingFeature"
git push origin feature/AmazingFeature
```

### 5. Create Pull Request
- Go to GitHub
- Create PR to `main` branch
- Add description
- Wait for review

### Development Guidelines
- Write clean, readable code
- Add comments for complex logic
- Test before submitting
- Follow existing code style
- Update docs as needed

---

## 📞 Support & Contact

### Getting Help

- **📧 Email:** support@codeyodha.com
- **💬 Slack:** [Code Yodha Community](https://codeyodha.slack.com)
- **🐛 Issues:** [GitHub Issues](https://github.com/Code-Yodha-NOVA/nova-system/issues)
- **📚 Wiki:** [Full Documentation](https://wiki.codeyodha.com)

### Report a Bug

```bash
# Create detailed bug report with:
1. What you were doing
2. What you expected
3. What happened instead
4. Error message/screenshot
5. Your environment (OS, browser, etc.)
```

### Feature Requests

```bash
# Describe the feature:
1. Problem it solves
2. Use case example
3. Expected behavior
4. Benefits
```

---

## 📄 License

N.O.V.A. is proprietary software developed by **Code Yodha Technologies**.

### Usage Rights
- ✅ Internal team use
- ✅ Client demonstrations
- ✅ Educational purposes (with permission)
- ❌ Commercial redistribution
- ❌ Public release without permission

For licensing questions: `legal@codeyodha.com`

---

## 👥 Team

### Creators
- **Swayam Mankar** - Lead Developer & Architect
- **Code Yodha Team** - Contributors & Advisors

### Special Thanks
- Groq for LLM API
- GitHub for API access
- ChromaDB team for vector database
- FastAPI community
- React community

---

## 📊 Project Statistics

```
Total Files:      120+
Lines of Code:    12,500+
Test Coverage:    75%+
Documentation:    Complete
API Endpoints:    25+
Frontend Pages:   6
Components:       40+
```

---

## 🎯 Future Vision

**Year 1 Goal:** Be the #1 developer onboarding platform in the industry

**Long-term Vision:** Every developer, everywhere, has instant access to team knowledge and guidance

---

## 📅 Changelog

### v2.1.0 (March 18, 2026)
- ✅ GitHub README fetching
- ✅ Chat integration improvements
- ✅ Forum UI redesign
- ✅ Dark mode support
- 🐛 Bug fixes and improvements

### v2.0.0 (February 2026)
- ✅ Full GitHub integration
- ✅ LangGraph agent system
- ✅ ChromaDB knowledge base
- ✅ Forum with voting

### v1.0.0 (January 2026)
- ✅ Initial release
- ✅ Chat interface
- ✅ My Path onboarding
- ✅ Basic knowledge base

---

## 📝 Notes

- This README is regularly updated
- Latest version: March 18, 2026
- Check `CHANGELOG.md` for detailed updates
- Join our community for latest news

---

**Made with ❤️ by Code Yodha Technologies**

**N.O.V.A. - Making Developer Onboarding Intelligent** 🚀
