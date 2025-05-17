# 📫 API Testing with Postman & Newman

This folder contains all necessary files to run **Postman API tests** using the **Newman CLI**, including environment and collection files.

---

## 📁 Structure

```
Postman/
├── DummyJSON_collection.json       # Postman API requests and test scripts
├── DummyJSON_environment.json      # Environment variables (e.g., base URL, auth tokens)
└── README.md                       # You're here!
```

---

## 🔁 How to Run Postman Collection using Newman

Make sure you have Node.js installed. Then install Newman globally:

```bash
npm install -g newman
```

### Run the Collection:

```bash
newman run DummyJSON_collection.json   -e DummyJSON_environment.json   -r cli,json,html
```

- `-e` specifies the environment file.
- `-r` specifies the reporters: `cli`, `json`, and `html`.

---

## 📊 Reporting

You can generate different types of reports:

- **CLI output**: View results in terminal
- **HTML report** (if configured with `newman-reporter-html`)
- **JSON report** for integration/log analysis

Install the HTML reporter (optional):

```bash
npm install -g newman-reporter-html
```

---

## 🧪 Test Assertions

Assertions inside Postman are written using JavaScript under the "Tests" tab for each request. Examples:

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains userId", function () {
    pm.response.to.have.jsonBody("userId");
});
```

---

## 🔄 CI/CD Integration

This collection can be run in:
- **Jenkins** using a shell/batch step
- **GitHub Actions** using Postman CLI
- **GitLab CI** pipelines for automated testing

---

## ✍️ Author

Ahmed Magdy  

Software Testing Engineer

Happy Testing! 🚀
