# English Zone OS

# Technology Stack

Version: 1.0

Status: Official

---

# Purpose

This document defines the official technologies used in the project.

No technology should be changed without updating this document.

Every developer and AI assistant must follow this stack.

---

# Architecture

Frontend

Flutter

Backend

Laravel 12

Database

PostgreSQL

Cache

Redis

Storage

Cloudflare R2

Queue

Laravel Queue + Redis

API

REST API

Authentication

Laravel Sanctum

Deployment

Docker

Version Control

Git + GitHub

Automation

n8n

Notifications

Firebase Cloud Messaging (FCM)

Video Meetings

Zoom API

Emails

Resend

Analytics

Firebase Analytics

---

# Frontend Stack

Framework

Flutter Stable

Language

Dart

State Management

Riverpod

Navigation

Go Router

HTTP Client

Dio

Local Storage

Hive

Secure Storage

flutter_secure_storage

Dependency Injection

Riverpod

Charts

fl_chart

Animations

Lottie

Image Cache

cached_network_image

---

# Backend Stack

Framework

Laravel 12

Language

PHP 8.4+

Authentication

Sanctum

Authorization

Policies + Gates

ORM

Eloquent ORM

Queue

Redis Queue

Scheduler

Laravel Scheduler

API Resources

Laravel API Resources

Validation

Form Requests

Mail

Resend

Storage

Cloudflare R2

---

# Database

Engine

PostgreSQL

Requirements

- Relational Database
- Foreign Keys
- Transactions
- Soft Deletes
- UUID Support
- Full Text Search Ready

---

# Cache

Redis

Used For

Sessions

Queues

Rate Limiting

Application Cache

Temporary Data

---

# File Storage

Cloudflare R2

Stores

Images

Videos

Documents

Homework Files

Assignments

Certificates

---

# Authentication

Email Login

Forgot Password

Reset Password

Remember Me

Future

Google Login

Apple Login

Passkeys

Two Factor Authentication

---

# Notifications

Firebase Cloud Messaging

Supports

Android

iOS

Web

Notification Types

Homework

Exams

Classes

Announcements

Certificates

Marketing

---

# WhatsApp

Automation Platform

n8n

Future

Official WhatsApp Business API

---

# Zoom

Zoom REST API

Functions

Create Meeting

Join Meeting

Meeting Reminder

Attendance Synchronization

---

# Email

Provider

Resend

Templates

Welcome

Password Reset

Homework

Exam

Certificate

Announcements

Marketing

---

# API Standards

RESTful

JSON Responses

Versioned

/api/v1

Future

/api/v2

---

# API Response Format

Success

```json
{
  "success": true,
  "message": "Operation completed successfully.",
  "data": {}
}
```

Error

```json
{
  "success": false,
  "message": "Validation failed.",
  "errors": {}
}
```

---

# Development Environment

Visual Studio Code

Claude Code

GitHub

Docker Desktop

Postman

TablePlus

Figma

---

# Git Strategy

Main

Production

Develop

Development

Feature/*

New Features

Fix/*

Bug Fixes

Release/*

Release Preparation

Hotfix/*

Emergency Fixes

---

# CI/CD

GitHub Actions

Automatic Testing

Automatic Build

Automatic Deployment

---

# Coding Standards

PSR Standards

SOLID Principles

DRY

KISS

Repository Pattern

Service Layer

DTO Pattern

Clean Architecture

---

# Flutter Standards

Feature First Structure

Reusable Widgets

Responsive Design

Dark Mode Ready

Localization Ready

No Hardcoded Strings

No Hardcoded Colors

---

# Laravel Standards

Controllers remain thin.

Business logic belongs to Services.

Database access belongs to Repositories.

Validation belongs to Form Requests.

Authorization belongs to Policies.

Events should trigger notifications.

Heavy tasks should run in Queues.

---

# Performance Targets

Application Startup

< 2 Seconds

API Response

< 300 ms

Database Queries

Optimized

Lazy Loading

Enabled

Caching

Enabled

---

# Security

HTTPS Only

Encrypted Passwords

Environment Variables

Rate Limiting

CSRF Protection

Audit Logs

Role Based Authorization

Input Validation

Secure File Upload

---

# Monitoring

Laravel Telescope

Firebase Crashlytics

Application Logs

Database Monitoring

Future

Sentry

Grafana

Prometheus

---

# Future Integrations

CRM

Payment Gateway

AI Services

Google Calendar

Microsoft Teams

Google Meet

SMS Gateway

Voice AI

---

# Golden Rules

Never introduce a new package unless necessary.

Prefer official libraries.

Keep dependencies updated.

Avoid abandoned packages.

Every technical decision must prioritize scalability, security and maintainability.

---

END OF DOCUMENT