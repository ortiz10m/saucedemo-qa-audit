# Defect Report: BUG001 - Failed to Remove Item from Cart

* **Report ID:** BUG001-CART-01
* **Severity:** High (Core functionality failure; blocks cart updates)
* **Priority:** High
* **Status:** Open
* **Environment:** Google Chrome (Latest), Desktop, SauceDemo Production (https://www.saucedemo.com)
* **Affected Component:** Inventory / Shopping Cart Module

---

## 1. Description
When authenticated with error_user, clicking the "Remove" button on the inventory page fails to remove the item. The UI state does not revert to "Add to cart", the cart counter remains unchanged, and an unhandled JavaScript exception is logged in the console.

## 2. Preconditions
* User is authenticated in SauceDemo using credentials:
  * Username: error_user
  * Password: secret_sauce
* At least one product has been added to the shopping cart (e.g., "Sauce Labs Backpack").

## 3. Steps to Reproduce
1. Navigate to https://www.saucedemo.com/inventory.html.
2. Locate "Sauce Labs Backpack" (previously added to the cart).
3. Click on the red "Remove" button.
4. Open the browser Developer Tools (F12 > Console tab).

## 4. Expected Result
* The item is removed from the cart.
* The button state changes from "Remove" back to "Add to cart".
* The shopping cart badge counter decreases by 1 (or disappears if empty).
* No unhandled runtime exceptions are thrown in the console.

## 5. Actual Result
* The button remains in the "Remove" state.
* The shopping cart counter does not decrease (stays at 1).
* The item persists in the cart state.
* The browser console throws the following unhandled error:
  Uncaught Error: Failed to remove item from cart. at p (index-XyuNVFOR.js:571:38300)

---

## 6. Technical Evidence
* **Console Log Trace:** Uncaught Error: Failed to remove item from cart.
* **Failure Type:** Client-Side Unhandled Exception (JavaScript state mismatch).
