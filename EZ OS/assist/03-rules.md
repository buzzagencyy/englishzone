# English Zone OS

# Project Rules

Version: 1.0

Status: Official

Priority: Highest

---

# Purpose

This document defines the official development rules for English Zone OS.

Every developer, AI assistant and contributor must follow these rules.

These rules take precedence over implementation preferences.

---

# Development Philosophy

Think First.

Plan First.

Document First.

Code Second.

Review Always.

Deploy Last.

Never rush implementation.

---

# Architecture Rules

Always follow Clean Architecture.

Business Logic must never exist inside the UI.

Controllers must remain lightweight.

Services contain business logic.

Repositories communicate with the database.

Policies control permissions.

Models represent data only.

---

# Documentation Rules

Every feature must be documented before development.

Every API must be documented.

Every database change must be documented.

Every important architectural decision must be documented.

---

# Coding Rules

Write readable code.

Prefer clarity over cleverness.

Keep functions short.

Keep files organized.

Never duplicate logic.

Always reuse existing components.

---

# Naming Rules

Variables

camelCase

Classes

PascalCase

Methods

camelCase

Files

snake_case

Folders

snake_case

Database Tables

snake_case

Database Columns

snake_case

Constants

UPPER_CASE

Routes

kebab-case

---

# Flutter Rules

Every feature has its own folder.

Never place business logic inside Widgets.

Create reusable Widgets.

Create reusable Components.

Support Responsive Layout.

Support Dark Mode.

Support Localization.

---

# Laravel Rules

Controllers are thin.

Services contain logic.

Repositories contain queries.

Form Requests contain validation.

Policies contain authorization.

Events trigger notifications.

Jobs handle background work.

Never query the database directly from Controllers.

---

# Database Rules

Always use Migrations.

Never modify production tables manually.

Always use Foreign Keys.

Use Soft Delete whenever possible.

Never duplicate data.

Store files outside the database.

Use UUID for public references.

---

# API Rules

RESTful APIs only.

JSON responses only.

Version every API.

Never break existing endpoints.

Always validate requests.

Always return consistent responses.

---

# Security Rules

Passwords must always be hashed.

Never store secrets in code.

Use Environment Variables.

Validate all user input.

Protect every endpoint.

Enforce Role Based Access Control.

Use HTTPS only.

Log sensitive actions.

---

# UI Rules

Keep interfaces simple.

Avoid unnecessary complexity.

One primary action per screen.

Consistent spacing.

Consistent typography.

Consistent colors.

Consistent navigation.

Accessibility is mandatory.

---

# Performance Rules

Optimize database queries.

Avoid unnecessary rebuilds.

Use caching.

Use lazy loading.

Compress images.

Paginate large datasets.

Background jobs for heavy tasks.

---

# Git Rules

Main branch is always stable.

Never push directly to Main.

Every feature has its own branch.

Every Pull Request must be reviewed.

Write meaningful commit messages.

---

# Testing Rules

Every important feature should be tested.

Business logic must have tests.

Fix bugs before adding new features.

Never release untested code.

---

# Logging Rules

Log important actions.

Examples:

User Login

Password Reset

Homework Submission

Exam Completion

Certificate Generation

Role Changes

Settings Changes

System Errors

---

# AI Rules

Claude Code must:

Read documentation before coding.

Understand the task completely.

Reuse existing code whenever possible.

Never rewrite working code unnecessarily.

Suggest improvements before major refactoring.

Keep architecture consistent.

---

# Feature Rules

Every feature must include:

Business Logic

Validation

Permissions

API

Documentation

Testing

Error Handling

Logging

---

# Definition of Done

A task is complete only if:

Business requirements are satisfied.

Code is clean.

Documentation updated.

Tests pass.

Permissions verified.

Performance acceptable.

Security reviewed.

No critical bugs remain.

---

# Things To Avoid

Hardcoded values.

Duplicate code.

Unused packages.

Unused files.

Magic numbers.

Inline business logic.

Copy & Paste programming.

Large unorganized classes.

Large unorganized widgets.

Breaking existing features.

---

# Decision Making

When multiple solutions exist:

Choose the solution that provides:

Better maintainability.

Better scalability.

Better security.

Better readability.

Better user experience.

---

# Project Standards

The project should always feel like a premium commercial software product.

Not a prototype.

Not an MVP.

Not a university project.

Production quality only.

---

# Final Rule

If any implementation conflicts with this document,

this document wins.

END OF DOCUMENT