# timetable
App Title: Teacher Timetable Manager
 Languages: Full bilingual support 
________________________________________
🎯 Purpose:
Create a web-based app to manage and assign teacher schedules in a school with:
•	A week from Sunday to Thursday
•	7 teaching sessions per day
•	Dynamic classes (Grades 7, 8, 9) with sub-grades (e.g., 7-1, 8-3)
________________________________________
✅ Core Functionalities:
1. Timetable Grid (جدول الحصص):
•	Grid: 5 days (Sun–Thu) × 7 periods
•	Assign session by:
o	Grade/Sub-grade (e.g., 8-2 / ٩-٣)
o	Subject (English/Arabic etc.)
o	Teacher (primary or replacement)
•	Color-coded or icon-indicated replacements
2. Class Branch Management (إدارة الفصول):
•	Dynamically add sub-grades (e.g., 8-5, 9-4)
•	Each sub-grade has its own timetable
•	Automatically added to system
3. Subject List (المواد الدراسية):
•	Support both English and Arabic subject names
json
CopyEdit
[
  "Arabic", "English", "Mathematics", "Social Studies", "Islamic Education",
  "Sport Education", "Art Education", "Computer Science", "Sciences", "Life skills",
  "لغة عربية", "لغة انجليزية", "رياضيات", "دراسات إجتماعية", "تربية إسلامية",
  "تربية رياضية", "فنون بصرية", "حاسوب", "علوم", "مهارات حياتية"
]
4. Teacher Assignment (تخصيص المعلم):
•	Assign sessions with:
o	Day, Time, Grade/Sub-grade, Subject, Teacher
o	Primary/Replacement toggle
•	Auto-check for double bookings or over-assignment
5. Teacher Availability (توفر المعلمين):
•	If teacher is absent, show real-time available teachers
•	Filter by:
o	Free during session
o	Under 15 sessions per week
•	Assign temporary replacements
6. Session Timing:
•	Sunday–Wednesday & Thursday schedule:
json
CopyEdit
[
  { "period": 1, "time": "07:10 – 07:55" },
  { "period": 2, "time": "08:00 – 08:45" },
  { "period": 3, "time": "08:50 – 09:35" },
  { "period": 4, "time": "10:00 – 10:45" },
  { "period": 5, "time": "10:50 – 11:35" },
  { "period": 6, "time": "11:55 – 12:40" },
  { "period": 7, "time": "12:45 – 13:30" } // Thursday ends at Period 6
]
7. Dashboard Overview (لوحة المعلومات):
•	Summary view for:
o	Total teachers
o	Weekly hours per teacher
o	Assigned classes
o	Action buttons: Add sub-grade, Assign teacher, Export, etc.
________________________________________
🧠 Advanced Features (Optional):
•	Validate subject matches teacher’s qualification
•	Restrict max sessions per teacher/day (e.g., ≤3/day)
•	Export timetable (PDF, Excel)
•	Teacher Authentication (login, session view, upload docs)
•	Admin Controls:
o	Assign teachers
o	Upload evaluation forms
o	Track submitted files
o	Send reminders
________________________________________
📋 Evaluation Feature:
•	Allow admins to fill out bilingual evaluation forms like:
json
CopyEdit
{
  "evaluation_criteria": [
    {
      "arabic": "الجوانب الشخصية والمهنية",
      "english": "Personal and Professional Aspects",
      "weight": "15%"
    }
  ],
  "rating_scale": [
    { "arabic": "ممتاز", "english": "Excellent", "score_range": "90 and above" }
  ]
}
________________________________________
🧱 Tech Stack:
•	Frontend: React + Tailwind CSS (with bilingual UI support)
•	Backend: Node.js + Express or Firebase
•	Database: PostgreSQL
•	Authentication: Admin/Teacher roles with login
________________________________________
📁 Suggested Folder Structure:
css
CopyEdit
src/
├── components/
│   ├── TimetableGrid.jsx
│   ├── AssignSessionModal.jsx
│   └── ReplacementFinder.jsx
├── pages/
│   ├── Dashboard.jsx
│   ├── Teachers.jsx
│   └── AssignTeacher.jsx
├── context/
│   ├── TeacherContext.js
│   └── TimetableContext.js
├── utils/
│   ├── validateTeacherHours.js
│   └── findAvailableTeachers.js
________________________________________
📚 Example Data Models:
Teacher
json
CopyEdit
{
  "id": "t1",
  "name": "Ali Hamidi",
  "subjects": ["Arabic", "Social Studies"],
  "assignedSessions": 12
}
Session
json
CopyEdit
{
  "day": "Monday",
  "period": 3,
  "grade": "9",
  "subGrade": "9-2",
  "subject": "Sciences",
  "teacher": "Ali Hamidi",
  "type": "Primary"
}
________________________________________
🔐 Authentication & Roles:
•	Teachers: View timetable, upload required documents
•	Admins:
o	Assign sessions & replacements
o	Evaluate and track teachers
o	Export reports
o	Submit request documents to teachers or group of teacher 
o	Can create groupe of teacher and assign mission 
o	Can view progress  of assigned missions
________________________________________
🧭 Final Notes:
Ensure full bilingual (RTL and LTR) UI support


data into a JSON format grouped by subject, including details such as session count, schedule entries, and teacher names.
Here is a JSON representation of a few sample entries to illustrate the structure:
json
CopyEdit
{
  "subjects": [
    {
      "name": "الشرعیة",
      "entries": [
        {
          "sessions": 4,
          "schedule": ["7/1", "7/1", "7/1", "7/1"],
          "teacher": "أحمد صلاح"
        },
        {
          "sessions": 12,
          "schedule": ["7/6", "7/7", "7/8", "7/7", "7/8", "7/6", "7/7", "7/6", "7/8", "7/8", "7/6", "7/7"],
          "teacher": "محمد محمود"
        }
        // more entries...
      ]
    },
    {
      "name": "اللغة العربیة",
      "entries": [
        {
          "sessions": 5,
          "schedule": ["8/1", "8/1", "8/1", "8/1", "8/1"],
          "teacher": "محمد أبو زایدة"
        }
        // more entries...
      ]
    }
    // more subjects...
  ]
}

