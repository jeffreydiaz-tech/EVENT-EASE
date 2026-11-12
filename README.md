# EventEase – Smart Campus Event Management Platform
### Discover Events. Register Easily. Make Memories.

**Academic Course:** 25CS208 – Web Technology  
**Academic Year:** 2026–2027  
**Project Category:** Responsive Frontend Web Application  
**Design Standard:** Modern SaaS Interface (Purple, Indigo, Blue, and Cyan Gradients)  

---

## 📌 1. Project Introduction

**EventEase** is a modern, responsive, and student-centric campus event management platform designed to centralize college event discovery, registrations, and participation tracking. 

Built strictly with native web technologies (**HTML5, CSS3, Vanilla JavaScript ES6+**), EventEase eliminates the need for complex, heavy frontend frameworks while delivering a high-performance, polished, SaaS-grade user experience for desktop, tablet, and mobile browsers.

* **Project Title:** EventEase – Smart Campus Event Management Platform
* **Tagline:** *Discover Events. Register Easily. Make Memories.*
* **Target Audience:** College students, departmental club coordinators, student affairs staff, and campus event organizers.
* **Academic Course:** 25CS208 – Web Technology

> **⚠️ Academic Demonstration Disclaimer:**  
> This platform is an academic frontend demonstration project. User authentication, profile persistence, and event registrations are implemented via the browser's **LocalStorage** and the **Web Crypto API (SHA-256 password hashing)**. Data is stored solely on the client machine and is not synchronized to an external backend database or shared across devices.

---

## 🎯 2. Problem Statement

College campuses buzz with technical workshops, hackathons, guest lectures, sports tournaments, and cultural fests. However:
1. **Information Fragmentation:** Event announcements are scattered across physical bulletin boards, unofficial WhatsApp groups, Telegram channels, and departmental emails.
2. **Missed Opportunities:** Students regularly miss registration cutoffs or learn about exciting workshops only after attendee caps have been reached.
3. **Lack of Centralized Tracking:** Students have no single place to track their confirmed registrations, retrieve digital entry passes, or manage cancellations when schedules conflict.

**EventEase solves this problem** by providing a centralized, accessible digital portal where students discover verified campus activities, register in a single click, access digital passes with simulated QR verification, and manage their event registrations from an intuitive student dashboard.

---

## 🚀 3. Key Objectives

1. **Centralized Discovery:** Provide a unified searchable and filterable directory of all campus activities across Technical, Cultural, Sports, Workshops, Seminars, and Competitions.
2. **Seamless Registration Flow:** Offer single-click event registration with real-time seat availability counters and duplicate registration safeguards.
3. **Student Dashboard:** Deliver a personalized student portal displaying profile credentials, active registrations, digital entry passes with printable layouts, and registration cancellation support.
4. **Demonstrate Web Engineering Principles:** Fulfill all technical requirements of 25CS208 by adhering to semantic HTML5, pure CSS Grid and Flexbox layouts, modular ES6+ JavaScript, strict regular expression form validation, asynchronous Fetch API integration, and WCAG 2.1 AA accessibility guidelines.

---

## 🌟 4. Core Features

### 4.1 Modern Landing Page (`index.html`)
* **Responsive Navigation:** Sticky blurred header, active navigation indicators, theme switch, dynamic auth status buttons, and accessible mobile drawer.
* **Hero Banner:** Compelling value proposition, call-to-action buttons ("Explore Events" and "Register Now"), and custom SVG campus event graphics.
* **Demonstration Statistics:** Quick metrics showcasing 24+ events, 1,250+ students, 12+ workshops, and 6 categories.
* **Featured Events Grid:** Dynamic rendering of top 6 flagship campus events with real-time seat bars and modal detail previews.
* **Interactive Category Cards:** Clickable categories (Technical, Cultural, Sports, Workshops, Seminars, Competitions) that filter the event catalog.
* **Event Budget Calculator:** Client-side estimation tool calculating total costs (venue, catering, decorations, equipment, miscellaneous) and per-participant expenses with zero-division handling and expense distribution visual bars.
* **Fetch API Campus Announcements:** Live asynchronous demonstration fetching campus news with loading states, error handling, and offline fallbacks.
* **FAQ Accordion & Validated Contact Form:** Interactive accordion panels and real-time validated contact messaging.

### 4.2 Event Explorer (`events.html`)
* **Real-time Keyword Search:** Instant search by title, description, or campus venue.
* **Multi-Facet Filtering:** Filter by stream/category and upcoming date ranges (Next 30 Days, November, December).
* **Sorting Capabilities:** Sort events by Earliest Date, Latest Date, Title (A–Z), and Popularity.
* **Event Details Modal:** In-depth view showing prerequisites, speaker info, venue maps, and seat availability.
* **Registration Action:** Authenticated one-click reservation with duplicate prevention and instant feedback.

### 4.3 Student Authentication (`signin.html`, `signup.html`, `register.html`)
* **Full Student Registration (`register.html`):** Strict regex validation for Full Name (`/^[a-zA-Z\s]{2,50}$/`), Student ID (`/^[A-Z0-9]{6,12}$/i`), Email (`RFC standard`), Mobile (`/^[6-9]\d{9}$/`), Academic Department, and strong Password rules.
* **Demonstration Sign-In (`signin.html`):** Pre-seeded demo credentials auto-fill button (`student@campus.edu` / `EventEase@2026`) for rapid evaluation, password visibility toggles, and inline error banners.
* **Safe Password Handling:** Uses Web Crypto API (`crypto.subtle.digest`) to store cryptographic SHA-256 digests in LocalStorage rather than plaintext.

### 4.4 Student Dashboard (`home.html`)
* **Personalized Overview:** Welcome banner displaying student name and department.
* **Profile Summary:** Student ID, email, contact details, and department affiliation.
* **Registration Metrics:** Counters for total registered, upcoming sessions, completed events, and activity points.
* **"My Registered Events":** Dynamically populated from LocalStorage. Includes digital entry ticket view with simulated QR codes, printable passes (`@media print`), and cancellation support with confirmation.
* **Recommended Events:** Suggestions of campus activities the student has not yet joined with 1-click quick registration.
* **Attendance History:** Historical participation records and certificate verification links.

### 4.5 Campus Assistant Chatbot (`js/chatbot.js`)
* Floating trigger button at bottom-right of every page with pulsating badge.
* Expandable chat window with automated scrolling and welcome message.
* Client-side keyword matching answering platform FAQs, registration guides, cancellation procedures, and support desks.
* Quick-action prompt chips for instant answers.

### 4.6 Dark / Light Mode System (`js/theme.js`)
* CSS Custom Properties tokens in `variables.css`.
* Persistent theme preference saved in `localStorage.setItem('eventease_theme', ...)`.
* Zero flash of unstyled theme (FOUC) through early script execution in `<head>`.

---

## 💻 5. Technology Stack

* **HTML5:** Semantic architecture (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`).
* **CSS3:** Custom properties (CSS variables), CSS Grid (multi-column dashboard), CSS Flexbox, smooth transitions, and responsive media queries.
* **Vanilla JavaScript ES6+:** Arrow functions, classes, template literals, async/await, DOM APIs, and strict mode.
* **Web APIs:**
  * **LocalStorage API:** Client-side state persistence for demo users, session tokens, and registered events.
  * **Web Crypto API (SubtleCrypto):** Client-side SHA-256 cryptographic password hashing.
  * **Fetch API:** Asynchronous data retrieval with AbortSignal timeouts and offline fallback handling.
* **Version Control & Hosting:** Git, GitHub, and static hosting readiness on Vercel (`vercel.json`).

---

## 📁 6. Project Folder Structure

```text
EventEase/
│
├── index.html                  # Landing page & featured campus events
├── events.html                 # Complete event discovery & explorer catalog
├── register.html               # Full student registration form with regex validation
├── signup.html                 # Quick account sign-up
├── signin.html                 # Demo student authentication with auto-fill
├── home.html                   # Authenticated student dashboard & digital passes
│
├── css/
│   ├── variables.css           # CSS custom properties (color tokens, gradients, dark mode)
│   ├── styles.css              # Core components (buttons, cards, modals, chatbot, tables)
│   └── responsive.css          # Responsive media queries (Desktop, Tablet, Mobile, Print)
│
├── js/
│   ├── app.js                  # Global application coordinator & toast system
│   ├── events.js               # Master campus events dataset, search, filter, and registration
│   ├── validation.js           # Regular expression rules and real-time form validation
│   ├── theme.js                # Dark/Light theme switching & persistence
│   ├── calculator.js           # Event budget calculator with participant division logic
│   ├── chatbot.js              # Floating campus assistant chatbot (keyword matching)
│   ├── storage.js              # LocalStorage manager & Web Crypto SHA-256 hashing
│   ├── api.js                  # Asynchronous Fetch API campus announcements demonstration
│   └── dashboard.js            # Student dashboard controller & digital ticket pass modal
│
├── assets/
│   ├── icons/
│   │   └── favicon.svg         # EventEase branded SVG favicon
│   ├── images/
│   │   ├── hero-illustration.svg
│   │   ├── web-dev-workshop.svg
│   │   ├── ai-seminar.svg
│   │   ├── coding-contest.svg
│   │   ├── cultural-fest.svg
│   │   ├── photo-contest.svg
│   │   ├── startup-summit.svg
│   │   ├── sports-meet.svg
│   │   └── robotics-expo.svg
│   └── data/
│       └── announcements.json  # Demonstrative JSON payload for Fetch API
│
├── docs/
│   ├── PROJECT_PROPOSAL.md     # Academic project proposal & scope document
│   ├── SRS.md                  # IEEE 830-style Software Requirements Specification
│   └── TESTING_REPORT.md       # Comprehensive 15-point test verification matrix
│
├── vercel.json                 # Static routing & security headers for Vercel
├── .gitignore                  # Git exclusion rules
└── README.md                   # Comprehensive technical documentation
```

---

## 🛠️ 7. Installation and Execution Instructions

EventEase is built entirely with pure client-side web technologies and requires no database servers, build steps, or package managers.

### Method 1: VS Code Live Server (Recommended)
1. Clone or extract the repository folder in VS Code.
2. Install the **Live Server** extension (by Ritwick Dey) from the VS Code Marketplace.
3. Right-click on `index.html` and select **"Open with Live Server"**.
4. The website will open in your browser at `http://127.0.0.1:5500/index.html`.

### Method 2: Python Built-in HTTP Server
If Python is installed on your workstation:
```bash
# Navigate to the project root directory
cd "e:/WEB TECH/micro web"

# For Python 3:
python -m http.server 8000
```
Open your browser and visit: `http://localhost:8000/index.html`.

### Method 3: Direct Browser Launch
You can directly open `index.html` in any modern web browser (Chrome, Firefox, Edge, Safari).  
*(Note: To test the Fetch API demo from `assets/data/announcements.json`, using an HTTP server like Method 1 or 2 is recommended due to browser CORS policies on `file://` protocols; if opened directly via `file://`, EventEase automatically serves the built-in offline fallback dataset).*

---

## 🔑 8. Demo Student Credentials

For academic grading and interactive testing:
* **Email:** `student@campus.edu`
* **Password:** `EventEase@2026`
* **Student ID:** `CS2026101`
* **Full Name:** `Aarav Sharma`

On the `signin.html` page, click the **"⚡ Auto-Fill Demo Credentials"** button to populate these values in a single click.

---

## 🌐 9. GitHub & Vercel Deployment Instructions

### Git Repository Setup
```bash
# Initialize git repository
git init

# Stage all files
git add .

# Commit changes
git commit -m "Build complete EventEase campus event management website"

# Connect to GitHub remote
git remote add origin https://github.com/<your-username>/eventease.git
git branch -M main
git push -u origin main
```

### Static Vercel Deployment
1. Log in to [Vercel](https://vercel.com).
2. Click **"Add New Project"** and import the GitHub repository.
3. Leave **Build Command** and **Output Directory** empty (Vercel automatically detects static HTML/CSS/JS repositories).
4. Click **"Deploy"**.
5. The `vercel.json` file in the root directory ensures clean URLs and security headers (`X-Content-Type-Options: nosniff`, `X-Frame-Options: SAMEORIGIN`).

---

## 📋 10. Academic Course Details

* **Course Code:** 25CS208
* **Course Title:** Web Technology
* **Microproject Title:** EventEase – Smart Campus Event Management Platform
* **Academic Year:** 2026–2027
* **License:** MIT License (Academic Use)
