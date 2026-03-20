# 🚀 SDET Learning Repo: Module 2 (Core Testing Skills)

> Complete hands-on repository for Test Case Design, API Testing, and Automation using Java + RestAssured.

---

# 📁 Project Structure

```
sdet-module-2/
│
├── README.md
├── test-cases/
│   ├── login_test_cases.md
│   ├── search_test_cases.md
│   └── cart_test_cases.md
│
├── api-tests/
│   ├── postman_collection.json
│   ├── curl_examples.sh
│   └── sample_requests.md
│
├── automation/
│   ├── pom.xml
│   └── src/
│       └── test/java/
│           └── api/
│               └── LoginTest.java
│
└── docs/
    └── test_plan.md
```

---

# 🧪 Sample Test Cases (Login)

```md
Test Case ID: TC_LOGIN_001
Description: Verify login with valid credentials
Steps:
1. Enter valid email
2. Enter password
3. Click login
Expected: Login successful
```

---

# 🔌 API Testing Examples

## cURL Example

```bash
curl -X POST https://reqres.in/api/login \
-H "Content-Type: application/json" \
-d '{"email":"eve.holt@reqres.in","password":"cityslicka"}'
```

---

## Postman JSON Snippet

```json
{
  "info": {
    "name": "Sample API"
  },
  "item": [
    {
      "name": "Login API",
      "request": {
        "method": "POST",
        "url": "https://reqres.in/api/login"
      }
    }
  ]
}
```

---

# 🤖 Automation Setup (Java + RestAssured)

## pom.xml

```xml
<project>
  <dependencies>
    <dependency>
      <groupId>io.rest-assured</groupId>
      <artifactId>rest-assured</artifactId>
      <version>5.3.0</version>
    </dependency>

    <dependency>
      <groupId>org.testng</groupId>
      <artifactId>testng</artifactId>
      <version>7.8.0</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
</project>
```

---

## LoginTest.java

```java
import io.restassured.RestAssured;
import io.restassured.response.Response;
import org.testng.Assert;
import org.testng.annotations.Test;

public class LoginTest {

    @Test
    public void testLoginAPI() {

        String requestBody = "{ \"email\": \"eve.holt@reqres.in\", \"password\": \"cityslicka\" }";

        Response response = RestAssured
                .given()
                .header("Content-Type", "application/json")
                .body(requestBody)
                .post("https://reqres.in/api/login");

        System.out.println(response.getBody().asString());

        Assert.assertEquals(response.getStatusCode(), 200);
        Assert.assertTrue(response.getBody().asString().contains("token"));
    }
}
```

---

# 📋 Test Plan (Sample)

```md
Project: Ecommerce App

Scope:
- Login
- Search
- Cart
- API Validation

Tools:
- Postman
- RestAssured

Entry Criteria:
- Build deployed

Exit Criteria:
- All critical bugs fixed
```

---

# 🎯 How to Use This Repo

1. Clone repo
2. Run API tests via Postman or curl
3. Execute automation via Maven

```bash
mvn test
```

---

# 🧑‍🏫 Trainer Notes (For You - Ayush)

Use this repo to:

* Teach manual → API → automation flow
* Give assignments from test-cases folder
* Run live coding sessions with RestAssured

---

# 🔥 Next Level Upgrade

* Add Selenium UI Automation
* Integrate CI/CD (GitHub Actions)
* Add reporting (Allure)

---

⭐ Star this repo if helpful!

---

# 🌐 UI Automation (Selenium + Page Object Model)

## 📁 Structure Addition

```
automation/
 └── src/test/java/ui/
     ├── pages/
     │   └── LoginPage.java
     └── tests/
         └── LoginUITest.java
```

---

## 🔹 LoginPage.java

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;

public class LoginPage {

    WebDriver driver;

    By email = By.id("email");
    By password = By.id("password");
    By loginBtn = By.id("login");

    public LoginPage(WebDriver driver) {
        this.driver = driver;
    }

    public void login(String user, String pass) {
        driver.findElement(email).sendKeys(user);
        driver.findElement(password).sendKeys(pass);
        driver.findElement(loginBtn).click();
    }
}
```

---

## 🔹 LoginUITest.java

```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;

public class LoginUITest {

    @Test
    public void testLoginUI() {
        WebDriver driver = new ChromeDriver();
        driver.get("https://example.com/login");

        LoginPage loginPage = new LoginPage(driver);
        loginPage.login("test@example.com", "123456");

        driver.quit();
    }
}
```

---

# ⚙️ CI/CD with GitHub Actions

## 📁 .github/workflows/test.yml

```yaml
name: Run Tests

on:
  push:
    branches: [ "main" ]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3

    - name: Set up Java
      uses: actions/setup-java@v3
      with:
        distribution: 'temurin'
        java-version: '17'

    - name: Run Tests
      run: mvn test
```

---

# 📊 Allure Reporting Setup

## 🔹 Add Dependency

```xml
<dependency>
  <groupId>io.qameta.allure</groupId>
  <artifactId>allure-testng</artifactId>
  <version>2.24.0</version>
</dependency>
```

---

## 🔹 Generate Report

```bash
mvn clean test
allure serve
```

---
