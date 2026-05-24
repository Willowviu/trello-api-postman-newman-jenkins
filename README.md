# Trello API Testing with Postman, Newman and Jenkins

This project demonstrates an automated API testing workflow using **Postman**, **Newman** and **Jenkins**.

The goal is to validate several Trello API endpoints through a Postman collection and execute the tests from the command line and through a Jenkins pipeline.

---

## Tech Stack

- Postman
- Newman
- Jenkins
- JavaScript assertions
- Trello REST API
- Git & GitHub
- CI/CD basics

---

## Project Structure

```text
trello-api-postman-newman-jenkins/
│
├── collections/
│   └── trello-api.postman_collection.json
│
├── Jenkinsfile
├── package.json
├── package-lock.json
├── README.md
└── .gitignore
```

---

## What This Project Covers

This project includes API tests for common Trello workflows such as:

- Getting Trello boards
- Creating a board
- Creating lists
- Creating a card
- Moving a card between lists
- Deleting or closing Trello resources
- Validating status codes
- Validating response body data

---

## Variables

The collection uses Postman variables to avoid exposing sensitive data.

Example variables:

```text
baseUrl
trelloKey
trelloToken
boardId
todoListId
doneListId
cardId
boardNumber
```

Sensitive values such as the Trello API key and token are **not included** in this repository.

---

## How to Run Locally

Install dependencies:

```bash
npm install
```

Run the tests:

```bash
npm test
```

This command executes:

```bash
newman run collections/trello-api.postman_collection.json
```

---

## Generate HTML Report

```bash
npm run test:report
```

The report will be generated in:

```text
reports/newman-report.html
```

---

## Jenkins Pipeline

This project includes a `Jenkinsfile` to run the API tests automatically in Jenkins.

Pipeline steps:

1. Install project dependencies.
2. Run the Postman collection with Newman.
3. Display the pipeline result.

---

## Security Note

This repository does not include real API keys, tokens, passwords or secrets.

The Trello API key and token should be stored securely and never committed to version control.

---

## Key Learning Outcomes

Through this project, I practiced:

- Creating and organizing Postman collections
- Writing API test assertions
- Using collection variables
- Running API tests with Newman
- Creating a Jenkins pipeline
- Preparing a GitHub repository for a QA Automation portfolio

---

## Author

**Fran de Miguel**  
Junior QA Automation Engineer  
Focus: Selenium · Java · API Testing · Postman · Newman · Jenkins · CI/CD
