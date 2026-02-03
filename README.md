# 🚀 GitHub CI Pipeline – Build & Test

## 📌 Project Overview

This project demonstrates a **basic Continuous Integration (CI) pipeline** using **GitHub Actions** for a Node.js application. The pipeline automatically runs tests whenever code is pushed to the repository or a pull request is created.

The goal of this project is to understand **CI fundamentals**, **YAML-based pipelines**, and how automated testing helps catch errors early in the development lifecycle.

---

## 🛠 Tools & Technologies Used

* **GitHub Actions** – CI pipeline automation
* **Node.js** – Runtime environment
* **JavaScript** – Application logic
* **Git & GitHub** – Version control and collaboration

---

## 📂 Project Structure

```
.github/
 └── workflows/
     └── ci.yml        # GitHub Actions CI pipeline
math.js                # Application source code
test.js                # Test file
README.md              # Project documentation
```

---

## 🧩 Application Description

The project contains a simple JavaScript function that performs addition. A test file validates the correctness of this function.

### ➕ math.js

```js
function add(a, b) {
  return a + b;
}

module.exports = add;
```

### 🧪 test.js

```js
const add = require('./math');

if (add(2, 3) !== 5) {
  throw new Error('Test failed ❌');
}

console.log('Test passed ✅');
```

---

## ⚙️ CI Pipeline Configuration

The CI pipeline is defined using a YAML file inside `.github/workflows/ci.yml`.

### 📄 ci.yml

```yaml
name: Node.js CI Pipeline

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build-and-test:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v4

    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '20'

    - name: Run tests
      run: node test.js
```

---

## 🔄 CI Workflow Execution

1. Developer pushes code to the `main` branch
2. GitHub Actions workflow is triggered automatically
3. A fresh Ubuntu runner is provisioned
4. Node.js is installed
5. Tests are executed using `node test.js`
6. Pipeline passes or fails based on test results

---

## ✅ Expected Results

* **Pass**: If all tests succeed, the pipeline completes successfully
* **Fail**: If any test fails, the pipeline stops and reports an error

This ensures that faulty code is not merged or deployed.

---

## 🧪 Local Setup & Testing

### Prerequisites

* Node.js installed
* Git installed

### Steps to Run Locally

```bash
node test.js
```

---

## 🎯 Key Learnings

* Understanding CI (Continuous Integration) concepts
* Writing GitHub Actions workflows using YAML
* Automating test execution on every code change
* Identifying and fixing build failures early

---

## 📈 Use Case in DevOps

This project reflects real-world DevOps practices where:

* CI pipelines validate code quality
* Automation reduces manual errors
* Teams ensure reliable and consistent builds
---

## ✨ Author

**Abhi Pal**
Cloud & DevOps Enthusiast

---

⭐ If you find this project useful, give it a star on GitHub!
