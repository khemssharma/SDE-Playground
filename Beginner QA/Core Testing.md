# 📘 Module 2: Core Testing Skills

> A practical guide to mastering test case design, defect management, and API testing fundamentals.

---

## 📌 Table of Contents

* [Day 1: Test Case Fundamentals](#-day-1-test-case-fundamentals)
* [Day 2: Test Design Techniques](#-day-2-test-design-techniques)
* [Day 3: Defect Management](#-day-3-defect-management)
* [Day 4: API Testing](#-day-4-api-testing)
* [Final Deliverable](#-final-deliverable)

---

# 🗓️ Day 1: Test Case Fundamentals

## 🔹 What is a Test Case?

A **test case** is a set of steps, inputs, and expected results used to validate a feature.

## 🔹 Test Scenario vs Test Case

| Test Scenario          | Test Case                        |
| ---------------------- | -------------------------------- |
| High-level             | Detailed                         |
| What to test           | How to test                      |
| Example: Login feature | Example: Enter valid credentials |

---

## 🔹 Structure of a Test Case

```md
Test Case ID: TC_LOGIN_001
Description: Verify login with valid credentials
Preconditions: User is registered
Steps:
  1. Open login page
  2. Enter username & password
  3. Click login
Expected Result: User should be logged in successfully
```

---

## ✍️ Writing Effective Test Cases

✅ Best Practices:

* Clear and concise
* Well-defined steps
* Expected results included
* Reusable & maintainable

---

## 😊 Happy Path Testing

```text
Flow:
Login → Add Product → Checkout
```

```md
TC_LOGIN
TC_ADD_PRODUCT
TC_CHECKOUT
```

---

## 🧪 Practice Exercise

Create:

* 5 Login test cases
* 5 Search test cases
* 5 Cart test cases

---

# 🗓️ Day 2: Test Design Techniques

## ⚠️ Risk-Based Testing

Focus on high-impact areas first.

```text
High Risk Areas:
- Payment systems
- Login/Auth
- Checkout flow
```

---

## 📊 Decision Table Testing

```md
| Condition | Action |
|----------|--------|
| Valid User | Allow Login |
| Invalid User | Show Error |
| Empty Fields | Show Validation |
```

---

## 🔍 Exploratory Testing

* No predefined steps
* Learn + Test simultaneously

---

## 📂 Test Data Strategy

```json
{
  "validUser": "test@example.com",
  "invalidUser": "",
  "edgeCase": "a@a.com"
}
```

---

## 📏 Boundary Value Analysis (BVA)

```text
Range: 1–100

Test Values:
0, 1, 2, 99, 100, 101
```

---

## 🚫 Negative Testing

```md
Test Case: Empty Login
Input: username="", password=""
Expected: Error message displayed
```

---

## 📦 Equivalence Partitioning

```text
Age Input:
<18     → Invalid
18–60   → Valid
>60     → Invalid
```

---

# 🗓️ Day 3: Defect Management

## 🐞 Bug Lifecycle

```text
New → Assigned → Open → Fixed → Retest → Closed
```

---

## 📝 Bug Report Template

```md
Title: Login button not working

Description:
Login button does not respond on click.

Steps to Reproduce:
1. Open login page
2. Enter valid credentials
3. Click login

Expected Result:
User logs in successfully

Actual Result:
Nothing happens

Severity: High
Priority: High
```

---

## ⚖️ Severity vs Priority

| Severity | Priority |
| -------- | -------- |
| Impact   | Urgency  |

Example:

```text
Login failure → High Severity + High Priority
```

---

## 🔍 Root Cause Analysis

### ✅ 5 Whys Example

```text
Problem: Login failed

Why 1 → Incorrect password
Why 2 → User forgot password
Why 3 → No reset option
Why 4 → Email service missing
Why 5 → Feature not implemented
```

---

### 🐟 Fishbone Diagram Categories

```text
- People
- Process
- Technology
- Environment
```

---

# 🗓️ Day 4: API Testing

## 🔌 What is API Testing?

Testing communication between systems using APIs.

---

## 🛠️ Tools

* Postman
* Swagger

---

## 🔄 API Request Example

```http
POST /api/login HTTP/1.1
Host: example.com
Content-Type: application/json

{
  "email": "test@example.com",
  "password": "123456"
}
```

---

## 📥 API Response Example

```json
{
  "status": 200,
  "message": "Login successful",
  "token": "abc123xyz"
}
```

---

## 🌐 HTTP Methods

```text
GET     → Fetch data
POST    → Create data
PUT     → Update data
DELETE  → Delete data
```

---

## 📡 Status Codes

```text
200 → Success
400 → Bad Request
401 → Unauthorized
404 → Not Found
500 → Server Error
```

---

## 🔐 Authentication Example (JWT)

```http
GET /api/user/profile
Authorization: Bearer abc123xyz
```

---

## 🧪 Postman Test Script Example

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response has token", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.token).to.exist;
});
```

---

# 🎯 Final Deliverable

## ✅ You Should Be Able To:

* Create a Test Plan
* Write effective test cases
* Perform UI + API testing
* Report and track defects

---

## 🚀 Bonus (For Developers/SDET Path)

```bash
# Sample API test using curl
curl -X POST https://api.example.com/login \
-H "Content-Type: application/json" \
-d '{"email":"test@example.com","password":"123456"}'
```

---

# 📌 Author Notes

This module is designed for **beginners to intermediate testers** aiming to transition into **SDET / QA Automation roles**.

---

⭐ *If this helped you, consider starring the repo!*
