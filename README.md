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

## AI tools used

OpenAI Codex was used to read the assessment, transcribe its starter files, prepare Docker/Compose configuration and stage commands, and identify verification requirements. Add any further AI assistance actually used. Assessed commands and screenshots must be produced by the student on their machine.

## Scan comparison

Pending actual execution. Counts must include all targets in each complete report. The gate checks only fixable CRITICAL vulnerabilities; report unfixed findings separately when present.

| Image | CRITICAL (all) | HIGH (all) | Image size in bytes |
| --- | --- | --- | --- |
| fest-backend:0.1 | PENDING | PENDING | PENDING |
| fest-backend:0.2 | PENDING | PENDING | PENDING |

Fixable CRITICAL gate exit code for 0.2: PENDING.

## Published release and signatures

1.0.0 pushed digest: PENDING.

1.0 and 1.0.0 point to the same release. The backend APP_VERSION is baked into the release using a build argument and image environment setting. The compose deployment must pull 1.0.0 from the student's registry.

1.0.0 digest signature verification: PENDING.

Unsigned 1.0.1 digest rejection: PENDING.

Only cosign.pub belongs in this repository. cosign.key, .env and credentials must remain private and absent from all commits.

## Evidence

Save whole-window, unedited screenshots under screenshots/: S1-2, S1-3, S2-2, S2-3, S2-4, S3-1, S3-3, S4-1, S4-2, S4-3, S5-1, S5-2, S5-3 and S5-4. Every terminal screenshot must show the real REGNO prompt and command. Browser evidence must show the address bar and required account identity.

## Incomplete steps

- Execution, scans, registry publication, signing, screenshot capture and submission are pending. Replace this line with actual remaining limitations after running the stages.
