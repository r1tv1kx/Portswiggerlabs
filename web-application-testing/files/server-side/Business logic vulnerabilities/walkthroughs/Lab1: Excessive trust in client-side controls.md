<div align='center'>
  <img width="804" alt="Screenshot 2025-06-02 at 12 37 12 PM" src="https://github.com/user-attachments/assets/202a01c9-8011-4874-a4ef-c216077fce7e" />
</div>

## Introduction

In this lab, you'll explore a **business logic vulnerability** that stems from **inadequate server-side input validation**. The application fails to properly enforce pricing constraints during the purchase workflow, allowing an attacker to manipulate item prices and complete a transaction at a significantly reduced cost.

Your goal is to exploit this flaw to **purchase a "Lightweight l33t leather jacket"** for an unintended price.

---

## Credentials

You can log in to your user account using the following credentials:

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

- Understand how improper input validation can lead to logic flaws in purchase flows
- Practice manipulating request parameters using an intercepting proxy (e.g., Burp Suite)
- Learn how business logic flaws can be exploited even when standard security controls (e.g., HTTPS, authentication) are in place

---

> **Note:** This lab simulates a real-world vulnerability observed in production systems and is intended for educational purposes.

## Accessing the Lab
### Step 1:

Click on access the lab.

Below is the screen which will appear. Here, click on view details of the first article which is leather jacket.
<div align='center'>
  <img width="1196" alt="Screenshot 2025-06-02 at 12 55 45 PM" src="https://github.com/user-attachments/assets/2a98b10d-e8d4-4bfe-8127-7b3aadbd5f31" />
</div>

### Step 2:

Open burpsuite and click on proxy and turn intercept to on.
<div align='center'>
  <img src="https://github.com/user-attachments/assets/785ce9d9-9cb2-4cff-90cf-f31dacdc836b"/>
</div>

### Step 3:

Go back to the browser and scroll down. Click on the add to cart button and open buerpsuite to capture the post request for add to cart click.
<div align='center'>
  <img src="https://github.com/user-attachments/assets/53f4f7dd-a83c-42bb-9e17-2699b85e00bf">
</div>

Here we got the post request.

### Step 4:

Now we will modify the request.

![image](https://github.com/user-attachments/assets/a605a9ec-c91d-49d5-bbdc-a9e0f68ad3a6)

In this we will modify quantity and price variable.
Below is the modified values(you can modify as per you choice also).
![image](https://github.com/user-attachments/assets/8b4e8dc7-4820-4bb0-aac8-cd3440f9c100)

### Step 5:
Now we will forward this request and check the browser.

![image](https://github.com/user-attachments/assets/cac9bbdc-d9d0-48d8-abb9-aa99984343d4)

### Step 6:

Now we will click on cart and place the order.

![image](https://github.com/user-attachments/assets/13630f4d-d6ef-40ed-a12e-a2bbf61300d0)

We successfully completed the lab!!
![image](https://github.com/user-attachments/assets/c0d9d638-ac5f-461d-a5af-064fe9fd0eea)


