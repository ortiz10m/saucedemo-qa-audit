# SauceDemo E-Commerce QA Audit

Comprehensive functional testing, test case design, defect reporting, and technical network analysis for the SauceDemo e-commerce platform.

## 📌 Project Overview
The objective of this project is to perform end-to-end functional and technical quality audits on key customer journeys, identifying runtime exceptions, boundary condition failures, and client-side usability defects.

---

## 📁 Repository Structure & Artifacts

### 1. Test Cases (`/test-cases`)
* **[TC001 - Authentication Test Suite](test-cases/TC001-login.md):** Verification of authentication mechanisms covering Happy Path, Negative Testing (invalid/empty inputs), and Security Edge Cases (unauthorized URL access prevention).

### 2. Defect Reports (`/bug-reports`)
* **[BUG001 - Cart Removal Failure](bug-reports/BUG001-remove-cart-failure.md):** Client-side unhandled exception during cart state mutation (`error_user`).
* **[BUG002 - Checkout Last Name Input Blocker](bug-reports/BUG002-checkout-lastname-input-failure.md):** Controlled input failure preventing form submission and blocking the checkout funnel.
* **[BUG003 - Broken Product Image Mapping](bug-reports/BUG003-broken-product-images.md):** Incorrect static asset data binding masked behind HTTP 200 responses (`problem_user`).

### 3. Executive Audit Summary (`/docs`)
* **[Test Execution & Release Summary](docs/test-execution-summary.md):** Full execution metrics, defect density breakdown, root cause analysis (RCA), and the final **NO-GO** production release verdict.

---

## 🛠 Tech Stack & Methodologies
* **Testing Types:** Functional, Black-box, Negative, Edge Case, and Exploratory Testing.
* **Technical Inspection:** Chrome DevTools (Console runtime trace analysis, Network HTTP inspection, Asset status code audits).
* **Documentation Standards:** Conventional Commits, Markdown traceability tables, and root-cause defect reports.
