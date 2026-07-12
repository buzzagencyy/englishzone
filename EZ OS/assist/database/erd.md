# English Zone OS

# Database ERD

Version: 1.0

Status: Planning

Owner: English Zone Academy

Last Updated: July 2026

---

# Purpose

This document defines the relationships between all database entities.

The goal is to ensure a consistent, scalable and normalized database design.

This document complements database/schema.md.

---

# Authentication Module

Role

↓

hasMany

Users

---

Role

↓

belongsToMany

Permissions

---

Permission

↓

belongsToMany

Roles

---

User

↓

hasOne

Student

OR

Teacher

OR

Administrator

---

User

↓

hasMany

Notifications

Devices

Login History

Sessions

---

# Academy Module

Branch

↓

hasMany

Teachers

Students

Groups

Classrooms

Announcements

---

Classroom

↓

belongsTo

Branch

---

# Student Module

Student

↓

belongsTo

User

---

Student

↓

belongsTo

Branch

---

Student

↓

belongsTo

Course

---

Student

↓

belongsTo

Level

---

Student

↓

belongsTo

Group

---

Student

↓

hasMany

Attendance Records

Homework Submissions

Assignment Submissions

Exam Results

Certificates

Notifications

Progress Records

---

Student

↓

belongsToMany

Guardians

---

# Teacher Module

Teacher

↓

belongsTo

User

---

Teacher

↓

belongsTo

Branch

---

Teacher

↓

belongsToMany

Courses

---

Teacher

↓

belongsToMany

Groups

---

Teacher

↓

hasMany

Classes

Homework

Assignments

Exams

Announcements

Reports

---

# Course Module

Course

↓

hasMany

Levels

Groups

Materials

Teachers

Students

---

Level

↓

belongsTo

Course

---

Level

↓

hasMany

Groups

Placement Tests

---

# Group Module

Group

↓

belongsTo

Course

---

Group

↓

belongsTo

Level

---

Group

↓

belongsTo

Teacher

---

Group

↓

belongsTo

Branch

---

Group

↓

hasMany

Students

Classes

Announcements

Homework

Assignments

Exams

---

# Class Module

Class

↓

belongsTo

Group

Teacher

Classroom

Zoom Meeting

---

Class

↓

hasMany

Attendance Records

Class Notes

Files

Recordings

---

# Attendance Module

Attendance Record

↓

belongsTo

Student

Class

Teacher

---

# Homework Module

Homework

↓

belongsTo

Teacher

Group

Class

---

Homework

↓

hasMany

Homework Submissions

Homework Files

Homework Feedback

---

Homework Submission

↓

belongsTo

Homework

Student

---

# Assignment Module

Assignment

↓

belongsTo

Teacher

Group

---

Assignment

↓

hasMany

Assignment Submissions

---

Assignment Submission

↓

belongsTo

Assignment

Student

---

# Exam Module

Exam

↓

belongsTo

Teacher

Group

---

Exam

↓

hasMany

Questions

Results

Statistics

---

Exam Question

↓

belongsTo

Exam

---

Exam Result

↓

belongsTo

Exam

Student

---

# Placement Test

Placement Test

↓

hasMany

Questions

Results

---

Placement Result

↓

belongsTo

Student

---

# Certificate Module

Certificate

↓

belongsTo

Student

Course

Level

---

Certificate

↓

hasMany

Verification Logs

---

# Notification Module

Notification

↓

belongsTo

User

---

Notification

↓

uses

Email

Push

WhatsApp

SMS (Future)

---

# Files Module

File

↓

belongsTo

Homework

Assignment

Class

Student

Teacher

Certificate

---

# Reports Module

Report

↓

belongsTo

User

---

Report

↓

uses

Analytics

Attendance

Homework

Exam

Student Progress

Teacher Performance

---

# AI Module

AI Conversation

↓

belongsTo

User

---

AI Conversation

↓

hasMany

Messages

---

AI Recommendation

↓

belongsTo

Student

Teacher

Administration

---

# CRM (Future)

Lead

↓

mayBecome

Student

---

Lead

↓

belongsTo

Campaign

---

Deal

↓

belongsTo

Lead

Sales Representative

---

# Payments (Future)

Payment

↓

belongsTo

Student

---

Invoice

↓

belongsTo

Student

---

Transaction

↓

belongsTo

Payment

---

# Global Rules

Every User belongs to one Role.

Every Student has one User.

Every Teacher has one User.

Every Group belongs to one Course.

Every Group belongs to one Level.

Every Group has one Teacher.

Every Student belongs to one Group.

Every Class belongs to one Group.

Every Attendance Record belongs to one Student and one Class.

Every Homework belongs to one Teacher and one Group.

Every Exam belongs to one Group.

Every Certificate belongs to one Student.

Every Notification belongs to one User.

---

# Database Principles

No orphan records.

Foreign keys required.

Soft Deletes enabled where appropriate.

Transactions required for critical operations.

Audit logs for sensitive actions.

---

# End of Document