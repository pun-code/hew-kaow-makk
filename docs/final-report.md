# Final Project Report: FanSi
**AI-Powered Fashion Styling and Recommendation Website**  
**Course:** Introduction to Software Engineering (15031001)  
**Team:** Hew Khao Mak  
**Repository:** https://github.com/pun-code/hew-kaow-makk  
**SDLC Methodology:** Agile Model (Scrum Framework — 10-Week Timeline)

---

## 1. Team Members
| Student ID | Full Name |
| :--- | :--- |
| `6931503112` | Phongchayut Pongsathrontong |
| `6931503040` | Tanachok Boonnak |
| `6931503028` | Chirason Sriphorm |
| `6931503022` | Kanyanat Chuyweth |
| `6931503118` | Sathit Saimongkhon |

---

## 2. Problem Statement & User Validation (M1 Foundation)
* **Problem:** University students and early-career adults (aged 18–25) who shop for clothing online often struggle to match clothing colors and styles to their individual body proportions and skin tone, wasting time searching across multiple websites and risking ill-fitting purchases.
* **User Discovery (Gate 1 Interviews — 4 September 2026):** Requirements were validated through interviews with three target users:
  1. Jakkaphat Palaaud (MFU Student)
  2. Phakamphut Sa-at (MFU Student)
  3. Nataphat Ngoenrungrueangrot (TU Student)
* **Solution Overview:** **FanSi** analyzes user body measurements and skin tone to recommend suitable fashion styles, render measurement-matched outfit previews, enable measurement-based style discovery, persist outfit bookmarks, and support bilingual switching (TH/EN).

---

## 3. Golden Thread Traceability Matrix (M1 → M2 → M3)
Every Functional Requirement (FR-1 to FR-5) and Use Case (UC-1 to UC-5) traces directly from a validated user pain point to a clickable feature in the M3 prototype:

| FR & Use Case | Validated User Pain | Prototype Implementation (M3 Current Build) | Planned AI Release (Future Scope) |
| :--- | :--- | :--- | :--- |
| **FR-1 / UC-1**<br>Body Measurement & Skin Tone Analysis + Outfit Preview | Users cannot determine which styles fit their proportions/skin tone or visualize outfits before choosing. | Inputs height, weight, gender, chest/waist/hip (inches), editable body type, and 1 of 5 skin tones. Rule-based engine (`scoreStyles()`, `pickImg()`, `makeGen()`) ranks 10 styles, labels the top result **"AI pick"**, and displays the closest curated library look with top/bottom, color palette, and fit advice. | External AI Styling & Image Generation API producing 5 AI-ranked styles and dynamically generated outfit preview images, plus unauthenticated guest mode access. |
| **FR-2 / UC-2**<br>Body Measurement-Based Style Search | Browsing general catalogs wastes time when outfits do not match individual measurements. | Interactive style tiles and a **"More of [style]"** gallery highlight the look closest to the user's entered measurements labeled **"Best Match"**. | Dedicated measurement search form returning exact matches or a "no matching styles found" notice with AI-generated alternatives. |
| **FR-3 / UC-3**<br>Personal Outfit Bookmark | Users forget previously liked outfits and have to repeat searches. | Clicking the bookmark button on a preview immediately saves the look to **Profile → Bookmarks** via browser `localStorage` and supports one-click removal/toggling. | Server-side account-linked bookmark persistence across sessions and devices. |
| **FR-4 / UC-4**<br>User Authentication & Bookmark Persistence | Bookmarked outfits are lost when closing the browser or switching devices. | Demo sign-in screen accepts non-empty email/username and password credentials, plus a demo Google sign-in profile; Profile page allows editing username, height, and weight. | Real Email/Password authentication and Google OAuth backed by a cloud database. |
| **FR-5 / UC-5**<br>Bilingual Language Translation (TH / EN) | Language barriers prevent Thai or international users from understanding UI labels and styling advice. | **EN/TH** switcher on the Style page dynamically updates labels, buttons, style descriptions, and analysis text using a pre-translated dictionary persisted in `localStorage`. | Full bilingual localization across all screens (including Sign-In and Profile) plus AI-generated Thai/English style descriptions. |

---

## 4. Non-Functional Requirements (NFR) Summary
* **NFR-1 (Performance):** Single standalone HTML file (~3.5 MB with embedded assets) designed to load and render within 3.0 seconds (verified via Chrome DevTools Performance/Network audit).
* **NFR-2 (Recommendation Accuracy):** Rule-based scoring engine evaluated against a 100-case body-measurement and style validation set targeting ≥ 80% alignment accuracy.
* **NFR-3 (Usability):** Timed usability trials with 3 first-time participants completing measurement entry, style preview, and bookmarking within 45 seconds without a manual.
* **NFR-4 (Availability):** Designed for ≥ 99.0% monthly uptime upon cloud deployment.
* **NFR-5 (Security & Privacy):** Client-side prototype stores only non-sensitive UI preferences and bookmarks in `localStorage` with zero plaintext passwords stored or transmitted over the network.

---

## 5. Explicit Out-of-Scope Boundaries
In accordance with Section 2.1 and Section 6 of the M2 SRS, the following features are intentionally excluded:
1. In-app e-commerce transactions or payment gateway integration.
2. User-generated outfit uploading or public style-sharing feeds.
3. In-app user-to-user messaging or social chat features.

---

## 6. How to Run the Prototype
1. Clone the repository:
   ```bash
   git clone [https://github.com/pun-code/hew-kaow-makk.git](https://github.com/pun-code/hew-kaow-makk.git)
