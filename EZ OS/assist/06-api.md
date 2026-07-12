# English Zone OS

# API Standards

Version: 1.0

Status: Official

Owner: English Zone Academy

Last Updated: July 2026

---

# Purpose

This document defines the official API standards for English Zone OS.

Every API endpoint must follow these standards.

Consistency is more important than personal preference.

---

# API Architecture

Style

REST API

Data Format

JSON

Encoding

UTF-8

Protocol

HTTPS Only

Authentication

Laravel Sanctum

Versioning

/api/v1/

Future

/api/v2/

---

# API Design Principles

Simple

Consistent

Predictable

Secure

Versioned

Scalable

Documented

---

# Base URL

Development

/api/v1

Production

/api/v1

---

# Authentication

Protected endpoints require authentication.

Authentication Method

Bearer Token

Example

Authorization

Bearer YOUR_ACCESS_TOKEN

---

# HTTP Methods

GET

Retrieve Data

POST

Create Data

PUT

Replace Resource

PATCH

Update Resource

DELETE

Delete Resource

---

# Standard Success Response

```json
{
  "success": true,
  "message": "Operation completed successfully.",
  "data": {},
  "meta": {}
}
```

---

# Standard Error Response

```json
{
  "success": false,
  "message": "Validation failed.",
  "errors": {
      "email": [
          "The email field is required."
      ]
  }
}
```

---

# Pagination Response

```json
{
  "success": true,
  "message": "Students retrieved successfully.",
  "data": [],
  "pagination": {
      "current_page": 1,
      "per_page": 20,
      "total": 250,
      "last_page": 13
  }
}
```

---

# HTTP Status Codes

200

OK

201

Created

204

No Content

400

Bad Request

401

Unauthorized

403

Forbidden

404

Not Found

409

Conflict

422

Validation Error

429

Too Many Requests

500

Internal Server Error

503

Service Unavailable

---

# Validation

Every request must be validated.

Validation happens before business logic.

Invalid requests must never reach Services.

---

# Filtering

Supported Format

GET

/students?status=active

/students?branch=dokki

/students?teacher=15

---

# Sorting

Supported Format

/students?sort=name

/students?sort=-created_at

Minus means Descending.

---

# Searching

Supported Format

/students?search=Ahmed

Global Search should support

Name

Email

Phone

Student Code

---

# Pagination

Default

20 Items

Allowed

10

20

50

100

Maximum

100

---

# Relationships

Support Include Parameter

Example

/students?include=group

/students?include=teacher

/students?include=attendance

---

# Date Format

ISO 8601

Example

2026-07-12T18:30:00Z

---

# File Upload

Multipart Form Data

Allowed

Images

PDF

Word

Excel

Audio

Video

Maximum Size

Configured from Settings

---

# Authentication Rules

Unauthenticated Users

401

Unauthorized

Inactive Users

403

Forbidden

Blocked Users

403

Forbidden

Expired Token

401

Unauthorized

---

# Authorization

Every endpoint checks permissions.

Example

students.view

students.create

students.update

students.delete

---

# API Naming

Plural Resources

/students

/teachers

/groups

/homeworks

Never

/getStudents

/createStudent

---

# API Versioning

Current

v1

Future

v2

Older versions remain supported during migration.

---

# Error Messages

Readable

Clear

Consistent

Never expose internal system information.

---

# Logging

Every important request should be logged.

Login

Logout

Password Reset

Homework Submission

Exam Submission

Certificate Download

Role Change

Settings Update

---

# Security

HTTPS Only

Rate Limiting

Token Authentication

Input Validation

Output Sanitization

Audit Logs

File Validation

CSRF Protection (Web)

---

# Rate Limiting

Authentication

5 Requests / Minute

Public APIs

60 Requests / Minute

Authenticated APIs

120 Requests / Minute

---

# API Documentation

Every endpoint must contain

Purpose

Method

Authentication

Permissions

Parameters

Validation

Example Request

Example Response

Possible Errors

---

# Performance

Pagination Required

Avoid N+1 Queries

Cache Static Data

Compress Responses

Lazy Loading

Optimized SQL

---

# Future Support

GraphQL

Webhook API

CRM API

Public API

Partner API

AI API

---

# Golden Rules

Every endpoint must:

Be documented.

Be authenticated when required.

Validate input.

Return consistent responses.

Respect permissions.

Handle errors gracefully.

Never expose sensitive information.

---

END OF DOCUMENT