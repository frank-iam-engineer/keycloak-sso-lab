# Keycloak SSO Lab

## Overview
This project demonstrates Single Sign-On (SSO) implementation using Keycloak as an Identity Provider (IdP).

It focuses on how users authenticate once and gain access to applications using identity tokens instead of repeated logins.

---

## Objectives
- Set up Keycloak as an Identity Provider
- Create and manage users, roles, and realms
- Configure a client application
- Demonstrate login using SSO
- Inspect and understand identity tokens (OIDC)
- Analyze security risks in SSO systems

---

## Architecture

User (Frank_IAM)
        ↓
   Keycloak (IdP)
        ↓
   Client Application

---

## Components

### Keycloak
Identity Provider responsible for:
- Authentication
- Token issuance
- Role management

### Realm
A security domain that contains:
- Users
- Roles
- Clients

### User
- Frank_IAM
- Assigned roles for access control

### Roles
- Define what a user can access

### Client
- Represents an application
- Uses OIDC for authentication

---

## Login Flow

1. User accesses application
2. Application redirects user to Keycloak
3. User logs in via Keycloak
4. Keycloak issues an access token
5. Application validates token
6. User gains access

---

## Token Breakdown

Keycloak issues tokens such as:

- Access Token
- ID Token
- Refresh Token

These tokens contain:
- User identity
- Roles (claims)
- Expiration time

---

## Security Insights

### 1. Token-Based Authentication
Applications trust tokens instead of passwords.

### 2. Centralized Authentication Risk
If the Identity Provider is compromised, all connected applications are affected.

### 3. Token Leakage Risk
Stolen tokens can be reused within their validity period.

### 4. Role-Based Access Control
Access is determined by roles embedded in tokens.

---

## Lessons Learned
- SSO improves usability but increases central risk
- Tokens replace passwords in modern systems
- Identity Providers are critical security components
- Proper role assignment is essential for least privilege

---

## Status
In Progress
