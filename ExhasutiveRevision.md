# GH-300 Complete Revision Guide
GitHub Copilot Fundamentals – Exam Preparation

This document is a complete revision guide for the GitHub Copilot Fundamentals exam (GH-300).  
It covers features, commands, APIs, governance, workflows, SDLC integration, and unit testing.

The goal is to remove knowledge gaps and provide exam-ready clarity.

---

# 1. GitHub Copilot Overview

GitHub Copilot is an AI-powered coding assistant that helps developers write code faster.

Core capabilities:

- Code completion
- Code generation
- Code explanation
- Test generation
- Documentation generation
- Code refactoring
- Debugging assistance

Copilot integrates into:

IDE
- Visual Studio Code
- Visual Studio
- JetBrains IDEs

Platforms
- GitHub.com
- CLI / Terminal

---

# 2. How Copilot Generates Suggestions

Copilot analyzes context from:

- Current file
- Open files
- Project structure
- Variable names
- Comments
- Documentation
- Code patterns

Copilot learns coding style from the repository.

Example:

If the project uses snake_case naming, Copilot continues using snake_case.

---

# 3. Ghost Text (Inline Suggestions)

Ghost text refers to inline suggestions that appear while typing.

Accept suggestion
Tab

Reject suggestion
Continue typing

Ghost text can generate:

- single lines
- blocks of code
- entire functions

Example:

Typing

def calculate_total(

Copilot may generate the rest of the function automatically.

---

# 4. Multiple Suggestions

Copilot may generate more than one solution.

Navigation:

Windows / Linux
Alt + ]
Alt + [

Mac
Option + ]
Option + [

Purpose:

Compare different implementations.

Example use case:

Two possible sorting algorithms.

---

# 5. Improving Suggestion Quality

Better prompts = better results.

Ways to improve results:

Use descriptive comments

Example:

Create a function that validates email format and returns true or false

Use meaningful variable names

Example:

customerOrderTotal instead of value

Provide expected output

Example:

Return JSON object containing user name and email.

---

# 6. Copilot Chat

Copilot Chat allows natural language interaction with code.

Tasks supported:

- explain code
- generate functions
- fix bugs
- generate tests
- write documentation
- optimize performance

---

## Opening Copilot Chat

Sidebar chat icon

Inline Chat

Windows
Ctrl + I

Mac
Cmd + I

Inline chat allows editing code without leaving the editor.

---

# 7. Chat Context References

Context references allow Copilot to understand scope.

---

## #file

Used to reference a specific file.

Example

#file:auth.js explain this function

Use case

Explain authentication logic inside a file.

---

## #selection

Used for selected code.

Example

#selection optimize this function

Use case

Refactor only selected code.

---

## @workspace

Used to reference entire project.

Example

@workspace where is calculateTax used

Use case

Find all usages of a function across project.

---

# 8. Slash Commands

Slash commands trigger predefined tasks.

| Command | Purpose |
|-------|--------|
| /doc | generate documentation |
| /explain | explain code |
| /fix | fix bugs |
| /generate | generate code |
| /optimize | improve performance |
| /tests | generate tests |
| /setupTests | configure testing framework |
| /fixTestFailure | repair failing tests |

Example:

/tests generate unit tests for this function including edge cases

---

# 9. Copilot CLI Commands

Copilot CLI helps in terminal environments.

Command format

gh copilot explain <command>

Example

gh copilot explain git reset --hard HEAD

Purpose

Explains what a command does.

---

Command format

gh copilot suggest "<task>"

Example

gh copilot suggest "find all large files"

Purpose

Generates shell commands to complete tasks.

---

# 10. Premium Request Units (PRUs)

PRUs measure advanced AI operations.

Typical consumption:

| Task | PRU Usage |
|----|----|
Standard chat request | 1 PRU |
Multi-file reasoning | 2-3 PRUs |
Project scaffolding | 3-5 PRUs |
Advanced reasoning | 4+ PRUs |

Examples consuming PRUs:

- PR summary generation
- code review assistance
- agent workflows
- multi-file edits

---

# 11. GitHub Copilot Plans

Copilot has four plans.

Free  
Pro  
Business  
Enterprise

---

## Feature Comparison

| Feature | Free/Pro | Business | Enterprise |
|------|------|------|------|
Public code filter | Yes | Yes | Yes |
User management | No | Yes | Yes |
Enterprise security | No | Yes | Yes |
IP indemnity | No | Yes | Yes |
Content exclusions | No | Yes | Yes |
SAML SSO | No | Yes | Yes |
Usage metrics | No | Yes | Yes |
Private codebase chat | No | No | Yes |

---

# 12. Public Code Filtering

Copilot can detect code that matches public repositories.

Options

Allow suggestions matching public code

Block suggestions matching public code

Blocking public code suggestions is required for:

IP indemnity protection.

---

# 13. Contractual Protections

Organizations receive legal protections.

---

## IP Indemnity

Available in

Business  
Enterprise

Meaning

GitHub assumes legal responsibility if Copilot suggestions violate intellectual property.

Requirement

Public code suggestions must be blocked.

---

## Data Protection Agreement

Defines how GitHub handles:

- prompts
- generated suggestions
- stored interaction data

Ensures compliance with privacy regulations.

---

## Copilot Trust Center

Provides transparency on:

- security
- privacy
- compliance
- model behavior

---

# 14. Content Exclusions

Content exclusions prevent specific files from influencing Copilot suggestions.

Example uses

- secrets
- proprietary algorithms
- internal configurations

---

## Repository Level Configuration

Repository

Settings → Copilot

Add paths to exclude.

Example

/config/secrets.json

---

## Organization Level Configuration

Organization

Settings → Copilot → Content exclusions

---

## Impact

Excluded files

- do not generate suggestions
- do not inform suggestions elsewhere
- are ignored by Copilot Chat

---

## Limitation

Content exclusions may not apply when

- IDE provides semantic references
- using certain chat participants

Propagation delay

Up to 30 minutes.

---

# 15. Troubleshooting Copilot

---

## Problem: No suggestions

Check

Internet connection  
Extension updates  
IDE compatibility  
Content exclusions

---

## Problem: Exclusions not working

Possible causes

Propagation delay  
Wrong scope  
IDE limitation

Indicator

Copilot icon with diagonal line.

---

## Problem: Poor suggestions

Improve by

- writing better prompts
- adding comments
- increasing context

---

# 16. Productivity Use Cases

Copilot improves productivity by

- reducing repetitive coding
- automating boilerplate
- accelerating learning
- reducing context switching

---

## Accelerating Learning

Copilot helps learn

- programming languages
- frameworks
- libraries

By generating examples.

Example

New Golang developer

Copilot generates function examples.

---

## Minimizing Context Switching

Copilot provides API references and suggestions inside IDE.

Benefits

- less documentation searching
- faster coding

---

# 17. Automation Use Cases

Copilot can generate

- REST API endpoints
- database models
- Docker configuration
- CI/CD pipelines
- microservice scaffolding

Complex automation consumes additional PRUs.

---

# 18. Pull Request Assistance

Copilot helps with

- PR summaries
- code review comments
- merge conflict resolution
- documentation updates

Benefits

- faster reviews
- improved consistency
- better documentation.

---

# 19. Copilot in the SDLC

Copilot enhances multiple stages.

---

## Requirement Phase

Helps with

- rapid prototyping
- translating user stories into code.

---

## Development Phase

Strongest impact.

Features

- code generation
- design pattern suggestions
- code optimization.

---

## Testing Phase

Copilot can

- generate unit tests
- suggest assertions
- detect edge cases.

---

## Deployment Phase

Copilot can generate

- deployment scripts
- configuration files.

Copilot does not deploy applications.

---

## Maintenance Phase

Copilot helps with

- bug fixes
- refactoring
- legacy code understanding.

---

# 20. Limitations of Copilot

---

## Code Quality

Generated code may contain bugs.

Manual review required.

---

## Context Misinterpretation

Copilot may misunderstand system architecture.

---

## Training Data Bias

Suggestions may include outdated practices.

---

## Architecture Decisions

Copilot assists with code-level tasks, not system architecture.

---

# 21. Measuring Productivity

Organizations use two main approaches.

---

## REST API Metrics

Provides usage statistics.

---

### Enterprise usage API

GET /enterprises/{enterprise}/GitHub Copilot/usage

Purpose

Measure Copilot usage across enterprise.

---

### Enterprise team usage API

GET /enterprises/{enterprise}/team/{team_slug}/GitHub Copilot/usage

Purpose

Measure team-level adoption.

---

### Organization usage API

GET /orgs/{org}/GitHub Copilot/usage

Purpose

Measure organization-wide usage.

---

Metrics returned

- suggestions generated
- suggestions accepted
- active users
- editor distribution
- language distribution

---

# 22. Copilot Developer Survey

Used for qualitative insights.

---

## Short Form

Frequency

Every 2 weeks.

Measures

- developer satisfaction
- perceived productivity.

---

## Long Form

Frequency

Every 4 weeks.

Measures

- team productivity
- workflow improvements.

Responses should be anonymized.

---

# 23. Unit Testing with Copilot

Copilot helps generate

- unit tests
- integration tests
- end-to-end tests.

Training example

C# with xUnit.

---

# 24. Supported Test Frameworks

xUnit  
NUnit  
MSTest

---

# 25. Methods for Generating Tests

---

## Generate Tests Smart Action

Right-click file

Copilot → Generate Tests

Creates test cases automatically.

---

## Inline Chat

Shortcut

Ctrl + I

Example

/tests generate unit tests for this method including edge cases.

---

## Chat Modes

Three modes exist.

---

### Ask Mode

Best for

- analysis
- generating tests across workspace.

---

### Edit Mode

Best for

- editing multiple files
- generating test files.

---

### Agent Mode

Best for

- automation
- project setup
- running tests.

Agent mode may consume PRUs.

---

# 26. Fixing Failing Tests

Two methods.

---

## Test Explorer Fix

Hover failing test

Click sparkle icon.

---

## Chat Command

/fixTestFailure

Agent mode can rerun tests automatically.

---

# 27. Visual Studio Code Testing Tools

C# Dev Kit provides

- Test Explorer
- run/debug tests
- view test results
- testing commands
- testing settings.

Run tests using green play icon.

---

# 28. Best Practices

Always

- review generated code
- validate security
- check edge cases
- supplement with manual tests
- write clear prompts.

Copilot enhances development but does not replace human review.

---

# 29. Final Exam Memory List

Ghost text = inline suggestion  
Inline chat shortcut = Ctrl + I  
/tests generates tests  
/setupTests configures testing framework  
Business & Enterprise provide IP indemnity  
Public code filtering required for indemnity  
Content exclusions remove files from context  
Content exclusion propagation ≈ 30 minutes  
Copilot strongest in development and testing phases  
REST APIs measure usage metrics  
Short survey cadence = 2 weeks  
Long survey cadence = 4 weeks  
Agent workflows consume PRUs
