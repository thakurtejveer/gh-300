# GH-300 Complete Revision Guide
## GitHub Copilot Fundamentals – Full Exam Preparation

This document contains a comprehensive revision guide for the **GitHub Copilot Fundamentals (GH-300)** exam.  
It consolidates all key concepts, commands, governance topics, workflows, and testing practices required to prepare for the exam.

---

# 1. GitHub Copilot Overview

GitHub Copilot is an **AI-powered coding assistant** that helps developers write code faster and more efficiently.

It provides:

- Code completion
- Code generation
- Code explanation
- Test generation
- Documentation generation
- Debugging assistance

Copilot integrates into:

- Visual Studio Code
- Visual Studio
- JetBrains IDEs
- GitHub.com
- Terminal environments

---

# 2. How GitHub Copilot Works

Copilot analyzes the development context and generates suggestions based on:

- Current file contents
- Other open files
- Project structure
- Comments and documentation
- Naming patterns
- Coding style

Copilot learns from the project and adapts suggestions to match the coding patterns used in the codebase.

---

# 3. Ghost Text (Inline Suggestions)

Ghost text refers to **inline code suggestions that appear as you type**.

Key behaviors:

Accept suggestion  
Tab

Ignore suggestion  
Continue typing

Ghost text can generate:

- single-line completions
- multi-line code
- entire functions

---

# 4. Multiple Suggestions

Copilot can generate multiple possible solutions.

Navigation shortcuts:

Windows / Linux

Alt + ]

Alt + [

Mac

Option + ]

Option + [

Purpose:

Allows developers to compare multiple implementations and choose the most suitable one.

---

# 5. Improving Copilot Suggestions

Copilot performs best when given **clear context**.

Ways to improve suggestion quality:

- Write clear comments
- Use descriptive variable names
- Provide function descriptions
- Define expected outputs

Example:

Create a REST API endpoint that returns user profile information.

Copilot can generate the complete endpoint code.

---

# 6. Copilot Chat

Copilot Chat allows developers to interact with the codebase using natural language.

Common tasks:

- Explain code
- Refactor code
- Generate tests
- Fix bugs
- Improve performance
- Write documentation

---

## Opening Copilot Chat

Open Chat Panel:

Click the Copilot Chat icon in the IDE sidebar.

Inline Chat Shortcut:

Windows  
Ctrl + I

Mac  
Cmd + I

Inline chat allows developers to interact with Copilot directly inside the code editor.

---

# 7. Chat Context Variables

Copilot can analyze different scopes of code.

---

## #file

Refers to a specific file.

Example:

#file:auth.js explain this code

---

## #selection

Refers to highlighted code.

Example:

#selection optimize this function

---

## @workspace

Refers to the entire project workspace.

Example:

@workspace where is the calculate function used

---

# 8. Slash Commands

Slash commands trigger specific Copilot actions.

Common slash commands:

/doc  
/explain  
/fix  
/generate  
/optimize  
/tests  
/setupTests  
/fixTestFailure

Examples:

/explain this code

/tests generate unit tests

/fix resolve the bug in this function

Purpose:

- Reduce prompt length
- Standardize tasks
- Improve accuracy of results

---

# 9. GitHub Copilot CLI

Copilot can also operate inside the terminal.

Capabilities:

- Explain commands
- Suggest shell commands
- Revise commands
- Automate tasks

Examples:

gh copilot explain git reset --hard HEAD

gh copilot suggest "find large files"

CLI mode allows developers to work faster without leaving the terminal environment.

---

# 10. Premium Request Units (PRUs)

Some Copilot actions consume **Premium Request Units**.

Examples of PRU usage:

- Pull request summaries
- Code review analysis
- Multi-file reasoning
- Agent workflows

Typical usage:

Standard request  
~1 PRU

Complex automation  
2–5 PRUs

Premium reasoning runs  
4+ PRUs

---

# 11. GitHub Copilot Plans

Copilot offers several subscription plans.

Plans:

Free  
Pro  
Business  
Enterprise

---

## Features Available in All Plans

- Copilot code completion
- IDE integrations
- Public code filtering
- Chat functionality

---

## Business and Enterprise Features

- User management
- Enterprise-grade security
- IP indemnity
- Content exclusions
- SAML SSO authentication
- Usage metrics
- Data excluded from training

---

## Enterprise-Only Features

- Tailored chat using private codebase
- Knowledge base integration
- Requires GitHub Enterprise Cloud

---

# 12. Public Code Filtering

Copilot can detect when suggestions match public repositories.

Options:

Allow suggestions matching public code  
Block suggestions matching public code

Blocking public code suggestions is important for:

- legal compliance
- IP protection
- enabling indemnity coverage

---

# 13. Contractual Protections

Organizations using Copilot may receive legal protections.

---

## IP Indemnity

Available in:

Business  
Enterprise

Meaning:

GitHub assumes legal responsibility if Copilot-generated code violates third-party intellectual property.

Requirement:

Public code filter must be blocked.

---

## Data Protection Agreement (DPA)

Defines how GitHub manages and protects:

- prompts
- generated suggestions
- stored data

Ensures compliance with privacy regulations.

---

## Copilot Trust Center

Provides transparency regarding:

- security
- privacy
- compliance
- intellectual property safeguards

---

# 14. Content Exclusions

Content exclusions prevent certain files or directories from influencing Copilot suggestions.

Example use cases:

- secrets
- configuration files
- proprietary algorithms

---

## Configure Repository-Level Exclusion

Repository → Settings → Copilot

Specify:

- files
- directories
- paths

---

## Configure Organization-Level Exclusion

Organization → Settings → Copilot → Content Exclusions

---

## Impact of Exclusions

Excluded content:

- will not generate suggestions
- will not influence other suggestions
- will not be used in Copilot Chat context

---

## Limitations of Exclusions

Content exclusions may not fully apply in:

- certain IDE chat features
- semantic symbol references
- external repository access

Configuration updates may take **up to 30 minutes** to apply.

---

# 15. Troubleshooting Copilot

Common problems and solutions.

---

## Missing Suggestions

Check:

- internet connection
- Copilot extension updates
- IDE compatibility
- content exclusion rules

---

## Content Exclusions Not Applying

Possible causes:

- propagation delay
- incorrect configuration scope
- IDE limitations

Indicator:

Copilot icon with diagonal line.

---

## Poor Suggestions

Improve suggestions by:

- writing better prompts
- adding descriptive comments
- increasing context length

---

# 16. Developer Productivity Use Cases

Copilot increases developer productivity by:

- reducing repetitive coding
- automating boilerplate code
- assisting learning
- improving documentation

---

## Accelerating Learning

Copilot helps developers learn:

- new languages
- frameworks
- libraries

By providing:

- sample implementations
- API usage examples
- parameter explanations

---

## Minimizing Context Switching

Copilot reduces the need to leave the editor.

Benefits:

- less documentation searching
- uninterrupted focus
- faster development cycles

---

# 17. Automation Use Cases

Copilot can generate complex project structures including:

- REST APIs
- database models
- microservice scaffolding
- CI/CD pipelines
- Docker configuration

Complex multi-file tasks may consume additional PRUs.

---

# 18. Pull Request Assistance

Copilot supports pull request workflows.

Capabilities:

- generate PR summaries
- suggest improvements
- draft review comments
- resolve merge conflicts

Benefits:

- faster review cycles
- consistent documentation
- improved code quality

---

# 19. Copilot Across the SDLC

Copilot enhances multiple phases of the **Software Development Lifecycle**.

---

## Requirement Phase

Copilot assists by:

- generating rapid prototypes
- translating user stories into code structures

---

## Design and Development

This phase sees the greatest benefit.

Capabilities:

- boilerplate generation
- design pattern suggestions
- code optimization
- language translation

---

## Testing and QA

Copilot can:

- generate unit tests
- identify edge cases
- generate test data
- suggest assertions

---

## Deployment

Copilot helps with:

- configuration files
- deployment scripts
- documentation updates

Copilot does not deploy applications.

---

## Maintenance

Copilot assists with:

- bug fixes
- refactoring
- legacy code explanations
- documentation updates

---

# 20. Limitations of GitHub Copilot

Copilot has several limitations.

---

## Code Quality Limitations

Generated code may:

- contain bugs
- miss edge cases
- require human review

---

## Context Limitations

Copilot may misunderstand:

- business requirements
- architectural context

---

## Training Data Bias

Suggestions reflect patterns in training data and may include outdated coding practices.

---

## Architectural Limitations

Copilot excels at code-level tasks but cannot replace human architectural decisions.

---

# 21. Measuring Copilot Productivity

Organizations measure Copilot’s impact using data-driven methods.

---

## REST API Usage Metrics

Provides information about:

- suggestion counts
- acceptance rates
- active users
- editor usage
- programming languages

Example endpoints:

GET /enterprises/{enterprise}/GitHub Copilot/usage

GET /enterprises/{enterprise}/team/{team_slug}/GitHub Copilot/usage

GET /orgs/{org}/GitHub Copilot/usage

---

# 22. Copilot Developer Survey

Used to collect developer feedback.

---

## Short-Form Survey

Frequency:

Every 2 weeks

Measures:

- developer satisfaction
- productivity improvements
- usability challenges

---

## Long-Form Survey

Frequency:

Every 4 weeks

Measures:

- team workflow impact
- collaboration improvements
- code quality changes

Survey responses should be anonymized.

---

# 23. Unit Testing with Copilot

Copilot can generate:

- unit tests
- integration tests
- end-to-end tests

Example used in training:

C# unit tests using xUnit.

---

# 24. Supported Test Frameworks

Common frameworks supported:

xUnit  
NUnit  
MSTest

---

# 25. Generating Unit Tests

There are four primary methods.

---

## Generate Tests Smart Action

Right-click code

Copilot → Generate Tests

Automatically creates test cases.

---

## Inline Chat

Shortcut:

Ctrl + I

Example:

/tests generate unit tests for this method including edge cases.

---

## Chat View Modes

Three chat modes exist.

---

### Ask Mode

Best for:

- analyzing workspace
- generating tests for entire files

---

### Edit Mode

Best for:

- editing multiple files
- creating new test files

---

### Agent Mode

Best for:

- automating workflows
- setting up test projects
- running tests automatically

Agent mode may consume multiple PRUs.

---

# 26. Fixing Failing Tests

Two common approaches.

---

## Test Explorer

Hover failing test → click sparkle icon.

---

## Chat Command

/fixTestFailure

Agent mode can rerun tests automatically after applying fixes.

---

# 27. Visual Studio Code Testing Tools

The C# Dev Kit extension provides:

- Test Explorer
- run and debug tests
- test result visualization
- testing commands
- testing settings

Run tests using:

green play icon.

---

# 28. Best Practices for Using Copilot

Always:

- review generated code
- validate security practices
- verify edge cases
- supplement with manual testing
- write descriptive prompts

Copilot should enhance development, not replace human judgment.

---

# 29. Key Exam Points

Remember the following:

Ghost text = inline suggestion  
Inline chat shortcut = Ctrl + I  
/tests generates tests  
Business and Enterprise plans include IP indemnity  
Public code filtering must be blocked for indemnity  
Content exclusions remove files from Copilot context  
Content exclusion updates may take 30 minutes  
Copilot is strongest in development and testing phases  
Copilot requires human review for quality assurance  
Usage metrics available via REST API  
Short survey cadence = 2 weeks  
Long survey cadence = 4 weeks  
Agent workflows consume Premium Request Units
