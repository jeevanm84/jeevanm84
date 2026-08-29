# Repository standards

These standards keep the portfolio consistent without forcing unrelated technologies into identical directory trees.

## Engineering narrative

Every technical project explains:

```text
Problem
→ Requirements
→ Architecture
→ Design decisions
→ Implementation
→ Testing
→ Deployment
→ Security
→ High availability
→ Scalability
→ Observability
→ Disaster recovery
→ Cost optimization
→ Troubleshooting
→ Cleanup
→ Lessons learned
```

Sections may state that a concern is not applicable, but must not silently ignore important production concerns.

## Baseline structure

```text
repository/
├── README.md
├── docs/
│   ├── END_TO_END_GUIDE.md
│   ├── ARCHITECTURE.md
│   ├── CODE_STRUCTURE.md
│   ├── SECURITY.md
│   ├── COST_AND_CLEANUP.md
│   ├── TROUBLESHOOTING.md
│   ├── INTERVIEW_QUESTIONS.md
│   └── ROADMAP.md
├── labs/
├── examples/
├── scripts/
├── tests/
├── diagrams/
├── .github/
│   ├── workflows/
│   ├── ISSUE_TEMPLATE/
│   ├── CODEOWNERS
│   └── pull_request_template.md
├── CONTRIBUTING.md
├── SECURITY.md
├── CODE_OF_CONDUCT.md
└── LICENSE
```

Only directories with real content are created.

## README contract

The first screen answers:

- What engineering problem does this solve?
- What will the reader build, diagnose, or learn?
- Can it run locally without a cloud account?
- Where is the single end-to-end guide?
- What is the architecture?

The remaining README contains:

1. Outcome and audience
2. Architecture or workflow diagram
3. Learning paths by level
4. Quick local verification
5. Repository map
6. Design decisions and trade-offs
7. Security, cost, and cleanup boundaries
8. Troubleshooting and interview links
9. Roadmap position and next repository
10. Contribution and support guidance

## Lab contract

Every lab includes:

- Objective
- Prerequisites
- Starting state
- Commands or implementation steps
- Expected observations
- Verification
- Failure injection where safe
- Recovery
- Explanation of why the result occurs
- Cleanup
- Extension exercises

Destructive commands operate only on explicitly created lab targets or temporary directories.

## Incident contract

Troubleshooting scenarios use:

```text
Incident → Symptoms → Impact → Investigation → Metrics → Logs → Commands
→ Root cause → Immediate mitigation → Permanent fix → Prevention → Lessons learned
```

## Interview contract

Interview material progresses through:

```text
Fundamentals → Intermediate → Advanced → Production
→ Senior Engineer → Architect/SRE scenarios
```

Answers link to working repository evidence whenever possible.

## Security and identity

- Public identity is `jeevanm84`.
- Use the GitHub noreply commit email.
- Never commit credentials, state, plan files, account IDs, customer details, employer data, internal URLs, or proprietary code.
- Cloud workflows use short-lived federation such as GitHub OIDC.
- Production or billable operations are manual and documented.
- Secret scanning, push protection, Dependabot, private vulnerability reporting, and protected branches are enabled where supported.

## Quality gate

Before publication:

1. Run formatting and syntax checks.
2. Run unit, integration, mock, or manifest validation appropriate to the project.
3. Test documentation links and scripts.
4. Scan for credentials and unwanted identities.
5. Verify the primary local path without cloud credentials.
6. Publish only after CI passes.
7. Add repository topics and a professional description.
8. Protect `main` with pull requests, review, required CI, linear history, and force-push/deletion prevention.
