# Phase 2 — Token Abuse & Validation

## Lab Setup

* Keycloak realm: frank-lab
* Two APIs: api-a (port 5000), api-b (port 5001)

---

## Finding 1 — No Audience Validation

### Observation

Both APIs accepted any valid token.

### Attack

Used token with:
"aud": "account"

Accessed both APIs successfully.

### Impact

Cross-API token abuse.

### Fix

Enforced:
audience="api-a" / audience="api-b"

### Result

* api-a accepts only api-a tokens
* api-b rejects them

---

## Finding 2 — Refresh Token Behavior

### Observation

Refresh token rotation enabled.

### Attack

Tried reusing old refresh token.

### Result

Old token invalidated after use.

### Impact

Prevents reuse attacks.

### Remaining Risk

Attacker with latest refresh token can maintain access until expiry.

---

## Finding 3 — Token Expiry

### Observation

Expired access token rejected by API.

### Impact

Prevents infinite token reuse.

---

## Key Takeaway

A valid signature is not enough.

Every API must enforce:

* issuer (iss)
* audience (aud)
* expiry (exp)
* roles/scopes
