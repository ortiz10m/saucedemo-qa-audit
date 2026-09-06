# Test Suite: TC001 - Authentication Module

**Target System:** SauceDemo (https://www.saucedemo.com)  
**Execution Type:** Manual Functional Testing  
**Author:** QA Engineering Team  

---

## 1. Test Scenario: Successful Login (Happy Path)
* **ID:** TC001-01
* **Priority:** High
* **Preconditions:** User is on the login page (`/`).
* **Test Data:** 
  * Username: `standard_user`
  * Password: `secret_sauce`

### Test Steps:
1. Navigate to the base URL.
2. Enter the valid username into the `Username` input field.
3. Enter the valid password into the `Password` input field.
4. Click the `Login` button.

* **Expected Result:** User is authenticated successfully and redirected to `/inventory.html`. The product catalog is displayed.

---

## 2. Test Scenario: Blank Password Field (Negative Testing)
* **ID:** TC001-02
* **Priority:** High
* **Preconditions:** User is on the login page (`/`).
* **Test Data:** 
  * Username: `standard_user`
  * Password: *[Empty]*

### Test Steps:
1. Navigate to the base URL.
2. Enter `standard_user` into the `Username` input field.
3. Leave the `Password` input field completely empty.
4. Click the `Login` button.

* **Expected Result:** Authentication fails. A visible error banner is displayed: *"Epic sadface: Password is required"*. Redirection does not occur.

---

## 3. Test Scenario: Locked-Out Account Handling (Edge Case)
* **ID:** TC001-03
* **Priority:** Medium
* **Preconditions:** User is on the login page (`/`).
* **Test Data:** 
  * Username: `locked_out_user`
  * Password: `secret_sauce`

### Test Steps:
1. Navigate to the base URL.
2. Enter `locked_out_user` into the `Username` field.
3. Enter `secret_sauce` into the `Password` field.
4. Click the `Login` button.

* **Expected Result:** System rejects the attempt with an explicit alert: *"Epic sadface: Sorry, this user has been locked out."* No session token or dashboard access is granted.
