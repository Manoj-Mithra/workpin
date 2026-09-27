<div align="center">

# 📍 Workpin
### **Location-Based Skilled Worker Hiring Platform**

A modern, mobile-first web application connecting skilled blue-collar workers with nearby clients through real-time, radius-based matching and direct communication.

[![Next.js](https://img.shields.io/badge/Next.js_16-black?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_v4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white)](https://supabase.com/)
[![Mapbox](https://img.shields.io/badge/Mapbox-000000?style=for-the-badge&logo=mapbox&logoColor=white)](https://mapbox.com/)
[![Academic Project](https://img.shields.io/badge/Academic_Project-DTI_2025--26-purple?style=for-the-badge)](Documentation.docx)

</div>

---

## 🎓 Academic Project Overview

> **"This project was developed by me — P. Manoj Mithra — as a capstone innovation project during my B.Tech in Computer Science & Engineering (Academic Year 2025–2026) at Gayatri Vidya Parishad College for Degree and P.G. Courses (Autonomous), Rushikonda, Visakhapatnam, in partial fulfillment of the requirements for the Design Thinking & Innovation (DTI) course."**

| Parameter | Details |
|:---|:---|
| **Author / Developer** | **P. Manoj Mithra** (Regd. No: `5231411208`) |
| **Institution** | Gayatri Vidya Parishad College for Degree and P.G. Courses (Autonomous), Rushikonda, Visakhapatnam |
| **Department** | Department of Computer Science & Engineering |
| **Academic Program** | B.Tech in Computer Science & Engineering |
| **Course** | Design Thinking & Innovation (DTI) — Project: `WORKPIN [DTI]` |
| **Academic Year** | 2025 – 2026 |
| **Project Mentor** | **Mr. Sri T. Sri Krishna**, Assistant Professor, Department of CSE |
| **Head of Department** | **Dr. G. R. S. Murthy**, Professor & Head, Department of CSE |
| **Collaborators** | S. Bhuvana (`5231411151`), T. Sai Venkata Sita Rama Swamy (`5231411171`), V. Ravindra (`5231411184`), P. Navadeep (`5231411209`), S. Prasanna (`5231411213`) |
| **Full Report** | [`Documentation.docx`](Documentation.docx) *(Complete academic documentation included in repo)* |

---

## 🎯 Purpose & Motivation

In semi-urban and urban localities, blue-collar workers (electricians, plumbers, carpenters, cleaners, and daily helpers) rely almost entirely on informal networks: word-of-mouth, personal contacts, or physically waiting at labor addas. This leaves them vulnerable to unpredictable income, lack of visibility, and long idle hours. Concurrently, residents and local businesses struggle to locate verified, available help quickly for urgent household or emergency repairs.

While platforms like Urban Company exist, they focus predominantly on pre-scheduled appointments and standardized services, with high commissions and rigid onboarding barriers that exclude local daily-wage tradespeople.

### **The Mission of Workpin**
I developed Workpin to eliminate middlemen and address this gap directly through a **hyperlocal, real-time, map-driven job marketplace**:
1. **Empower local workers** with a mobile-friendly digital presence, real-time job alerts within a customizable radius (1–50 km), and instant client communication.
2. **Provide clients** with immediate visibility of nearby available tradespeople, transparent profiles with ratings, one-tap hiring, and real-time chat.
3. **Bridge language barriers** by offering native accessibility in **Telugu (తెలుగు)**, **Hindi (हिन्दी)**, **Tamil (தமிழ்)**, and **English**.

---

## 🧠 Design Thinking Methodology

The development followed the standard five-stage **Design Thinking** framework documented in our project thesis:

```
[1. Empathize] ➔ [2. Define] ➔ [3. Ideate] ➔ [4. Prototype] ➔ [5. Test]
```

1. **Empathize**: Conducted informal field interviews with local tradespeople (plumbers, electricians, painters) and household residents around Visakhapatnam to understand pain points in job discovery, payment trust, and technology adoption.
2. **Define**: Formulated the core problem statement: *Workers need a simple, accessible mechanism to discover nearby work in real time, while clients need quick, verified help without lengthy booking procedures.*
3. **Ideate**: Compared traditional directory listings vs. contact boards vs. dynamic map-first interfaces. Chose an interactive map-first approach paired with proximity filters for immediate spatial relevance.
4. **Prototype**: Iterated from low-fidelity wireframes to high-fidelity responsive prototypes using Next.js 16, Tailwind CSS v4, shadcn/ui, and Mapbox GL JS.
5. **Test**: Tested with peer groups and local users to validate ease of use, multilingual toggling, and fast job-request workflows.

---

## ✨ Key Features

<table>
<tr>
<td width="50%">

### 🗺️ Map-First Proximity Discovery
Real-time Mapbox GL JS integration showing nearby jobs and workers with live distance calculations (Haversine formula), radius filters (1–50 km), and instant map ↔ list views.

### 🌐 Native Multilingual Support
Full UI localization in **English**, **తెలుగు (Telugu)**, **हिन्दी (Hindi)**, and **தமிழ் (Tamil)** with an accessible top-level switcher for diverse vernacular users.

### 💬 Real-Time Chat System
Supabase Realtime WebSocket messaging channel activated instantly once a client accepts a worker's application, preventing spam while ensuring rapid coordination.

</td>
<td width="50%">

### 🔐 Role-Based Access Control
Dedicated interfaces for **Workers** (browse jobs, set availability, apply, track status) and **Clients** (post jobs, inspect applicants, hire, review).

### ⭐ Reputation & Rating System
1-to-5 star feedback engine with automated PostgreSQL triggers recalculating cumulative worker ratings upon job completion.

### 💳 Simulated Payment System
Built-in mock payment modal demonstrating UPI and Cash settlements for frictionless end-of-job closure.

</td>
</tr>
</table>

### Additional Highlights
- 📱 **Mobile-First UX**: Responsive bottom navigation for phones alongside a collapsible desktop drawer.
- 🔄 **Atomic Auto-Rejection**: Accepting a worker automatically rejects pending competitor bids via database triggers.
- 🟢 **Live Availability Toggle**: Workers can toggle between *Available* and *Busy* in a single tap.
- 📞 **Direct Contact**: Click-to-call functionality for accepted jobs.
- 🌙 **Theme Modes**: Seamless Dark & Light theme switches with `next-themes`.

---

## 🏛️ System Architecture

```
   +--------------------------------------------------------------+
   |                       Client Interface                       |
   |   (Next.js 16 App Router · React · Tailwind CSS · shadcn/ui)  |
   +--------------------------------------------------------------+
              |                                      |
              v                                      v
   +----------------------+               +-----------------------+
   |      Mapbox API      |               |     Supabase BaaS     |
   | (GL JS & Geolocation)|               | (Postgres · Auth · RT)|
   +----------------------+               +-----------------------+
                                                     |
                                   +-----------------+-----------------+
                                   |                 |                 |
                              +----------+     +-----------+     +-----------+
                              | Postgres |     | Realtime  |     |  Storage  |
                              | Database |     | WebSockets|     |  & Auth   |
                              +----------+     +-----------+     +-----------+
```

Workpin is designed as a decoupled modern web architecture:
- **Presentation Layer**: Next.js 16 (React 19) App Router providing server and client components, optimized for mobile responsiveness.
- **Service Layer**: Mapbox GL JS for vector map rendering, user geolocation, and geospatial pin markers.
- **Backend as a Service (BaaS)**: Supabase managing PostgreSQL relational persistence, JWT session authentication, and WebSocket Realtime subscriptions.

*(Refer to [`architecture.svg`](architecture.svg) and [`workflow.svg`](workflow.svg) for detailed schematics.)*

---

## 🗄️ Database Schema & Triggers

The relational schema is configured in [`supabase/schema.sql`](supabase/schema.sql):

```
profiles (workers & clients)
   │
   ├── jobs (posted by clients)
   │     └── requests (worker applications)
   │           └── messages (real-time chat on accepted jobs)
   └── ratings (evaluations left by clients)
```

- **`handle_new_user`**: Trigger automatically creating a profile record upon Supabase auth sign-up.
- **`handle_request_acceptance`**: Trigger that transitions a job to `in_progress` and auto-rejects all other pending applications.
- **`update_worker_rating`**: Trigger that re-computes the cumulative average rating and total review count on profile updates.

---

## 🛠️ Tech Stack

| Domain | Technology | Description |
|:---|:---|:---|
| **Frontend Framework** | **Next.js 16** | React App Router framework with SSR and client optimization |
| **Language** | **TypeScript 5** | Strict type safety across components and database models |
| **Styling** | **Tailwind CSS v4** + **shadcn/ui** | Clean, accessible design system with customizable tokens |
| **Backend & Database** | **Supabase** | Managed PostgreSQL, Row Level Security (RLS), and Realtime |
| **Mapping Engine** | **Mapbox GL JS** | Interactive geospatial rendering and pin tracking |
| **Icons & Notifications** | **Lucide React** + **Sonner** | Modern iconography and responsive toast alerts |
| **Theming** | **next-themes** | Persistent dark/light mode toggle |

---

## 📂 Project Organization

```
workpin/
├── Documentation.docx         # 📄 Complete Academic Project Documentation
├── architecture.svg          # 🏛️ Architecture Diagram
├── workflow.svg              # 🔄 Workflow Process Diagram
├── supabase/
│   └── schema.sql            # 🗄️ Database tables, RLS policies, & trigger functions
├── src/
│   ├── app/
│   │   ├── (app)/            # Authenticated application pages
│   │   │   ├── page.tsx      # Map home view & radius discovery
│   │   │   ├── activity/     # Pending, accepted, & past job requests
│   │   │   ├── chat/         # Live chat threads
│   │   │   ├── jobs/[id]/    # Job specifics & applicant management
│   │   │   ├── post-job/     # Client job publishing wizard
│   │   │   └── profile/      # User profile, skills, & role switcher
│   │   ├── (auth)/           # Authentication flows (login, register)
│   │   └── layout.tsx        # Global layout with theme and i18n providers
│   ├── components/
│   │   ├── map/              # Mapbox wrapper, listing views, location prompt
│   │   ├── jobs/             # Job cards, applicant dialogs
│   │   ├── nav/              # Navigation bars (mobile bottom nav, desktop header)
│   │   ├── ratings/          # Star rating dialog
│   │   └── payment/          # Mock payment gateway simulation
│   ├── lib/
│   │   ├── supabase/         # Supabase client/server connectors
│   │   ├── i18n/             # Multilingual dictionary context
│   │   ├── geo.ts            # Haversine distance computations
│   │   └── types.ts          # TypeScript entities
│   └── locales/              # en.json, te.json, hi.json, ta.json
```

---

## ⚡ Getting Started Locally

### Prerequisites
- Node.js 18.x or later
- npm or pnpm
- A free [Supabase](https://supabase.com) project
- A free [Mapbox](https://mapbox.com) public access token

### 1. Clone & Install
```bash
git clone https://github.com/Manoj-Mithra/workpin.git
cd workpin
npm install
```

### 2. Environment Configuration
Create a `.env.local` file in the project root:
```env
NEXT_PUBLIC_SUPABASE_URL=https://your-supabase-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-supabase-anon-key
NEXT_PUBLIC_MAPBOX_TOKEN=pk.your-mapbox-token
```

### 3. Database Initialization
1. In your **Supabase Dashboard**, open the **SQL Editor**.
2. Copy and paste the entire script from [`supabase/schema.sql`](supabase/schema.sql).
3. Click **Run**.
4. In **Authentication → Providers → Email**, uncheck *"Confirm email"* for frictionless prototyping.

### 4. Run Development Server
```bash
npm run dev
```
Navigate to **[http://localhost:3000](http://localhost:3000)** in your browser.

---

## 🔮 Future Enhancements

As documented in the project report, future iterations can expand the current prototype into a production service:
- **Government ID Verification**: Aadhaar / DigiLocker integration for worker vetting and client safety.
- **Production Payment Gateways**: Integration with Razorpay / Cashfree for automated escrow and UPI instant payouts.
- **AI Matching**: Skill-based recommendation engine prioritizing top-rated nearby workers using machine learning.
- **Progressive Web App (PWA) / Native App**: Offline cache capabilities and Push Notifications for low-connectivity environments.

---

## 📜 Acknowledgements & License

I express my deepest gratitude to:
- **Prof. K. S. Bose**, Principal, for institutional encouragement.
- **Prof. P. V. Vinay**, Director, for providing technical infrastructure.
- **Dr. G. R. S. Murthy**, Professor & Head of CSE, for academic leadership and guidance.
- **Mr. Sri T. Sri Krishna**, Assistant Professor & Project Mentor, for continuous mentorship and valuable feedback throughout the Design Thinking journey.
- My project teammates for their cooperation and contributions.

This project is licensed under the [MIT License](LICENSE) — open for educational and community development.

<div align="center">

**Developed with ❤️ by P. Manoj Mithra (5231411208)**  
*GVPCDPGC, Rushikonda, Visakhapatnam*

</div>
