# Defect Report: BUG003 - Product Catalog Images Replaced by Generic Error Asset

* **Report ID:** BUG003-INV-01
* **Severity:** Medium (Cosmetic/Asset mapping failure; core transaction flow remains functional)
* **Priority:** High (Severe UX degradation impacting customer purchase intent)
* **Status:** Open
* **Environment:** Google Chrome (Latest), Desktop, SauceDemo Production (https://www.saucedemo.com)
* **Affected Component:** Inventory Module / Product Catalog Display

---

## 1. Description
When authenticating with problem_user, all items in the inventory catalog fail to display their corresponding product imagery. The frontend incorrectly loads a fallback error asset (sl-404-Cq1a9k9X.jpg) across all product cards, despite the network returning an HTTP 200 status code.

## 2. Preconditions
* User is authenticated in SauceDemo using credentials:
  * Username: problem_user
  * Password: secret_sauce

## 3. Steps to Reproduce
1. Navigate to https://www.saucedemo.com.
2. Log in using problem_user credentials.
3. Observe the product catalog grid on the /inventory.html page.
4. Inspect image requests in DevTools (Network tab).

## 4. Expected Result
* Each product card displays its unique and accurate product image (e.g., sauce-backpack-1200x1500.jpg for the Sauce Labs Backpack).

## 5. Actual Result
* Every product card displays the identical "dog with tennis ball" error graphic.
* Image asset requests resolve to sl-404-Cq1a9k9X.jpg.

---

## 6. Technical Evidence
* **Asset URL:** https://www.saucedemo.com/static/media/sl-404-Cq1a9k9X.jpg
* **HTTP Status Code:** 200 OK (Asset exists, but binding/mapping in the catalog component is incorrect).
* **Failure Type:** Static Asset Mismatch / Data Binding Defect.
