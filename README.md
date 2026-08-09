# Entra ID IAM Lab

## Overview
A simulated Identity and Access Management (IAM) environment built in Microsoft Entra ID, modeling a small organization to demonstrate core IAM practices: least-privilege access design, the Joiner-Mover-Leaver (JML) lifecycle, and verification of security control effectiveness — not just configuration.

## Scenario
A fictional 5-person company with distinct departments (HR, IT, Finance, Marketing, Operations) was modeled to test realistic identity and access scenarios.

| User | Job Title | Department |
|---|---|---|
| Bob Mitchel | HR Manager | HR |
| Mark Chen | IT Support Specialist | IT |
| Laura Novak | Finance Analyst | Finance |
| Alica Carter | Marketing Coordinator → Marketing Manager | Marketing |
| Patric Sjoberg | General Employee | Operations |

**Groups:** `IT-Admins`, `Finance-Team`, `All-Employees`

## What This Demonstrates

### 1. Least-Privilege RBAC Design
Roles were assigned based on actual job function, not department or seniority:

| User | Entra Role | Justification |
|---|---|---|
| Bob Mitchel | User Administrator | Manages employee accounts for HR |
| Mark Chen | Helpdesk Administrator | IT support-level tasks only, not Global Admin |
| Laura Novak | Reports Reader | Read-only visibility for Finance |
| Alica Carter | None → Finance-Team member | No admin need; gained cross-functional access after promotion |
| Patric Sjoberg | None (standard user) | No admin need |

### 2. Joiner-Mover-Leaver (JML) Lifecycle
- **Joiner** — Created 5 users with role-appropriate job titles, departments, and least-privilege RBAC roles.
- **Mover** — Promoted Alica Carter from Marketing Coordinator to Marketing Manager, added her to the Finance-Team group to reflect new cross-functional access needs, and reviewed her existing permissions.
- **Leaver** — Offboarded Mark Chen: removed group memberships and role assignments, revoked active sessions, and disabled his account.

### 3. Control-Effectiveness Testing
Enabled Security Defaults (MFA enforcement) and tested it live rather than assuming it worked because the setting was "on."

**Key Finding:** Initial sign-in logs showed `Result: Not Applied` despite Security Defaults being enabled — caused by the 14-day MFA registration grace period. Resolved by enabling per-user MFA, then re-verified via sign-in logs that enforcement was active (user correctly blocked pending MFA registration).

This reflects a real audit distinction: **a control being configured is not the same as a control being enforced.** Verifying via logs rather than trusting the settings page is a core control-testing practice in IT audit and IAM work.

## Tools Used
Microsoft Entra ID, Azure Portal, Entra Admin Center

## Author
Bugra Ayten
