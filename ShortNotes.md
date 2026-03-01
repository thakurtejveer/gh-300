# GH-300  
# GitHub Copilot Fundamentals – Part 1 (Sections 1.1 & 1.2)

---

# 1.1 Responsible AI with GitHub Copilot

## What is Responsible AI?

Responsible AI is the practice of developing and using AI systems in a:

- Safe
- Trustworthy
- Ethical
- Accountable

manner, keeping people and their goals at the center of system design.

Primary Goal:
Ensure AI systems are safe, trustworthy, and ethical.

---

## AI Risks to Remember

AI systems can:

- Produce biased outputs
- Be non-transparent (black-box decisions)
- Violate privacy
- Generate harmful or incorrect results
- Reduce accountability if unchecked

Important:
AI does NOT remove human responsibility.

---

## Mitigating AI Risks

Organizations should:

- Implement governance frameworks
- Ensure transparency
- Include human oversight
- Review and balance training data
- Monitor model performance across groups
- Use adversarial debiasing
- Log and audit AI outputs

---

# Microsoft & GitHub’s Six Principles of Responsible AI

Memorize these exactly:

1. Fairness  
2. Reliability and Safety  
3. Privacy and Security  
4. Inclusiveness  
5. Transparency  
6. Accountability  

---

## 1. Fairness

AI systems should treat all people fairly.

Key actions:
- Review training data
- Test with balanced demographic samples
- Use adversarial debiasing
- Monitor across user segments

Focus: Avoid bias and discrimination.

---

## 2. Reliability and Safety

AI must:
- Perform consistently
- Handle unexpected conditions safely
- Minimize physical, emotional, and financial harm
- Resist harmful manipulation

Reliable = predictable and stable behavior.

---

## 3. Privacy and Security

AI systems must:

- Obtain user consent
- Collect only necessary data
- Anonymize personal data (pseudonymization, aggregation)
- Encrypt data in transit and at rest
- Protect keys using secure vaults or HSMs
- Limit access to sensitive models

Focus: Data protection and controlled access.

---

## 4. Inclusiveness

AI systems must:

- Work across diverse users and groups
- Be accessible (screen readers, captions, voice control)
- Support multiple languages
- Function in low-connectivity environments
- Empower all users equally

---

## 5. Transparency

AI systems must:

- Explain how they work
- Document capabilities and limitations
- Enable logging and auditing
- Justify design decisions

Goal: Build trust and clarity.

---

## 6. Accountability

- Humans remain responsible for AI systems.
- Organizations must monitor and mitigate risks.
- Developers must validate AI-generated outputs.

AI does not replace human accountability.

---

# 1.2 Introduction to GitHub Copilot

## What is GitHub Copilot?

GitHub Copilot is an AI-powered coding assistant that helps developers:

- Generate code
- Explain code
- Refactor implementations
- Fix bugs
- Write tests
- Create documentation

Powered by:
- OpenAI Codex
- Large language models trained on public code

---

## Supported Environments

- VS Code
- Visual Studio
- JetBrains IDEs
- Neovim
- GitHub.com

---

# Core Copilot Features

## Inline Suggestions

- Real-time code completion
- Accept with Tab
- Reject with Esc
- Multiple suggestions available

---

## Copilot Chat

- Ask questions in natural language
- Explain code logic
- Generate tests or documentation
- Context-aware responses

---

## Inline Chat

- Context-specific interaction inside editor
- Shortcut: Ctrl+I (Windows/Linux) / Cmd+I (Mac)

Common slash commands:
- /explain
- /suggest
- /tests
- /comment

---

## Pull Request Summaries

- Automatically generates PR descriptions.

---

## Code Review Assistance

- Suggest improvements
- Identify issues
- Describe changes

---

## Copilot CLI

- Suggest shell commands
- Explain terminal errors
- Generate scripts

---

## Copilot Coding Agent

- Executes multi-step coding tasks
- Generates related files
- Builds scaffolding from specifications

---

# Subscription Plans

## GitHub Copilot Free

- 2000 code completions per month
- 50 chat requests per month
- Access to advanced AI models

---

## GitHub Copilot Pro

- Unlimited completions
- Unlimited chat
- Advanced suggestions

---

## GitHub Copilot Pro+

- All Pro features
- Additional premium request capacity
- Priority infrastructure access

---

## GitHub Copilot Business

- Organization-wide management
- Policy controls
- Security vulnerability filtering
- Public code filtering
- IP indemnity

---

## GitHub Copilot Enterprise

Includes all Business features plus:

- Personalization using organization codebase
- GitHub Enterprise Cloud integration
- AI-powered search across codebase
- Organization-wide customization
- Enhanced PR support

Key Difference:
Enterprise = Business + personalization and deeper integration.

---

# Setup & Configuration (VS Code)

Enable / Disable:
- From status bar (globally or per language)

Inline Suggestions:
Settings → Extensions → GitHub Copilot → Enable Auto Completions

Troubleshooting:
- Open extension logs
- Use "Collect Diagnostics"
- Check firewall/proxy issues

---

# High-Probability Exam Areas

- Six Responsible AI principles (exact wording)
- Bias mitigation techniques
- Privacy and encryption practices
- Business vs Enterprise differences
- Inline suggestions vs Chat vs Inline Chat
- Developer responsibility for validating AI-generated code
