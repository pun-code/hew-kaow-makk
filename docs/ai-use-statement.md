# AI-Use Statement
**Project:** FanSi – AI-Powered Fashion Styling and Recommendation Website  
**Course:** Introduction to Software Engineering (15031001)  
**Team:** Hew Khao Mak  
**Repository:** https://github.com/pun-code/hew-kaow-makk

---

## 1. Purpose of This Statement
This document transparently discloses how Team **Hew Khao Mak** utilized generative AI tools across Milestones M1, M2, and M3, along with the human verification and engineering controls applied to every AI-assisted artifact.

---

## 2. AI Tools Used
* **Google Gemini:** Used during M1 and M2 to structure problem statements, refine project scope, draft initial SRS sections (User Stories, NFRs, Use Cases), and generate visual/styling prompt references.
* **Anthropic Claude:** Used during M2 and M3 to audit consistency across the M1 Charter, M2 SRS, and prototype source code; refine the Use-Case Diagram (Figure 1); and assist in structuring and debugging the single-file HTML/CSS/JS prototype.

---

## 3. Chronological AI Usage Log (M1 – M3)

| Milestone & Date | AI Tool | What We Asked | What AI Produced | Human Verification & Changes Applied |
| :--- | :--- | :--- | :--- | :--- |
| **M1 / M2**<br>27 Aug 2026 | **Google Gemini** | Draft problem statements, refine project scope for 18–25 online shoppers, and structure the SRS (User Stories, NFRs, Use Cases, and initial Use-Case Diagram). | Structured SRS draft covering FR-1 to FR-5, NFR-1 to NFR-5, Use Cases (UC-1 to UC-5), and an initial diagram. | Team refined custom AI model constraints, removed e-commerce/payment flows into Out of Scope, aligned requirements with 4 September 2026 user interview findings, and adjusted UC-4 authentication wording. |
| **M2 / M3**<br>16 Nov 2026 | **Anthropic Claude** | Audit the prototype website against the M1 Charter and M2 SRS; update SRS descriptions to reflect actual prototype behavior while keeping planned AI/OAuth features separate, and redraw the Use-Case Diagram. | List of discrepancies between prototype code and SRS, revised SRS with explicit **"Prototype status"** blocks, and updated Use-Case Diagram (Figure 1) distinguishing current vs. planned external actors. | Team reviewed and approved each proposed edit before applying; preserved original acceptance criteria; and verified every **"Prototype status"** claim by running and testing the prototype in the browser. |
| **M3**<br>Implementation & Testing | **Claude & Gemini** | Assist in organizing single-file HTML/CSS/JS components, rule-based style scoring (`scoreStyles()`, `pickImg()`, `makeGen()`), `localStorage` bookmark state, and EN/TH dictionary switching. | Starter UI layout, responsive style cards, rule-based scoring logic, and bilingual translation dictionary structure. | Team inspected all generated code, fixed state edge cases, verified responsive rendering across viewports, and confirmed all 5 Must FRs are clickable without dead screens. |

---

## 4. Human Verification & Engineering Controls
1. **Strict Separation of Prototype vs. Planned AI Features:** All documentation and UI labels explicitly distinguish between what the M3 prototype executes locally (rule-based scoring across 10 styles, curated image library matching, `localStorage` persistence, demo sign-in, and dictionary-based EN/TH switching) and what is scoped for the future AI release (live AI styling/image generation APIs and Google OAuth).
2. **End-to-End Runtime Testing:** Every AI-suggested code snippet and SRS status description was validated by running the HTML prototype directly in a web browser and testing all user flows (FR-1 through FR-5).
3. **Team Accountability:** Every member of Team **Hew Khao Mak** reviewed the repository commits, requirement traceability, and code modules corresponding to their responsibilities in preparation for the individual Oral Exam.

---

## 5. Representative Prompts Used
* **Requirements & Golden Thread Audit:** *"Check the prototype website against the M1 charter and this SRS, revise the SRS to match the website while keeping the planned Google login, API, AI and image generation, and redraw the use-case diagram."*
* **Prototype Logic & UI Implementation:** *"Structure a standalone HTML/CSS/JS prototype supporting body measurement and skin-tone rule-based style scoring, 'Best Match' style galleries, localStorage outfit bookmarks, and an EN/TH language toggle."*
