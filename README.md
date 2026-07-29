# SkillBridge Africa – Complete Ecosystem

**SkillBridge Africa** is a full-featured, multi‑platform ecosystem designed to connect African youth with mentors, practical learning, and career opportunities. The project consists of four interconnected web applications:

- **Homepage (`index.html`)** – The central landing page showcasing the platform, with navigation to all sub‑platforms.
- **Youth Platform (`youth.html`)** – A personal dashboard for learners to enroll in courses, track progress, request mentorship, and manage their schedule.
- **Mentor Platform (`mentor.html`)** – A dedicated space for approved mentors to manage requests, appointments, mentees, and availability.
- **Admin Dashboard (`admin.html`)** – A powerful control panel for administrators to manage users, approve mentors, moderate content, and view platform analytics.

All platforms share a **single authentication system** and store data in the browser’s `localStorage`, making the entire suite fully functional without a backend server – perfect for prototyping, demos, or lightweight deployments.

---

## Table of Contents

- [Features at a Glance](#features-at-a-glance)
- [Platform Details](#platform-details)
  - [Homepage](#homepage)
  - [Youth Platform](#youth-platform)
  - [Mentor Platform](#mentor-platform)
  - [Admin Dashboard](#admin-dashboard)
- [Authentication & Roles](#authentication--roles)
- [Data Storage & Sharing](#data-storage--sharing)
- [Getting Started](#getting-started)
- [Default Admin Credentials](#default-admin-credentials)
- [Technologies Used](#technologies-used)
- [Future Enhancements](#future-enhancements)

---

## Features at a Glance

| Feature | Homepage | Youth | Mentor | Admin |
|---------|----------|-------|--------|-------|
| User registration & login | ✅ | ✅ | ✅ | ✅ |
| Browse & apply for opportunities | ✅ | ✅ | – | ✅ (manage) |
| Discover & contact talent | ✅ | – | – | – |
| Request & manage mentorship | ✅ | ✅ | ✅ | ✅ (approve) |
| Enroll in courses & track progress | – | ✅ | – | – |
| Weekly calendar & scheduling | – | ✅ | ✅ | – |
| Community posts & interactions | ✅ | ✅ | – | ✅ (moderate) |
| Admin user management | – | – | – | ✅ |
| Platform analytics & reports | – | – | – | ✅ |

---

## Platform Details

### Homepage (`index.html`)
- Serves as the main entry point for all users.
- Displays a hero section with stats (opportunities, talents, mentors).
- Quick navigation cards to jump to Opportunities, Talent, Mentorship, Youth Platform, and Admin (only visible to admins – but hidden from regular users).
- Users can browse opportunities, talent, and community posts without logging in, but must log in to apply, post, or contact.
- **Guest view** is fully functional – users see content but are prompted to log in for interactions.

### Youth Platform (`youth.html`)
- A personal learning and growth dashboard.
- **Courses**: Enroll in practical courses, complete lessons, earn XP, and receive certificates upon completion.
- **Mentorship**: Browse approved mentors, send requests, and chat with connected mentors.
- **Opportunities**: View and apply for internships, jobs, and gigs.
- **Community**: Share posts, like, and comment.
- **Calendar**: Full weekly calendar to schedule events (mentorship sessions, study time, etc.) with color‑coded types.
- **Profile**: Track progress, view earned certificates, and see activity history.

### Mentor Platform (`mentor.html`)
- Designed for approved mentors to manage their mentorship activities.
- **Requests**: View pending mentorship requests from youth; accept or decline.
- **My Mentees**: List of current mentees; schedule appointments or remove mentees.
- **Calendar**: See all appointments and availability; click any time slot to add a new appointment.
- **Availability**: Set available time slots for each day of the week – these are shown to youth when they request mentorship.
- **Profile**: Manage personal info, expertise, and suggest opportunities to mentees.
- **Auto‑accept**: Optional setting to automatically accept all incoming requests.

### Admin Dashboard (`admin.html`)
- The control centre for the entire ecosystem.
- **Dashboard**: Quick stats (total users, approved mentors, pending applications, opportunities).
- **Users**: View all registered users and delete non‑admin accounts.
- **Mentors**: Manage all mentor profiles – approve, reject, or revoke approval. Pending applications are highlighted.
- **Opportunities**: View all posted opportunities and delete inappropriate ones.
- **Community**: View all community posts and delete any violating content.
- **Reports**: Visual charts for user growth and mentor status, plus a summary of platform metrics (total users, mentors, opportunities, posts, requests).

---

## Authentication & Roles

- All platforms share the same authentication system stored in `localStorage`.
- **Three user roles**:
  - **Youth**: Default role for new registrations.
  - **Mentor**: Assigned after admin approval (via the mentor profile).
  - **Admin**: Only one admin account exists by default (see credentials below).
- **Login flow**:
  - Any user can log in on any platform.
  - If an **admin** logs in, they are automatically redirected to the Admin Dashboard.
  - If a **mentor** logs in, they are taken to the Mentor Platform.
  - **Youth** users land on the Youth Platform (or homepage).
- **Sign‑up** creates a youth account. The admin account is pre‑seeded and cannot be created via sign‑up.

---

## Data Storage & Sharing

All data is stored in the browser’s `localStorage` under these keys:

| Key | Description |
|-----|-------------|
| `sb_users` | Array of user objects (name, email, password, role) |
| `sb_auth_user` | Currently logged‑in user (session) |
| `sb_mentor_profiles` | Object mapping email → mentor profile (expertise, mentees, requests, availability, appointments, etc.) |
| `sb_opps` | Array of opportunities (jobs, internships, gigs) |
| `sb_posts` | Array of community posts with likes and comments |
| `sb_applications` | Applications submitted to opportunities |
| `sb_messages` | Contact messages sent to talents |
| `sb_mentor_reqs` | Legacy mentor requests (also stored in mentor profiles) |
| `sb_mentor_avail` | Legacy availability (now inside mentor profiles) |
| `sb_calendar_events` | Legacy events (now inside youth/mentor schedules) |
| `sb_youth_profiles` | Additional youth‑specific data (courses, XP, schedule, etc.) |

Because all platforms use the same `localStorage` keys, data is automatically shared across platforms in the same browser (same origin). This enables seamless switching between platforms without losing any information.

---

## Getting Started


# SkillBridge Africa Admin Dashboard

A fully responsive admin dashboard for managing users, mentors, opportunities, and community posts on the SkillBridge Africa platform.

## Live Demo
[Live URL](https://drive.google.com/file/d/1dbhYIAqd6tqZmECW422mtuPMxKzya-s0/view?usp=sharing)

## Features
- Admin authentication
- Dashboard with real‑time statistics
- User management (view, delete)
- Mentor application approval/rejection
- Opportunities & community post moderation
- Context‑aware search
- Reports with visual charts

## How to Run Locally
1. Clone the repository:
   git clone https://github.com/your-username/your-repo-name.git
2. Open the folder and double‑click `admin.html`, or open it with a live server (no build tools required).
3. Log in using the default admin credentials:
   - **Email:** m.byusa@alustudent.com
   - **Password:** SkillBridgeAfrica@1

## Tech Stack
- HTML5, CSS3, vanilla JavaScript
- LocalStorage for data persistence (prototype)

## Project Structure
- `admin.html` – The entire application (all screens included)

## SRS Document
[Software Requirements Specification](link-to-srs)

## License
MIT

1. **Clone or download** the project files. You should have these HTML files:
   - `index.html` (homepage)
   - `youth.html` (youth platform)
   - `mentor.html` (mentor platform)
   - `admin.html` (admin dashboard)
   - (Optional) `README.md` – this file.

2. **Open `index.html`** in any modern web browser (Chrome, Firefox, Edge, etc.). No server required – everything runs client‑side.

3. **Explore** the platform as a guest, or **sign up** as a youth to get started.

4. **To test the admin features**, use the default admin credentials (see below). You can log in from any platform; you will be redirected to the admin dashboard.

5. **To test mentor features**, you can either:
   - Register as a youth, then log in to the mentor platform (a mentor profile will be auto‑created).
   - Have an admin approve your mentor profile (go to the admin dashboard → Mentors → Approve).
   - Once approved, you will have full mentor capabilities.

---

## Default Admin Credentials

| Email | Password |
|-------|----------|
| `m.byusa@alustudent.com` | `SkillBridgeAfrica@1` |

> **Note:** This admin account is pre‑seeded. It cannot be deleted or modified via the UI.

---

## Technologies Used

- **HTML5 / CSS3** – Responsive, semantic markup with a custom dark‑blue theme.
- **JavaScript (Vanilla ES6)** – All logic, state management, and DOM manipulation.
- **Tabler Icons** – Icon library for clean, modern icons.
- **localStorage** – Persistent client‑side storage.
- **No external libraries or frameworks** – Pure, lightweight, and fast.

---

## Future Enhancements

- **Backend integration** – Replace localStorage with a real database (e.g., Firebase, Supabase, or a custom API).
- **Email notifications** – Send confirmation emails for sign‑up, mentorship requests, etc.
- **Video calling** – Integrate a video chat API for remote mentorship sessions.
- **Mobile apps** – Wrap the web apps in native containers (React Native, Flutter).
- **Advanced reporting** – More detailed analytics with charts and export options.
- **Multi‑language support** – Localize the UI for different African languages.

---

## License

This project is open‑source and available under the MIT License. Feel free to use, modify, and distribute it for educational or commercial purposes.

---

## Support

For questions, feedback, or contributions, please reach out to the project maintainers or open an issue in the repository.

---

*SkillBridge Africa – Empowering the next generation of African leaders through mentorship, learning, and opportunity.*