# Skill Gap Analyzer for Campus 🎓

AI-powered placement readiness platform for students and campus placement cells.

![React](https://img.shields.io/badge/React-18.2-blue)
![Firebase](https://img.shields.io/badge/Firebase-10.7-orange)
![Gemini](https://img.shields.io/badge/Gemini-AI-purple)
![Tailwind](https://img.shields.io/badge/Tailwind-3.4-cyan)

## 🎯 Project Overview

This MVP demonstrates how AI can identify skill gaps between students and industry requirements, generating personalized learning roadmaps using Google technologies.

### Core Features

- **🔐 Authentication** - Firebase Auth with email/password (Student & Admin roles)
- **📊 Student Dashboard** - Enter details, select skills, choose career path
- **🤖 AI Analysis** - Gemini API compares skills with industry requirements
- **📈 Results Page** - Readiness score, missing skills, learning roadmap
- **👨‍💼 Admin Dashboard** - Campus-wide analytics and insights

## 🚀 Quick Start

### Prerequisites

- Node.js 18+
- Firebase Project
- Google Gemini API Key

### Installation

```bash
# Clone and navigate
cd skill-gap-analyzer

# Install dependencies
npm install

# Create environment file
cp .env.example .env
```

### Configure Environment Variables

Edit `.env` with your credentials:

```env
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id
VITE_GEMINI_API_KEY=your_gemini_api_key
```

### Run Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 📁 Project Structure

```
skill-gap-analyzer/
├── src/
│   ├── components/
│   │   ├── auth/
│   │   │   ├── Login.jsx        # Login page
│   │   │   └── Signup.jsx       # Registration page
│   │   ├── student/
│   │   │   ├── StudentDashboard.jsx  # Main student interface
│   │   │   └── Results.jsx      # Analysis results page
│   │   ├── admin/
│   │   │   └── AdminDashboard.jsx    # Admin analytics
│   │   └── common/
│   │       ├── Landing.jsx      # Welcome page
│   │       └── ProtectedRoute.jsx
│   ├── config/
│   │   └── firebase.js          # Firebase configuration
│   ├── context/
│   │   └── AuthContext.jsx      # Authentication state
│   ├── data/
│   │   └── industrySkills.js    # Skills & roles dataset
│   ├── services/
│   │   ├── geminiService.js     # Gemini AI integration
│   │   └── firestoreService.js  # Database operations
│   ├── App.jsx                  # Main app with routing
│   ├── main.jsx                 # Entry point
│   └── index.css                # Tailwind styles
├── public/
├── .env.example
├── firebase.json
├── firestore.rules
├── package.json
├── tailwind.config.js
└── vite.config.js
```

## 🔥 Firebase Setup

### 1. Create Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com)
2. Create new project
3. Enable Authentication (Email/Password)
4. Enable Firestore Database

### 2. Firestore Collections

```
users/
  └── {userId}
      ├── name: string
      ├── email: string
      ├── role: "student" | "admin"
      ├── branch: string
      ├── year: number
      ├── skills: string[]
      └── career_interest: string

skill_analysis/
  └── {analysisId}
      ├── userId: string
      ├── career_role: string
      ├── readiness_score: number
      ├── matched_skills: string[]
      ├── missing_skills: string[]
      ├── learning_roadmap: object[]
      └── createdAt: timestamp
```

### 3. Deploy Firestore Rules

```bash
firebase deploy --only firestore:rules
```

## 🤖 Gemini AI Prompt

The AI prompt is designed to output structured JSON:

```
You are an AI career skill analyzer...

Output JSON format:
{
  "career_role": "",
  "readiness_score": 0,
  "matched_skills": [],
  "missing_skills": [],
  "recommended_skills": [],
  "learning_roadmap": [...]
}
```

See `src/services/geminiService.js` for the full prompt.

## 🎥 Demo Flow (2-3 minutes)

1. **Landing Page** - Show the problem statement
2. **Student Signs Up** - Create account
3. **Fill Profile** - Select branch, year, skills
4. **Choose Career** - Pick "Frontend Developer"
5. **Click Analyze** - Show AI processing
6. **View Results** - Readiness score, missing skills, roadmap
7. **Switch to Admin** - Login as admin
8. **Campus Insights** - Show aggregated analytics

## 🚀 Deployment

### Deploy to Firebase Hosting

```bash
# Build the app
npm run build

# Deploy to Firebase
firebase deploy
```

## 🎨 Tech Stack

| Technology | Purpose |
|------------|---------|
| React 18 | Frontend framework |
| Tailwind CSS | Styling |
| Firebase Auth | Authentication |
| Firestore | Database |
| Gemini API | AI analysis |
| Vite | Build tool |
| Lucide React | Icons |

## 📊 Admin Analytics

The admin dashboard displays:

- **Total Students Analyzed** - Unique users count
- **Average Readiness Score** - Campus average
- **Top Missing Skills** - Skills students lack most
- **Role-wise Readiness** - Scores by career path

## 🏆 Hackathon Notes

This MVP is optimized for:

✅ **Demo clarity** - Clean UI, fast interactions  
✅ **Core value** - AI-driven insights, not just forms  
✅ **Technical depth** - Firebase + Gemini integration  
✅ **Real impact** - Solves actual student problems

## 📝 License

MIT License - Built for hackathon demonstration.

---

**Built with ❤️ using React, Firebase & Google Gemini AI**
