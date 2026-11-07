# 📚 Class 12 Arts Study Hub | Diya's Personal Digital Notebook

A modern, fast, and student-friendly **Class 12 Arts Study Management App** built specially for **Diya**, studying at **Mahatma Fule College, Talodhi Balapur, District Chandrapur, Maharashtra, India**.

Designed like a clean personal digital notebook, this application enables full management of Class 12 Arts subjects, chapters, personal handwritten notes (JPG/PNG/PDF), daily to-do lists, multi-year study calendar, exam timetable countdowns, study planner with Pomodoro timer, syllabus progress, and profile settings.

---

## 🌟 Key Features

1. **Class 12 Arts Subjects Management**
   - Editable subjects list (initial demo contains: *History, Political Science, Geography, Sociology, Economics, English Yuvakbharati, Marathi Yuvakbharati, Psychology, Hindi Yuvakbharati*).
   - Custom theme colors, subject icons, descriptions, and automatic progress percentages.
   - Add, edit, or delete any subject with confirmation protection.

2. **Subject → Chapter → Handwritten Notes Structure**
   - Direct, intuitive notebook hierarchy: `Subject → Chapter → Handwritten Notes`.
   - Chapter details: chapter number, title, syllabus description, important topics tags, and revision status (`Completed ✅`, `In Progress 🟡`, `Need Revision 🔴`, `Not Started ⚪`).

3. **Handwritten Notes Gallery & Viewer**
   - Upload notebook page photos (**JPG, JPEG, PNG**) or scanned **PDFs** directly to any chapter.
   - Page-by-page multi-page organization (`Page 1`, `Page 2`, `Page 3`...).
   - High-performance fullscreen viewer with **Zoom In, Zoom Out, Reset, 90° Rotation, Download, and Delete**.
   - Dedicated **"My Notes"** section with filtering by subject, chapter, and date.

4. **Quick Revision Notes & Important Questions**
   - Lined digital notebook section for key dates, thinkers, and quick revision highlights.
   - Question bank for Maharashtra Board exam practice with marks weightage (2, 3, 4, 8 marks), model answer notes, importance stars, and completion toggles.

5. **Clean Dashboard**
   - Warm "Welcome Back 👋" greeting and current Indian date format.
   - Summary counters: Total Subjects, Completed Chapters, Pending Tasks, and Upcoming Exams.
   - Next Exam countdown highlight banner.
   - Today's interactive To-Do checkboxes.
   - Active study streak counter (🔥 5 Day Streak).

6. **Daily To-Do List**
   - Manage daily study tasks by category (*Study, Assignment, Revision, Exam, Personal*) and priority (*High, Medium, Low*).
   - Filter by Today, Upcoming, Completed, and All.

7. **Multi-Year Study Calendar**
   - Support for **Day View** and **Month View** across multi-year navigation (**2025, 2026, 2027, 2028, 2029+**).
   - Color-coded event badges for Exams, Assignments, Study sessions, College events, and Reminders.

8. **Exam Timetable**
   - Chronological table view: Date, Subject, Time, Exam Name, Duration, Room, and Preparation Notes.
   - "NEXT EXAM" highlight card with remaining days countdown.

9. **Study Planner & Pomodoro Focus Timer**
   - Plan sessions by subject, chapter, study date, duration, and specific goal.
   - Integrated Pomodoro focus timer (25m, 45m, 60m, 90m, 120m) with celebration confetti upon goal completion.

10. **Simple & Secure Student Access**
    - Student passcode login preventing unauthorized modification.
    - Default password: `arts12` (customizable).
    - Confirmation modal dialog before deleting subjects, chapters, notes, exams, or tasks.

11. **Responsive & Themed UI**
    - Seamless Light ☀️ and Dark 🌙 modes saved to user preferences.
    - Responsive layout: desktop sidebar and mobile bottom navigation bar (`Home`, `Subjects`, `Notes`, `Calendar`, `Tasks`, `More`).

---

## 🛠️ Tech Stack

- **Frontend**: React 18, TypeScript, Vite, Tailwind CSS, Lucide React, Canvas Confetti
- **Backend**: Fastify (Node.js), TypeScript, `@fastify/multipart`, `@fastify/static`, `@fastify/cors`
- **Database Options**:
  - **Local Zero-Config Storage**: Built-in file-persisted JSON database (`server/data/db.json`) for instant out-of-the-box local testing.
  - **Supabase / PostgreSQL**: Production-ready schema provided in `supabase/schema.sql` with Row Level Security (RLS) and storage bucket configurations.
- **File Storage**: Local uploads in `server/uploads/` with direct static streaming, or Supabase Storage bucket (`notes-storage`).

---

## 📁 Project Structure

```text
DIYA/
├── client/                     # Frontend React + TypeScript application
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── icons/          # SubjectIcon mapping
│   │   │   ├── layout/         # Header, Sidebar, MobileNavbar, ConfirmModal
│   │   │   ├── notes/          # HandwrittenNoteViewer, UploadNoteModal
│   │   │   └── search/         # GlobalSearchModal
│   │   ├── context/            # AppContext.tsx (state, auth, theme, CRUD)
│   │   ├── pages/              # Dashboard, Subjects, Notes, Calendar, Todo, etc.
│   │   ├── services/           # api.ts (backend client & offline cache)
│   │   ├── types/              # index.ts (TypeScript interfaces)
│   │   ├── App.tsx
│   │   ├── index.css           # Tailwind CSS & lined notebook styles
│   │   └── main.tsx
│   ├── index.html
│   ├── package.json
│   ├── tailwind.config.js
│   ├── tsconfig.json
│   └── vite.config.ts
│
├── server/                     # Backend Fastify + Node.js API
│   ├── data/                   # Auto-generated JSON database (db.json)
│   ├── uploads/                # Local uploaded handwritten notes (JPG/PNG/PDF)
│   ├── src/
│   │   ├── index.ts            # Fastify server & REST endpoints
│   │   ├── store.ts            # Data store & initial Class 12 Arts demo seed
│   │   └── types.ts            # Data models & database types
│   ├── package.json
│   ├── tsconfig.json
│   └── .env.example
│
├── supabase/
│   └── schema.sql              # Complete PostgreSQL schema, tables, RLS & storage
│
├── package.json                # Root package.json for monorepo scripts
└── README.md
```

---

## 🚀 Setup & Installation Instructions

### Step 1: Install Dependencies

Open a terminal in the root directory:

```bash
# Install root, client, and server dependencies
npm run install:all
```

Or install separately:
```bash
cd client && npm install
cd ../server && npm install
```

---

### Step 2: Configure Environment Variables

#### Backend (`server/.env`):
Copy `server/.env.example` to `server/.env`:
```ini
PORT=5000
NODE_ENV=development

# Optional: Supabase configuration (if connecting to Supabase cloud)
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_ANON_KEY=your-anon-key
SUPABASE_SERVICE_ROLE_KEY=your-service-role-key
```

#### Frontend (`client/.env`):
Copy `client/.env.example` to `client/.env`:
```ini
VITE_API_URL=/api
```

---

### Step 3: Connect Supabase (Optional for Cloud Setup)

1. Go to [https://supabase.com](https://supabase.com) and create a free project.
2. In Project Settings > API, copy your **Project URL** and **anon public key**.
3. Add these credentials to `server/.env` or `client/.env`.

*(Note: The app works out of the box with the included Fastify local storage without requiring Supabase).*

---

### Step 4: Create Database Tables (Supabase)

1. Open your Supabase Dashboard and click on the **SQL Editor** tab.
2. Open the file `supabase/schema.sql` from this repository.
3. Paste the contents into the SQL Editor and click **Run**.
4. This will create:
   - `profiles`
   - `subjects`
   - `chapters`
   - `handwritten_notes`
   - `quick_notes`
   - `important_questions`
   - `tasks`
   - `calendar_events`
   - `exams`
   - `study_plans`
   - Row Level Security (RLS) policies and performance indexes.

---

### Step 5: Configure Supabase Storage

1. In Supabase Dashboard, navigate to **Storage**.
2. Click **New Bucket**, name it `notes-storage`, and set it to **Public**.
3. The policies included at the end of `supabase/schema.sql` will grant read and upload access.

---

### Step 6 & 7: Start Frontend and Backend

You can run both concurrently from the root directory:

```bash
# Start backend and frontend simultaneously
npm run dev
```

Or run each in its own terminal:

#### Start Backend (Terminal 1):
```bash
npm run dev:server
# Server will run on http://localhost:5000
```

#### Start Frontend (Terminal 2):
```bash
npm run dev:client
# Frontend will run on http://localhost:5173
```

Open your browser and navigate to **`http://localhost:5173`**.

---

### Step 8: Test Login

1. When the app loads, you will see the **"Welcome Back 👋"** student login screen.
2. Click the **"Auto-fill Diya's credentials"** button (or type username: `diya`, password: `arts12`).
3. Click **"Open Study Notebook"**.
4. The Dashboard will immediately display today's tasks, the next exam countdown, study progress, and Arts subjects.

---

### Step 9: Test Handwritten Note Upload

1. Click on **Subjects** in the navigation bar.
2. Click on **History (इतिहास)**.
3. Click on **Chapter 1: Renaissance in Europe and Science**.
4. Select the **Handwritten Notes** tab.
5. Click **+ Upload Notes**.
6. Select any image (JPG/PNG) or PDF of a notebook page from your computer or phone.
7. Fill in the page number (e.g., `4`) and page title (e.g., `Printing Press Notes`).
8. Click **Save to Chapter**.
9. The new page appears in the gallery immediately! Click on it to test **Zoom In, Zoom Out, Rotate, and Fullscreen view**.

---

### Step 10: Production Build

To build optimized production assets:

```bash
# Build both client and server
npm run build
```

- The client static bundle will be generated in `client/dist/`.
- The server compiled JavaScript will be in `server/dist/`.

---

## 🔧 Troubleshooting

1. **Port 5000 is already in use:**
   Change `PORT=5001` in `server/.env` and adjust the proxy in `client/vite.config.ts`.
2. **Notes images not showing on mobile:**
   Make sure you are accessing the dev server via your computer's local IP address (e.g. `http://192.168.1.X:5173`) and that both devices are on the same Wi-Fi network.
3. **Resetting to sample demo data:**
   Go to **Settings** in the app and click **"Reset / Reload Sample Data"** to restore example Maharashtra Board chapters and notes.

---

Made with ❤️ for Diya's Maharashtra Class 12 Arts Board Exam preparation at Mahatma Fule College, Talodhi Balapur.

