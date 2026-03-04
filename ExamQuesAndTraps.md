# GH-300 Likely Exam Questions & Traps
GitHub Copilot Fundamentals – Exam Strategy Section

This section highlights concepts that frequently appear in exam questions or are designed to trick candidates.

Focus on understanding **when a feature is used**, not just what it does.

---

# 1. Ghost Text vs Copilot Chat

Exam questions often test the difference.

Ghost Text
Inline suggestion that appears automatically while typing.

Accept suggestion
Tab

Used for
Code completion

---

Copilot Chat

Used for

- explaining code
- generating tests
- debugging
- refactoring
- answering questions

Shortcut for Inline Chat

Ctrl + I

Common exam trap

Ghost text ≠ Chat

---

# 2. Chat Context Variables

Know the difference between these.

| Context | Meaning |
|------|------|
#file | specific file |
#selection | highlighted code |
@workspace | entire project |

Example question

Which context variable allows Copilot to analyze the entire project?

Answer

@workspace

---

# 3. Slash Commands

Slash commands are designed to **reduce prompt length and improve accuracy**.

Most important commands:

| Command | Purpose |
|------|------|
/doc | generate documentation |
/explain | explain code |
/fix | repair bugs |
/generate | generate code |
/optimize | improve performance |
/tests | generate tests |
/setupTests | configure testing framework |
/fixTestFailure | repair failing tests |

Exam trap

/tests generates tests  
NOT /test

---

# 4. Copilot Chat Modes

There are three modes in Chat view.

| Mode | Purpose |
|------|------|
Ask | ask questions and analyze code |
Edit | modify multiple files |
Agent | automate complex workflows |

Agent mode can

- create test projects
- run commands
- run tests
- modify files automatically

Exam trap

Agent mode may consume **multiple premium requests**.

---

# 5. Premium Request Units (PRUs)

PRUs measure advanced Copilot operations.

Examples consuming PRUs

- pull request summaries
- multi-file reasoning
- agent workflows
- advanced reasoning models

Typical usage

Standard request  
1 PRU

Complex task  
2–5 PRUs

Exam trap

Not every Copilot action consumes PRUs.

---

# 6. Copilot Plans

Know which features belong to which plan.

| Feature | Free / Pro | Business | Enterprise |
|------|------|------|------|
Public code filter | Yes | Yes | Yes |
User management | No | Yes | Yes |
Content exclusions | No | Yes | Yes |
SAML SSO | No | Yes | Yes |
Usage metrics | No | Yes | Yes |
IP indemnity | No | Yes | Yes |
Private codebase chat | No | No | Yes |

Exam trap

IP indemnity is NOT Enterprise only.

Correct answer

Business AND Enterprise.

---

# 7. Public Code Filtering

Copilot can detect suggestions that match public repositories.

Settings

Allow suggestions matching public code

Block suggestions matching public code

Important rule

Blocking public code suggestions is required for IP indemnity.

---

# 8. Content Exclusions

Content exclusions prevent files from influencing suggestions.

Example excluded content

- secrets
- configuration files
- proprietary algorithms

Effects

Excluded files

- cannot generate suggestions
- cannot influence suggestions in other files
- are ignored by Copilot chat

Exam trap

Content exclusion changes may take **up to 30 minutes**.

---

# 9. Troubleshooting Copilot

Most common troubleshooting question.

If Copilot stops showing suggestions:

First check

Internet connection.

Other checks

- extension version
- IDE compatibility
- content exclusion settings

---

# 10. Copilot in SDLC

Exam questions may ask where Copilot provides the most value.

Copilot impacts:

Requirement phase  
Design & development  
Testing  
Deployment assistance  
Maintenance

Strongest phase

Development.

Second strongest

Testing.

---

# 11. Developer Productivity Use Cases

Most common productivity benefits.

- reduce repetitive coding
- generate boilerplate code
- generate documentation
- generate tests
- reduce context switching

Exam trap

Copilot does NOT replace developers.

---

# 12. Copilot Limitations

Important for scenario questions.

Copilot limitations include

- may generate incorrect code
- may miss edge cases
- may misunderstand architecture
- may suggest outdated practices

Best practice

Always review generated code.

---

# 13. Copilot Usage Metrics APIs

These endpoints measure Copilot usage.

Enterprise usage

GET /enterprises/{enterprise}/GitHub Copilot/usage

Purpose

Enterprise-level usage metrics.

---

Team usage

GET /enterprises/{enterprise}/team/{team_slug}/GitHub Copilot/usage

Purpose

Team adoption analysis.

---

Organization usage

GET /orgs/{org}/GitHub Copilot/usage

Purpose

Organization-level Copilot analytics.

Exam trap

Questions often test the **correct endpoint structure**.

---

# 14. Copilot Developer Survey

Two survey types exist.

Short form

Frequency

Every 2 weeks

Measures

- developer satisfaction
- time saved.

---

Long form

Frequency

Every 4 weeks

Measures

- workflow improvements
- collaboration changes.

Exam trap

Short survey ≠ weekly.

---

# 15. Unit Testing with Copilot

Copilot can generate

- unit tests
- integration tests
- end-to-end tests

Most common example

C# + xUnit.

Supported frameworks

- xUnit
- NUnit
- MSTest

---

# 16. Methods to Generate Unit Tests

There are four ways.

Generate Tests Smart Action

Right-click → Generate Tests

Inline Chat

Ctrl + I  
/tests generate unit tests

Chat Ask Mode

Analyze workspace and generate tests.

Agent Mode

Automates full testing workflow.

Exam trap

Smart Action generates tests **without writing a prompt**.

---

# 17. Fixing Failing Tests

Two common methods.

Test Explorer fix

Hover failing test → sparkle icon.

Slash command

/fixTestFailure

Agent mode may rerun tests automatically.

---

# 18. Visual Studio Code Testing Tools

C# Dev Kit provides

- Test Explorer
- run/debug tests
- view test results
- test commands

Run test button

Green play icon.

---

# 19. Common Scenario Question Themes

Expect questions about

Choosing correct Copilot plan

Selecting the right chat mode

Handling sensitive code

Generating tests

Troubleshooting missing suggestions

Measuring Copilot productivity.

---

# 20. Final Exam Memory Triggers

Ghost text = inline suggestion

Inline chat shortcut = Ctrl + I

/tests generates tests

/setupTests configures test framework

IP indemnity requires blocking public code suggestions

Content exclusions remove files from Copilot context

Content exclusion propagation ≈ 30 minutes

REST API endpoints measure Copilot usage

Short survey cadence = 2 weeks

Long survey cadence = 4 weeks

Agent workflows consume PRUs
