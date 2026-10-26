# Student Hub — Apple Design System Edition 

A production-ready, top-tier academic dashboard crafted using the **Apple Design Language** (minimalist, sophisticated, fluid, and dark-mode native).

---

## 🎨 Apple Design Philosophy & Aesthetics

1. **Typography & Hierarchy:**
   - Ultra-clean font hierarchy powered by Inter (`tracking-tight`, high-contrast weights, tabular figures).
   - Cinematic headlines: *"Your academic universe. Perfectly aligned."*
2. **Materials & Depth:**
   - Deep obsidian monochromatic base (`#000000` / `#0a0a0a`), clean titanium silvers, and frosted whites.
   - Frosted glassmorphism (`backdrop-blur-2xl bg-[#0c0c0e]/80` and `border border-white/[0.08]`).
   - Deep specular highlights and soft drop shadows.
3. **Apple Bento Grid:**
   - 8-semester curriculum presented in an interactive Bento Grid with status badges, progress rings, SGPA breakdown, and hover-lift micro-interactions.
4. **iOS Segmented Control & Receipt Transcript:**
   - Smooth spring-animated segmented control pill for switching between **Results**, **Attendance**, and **Remarks**.
   - Tabular results styled like a high-end luxury receipt with ultra-thin dividers and aligned numbers.
   - High-precision circular attendance indicators and linear warning bars.
   - Faculty remarks formatted like Apple Notes / Messages with professor avatars and category filters.

---

## 🛠️ Tech Stack & Security

- **Framework:** Next.js 16 (App Router) + TypeScript
- **Styling:** Tailwind CSS + Apple HIG design tokens
- **Animations:** Framer Motion (spring physics, layout animations, ring transitions)
- **Icons:** Lucide React
- **Authentication:** JWT via `jose`, bcrypt password hashing, HttpOnly cookies, SameSite=Lax
- **Route Protection:** Next.js Proxy/Middleware with unauthenticated redirection
- **Security Headers:** Strict CSP, X-Frame-Options: DENY, X-Content-Type-Options: nosniff, Referrer-Policy

---

## 🚀 Getting Started

```bash
# Navigate to project
cd student-hub

# Run development server
npm run dev
# Accessible at: http://localhost:3000

# Build for production
npm run build
npm start
```

---

## 🔐 Verified Demo Credentials

| Field | Demo Credential |
|---|---|
| **Student ID / Email** | `CS2021001` or `arjun.sharma@university.edu` |
| **Password** | `password123` |
| **One-Tap Autofill** | Click the demo badge directly on the login card |

---

## 📁 Project Architecture

```
student-hub/
├── src/
│   ├── app/
│   │   ├── api/auth/
│   │   │   ├── login/route.ts      # Bcrypt verification & HttpOnly JWT cookie issue
│   │   │   ├── logout/route.ts     # Cookie clear endpoint
│   │   │   └── me/route.ts         # User session validator
│   │   ├── dashboard/page.tsx      # Apple Bento Grid 8-Semester Dashboard
│   │   ├── semester/[id]/page.tsx  # Segmented Control (Results, Attendance, Remarks)
│   │   ├── login/page.tsx          # Apple Floating Card Login with iOS Switch
│   │   ├── layout.tsx              # Root Layout & Theme/Auth Providers
│   │   ├── page.tsx                # Clean redirect to /dashboard
│   │   └── globals.css             # Apple Design System tokens & CSS utilities
│   ├── context/
│   │   ├── AuthContext.tsx         # Client Auth state and cookie synchronization
│   │   └── ThemeContext.tsx        # Dark / Light Mode with localStorage memory
│   ├── lib/
│   │   ├── auth.ts                 # Jose JWT signing/verification & bcrypt mock users
│   │   ├── data.ts                 # Full 8-semester mock curriculum & student dataset
│   │   └── utils.ts                # Apple color helpers, SGPA calculators, formatting
│   └── proxy.ts                    # Next.js route protection proxy
├── .env.local                      # JWT secret and app environment variables
├── next.config.ts                  # Production security headers & CSP
└── tailwind.config.ts              # Tailwind dark mode & typography setup
```
