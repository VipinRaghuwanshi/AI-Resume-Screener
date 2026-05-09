# CLAUDE.md — AI Resume Screener Tool

## Project Overview

**Project:** AI Resume Screener Tool for Indian HR Consultants  
**Owner:** Abhijeet (AI Learners India)  
**Goal:** Build a single-file HTML tool that helps Indian HR consultants and recruitment agencies score multiple resumes against a job description automatically.

---

## Indian Context Rules

All sample data, placeholders, and demo content must reflect the Indian recruitment landscape:

- **Names:** Use Indian names only — e.g., Rohit Kumar, Priya Sharma, Anand Pillai, Sneha Reddy, Arjun Mehta
- **Companies:** Use Indian companies only — TCS, Infosys, Wipro, Razorpay, Flipkart, Paytm, Zerodha, PhonePe
- **Cities:** Use Indian cities only — Bangalore, Pune, Hyderabad, Mumbai, Chennai, Indore, Ahmedabad
- **Salary/Package:** Always use Indian Rupees and LPA notation — e.g., `22 LPA`, `₹18 LPA`
- **Education:** Use Indian institutions — IIT, NIT, BITS, VIT, Anna University, IIIT

---

## Tech Stack

- **Delivery:** Single HTML file (`index.html`) with all CSS and JavaScript embedded
- **Dependencies:** No external libraries except:
  - Optional CDN-based fonts (e.g., Google Fonts)
  - PDF.js (via CDN) for PDF parsing — added in Prompt 5
- **Backend:** None — all logic runs entirely in the browser
- **Compatibility:** Must work when opened directly in Chrome, Edge, or Safari (no local server required)

---

## Features — Build in This Order

### 1. Input Layout
- Two textareas side by side:
  - **Left:** Job Description input
  - **Right:** Multiple resumes separated by `---`

### 2. Score Resumes Button
- Triggers parsing and scoring of all resumes against the JD

### 3. Smart Resume Parsing
Extract per resume:
- Name
- Email
- Phone
- Years of Experience
- Skills
- Current Company
- Education

### 4. Scoring Algorithm (0–100 points)
| Component | Weight | Logic |
|---|---|---|
| Skill overlap with JD | 60 pts | % of JD skills found in resume |
| Experience range match | 25 pts | Match against JD's required experience |
| Location match | 15 pts | City mentioned in JD vs resume |

> ⚠️ **Do not change scoring weights without explicit instruction from Abhijeet.**

### 5. Results Display
- Sorted high-to-low by score
- Tier badges:
  - 🟢 **Strong Match** — 80 and above
  - 🟡 **Maybe** — 50 to 79
  - 🔴 **Skip** — below 50

### 6. Expandable Detail View
- Per resume card: show matched skills and missing skills on expand

### 7. Export Shortlist as CSV
- Button to download shortlisted candidates (Strong Match + Maybe) as a `.csv` file

### 8. UI Design
- Professional look: blue-purple gradient header
- Card layout for results
- Fully responsive (works on desktop and tablet)

### 9. PDF File Upload Support
- Added in **Prompt 5**
- Use PDF.js (CDN) to parse uploaded PDF resumes
- Extracted text feeds into the same scoring pipeline

---

## Code Standards

- No external APIs — ever
- Code must be production-clean:
  - Meaningful comments throughout
  - Clearly separated sections (HTML structure / CSS styles / JS logic)
  - Easy to modify by a non-expert
- All UI text in **English** (HR consultants prefer English UI)
- All sample/placeholder data must reflect realistic Indian recruitment scenarios

---

## File Structure

```
index.html          ← Single deliverable file (HTML + CSS + JS all embedded)
CLAUDE.md           ← This file (project spec for Claude)
```

---

## Prompt History Reference

| Prompt # | Feature Added |
|---|---|
| 1–4 | Core tool: input, parsing, scoring, results, export, UI |
| 5 | PDF.js integration for PDF resume upload |

---

## Owner Notes

- Maintained by: **Abhijeet, AI Learners India**
- Target users: Indian HR consultants and recruitment agencies
- Scoring logic is intentional and calibrated — do not modify weights unless explicitly told