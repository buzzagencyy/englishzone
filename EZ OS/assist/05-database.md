# English Zone OS

# Database Architecture

Version: 1.0

Status: Official

Owner: English Zone Academy

Last Updated: July 2026

---

# Purpose

This document defines the database architecture standards for English Zone OS.

It explains how the database should be designed.

It does NOT contain the table definitions.

The actual schema exists in:

database/schema.md

---

# Database Engine

PostgreSQL

Reasons

- Reliable
- Scalable
- Secure
- ACID Compliant
- Excellent Performance
- Excellent Laravel Support

---

# Database Philosophy

The database is the heart of the platform.

Every business operation depends on data consistency.

Database quality directly affects software quality.

The database must prioritize:

- Consistency
- Performance
- Security
- Maintainability
- Scalability

---

# Design Principles

Normalize data whenever possible.

Avoid duplicated data.

Avoid storing calculated values.

Prefer relationships over duplicated columns.

Always use Foreign Keys.

Never create orphan records.

---

# Primary Keys

Every business table uses:

BIGINT

Auto Increment

Example

id

---

# UUID

Every important business entity should also have

uuid

Purpose

Public URLs

API references

External integrations

Future CRM

Future Mobile Sync

UUID must never replace the primary key.

---

# Timestamps

Every business table must include

created_at

updated_at

deleted_at

Soft Delete should be enabled whenever appropriate.

---

# Soft Deletes

Soft Delete is required for:

Students

Teachers

Courses

Groups

Homework

Assignments

Certificates

Files

Reports

Never permanently delete important business data.

---

# Relationships

Every relationship must use Foreign Keys.

Relationship Types

One To One

One To Many

Many To Many

Never leave orphan records.

---

# Transactions

Business operations affecting multiple tables must use Database Transactions.

Examples

Student Registration

Certificate Generation

Exam Submission

Homework Submission

Payments

Enrollment

---

# Index Strategy

Every table should index

Primary Key

UUID

Foreign Keys

Status

Created Date

Updated Date

Email

Phone

Search Fields

Indexes should improve read performance without unnecessary duplication.

---

# File Storage

Files should never be stored inside PostgreSQL.

Store only metadata.

Example

File Name

Storage Path

File Size

Mime Type

Uploaded By

Upload Date

Actual files will be stored in Cloudflare R2.

---

# Audit Strategy

Important actions must be logged.

Examples

User Login

Student Created

Teacher Updated

Homework Submitted

Exam Completed

Certificate Generated

Role Changed

Settings Updated

---

# Security

Passwords are always hashed.

Sensitive values should be encrypted when required.

Never store API Keys.

Never store Secrets.

Never expose internal IDs publicly.

---

# Data Integrity

Every foreign key must be validated.

Required fields should never be nullable unless necessary.

Business constraints must be enforced at database level whenever possible.

---

# Naming Convention

Tables

snake_case

Examples

students

teachers

courses

levels

groups

Columns

snake_case

Examples

first_name

last_name

student_code

created_at

updated_at

Indexes

Descriptive names

Foreign Keys

Consistent naming

---

# Data Types

Use appropriate data types.

Examples

BIGINT

UUID

VARCHAR

TEXT

BOOLEAN

DATE

TIME

TIMESTAMP

JSONB

ENUM

Avoid using TEXT when VARCHAR is sufficient.

---

# Future Compatibility

The database must support future modules without major redesign.

Future modules include

CRM

Payments

Finance

Marketing

Parent Portal

Marketplace

Gamification

AI

Multiple Academies

---

# Backup Strategy

Daily Backup

Weekly Backup

Monthly Archive

Encrypted Storage

Automatic Recovery Testing

---

# Performance Strategy

Optimize Queries

Proper Indexes

Avoid N+1 Queries

Use Pagination

Use Caching

Optimize Relationships

Archive Old Data When Necessary

---

# Migration Rules

Every change must be implemented using Laravel Migrations.

Never modify production tables manually.

Every migration must be reversible.

Rollback must always work correctly.

---

# Seeders

Seeders are only for

Development

Testing

Demo Data

Never use fake data in Production.

---

# Database Quality Checklist

Before creating any new table

✔ Business purpose defined

✔ Relationships defined

✔ Indexes planned

✔ Constraints defined

✔ Foreign Keys defined

✔ Soft Delete evaluated

✔ Audit requirements evaluated

✔ Documentation updated

---

# Golden Rule

The database is the single source of truth.

Every table must be documented before implementation.

Every migration must match the official schema documentation.

No undocumented database change is allowed.

---

END OF DOCUMENT