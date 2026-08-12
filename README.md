<img src="https://github.com/Deptl/CoinManager/blob/master/images/coinmanager-github-banner.png" />

# CoinManager - Distributed Microservices Architecture Documentation

## Table of Contents
1. [System Architecture](#system-architecture)
2. [Mobile Application](#mobile-application)
3. [Project Repositories](#project-repositories)
4. [Microservices API Endpoints](#microservices-api-endpoints)
5. [Koig API Gateway & Custom Plugins](#kong-api-gateway--custom-plugins)
6. [Docker Deployment](#docker-deployment)
7. [Technical Specifications](#technical-specifications)

---

## System Architecture

### Overview
CoinManager is a distributed microservices application built with Java Spring Boot that helps you track your daily expenses. It offers unique features such as automatically parsing SMS messages from your bank to add expenses, and an OCR feature that scans receipt images to add expenses as well. The system uses a sophisticated architecture powered by LLMs for SMS parsing, OCR for extracting data from images, Kafka for decoupling services, Kong API Gateway for routing, and a React Native mobile application for the user interface.

### High Level Design


---

## Mobile Application

---

## Project Repositories

### Backend Microservices

1. AuthService: [`Repository`](https://github.com/Deptl/CoinManager-AuthService)
    - User authentication and authorization
    - JWT token generation and validation
    - Access token management
    - User credential verification

2. UserService: [`Repository`](https://github.com/Deptl/CoinManager-UserService)
    - User profile management and Storage
    - Transaction analytics and computations
    - Budget tracking and limiting
    - User preference settings

3. ExpenseService: [`Repository`](https://github.com/Deptl/CoinManager-ExpenseService)
    - Transaction recording and storing
    - Expense categorization and management
    - Transaction history maintenance
    - Real-time transaction procession using kafka

4. MessageService: [`Repository`](https://github.com/Deptl/CoinManager-ExpenseService)
    - Automated SMS parsing
    - Natural Langauge Processing for transaction extraction
    - Integration with external AI services (GROQ API)
    - Machine learning for transaction categorization

### Frontend Mobile Application

5. Mobile Appliction: [`Repository`](https://github.com/Deptl/CoinManager-MobileApp)
    - React Native Mobile Application
    - Cross-Platform technology
    - Light and Dark theme across the application
    - Real-time analytics

---

## Microservices API Endpoints

1. AuthService
    - `POST: /auth/v1/login` - User authentication
    - `POST: /auth/v1/register` - New user registeration
    - `POST: /auth/v1/refresh` - Refresh token mechanism
    - `POST: /auth/v1/logout` - Session termination
    - `GET: /auth/v1/ping` - Health check and token validation

2. UserService
    - `GET: /user/v1/profile` - Get user profile
    - `PUT: /user/v1/profile` - Update user profile
    - `GET: /user/v1/analytics` - Get spending analytics
    - `GET: /user/v1/budget` - Get budget information
    - `POST: /user/v1/budget/set` - Set budget

3. ExpenseService
    - `POST: /expense/v1/add` - Add new transaction
    - `GET: /expense/v1/list` - Get all transactions
    - `PUT: /expense/v1/update/{id}` - Update transaction
    - `DELETE: /expense/v1/delete/{id}` - Delete transaction
    - `GET: /expense/v1/categories` - Get transaction categories

4. MessageService
    - `POST: /v1/ds/parse` - Parse SMS 
    - `GET: /v1/ds/health` - Service health check
    - `POST: /v1/ds/categorize` - Categorize transaction
    - `GET: /v1/ds/stats` - Get processing statistics
