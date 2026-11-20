
# AutoLoc Security Notes

## Authentication
Authentication verifies the identity of a user.

Spring Security uses HTTP Basic Authentication
for this classroom exercise.

## Authorization
Authorization determines what an authenticated
user is allowed to access.

## Access Rules
- /api/public/** is available to everyone.
- /api/** requires USER or ADMIN.
- /api/admin/** requires ADMIN.

The specific ADMIN rule must come before the
broader /api/** rule because request matching
uses the first matching authorization rule.

## HTTP Status Codes
- 200: Request successful.
- 401: Authentication is missing or invalid.
- 403: User is authenticated but lacks permission.

## Password Encoding
BCrypt hashes passwords so they are not stored
as readable plaintext.

## In-Memory Users
In-memory users are suitable for classroom
demonstrations but not production applications.

Production applications should use persistent
user accounts, secure credential management,
and appropriate access controls.

## Database Authentication
A production design would require user and role
entities, database repositories, a UserDetailsService
implementation, and secure password handling.
