# Phase 0 — Zero Trust (Lab Insight)

## Core Lesson

A valid token is not automatically trusted.

## What must be verified

* `iss` → trusted issuer
* `aud` → correct API
* `exp` / `nbf` → validity window
* roles/scopes → authorization

## Implicit Trust Found

The API originally trusted any bearer token without verifying context.

## Fix

Validate full JWT context on every request.

## Extra Hardening

Use token binding / DPoP to reduce replay risk.
