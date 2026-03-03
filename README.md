# practices

This repository contains org-level software engineering practices for RMI. It defines shared principles, process expectations, architecture guidance, security expectations, and reusable templates.

## What Lives Here
- Organization-wide standards and guidance that apply across repositories.
- Shared templates and reference documents.
- Cross-cutting expectations for maintainers and contributors.

## What Lives in Each Product Repository
- Product-specific architecture and ADRs.
- Product-specific runbooks and operational procedures.
- Product-specific issue triage labels, release cadence, and local workflow exceptions.
- Product-specific onboarding, setup, and contribution details.

## How To Adopt (Maintainer Checklist)
1. Review [Documentation Index](INDEX.md) and identify docs relevant to your repository.
2. Align repository settings with [Pull Requests](process/pull_request.md) guidance (protected branch, required checks, reviewer expectations).
3. Align commit and branching behavior with [Git](process/git.md).
4. Establish and communicate your repository’s versioning and release approach using [Software Versioning](process/version.md).
5. If your team is starting new work, use the [PRD Template](templates/prd_template.md).
6. Document any approved deviations from org-level guidance in your repository `README`.

## Table of Contents
- [Documentation Index](INDEX.md)

### Principles
- [Repository Maintainer Guidelines](principles/maintainer.md)

### Process
- [Git](process/git.md)
- [Pull Requests](process/pull_request.md)
- [Software Versioning](process/version.md)

### Architecture
- API design principles (planned)
- Testing philosophy (planned)
- Observability guidance (planned)

### Security
- Secrets handling (planned)
- Vulnerability disclosure expectations (planned)

### Templates
- [PRD Template](templates/prd_template.md)

### Meta
- Maturity model (planned)
- Glossary (planned)

## Compatibility Notes
Legacy root paths (`git.md`, `pull_request.md`, `maintainer.md`, `version.md`, `prd_template.md`) are preserved as compatibility links to their new locations.

## Related Resources
- [Resources](https://rmi-pacta.github.io/resources/)
