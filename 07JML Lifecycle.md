## What I did
Simulated the full Joiner-Mover-Leaver (JML) identity lifecycle in Microsoft Entra ID:
- **Joiner**: Created 5 users with role-appropriate job titles, departments, and least-privilege RBAC roles.
- **Mover**: Promoted Alica Carter to Marketing Manager and added her to the Finance-Team group to reflect new cross-functional access needs, after reviewing her existing permissions.
- **Leaver**: Offboarded Mark Chen by removing his group memberships and role assignments, revoking active sessions, and disabling his account.

## Screenshots
**Joiner- User Creation**
1. Created 5 users and assigned them
![screenshot](./images/Pasted%20image%2020260809081858.png)

**Mover- Alica Carter from Marketing Coordinator to Marketing Manager**

1. Changed her job title
 ![screenshot](./images/Pasted%20image%2020260809092823.png)
Coordinator to Manager
![screenshot](./images/Pasted%20image%2020260809092858.png)

2. Assigned her to Finance Team security group
![screenshot](./images/Pasted%20image%2020260809094011.png)

**Leaver- Offboarded Mark Chen**
1. Removed his group memberships and role assignments
![screenshot](./images/Pasted%20image%2020260809094947.png)

![screenshot](./images/Pasted%20image%2020260809095014.png)

2. Disabled his account
![screenshot](./images/Pasted%20image%2020260809094811.png)

![screenshot](./images/Pasted%20image%2020260809094905.png)

3. Revoked all his sessions
![screenshot](./images/Pasted%20image%2020260809094725.png)

## Why it matters
JML is a core IAM lifecycle model used to manage access as employees join, change roles, and leave an organization. Properly executing the Leaver stage — removing all access, not just disabling login — is critical: incomplete offboarding is one of the most common findings in real access audits, since leftover permissions on inactive accounts represent significant security risk.