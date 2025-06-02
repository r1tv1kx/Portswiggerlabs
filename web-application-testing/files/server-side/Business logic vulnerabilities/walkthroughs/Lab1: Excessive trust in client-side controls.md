# Lab 1: Excessive trust in client-side controls
<div align="center">
  <img width="804" alt="Lab Banner" src="https://github.com/user-attachments/assets/202a01c9-8011-4874-a4ef-c216077fce7e" />
</div>

## Introduction

In this lab, you will explore a **business logic vulnerability** caused by **inadequate server-side input validation**. The application does not properly enforce pricing constraints during the purchase workflow, allowing an attacker to manipulate item prices and complete transactions at significantly reduced costs.

Your objective is to exploit this flaw to **purchase a "Lightweight l33t leather jacket"** for an unintended price.

---

## Credentials

Use the following credentials to log in:

Username: 
```
wiener
```
Password: 
```
peter
```
Login with the credentials.

---

## Learning Objectives

By completing this lab, you will:

- Understand how improper input validation can lead to logic flaws in purchase flows.
- Practice intercepting and modifying request parameters using a proxy tool (e.g., Burp Suite).
- Learn how business logic vulnerabilities can be exploited even when standard security measures (HTTPS, authentication) are in place.

> **Note**: This lab simulates a real-world vulnerability observed in production environments. It is intended strictly for educational purposes.

---

## Lab Walkthrough

### Step 1: Access the Lab

Click **Access the Lab**. The landing page will appear.

Click on **View Details** for the first item (the leather jacket).

<div align="center">
  <img width="1196" alt="View Jacket" src="https://github.com/user-attachments/assets/2a98b10d-e8d4-4bfe-8127-7b3aadbd5f31" />
</div>

---

### Step 2: Enable Proxy Interception

Open **Burp Suite**, go to the **Proxy** tab, and turn **Intercept** to **ON**.

<div align="center">
  <img src="https://github.com/user-attachments/assets/785ce9d9-9cb2-4cff-90cf-f31dacdc836b"/>
</div>

---

### Step 3: Intercept Add-to-Cart Request

Go back to the browser, scroll down, and click **Add to Cart**.

This triggers a `POST` request that Burp Suite will capture.

<div align="center">
  <img src="https://github.com/user-attachments/assets/53f4f7dd-a83c-42bb-9e17-2699b85e00bf" />
</div>

---

### Step 4: Modify the Request

In Burp Suite, locate the intercepted `POST` request. Modify the parameters such as `quantity` and `price` to reflect an unrealistic or reduced value.

Original Request:

<div align="center">
  <img src="https://github.com/user-attachments/assets/a605a9ec-c91d-49d5-bbdc-a9e0f68ad3a6" />
</div>

Modified Request Example:

<div align="center">
  <img src="https://github.com/user-attachments/assets/8b4e8dc7-4820-4bb0-aac8-cd3440f9c100" />
</div>

---

### Step 5: Forward the Request

Forward the modified request in Burp Suite and return to the browser.

Check that the item has been added to the cart with the manipulated price.

<div align="center">
  <img src="https://github.com/user-attachments/assets/cac9bbdc-d9d0-48d8-abb9-aa99984343d4" />
</div>

---

### Step 6: Complete the Purchase

Click on the **Cart**, then proceed to **Place Order**.

<div align="center">
  <img src="https://github.com/user-attachments/assets/13630f4d-d6ef-40ed-a12e-a2bbf61300d0" />
</div>

You should see a confirmation message indicating the purchase was successful at the modified price.

<div align="center">
  <img src="https://github.com/user-attachments/assets/c0d9d638-ac5f-461d-a5af-064fe9fd0eea" />
</div>

---

## Conclusion

This lab demonstrates how a seemingly minor oversight in server-side validation can result in a critical business logic flaw. Always ensure that sensitive operations, such as pricing and quantity validation, are enforced on the server, not just the client.
