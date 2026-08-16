# Security Policy

## Reporting a security issue

Report suspected vulnerabilities privately through the repository's configured security reporting mechanism, such as its private vulnerability reporting feature or the security contact published by maintainers. If no private channel is configured, contact project maintainers through the repository's authenticated administration or support process and request a private security review.

Include enough information to reproduce and assess the issue: affected component or version, impact, reproduction steps or proof of concept, relevant logs, and suggested mitigation. Remove secrets, credentials, personal data, and unrelated private information.

**Do not disclose vulnerabilities publicly, open a public issue, or publish proof-of-concept details before maintainers have reviewed the report and coordinated disclosure.**

## Responsible disclosure

Report issues in good faith and allow reasonable time to investigate, validate, develop a fix, and coordinate release or disclosure. Do not access, alter, retain, or exfiltrate data that does not belong to you; stop testing after demonstrating the issue. Do not use a vulnerability to disrupt services, degrade availability, extort, harass, or threaten others.

Maintainers will acknowledge reports when possible, evaluate severity and affected scope, coordinate remediation, and communicate next steps through the private reporting channel. Disclosure timing and credit, when appropriate, should be agreed with maintainers and must not expose users to avoidable risk.

## Security scope

The security scope includes vulnerabilities in maintained source code, repository configuration, published artifacts, documented contribution and governance workflows, and supported interfaces operated as part of this project. Explain how the issue affects users, contributors, maintainers, or the integrity of governance records.

Out-of-scope examples include third-party services or dependencies not controlled by this project, unsupported versions, social engineering, denial-of-service testing against shared infrastructure, and findings requiring already-compromised credentials. Report them when they create material project risk and explain the connection.

## Security practices for contributors

- Never commit secrets, credentials, private keys, tokens, or sensitive personal data.
- Use redacted examples and sanitized Evidence Artifact references.
- Do not bypass required review, provenance, traceability, or Human approval gates for security-sensitive changes.
- Follow the contribution process for fixes and document relevant validation without revealing exploitable details.
