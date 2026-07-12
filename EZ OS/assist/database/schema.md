# English Zone OS

# Database Schema

Version: 1.0

Status: Draft

Owner: English Zone Academy

Last Updated: July 2026

---

# Overview

This document defines the complete database schema for English Zone OS.

Every table, relationship and business entity must be documented here before implementation.

This document is the single source of truth for:

- Laravel Models
- Migrations
- Relationships
- Foreign Keys
- Indexes
- Constraints

---

# Database Engine

PostgreSQL

Character Set

UTF-8

Timezone

UTC

Soft Deletes

Enabled

UUID

Enabled

Audit Logs

Enabled

---

# Database Modules

Authentication

Academy

Students

Teachers

Courses

Levels

Groups

Classes

Attendance

Homework

Assignments

Exams

Placement Tests

Certificates

Notifications

Files

Reports

Settings

AI

CRM (Future)

Payments (Future)

Marketing (Future)

---

# Table Naming Convention

Plural

snake_case

Examples

users

students

teachers

courses

groups

classes

attendance_records

homework_submissions

---

# Standard Columns

Every business table should contain

id

uuid

created_at

updated_at

deleted_at

created_by

updated_by

status

---

# Status Values

active

inactive

pending

completed

cancelled

blocked

archived

---

# Relationship Standards

One To One

One To Many

Many To Many

All relationships use Foreign Keys.

No orphan records.

---

# ==========================
# AUTHENTICATION
# ==========================

Tables

users

roles

permissions

role_user

permission_role

personal_access_tokens

password_reset_tokens

sessions

login_history

devices

---

# ==========================
# ACADEMY
# ==========================

Tables

branches

classrooms

holidays

announcements

settings

academic_terms

---

# ==========================
# STUDENTS
# ==========================

Tables

students

student_profiles

student_guardians

student_documents

student_notes

student_tags

student_histories

student_status_logs

student_progress

---

# ==========================
# TEACHERS
# ==========================

Tables

teachers

teacher_profiles

teacher_documents

teacher_notes

teacher_specializations

teacher_availability

teacher_histories

teacher_attendance

---

# ==========================
# COURSES
# ==========================

Tables

courses

course_categories

course_levels

course_packages

course_materials

course_prices

---

# ==========================
# LEVELS
# ==========================

Tables

levels

level_requirements

placement_tests

placement_questions

placement_answers

placement_results

---

# ==========================
# GROUPS
# ==========================

Tables

groups

group_students

group_teachers

group_schedules

group_announcements

---

# ==========================
# CLASSES
# ==========================

Tables

classes

class_files

class_notes

class_recordings

zoom_meetings

---

# ==========================
# ATTENDANCE
# ==========================

Tables

attendance_records

attendance_logs

---

# ==========================
# HOMEWORK
# ==========================

Tables

homeworks

homework_files

homework_submissions

homework_feedback

homework_grades

---

# ==========================
# ASSIGNMENTS
# ==========================

Tables

assignments

assignment_files

assignment_submissions

assignment_feedback

assignment_grades

---

# ==========================
# EXAMS
# ==========================

Tables

exam_categories

exams

exam_sections

exam_questions

exam_options

student_exam_answers

exam_results

exam_statistics

---

# ==========================
# CERTIFICATES
# ==========================

Tables

certificates

certificate_templates

certificate_logs

certificate_verification

---

# ==========================
# NOTIFICATIONS
# ==========================

Tables

notifications

notification_templates

notification_logs

push_tokens

notification_preferences

---

# ==========================
# FILES
# ==========================

Tables

files

folders

attachments

media

---

# ==========================
# REPORTS
# ==========================

Tables

reports

report_exports

dashboard_widgets

analytics_events

audit_logs

activity_logs

---

# ==========================
# SETTINGS
# ==========================

Tables

system_settings

email_settings

zoom_settings

whatsapp_settings

notification_settings

branding_settings

security_settings

---

# ==========================
# AI
# ==========================

Tables

ai_conversations

ai_messages

ai_usage

ai_feedback

ai_recommendations

prompt_history

---

# ==========================
# FUTURE MODULES
# ==========================

CRM

crm_contacts

crm_leads

crm_tasks

crm_notes

crm_logs

---

Payments

payments

payment_methods

transactions

invoices

invoice_items

refunds

---

Marketing

campaigns

landing_pages

forms

marketing_emails

marketing_whatsapp

---

# Estimated Tables

Core Tables

≈ 75

Junction Tables

≈ 25

Future Tables

≈ 35

Estimated Total

120+ Tables

---

# Development Rules

No table should be implemented before documentation.

Every new table must be added here.

Every schema change must update this document.

---

# Next Step

The next document

database/erd.md

will define every relationship between these tables.

After completing the ERD,

each table will be documented individually with:

Purpose

Columns

Relationships

Indexes

Constraints

Business Rules

Validation Rules

---

# =====================================================================
# TABLE: users
# =====================================================================

## Description

Stores all authenticated users in the system.

Every person who can log into English Zone OS must have exactly one user account.

This table contains authentication data only.

Business-specific data belongs to Student, Teacher or Administrator tables.

---

## Columns

| Column | Type | Required | Description |
|----------|----------|----------|------------------------------|
| id | BIGINT | Yes | Primary Key |
| uuid | UUID | Yes | Public Identifier |
| role_id | BIGINT | Yes | FK → roles.id |
| first_name | VARCHAR(100) | Yes | First Name |
| last_name | VARCHAR(100) | Yes | Last Name |
| email | VARCHAR(255) | Yes | Login Email |
| phone | VARCHAR(30) | No | Mobile Number |
| password | VARCHAR(255) | Yes | Hashed Password |
| avatar | TEXT | No | Profile Image |
| language | VARCHAR(10) | Yes | Default Language |
| timezone | VARCHAR(100) | Yes | User Timezone |
| last_login_at | TIMESTAMP | No | Last Login |
| email_verified_at | TIMESTAMP | No | Verification Date |
| remember_token | VARCHAR(255) | No | Remember Token |
| status | ENUM | Yes | User Status |
| created_at | TIMESTAMP | Yes | Creation Date |
| updated_at | TIMESTAMP | Yes | Last Update |
| deleted_at | TIMESTAMP | No | Soft Delete |

---

## Status Values

active

inactive

blocked

pending

archived

---

## Relationships

belongsTo

Role

---

hasOne

Student

Teacher

Administrator

---

hasMany

Notifications

Sessions

Devices

Activity Logs

Audit Logs

---

## Indexes

PRIMARY(id)

UNIQUE(email)

INDEX(phone)

INDEX(uuid)

INDEX(role_id)

INDEX(status)

---

## Validation Rules

Email must be unique.

Password must be hashed.

Role is required.

Status defaults to Active.

---

## Business Rules

One email = One account.

Deleted users cannot login.

Blocked users cannot access APIs.

Only active users may authenticate.

Passwords are never stored as plain text.

---

## Future Fields

Google ID

Apple ID

Microsoft ID

Two Factor Secret

Passkey Identifier

Biometric Enabled

Preferred Theme

Preferred Notification Settings

---

# =====================================================================
# TABLE: roles
# =====================================================================

## Description

Stores all system roles.

Roles define the highest permission level assigned to a user.

---

## Default Roles

Super Admin

Administration

Teacher

Student

Parent

Sales

Marketing

Finance

Support

---

## Columns

| Column | Type | Required | Description |
|----------|----------|----------|----------------|
| id | BIGINT | Yes | Primary Key |
| uuid | UUID | Yes | Public ID |
| name | VARCHAR(100) | Yes | Internal Name |
| display_name | VARCHAR(100) | Yes | Display Name |
| description | TEXT | No | Description |
| created_at | TIMESTAMP | Yes | Created At |
| updated_at | TIMESTAMP | Yes | Updated At |

---

## Relationships

hasMany Users

belongsToMany Permissions

---

## Business Rules

Role names must be unique.

Default roles cannot be deleted.

---

# =====================================================================
# TABLE: permissions
# =====================================================================

## Description

Stores all available permissions inside the platform.

Roles receive permissions.

Users inherit permissions from their role.

---

## Columns

| Column | Type | Required | Description |
|----------|----------|----------|----------------|
| id | BIGINT | Yes | Primary Key |
| uuid | UUID | Yes | Public ID |
| module | VARCHAR(100) | Yes | Module Name |
| action | VARCHAR(100) | Yes | Action Name |
| created_at | TIMESTAMP | Yes | Created At |
| updated_at | TIMESTAMP | Yes | Updated At |

---

## Example Permissions

students.view

students.create

students.update

students.delete

teachers.view

teachers.create

courses.view

attendance.mark

homework.grade

reports.export

settings.manage

---

## Relationships

belongsToMany Roles

---

## Business Rules

Permissions cannot be duplicated.

Permission names must follow

module.action

Example

students.create

groups.update

reports.export

notifications.send

---

# =====================================================================
# TABLE: role_user
# =====================================================================

## Purpose

Pivot table connecting users and roles.

(Currently every user has one role, but this allows future multi-role support.)

Columns

user_id

role_id

created_at

---

# =====================================================================
# TABLE: permission_role
# =====================================================================

## Purpose

Maps permissions to roles.

Allows flexible permission management without changing code.

Columns

permission_id

role_id

created_at
