# Credit Application System

A full-stack demo application that simulates a simplified banking credit application process.
The system allows users to submit loan applications, calculates affordability based on financial data, and provides a decision (approved, rejected, or manual review).

This project demonstrates backend development with **Java and Spring Boot**, database integration, frontend interaction, and basic automated testing.

---

## Overview

In many banking systems, credit applications require collecting financial data, calculating affordability, and evaluating risk before approving a loan.

This project simulates a simplified version of that process.
Users can submit a credit application through a web interface, and the backend evaluates the application based on basic financial rules.

The goal of this project is to demonstrate full-stack software engineering skills including:

* backend API development
* database modeling
* frontend interaction
* testing and validation
* clean project architecture

---

## Features

* Submit credit applications
* Store applications in a database
* Calculate affordability based on income and expenses
* Basic decision logic (approve / reject / manual review)
* View submitted applications
* REST API for backend services
* Frontend form for non-technical users

---

## Tech Stack

### Backend

* Java
* Spring Boot
* Spring Data JPA / Hibernate
* Gradle

### Frontend

* Vue
* JavaScript
* HTML / CSS

### Database

* PostgreSQL

### Testing

* JUnit
* Mockito

### Tools

* Git
* IntelliJ IDEA
* Docker (optional)

---

## System Architecture

Frontend (Vue) communicates with the backend via REST API.

```
Frontend (Vue)
      |
      v
Spring Boot REST API
      |
      v
Service Layer (business logic)
      |
      v
Repository Layer (JPA/Hibernate)
      |
      v
PostgreSQL Database
```

---

## Example Credit Evaluation Logic

The system calculates a simplified affordability score.

Example rules:

```
disposable_income = income - expenses - existing_loan_payments
debt_ratio = requested_loan_payment / income
```

Decision logic:

* If disposable income < 0 → Reject
* If debt ratio too high → Manual Review
* Otherwise → Approve

These rules are simplified for demonstration purposes.

---

## API Endpoints

### Create Application

POST `/api/applications`

```
{
  "name": "John Doe",
  "email": "john@example.com",
  "monthlyIncome": 3000,
  "monthlyExpenses": 1200,
  "existingLoanPayments": 200,
  "requestedLoanAmount": 10000,
  "loanPeriodMonths": 36
}
```

### Get Application

GET `/api/applications/{id}`

### List Applications

GET `/api/applications`

---

## Running the Project

### Backend

```
./gradlew bootRun
```

### Frontend

```
npm install
npm run dev
```

---

## Future Improvements

* Authentication for admin users
* More advanced credit scoring
* Automated UI testing
* Docker deployment
* CI/CD pipeline
* Better risk models

---

## Project Purpose

This project was built as a portfolio project to demonstrate practical software engineering skills including backend development, database design, API development, and frontend integration.
