# Math Quest — Singapore Math Grade 4 Practice App

A gamified, assignment-based math practice web app for a 4th-grade student
following the Singapore Math curriculum, with a companion Teacher/Admin
dashboard for tracking progress and managing assignments.

## Tech Stack

- React 18 + Vite
- Tailwind CSS
- Lucide React icons
- LocalStorage as the persistence layer (no backend required)

## Getting Started

```bash
npm install
npm run dev
```

Then open the printed local URL in your browser.

To build for production:

```bash
npm run build
npm run preview
```

## Structure

- `src/data/curriculum.js` — Singapore Math Grade 4 chapter/subtopic map and badge definitions.
- `src/utils/mathEngine.js` — dynamic question generators for every chapter (place value, fractions, decimals, geometry, data/graphs, bar-model word problems).
- `src/utils/storage.js` — localStorage-backed mock database: student profile, streaks, badges, chapter stats, activity log, assignments.
- `src/context/AppContext.jsx` — shared app state (student progress + teacher/student role).
- `src/components/common/` — `ProgressBar`, `Badge`, `ConfettiOverlay`, `XpPopup`, `Modal`.
- `src/components/student/` — `StudentDashboard`, `DailyQuest`, `ChapterSelect`, `QuizRunner`, `BarModelVisualizer`, `MiniChart`, `Results`.
- `src/components/teacher/` — `TeacherLogin`, `TeacherDashboard`, `AnalyticsCharts`, `AssignmentManager`, `ActivityLog`.

## Teacher Dashboard

Switch to the "Teacher" tab in the header and log in with the password:

```
teacher123
```

From there you can view chapter-by-chapter accuracy analytics, see which
sub-topics the student is struggling with, review the daily activity log,
and assign/lock chapters for the next day's practice.

## Deployment

Every push to `main` builds and deploys the app to GitHub Pages via
`.github/workflows/deploy.yml`. Once the first workflow run completes, the
app is live at:

```
https://spatro4.github.io/student_-app/
```

If Pages isn't enabled yet for this repo, go to **Settings → Pages** and
set the source to **GitHub Actions** (the workflow will otherwise fail on
its very first run with a "not enabled" error, then succeed once you
re-run it after enabling).
