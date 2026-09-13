# Campus 360 — Event-Driven Academic Management Platform

A full-stack academic management platform built with Django and Django REST Framework, designed with role-based access control, JWT authentication, REST APIs, and an event-driven AWS architecture.

Campus 360 provides separate dashboards and permissions for faculty and students while using AWS services to handle asynchronous exam-notification workflows.

---

## Overview

Campus 360 is an academic management platform that centralizes student, faculty, course, attendance, marks, and examination-related operations.

The platform implements role-based access control where:

- Faculty members can create and manage academic information.
- Students have controlled read-only access to their academic information.
- JWT authentication secures REST API access.
- AWS S3 provides cloud-based object storage.
- Amazon EventBridge detects exam scheduling events.
- AWS Lambda processes event-driven operations.
- Amazon SNS handles notification delivery.
- Docker provides containerized application deployment.
- GitHub Actions supports CI/CD automation.

The project focuses on applying backend engineering, REST API development, cloud integration, event-driven architecture, authentication, and containerization in a single production-oriented application.

---

## Key Features

### Authentication & Authorization

- User authentication using Django authentication.
- JWT-based API authentication.
- Role-based access control.
- Separate student and faculty workflows.
- Permission-based access to academic resources.
- Protected API endpoints.

### Student Dashboard

Students can:

- View academic information.
- View enrolled courses.
- View attendance information.
- View examination information.
- View marks and academic results.
- Access information according to their assigned permissions.

Students do not have administrative modification privileges.

### Faculty Dashboard

Faculty members can:

- Manage academic information.
- Manage courses.
- Manage student-related academic records.
- Manage attendance.
- Manage marks.
- Schedule examinations.
- Trigger the examination notification workflow.

### Event-Driven Exam Notification

When a faculty member schedules an examination, the application can initiate an event-driven notification workflow.

```text
Faculty
   |
   v
Django Application
   |
   v
Exam Scheduled Event
   |
   v
Amazon EventBridge
   |
   v
AWS Lambda
   |
   v
Amazon SNS
   |
   v
Student Email Notification
