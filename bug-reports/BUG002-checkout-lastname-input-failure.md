# Defect Report: BUG002 - Last Name Input Field Fails to Accept Keystrokes

* **Report ID:** BUG002-CHK-01
* **Severity:** High (Blocks checkout completion; mandatory field cannot be filled)
* **Priority:** High
* **Status:** Open
* **Environment:** Google Chrome (Latest), Desktop, SauceDemo Production (https://www.saucedemo.com)
* **Affected Component:** Checkout Module / Customer Information Form

---

## 1. Description
When authenticated with error_user, the "Last Name" input field on the Checkout page fails to register keyboard inputs. Keystrokes do not render into the field, leaving it empty and blocking the user from proceeding with the checkout flow.

## 2. Preconditions
* User is authenticated using credentials:
  * Username: error_user
  * Password: secret_sauce
* User has at least one item added to the shopping cart.

## 3. Steps to Reproduce
1. Click on the shopping cart icon at the top right.
2. Click the green "Checkout" button.
3. Focus on the "Last Name" input field.
4. Attempt to type any alphabetic string (e.g., "Perez").

## 4. Expected Result
* The input field captures keyboard events and displays the typed characters.
* The field state updates correctly to allow form submission.

## 5. Actual Result
* The input field remains completely blank despite user keyboard input.
* Clicking "Continue" triggers the validation error: "Error: Last Name is required", trapping the user in the form.

---

## 6. Technical Evidence
* **Failure Type:** DOM Event Handling / Controlled Input Failure.
* **Impact:** Prevents order placement for all users hitting this client-side state.
