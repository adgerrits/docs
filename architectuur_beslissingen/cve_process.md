# CVE process

## Status

Review.

## Context

Common Vulnerability Exposures ([CVEs](https://cve.mitre.org/)) are faced in images employed by:

- __Cloud provider__: when deploying Kubernetes clusters
- __Cloud broker__: when deploying DevOps tooling and building blocks
- __Cloud consumer__: when building and deploy applications

## Decisions

CVE are the full responsibility of the image employer.

CVEs cannot be managed by a central cloud broker "watchdog", this does not scale.

It is allowed to have images running with CVEs, to avoid sudden termination due to new discovered CVEs.

## Consequences

Namespaces in Test and Production should be well-isolated, to avoid CVE-side effects in multi-tenant clusters.

CVEs should be reviewed and fixed (or documented/whitelisted for auditing purposes) by the image employer. Recommendation: consider at least High or Critical CVEs.

The CVE process should be facilitated:

- When building private images, they should be pushed to a platform registry, in order to scan them upfront on CVEs
- When deploying images, they should be pulled from the platform registry, in order to scan them afterwards on (possibly new discovered) CVEs
