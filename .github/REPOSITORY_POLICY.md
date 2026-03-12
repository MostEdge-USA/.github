# Repository Governance Policy

## Purpose

This document establishes the governance, security, and operational standards for repositories within this organization.
The goal is to ensure consistent development practices, protect organizational assets, and maintain secure and scalable software development workflows.

All repositories and contributors must adhere to the standards outlined in this policy.

---

# Repository Ownership

Every repository must have an **owning team** responsible for:

* code maintenance
* security compliance
* dependency management
* operational stability
* documentation

Ownership must be assigned through **GitHub teams**, not individual users.

Example:

```
Repository: smartbooks-ui
Owner: smartbooks
```

Platform or shared repositories may be owned by the **platform engineering team**.

---

# Repository Creation

Repository creation must follow standardized naming and governance rules.

### Naming Standard

Repositories must follow the format:

```
product-application-stack
```

Examples:

```
sava-ui
sava-api
sava-backend
smartbooks-ui
smartbooks-api
identity-backend
```

### Naming Definitions

| Segment     | Meaning             |
| ----------- | ------------------- |
| product     | product or domain   |
| application | application/service |
| stack       | technology type     |

Allowed stack suffixes:

```
-ui
-api
-backend
-app
```

Repositories should **not exceed three segments**.

---

# Access Management

Access must follow the **principle of least privilege**.

### Access Guidelines

* Access should be granted through **GitHub teams**
* Direct user repository permissions should be avoided
* Administrative privileges must be limited
* Repository access must be reviewed periodically

Example structure:

```
Team: developers → read access
Team: platform → maintain
Team: product-team → write
```

---

# Branch Protection

Critical branches must be protected using organization rules.

Protected branches include:

```
main
development
release/*
```

Branch protection should enforce:

* pull request required before merge
* minimum review approvals
* required CI status checks
* restriction of force pushes
* prevention of branch deletion

---

# Pull Request Requirements

All code changes must be submitted through **pull requests**.

Pull requests must include:

* a clear description of the change
* context or related issue references
* successful CI validation
* approval from authorized reviewers

Direct commits to protected branches are prohibited.

---

# Security Requirements

Repositories must comply with secure development practices.

### Secret Management

The following must **never be committed** to repositories:

* API keys
* tokens
* private credentials
* certificates
* passwords
* `.env` files containing secrets

Instead:

* use **GitHub Secrets**
* use external secret management systems
* rotate credentials immediately if exposed

---

### Security Controls

The organization may enforce the following controls:

* secret scanning
* push protection
* dependency vulnerability scanning
* automated security checks
* code review enforcement

Security incidents must be reported immediately through internal channels.

---

# CI/CD and Automation

Repositories should integrate with standardized CI/CD pipelines.

Recommended practices include:

* automated builds and testing
* dependency scanning
* artifact versioning
* automated deployment pipelines
* infrastructure validation

Shared CI workflows may be provided by **platform repositories**.

---

# Platform Repositories

Shared platform repositories may include:

```
platform-github-workflows
platform-repository-template
platform-kube-config
platform-kube-templates
platform-devops-tools
```

These repositories provide:

* reusable CI/CD workflows
* repository templates
* infrastructure automation
* shared development tooling

Platform repositories are maintained by the **platform engineering team**.

---

# Repository Lifecycle

Repositories may transition through the following lifecycle stages:

| Stage       | Description               |
| ----------- | ------------------------- |
| Active      | actively maintained       |
| Maintenance | limited development       |
| Deprecated  | scheduled for replacement |
| Archived    | no longer maintained      |

Archived repositories must be marked read-only.

---

# Compliance

All repository activity must comply with:

* internal security policies
* applicable legal requirements
* intellectual property protections
* organizational governance standards

---

# Policy Enforcement

Violations of this policy may result in:

* removal of repository access
* revocation of privileges
* required remediation actions
* escalation through internal governance processes

---

# Policy Updates

This policy may be updated periodically to reflect evolving organizational practices, technology standards, and security requirements.

Contributors are expected to remain aware of and follow the current policy.
