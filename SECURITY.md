# Security Policy

## Scope

This repository is a static web page (`index.html`, `data.js`) with no backend, accounts or stored user data. Relevant security issues are, for example:

- script injection (XSS) through the data or the page code,
- a link in the data that points to a malicious or hijacked site,
- a compromised third-party script.

For vulnerabilities in FortiAIGate or other Fortinet products, use the [Fortinet PSIRT](https://www.fortiguard.com/psirt) process instead.

## Reporting a vulnerability

Please do not open a public issue. Report privately through GitHub: open the **Security** tab of this repository and choose **Report a vulnerability**.

Include what you found, where (file and line, or the node in the graph) and how to reproduce it. We aim to respond within 7 days.

## Supported versions

Only the current `main` branch, which is what the live page serves.
