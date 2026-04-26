# Phase 1 — LDAP Nested Group Privilege Escalation

## Observation
LDAP supports nested group membership.

## Attack
Bob was added to the lower-privileged `ops` group.

Because `ops` is a member of `admins`, Bob inherited admin access indirectly.

## Impact
A user can gain admin privileges without being directly added to the admin group.

## Fix
- Restrict who can modify group membership
- Audit all group changes
- Monitor nested groups
- Avoid nesting sensitive admin groups

## Result
Privilege escalation confirmed via group nesting.
