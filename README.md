# FestPass Docker and Container Security Assessment

Name: Sameer Kumar Singh

REGNO: 202401100100220

PORT: 8020

Docker Hub username: sameer8765

Docker Hub repository: https://hub.docker.com/r/sameer8765/fest-backend

## Application

The frontend serves the supplied registration page using Nginx. Requests under /api/ go to the Flask backend. Only the backend shares the database network with PostgreSQL. PostgreSQL data is stored in a named volume, so `docker compose down` does not remove registrations.

Create .env using .env.example and a private database password. Run `docker compose up -d --wait`, then open the configured localhost port. Use `docker compose down` to stop the stack while keeping the database volume.

The source files are transcribed from the assessment starter code. PDF line wrapping is normalized without changing application behavior.

## Scan comparison

The following totals combine the operating-system and Python targets in the complete saved reports. The separate gate checks only fixable CRITICAL vulnerabilities.

| Image | CRITICAL (all) | HIGH (all) | Image size in bytes |
| --- | --- | --- | --- |
| fest-backend:0.1 | 234 | 2249 | 1607243537 |
| fest-backend:0.2 | 0 | 49 | 200093417 |

Fixable CRITICAL gate exit code for 0.2: 0 (passed). The complete report still contains 49 HIGH findings; the filtered gate does not assert zero vulnerabilities at all severities.

## Published release and signatures

1.0.0 pushed digest: sha256:b4b5c1b4158cb21746ce44bda9a0f838786f87b7fdf349fa89a966ee31429ab1.

1.0 and 1.0.0 point to the same release. The backend APP_VERSION is baked into the release using a build argument and image environment setting. After removing local backend images, Compose pulled 1.0.0 from Docker Hub. The API confirmed version 1.0.0, the correct REGNO, database connectivity and both original registrations.

1.0.0 digest signature verification: passed with cosign.pub, exit code 0. The cosign claims, transparency-log inclusion and public-key signature were verified.

Unsigned 1.0.1 verification: rejected with "no signatures found", exit code 10. Version 1.0.1 was built with APP_VERSION=1.0.1, pushed separately, and left unsigned. Version 1.0.0 remains deployed.

Only cosign.pub belongs in this repository. cosign.key, .env and credentials must remain private and absent from all commits.

## Evidence

Evidence screenshots are stored under screenshots/. Required evidence codes: S1-2, S1-3, S2-2, S2-3, S2-4, S3-1, S3-3, S4-1, S4-2, S4-3, S5-1, S5-2, S5-3 and S5-4. Every terminal screenshot must show the real REGNO prompt and command. Browser evidence must show the address bar and required account identity.
