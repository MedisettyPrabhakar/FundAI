# Here are your Instructions

# 🚀 Local Development Setup Guide - VSCode

This guide will help you run the CampaignIQ project on your local machine using VSCode.

## Prerequisites

Before you begin, make sure you have the following installed:

1. **Node.js** (v16 or higher) - [Download here](https://nodejs.org/)
2. **Python** (v3.9 or higher) - [Download here](https://www.python.org/)
3. **Visual Studio Code** - [Download here](https://code.visualstudio.com/)
4. **Git** - [Download here](https://git-scm.com/)
5. **Yarn** (optional, but recommended) - Run: `npm install -g yarn`

## Step 1: Clone the Repository

Open your terminal (or VSCode integrated terminal) and run:

```bash
git clone https://github.com/MedisettyPrabhakar/AI-Optimized-Crowdfunding-Platform-with-Campaign-Success-Prediction
cd FundAI
```
# Step 2: Open Project in VSCode

```bash
code .
```

Or manually open VSCode and use `File > Open Folder` to open the `FundAI` folder.

---

## Step 3: Backend Setup

### 3.1 Navigate to Backend Directory

Open a terminal in VSCode (`Terminal > New Terminal`) and run:

```bash
cd backend
```

### 3.2 Create Python Virtual Environment

**For Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**For macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

You should see `(venv)` prefix in your terminal now.

### 3.3 Install Python Dependencies

```bash
pip install -r requirements.txt
```

This will install:
- FastAPI
- Supabase Python Client
- Google Generative AI
- bcrypt
- uvicorn
- and other dependencies

### 3.4 Create Backend Environment File

Create a file named `.env` in the `backend` folder with the following content:

```env
SUPABASE_URL=*your_supabase_url*
SUPABASE_KEY=*your_supabase_key*
GEMINI_API_KEY=*your_gemini_API_key*
STRIPE_API_KEY=*your_stripe_API_key*
STRIPE_PUBLISHABLE_KEY=*your_stripe_Publishable_key*
CORS_ORIGINS="*"
FRONTEND_URL=http://localhost:8001

```

## Step 4: Frontend Setup

### 4.1 Open New Terminal

Keep the backend terminal open, and open a new terminal in VSCode:
- Click the `+` icon in the terminal panel
- Or press `Ctrl + Shift + ` ` (backtick)

### 4.2 Navigate to Frontend Directory

```bash
cd frontend
```

### 4.3 Install Node Dependencies

**Using Yarn (Recommended):**
```bash
yarn install
```

**Or using npm:**
```bash
npm install
```

This will install:
- React
- React Router
- Axios
- Tailwind CSS
- Shadcn UI components
- Recharts
- and other dependencies

### 4.4 Create Frontend Environment File

Create a file named `.env` in the `frontend` folder with the following content:

```env
REACT_APP_BACKEND_URL=http://localhost:8001
WDS_SOCKET_PORT=443
REACT_APP_ENABLE_VISUAL_EDITS=false
ENABLE_HEALTH_CHECK=false
REACT_APP_SUPABASE_URL=*your_supabase_url*
REACT_APP_SUPABASE_ANON_KEY=*your_supabase_key*
REACT_APP_STRIPE_PUBLISHABLE_KEY=*your_stripe_Publishable_key*
```

**Note:** In local development, we use `http://localhost:8001` 

---

## Step 5: Run the Application

You should now have **2 terminals open** in VSCode:

### Terminal 1 - Run Backend Server

```bash
cd backend
# Activate virtual environment if not already active
# Windows: venv\Scripts\activate
# macOS/Linux: source venv/bin/activate

# Start the backend server
uvicorn server:app --reload --host 0.0.0.0 --port 8001
```

You should see:
```
INFO:     Uvicorn running on http://0.0.0.0:8001 (Press CTRL+C to quit)
INFO:     Started reloader process
INFO:     Started server process
INFO:     Application startup complete.
```

### Terminal 2 - Run Frontend Development Server

```bash
cd frontend

# Start the frontend server
yarn start
# OR
npm start
```

You should see:
```
Compiled successfully!

You can now view frontend in the browser.

  Local:            http://localhost:3000
```

---

## Step 6: Access the Application

Open your web browser and navigate to:

```
http://localhost:3000
```

You should see the CampaignIQ homepage!
---