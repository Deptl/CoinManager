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