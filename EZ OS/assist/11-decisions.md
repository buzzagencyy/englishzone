# English Zone OS

# Architecture Decision Log (ADL)

Version: 1.0

Status: Active

Owner: English Zone Academy

Last Updated: July 2026

---

# Purpose

This document records every important technical and business decision made during the project.

Every major decision must include:

- Context
- Decision
- Reason
- Alternatives
- Consequences

Never change a major architectural decision without documenting it here.

---

# Decision Format

Decision ID

Date

Status

Context

Decision

Reason

Alternatives

Consequences

Owner

---

# ADR-001

Title

Use Flutter as the Frontend Framework

Status

Accepted

Context

The platform must support Android, iOS and Web.

Decision

Flutter will be used for all frontend applications.

Reason

Single codebase.

Excellent performance.

Native experience.

Large ecosystem.

Fast development.

Alternatives

React Native

Native Android

Native iOS

Consequences

Lower maintenance cost.

Unified UI.

Shared business logic.

---

# ADR-002

Title

Use Laravel as Backend

Status

Accepted

Context

The backend must support rapid development while remaining scalable.

Decision

Laravel 12.

Reason

Mature ecosystem.

Excellent authentication.

Queues.

Notifications.

Events.

Strong community.

Alternatives

NestJS

ASP.NET

Spring Boot

Consequences

Faster development.

Easy maintenance.

Excellent API support.

---

# ADR-003

Title

Use PostgreSQL

Status

Accepted

Context

The platform requires a reliable relational database.

Decision

PostgreSQL.

Reason

ACID.

Performance.

JSON Support.

Scalability.

Laravel compatibility.

Alternatives

MySQL

MariaDB

MongoDB

Consequences

Reliable data consistency.

Future-ready architecture.

---

# ADR-004

Title

Use Riverpod

Status

Accepted

Context

Flutter requires scalable state management.

Decision

Riverpod.

Reason

Modern.

Simple.

Scalable.

Compile-time safety.

Alternatives

Bloc

Provider

GetX

Consequences

Cleaner architecture.

Better testing.

---

# ADR-005

Title

Use REST API

Status

Accepted

Context

Frontend communicates with backend.

Decision

REST API.

Reason

Simple.

Standard.

Easy documentation.

Excellent tooling.

Alternatives

GraphQL

gRPC

Consequences

Fast development.

Easy maintenance.

---

# ADR-006

Title

Authentication Strategy

Status

Accepted

Decision

Laravel Sanctum.

Reason

Secure.

Simple.

Mobile Friendly.

SPA Friendly.

---

# ADR-007

Title

Notification Service

Status

Accepted

Decision

Firebase Cloud Messaging.

Reason

Reliable.

Cross-platform.

Free.

---

# ADR-008

Title

Automation Platform

Status

Accepted

Decision

n8n

Reason

Open Source.

Powerful.

Self Hosted.

Easy Integration.

---

# ADR-009

Title

Video Platform

Status

Accepted

Decision

Zoom API

Reason

Widely used.

Reliable.

Easy Integration.

---

# ADR-010

Title

Object Storage

Status

Accepted

Decision

Cloudflare R2

Reason

Low Cost.

S3 Compatible.

Scalable.

---

# ADR-011

Title

Email Provider

Status

Accepted

Decision

Resend

Reason

Modern API.

Reliable Delivery.

Developer Friendly.

---

# ADR-012

Title

Repository Structure

Status

Accepted

Decision

Monorepo

Reason

Frontend and Backend maintained together.

Shared documentation.

Single versioning.

---

# ADR-013

Title

Architecture Style

Status

Accepted

Decision

Modular Clean Architecture.

Reason

Scalable.

Maintainable.

Easy Testing.

Reusable.

---

# ADR-014

Title

Documentation First

Status

Accepted

Decision

No feature starts before documentation.

Reason

Reduce mistakes.

Improve planning.

Improve AI accuracy.

---

# ADR-015

Title

Feature Development Order

Status

Accepted

Decision

Documentation

↓

Database

↓

API

↓

Backend

↓

Frontend

↓

Testing

↓

Deployment

Reason

Reduces rework.

Keeps architecture stable.

---

# Pending Decisions

The following decisions are intentionally postponed.

CRM Vendor

Payment Gateway

SMS Provider

AI Provider

Speech Recognition

Calendar Integration

Video Recording Storage

Enterprise Features

---

# Rejected Decisions

Every rejected decision should be documented here.

Reason for rejection.

Date.

Alternative.

Current Status.

---

# Review Policy

Review this document before every major release.

Never remove historical decisions.

If a decision changes,

mark the previous one as

Superseded

and create a new record.

---

# Golden Rules

Every important decision must be documented.

Never rely on memory.

Architecture decisions should remain transparent for every future developer and AI assistant.

---

END OF DOCUMENT