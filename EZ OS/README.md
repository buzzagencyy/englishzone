# 🚀 English Zone OS

The complete digital operating system for English Zone Academy.

---

# Overview

English Zone OS is a modern Education Operating System designed to manage every aspect of English Zone Academy.

This project combines

- Public Website
- Student Portal
- Teacher Portal
- Administration Dashboard
- Super Admin Dashboard
- Android Application
- iOS Application

inside one unified platform.

This is not just an LMS.

It is a complete academy operating system.

---

# Features

## Authentication

- Login
- Forgot Password
- Role Management
- Session Management

---

## Student Portal

- Dashboard
- Schedule
- Attendance
- Homework
- Assignments
- Exams
- Materials
- AI Practice
- Certificates
- Notifications
- Profile

---

## Teacher Portal

- Dashboard
- Attendance
- Homework
- Assignments
- Exams
- Reports
- Student Progress
- Learning Materials

---

## Administration

- Student Management
- Teacher Management
- Branches
- Courses
- Levels
- Groups
- Scheduling
- Placement Tests
- Certificates
- Reports
- Notifications
- Settings

---

## Future Modules

- CRM
- Finance
- HR
- Marketing
- Parent Portal
- Payments
- Gamification
- AI Assistant
- Business Intelligence

---

# Tech Stack

## Frontend

Flutter

## Backend

Laravel

## Database

PostgreSQL

## Cache

Redis

## Storage

Cloudflare R2

## Authentication

Laravel Sanctum

## Notifications

Firebase Cloud Messaging

## Automation

n8n

## Meetings

Zoom API

---

# Project Structure

```
EZ OS/

assist/
branding/
database/
specs/
assets/

backend/
frontend/

CLAUDE.md
README.md
```

---

# Documentation

Project documentation lives inside

```
assist/
```

Important documents

```
00-project.md

01-plan.md

02-tech-stack.md

03-rules.md

04-roadmap.md

05-database.md

06-api.md

07-ui-ux.md

08-integrations.md

10-backlog.md

11-decisions.md
```

Database

```
database/

schema.md

erd.md
```

Specifications

```
specs/

learner-portal.md

teacher-portal.md

admin-dashboard.md

website.md
```

Branding

```
branding/

english-zone.md

design-system.md
```

---

# Development Order

Phase 1

Planning

↓

Architecture

↓

Database

↓

Backend

↓

Frontend

↓

Testing

↓

Deployment

---

# Development Principles

Documentation First

Architecture First

Security First

Performance First

Automation First

Mobile First

AI Ready

---

# Coding Standards

- Clean Architecture
- SOLID
- DRY
- KISS
- Feature First
- Repository Pattern
- Service Layer

---

# Branch Strategy

main

Production

develop

Development

feature/*

Features

fix/*

Bug Fixes

hotfix/*

Production Fixes

---

# Main Modules

Authentication

Website

Student Portal

Teacher Portal

Administration Dashboard

Courses

Levels

Groups

Attendance

Homework

Assignments

Exams

Placement Test

Certificates

Notifications

Reports

AI

---

# Assets

Brand assets should be stored inside

```
assets/

branding/

icons/

fonts/

illustrations/

images/

animations/

videos/
```

---

# Running the Project

Backend

```
cd backend

composer install

cp .env.example .env

php artisan key:generate

php artisan migrate

php artisan serve
```

Frontend

```
cd frontend

flutter pub get

flutter run
```

---

# Environment

Development

Docker

Production

Linux

Nginx

PHP

PostgreSQL

Redis

Cloudflare

---

# Goals

Build the best English learning platform in the Middle East.

Deliver premium learning experiences.

Automate academy operations.

Support future growth.

Build scalable software.

---

# License

Private Project

Copyright © English Zone Academy

All Rights Reserved.