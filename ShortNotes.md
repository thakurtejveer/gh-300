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


# GH-300  
# GitHub Copilot Fundamentals – Section 1.3  
# Introduction to Prompt Engineering with GitHub Copilot

---

# 1.3 Prompt Engineering Overview

## What is Prompt Engineering?

Prompt engineering is the practice of crafting clear, precise, and structured instructions to get accurate and relevant responses from GitHub Copilot.

Key Idea:
Better prompts → Better code suggestions → Fewer revisions → Faster development.

---

## Learning Focus

You must understand:

- How prompts influence Copilot responses
- Best practices for writing effective prompts
- Role prompting and chat history management
- How Copilot processes prompts internally
- Data handling and filtering
- LLMs and fine-tuning (LoRA)

---

# 1.3.1 Why Prompt Engineering Matters

GitHub Copilot:
- Is powered by Large Language Models (LLMs)
- Trained on public source code + natural language
- Provides context-aware suggestions

However:
Copilot performance depends heavily on prompt clarity.

Clear + specific + contextual prompts improve accuracy.

---

# 1.3.2 GitHub Copilot User Prompt Process Flow

Copilot follows an inbound and outbound process.

---

## Inbound Flow (Prompt → Model)

### 1. Secure Prompt Transmission

- Prompt sent over HTTPS
- Ensures confidentiality
- Protects sensitive data

---

### 2. Context Gathering

Copilot collects:

- Code before and after cursor
- Filename and file type
- Adjacent open tabs
- Project structure and file paths
- Programming language and frameworks

Uses:
Fill-in-the-Middle (FIM) technique  
→ Considers both preceding and following code.

Key Point:
Copilot does NOT rely only on your prompt. It uses surrounding context.

---

### 3. Proxy Filter

- Runs in GitHub-owned Azure tenant
- Blocks prompt manipulation attempts
- Prevents system exploitation

---

### 4. Toxicity Filtering (Before Generation)

Filters:

- Hate speech
- Inappropriate content
- Personal data

Goal:
Prevent harmful or sensitive output.

---

### 5. Code Generation (LLM Stage)

- Prompt + context passed to LLM
- Generates context-aware suggestions
- Ensures alignment with project requirements

---

## Outbound Flow (Model → User)

### 6. Post-Processing & Validation

After generation:

- Toxic content rechecked
- Security checks applied
- Vulnerability checks (XSS, SQL injection)
- Optional public code similarity filter (~150+ characters)

If failed → suggestion truncated or discarded.

---

### 7. Suggestion Delivery & Feedback Loop

- Valid suggestions returned
- Copilot learns from:
  - Accepted suggestions
  - Modifications
  - Rejections

Process repeats for each prompt.

---

# 1.3.3 GitHub Copilot Data Handling

## Code Suggestions

- Prompts are NOT retained for foundational model training.
- Prompts are discarded after suggestion.
- Individual users can opt out of prompt sharing.

---

## Copilot Chat Data

- Maintains conversation history for context.
- Outside editor: data retained ~28 days.
- Retention policies may vary inside IDE.

Important:
Chat has broader retention compared to inline completions.

---

## Supported Prompt Types in Chat

- Direct questions
- Code generation requests
- Code explanation
- Open-ended queries
- Contextual prompts with snippets

Copilot Chat handles diverse coding inputs.

---

# Context Window Limitations

Standard Copilot:
~200–500 lines of code (few thousand tokens)

Copilot Chat:
~4k tokens context window

Best Practice:
Break large problems into smaller prompts.

---

# 1.3.4 Large Language Models (LLMs)

## What Are LLMs?

LLMs are AI models trained on massive text datasets to:

- Understand language
- Generate coherent text
- Predict next tokens
- Perform contextual reasoning

They use:
Neural networks with millions/billions of parameters.

---

## Role of LLMs in Copilot

LLMs:
- Analyze prompt + surrounding code
- Generate context-aware completions
- Improve productivity

---

# Fine-Tuning LLMs

Fine-tuning:
- Adapts pretrained model to specific tasks
- Uses smaller task-specific dataset
- Improves performance for domain use

---

# LoRA Fine-Tuning (Important for Exam)

LoRA = Low-Rank Adaptation

Instead of retraining full model:

- Adds smaller trainable layers
- Keeps original model unchanged
- Saves resources
- Faster adaptation

Advantage:
Efficient + cost-effective fine-tuning.

Exam Focus:
LoRA adds small trainable components instead of retraining entire network.

---

# Prompt Engineering Best Practices

To improve prompts:

### The 4S Method of Prompt Engineering

1. Specify  
   Be explicit and detailed in your instructions.

2. Structure  
   Organize the prompt clearly (steps, format, constraints).

3. Supply Context  
   Provide relevant code, file details, and requirements.

4. Simplify  
   Keep prompts focused and break complex tasks into smaller parts.

- Be specific and explicit
- Provide relevant context
- Define desired output format
- Use role prompting when needed
- Manage chat history carefully
- Break complex tasks into smaller steps

Better context → Better results.

---

# High-Probability Exam Areas

- Prompt process flow steps (secure transmission → context → filtering → LLM → validation)
- Fill-in-the-Middle (FIM)
- Context window limits
- Data retention differences (editor vs chat)
- LoRA fine-tuning
- Toxicity filtering
- Public code similarity filtering
- Prompt clarity improves suggestion quality

---

# Ultra-Short Cram Summary

Prompt Engineering = Crafting precise instructions for better Copilot results.

Process:
Secure transmission → Context gathering → Proxy filter → Toxicity filter → LLM → Post-validation → Delivery.

Context matters:
File content + open tabs + project structure.

Data:
Inline prompts discarded.
Chat retains data (~28 days).

LLMs:
Large pretrained models.
Fine-tuned using LoRA (efficient adaptation).

Human remains responsible for reviewing AI-generated code.

# GH-300  
# GitHub Copilot Fundamentals – Section 1.4  
# Introduction to Copilot Spaces

---

# 1.4 Overview – What Are Copilot Spaces?

## Definition

GitHub Copilot Spaces is a dedicated Copilot chat grounded in a curated set of context that you choose.

Unlike general Copilot Chat:
- General chat = broad, exploratory
- Spaces = focused, repeatable, domain-specific

Spaces trade breadth for depth → more predictable, grounded responses.

---

## When to Use a Space

Use a Space when you need:

- Consistent, reproducible answers
- Focus on a specific service, dataset, or runbook
- Repeatable workflows
- Domain-specific assistance

Avoid Spaces when:
- You need broad discovery across many repos
- You don’t have a specific scope

---

# Why Context Matters in Spaces

Spaces improve quality because:

- You control the context
- The model focuses only on attached sources
- Ordering of context influences output
- Narrower scope → higher precision

Important:
Model context limits still apply → keep Spaces small and focused.

---

# Setting Context in a Space

You can add:

## 1️⃣ Instructions (Free Text)

Used to:
- Define goals
- Specify tone/style
- Set constraints
- Provide canonical examples
- Explain what to avoid

Best Practice:
Keep instructions brief, focused, actionable.

---

## 2️⃣ Attachments

Attachments provide grounded context.

You can:

- Attach files or folders from repo
- Link issues or pull requests
- Upload local files (if allowed)
- Add text content (notes, transcripts)

Important:
Attached GitHub files reflect the repository's default branch.

---

# Creating a Space

Steps:

1. Go to https://github.com/copilot/spaces
2. Click Create Space
3. Name the Space clearly
4. Choose ownership:
   - Personal
   - Organization (if available)
5. Add description (for humans, not model)
6. Save

You can edit name and description anytime.

---

# Ownership & Visibility

You can:

- Keep Space personal
- Make it organization-owned (if supported)

Key Rule:
Spaces follow GitHub's existing permission model.

A Space does NOT grant new access.
Users only see content they already have permission to view.

---

# Security & Access

- Linked private repos remain permission-protected
- Avoid pasting sensitive data in free-text
- Prefer linking version-controlled files
- Remove obsolete or confidential materials

Spaces inherit repository/issue/PR permissions.

---

# Versioning & Freshness

- Linked files reflect default branch
- Issues/PRs update automatically
- Keep scope small
- For historical snapshot:
  - Narrow references
  - Add short example
  - Attach text file if needed

---

# Governance Best Practices

Treat governance as lightweight but intentional.

Do:

- Assign a Space owner
- Add "How to use this Space" note
- Include 1–3 canonical examples
- Use naming conventions
- Set review cadence (monthly / per release)
- Split large Spaces into smaller ones

One job per Space.

---

# Naming & Discoverability

Use:

- Clear, purpose-driven titles
- Service or team prefixes
- 1–2 sentence description
- Tags/keywords
- Shared org catalog (if available)

Goal: Easy to find, easy to use.

---

# Do’s and Don’ts in a Space

## ✅ Do

- Keep questions tightly scoped
- Use attached sources
- Confirm intent first
- Add constraints (format, time range, paths)
- Ask for runnable outputs
- Request references for traceability
- Keep most important sources first
- Keep context fresh

---

## ❌ Don’t

- @-mention people (doesn’t notify)
- Invoke extensions inside Space
- Expect discovery outside attached content
- Let Space grow too large
- Exceed model context limits
- Paste sensitive data in free text

If answers become vague:
→ Reduce sources or split Space.

---

# Model Context Limits

Spaces still operate within model context limits.

If you see:
- Size warnings
- Vague responses

Action:
- Reduce sources
- Split into smaller Spaces

---

# High-Probability Exam Areas

- Difference: Spaces vs General Chat
- Spaces improve consistency via curated context
- Ownership options (personal vs org)
- Spaces inherit GitHub permissions
- Attached files reflect default branch
- Don’t paste sensitive data
- Split large Spaces into smaller ones
- Ordering of context affects output

---

# Ultra-Short Cram Summary

Copilot Spaces = Focused, context-grounded Copilot environment.

Best for:
Repeatable, tightly scoped tasks.

Key principles:
- Curate context carefully
- One job per Space
- Follow GitHub permissions
- Keep scope small
- Lead with most important sources
- Assign ownership and review regularly



# GH-300  
# GitHub Copilot Fundamentals – Section 1.5  
# Using Advanced GitHub Copilot Features

---

# 1.5 Overview

GitHub Copilot helps you:

- Write code faster
- Fix bugs
- Create tests
- Write documentation
- Interact using chat and agents

Works inside:
- Visual Studio Code
- GitHub Codespaces
- Other supported editors

---

# Ghost Text

Ghost text = Suggestions that appear in your editor while typing.

- Appears in light/grey text
- Accept with Tab
- Ignore by continuing to type

Ghost text does not require a prompt.
Copilot uses open files as context by default.

---

# Chat Feature

You can talk to Copilot using natural language.

Open Chat:
- Click chat icon in VS Code sidebar

Use Chat to:
- Ask coding questions
- Generate code
- Explain code
- Write tests
- Write documentation

---

# Inline Chat

Inline chat lets you interact without leaving your code.

Open inline chat:
- Windows: Ctrl + i
- Mac: Command + i

Benefit:
You stay inside the file while getting help.

---

# Slash Commands

Slash commands are shortcuts to perform common tasks quickly.

Used in:
- Chat pane
- Inline chat

Common slash commands:

- /fix → Fix code
- /doc → Add documentation
- /explain → Explain code
- /generate → Generate code
- /help → Get help about Copilot
- /optimize → Improve performance
- /tests → Create unit tests

Purpose:
Get better results without writing long prompts.

---

# Implicit Prompts

Implicit prompts = Using slash commands with selected code.

Example:
Select buggy code → open inline chat → type /fix

Benefit:
- Faster interaction
- No need to write long explanations
- Easier bug fixing

---

# Agents

Agents allow context-specific questions.

You must prefix your question with @agent_name.

---

## @workspace Agent

- Uses entire project as context
- Good for project-wide questions
- Example:
  @workspace How do I package this project?

Use for:
- Creating Dockerfiles
- Writing README documentation
- Understanding full project structure

---

## @terminal Agent

- Uses terminal output as context
- Helps fix command errors
- Example:
  @terminal How do I fix this error?

---

## @file Agent

- Focuses on a specific file
- Example:
  @file Can you refactor this function?

---

## @directory Agent

- Focuses on a specific folder
- Example:
  @directory How can I improve scripts in this folder?

---

# Selective Context

By default:
Copilot uses open files as context.

You can narrow context using:
- Agents
- Selecting code
- Inline chat

This gives more precise answers.

---

# Using Copilot in Existing Projects

Copilot can help you:

- Add new API routes
- Fix bugs
- Create unit tests
- Write documentation
- Generate Dockerfiles

Example workflow:
1. Create new route (inline chat)
2. Create test using /tests
3. Document project using @workspace

---

# Codespaces Notes

Codespaces:
- Cloud development environment
- Preconfigured with Copilot
- Runs in browser
- Limited free hours per month

Important:
Commit and push changes before deleting Codespace.

---

# High-Probability Exam Areas

- Definition of ghost text
- Shortcut for inline chat (Ctrl+i / Cmd+i)
- Purpose of slash commands
- Difference between chat and inline chat
- What agents do
- Role of @workspace
- Benefit of implicit prompts
- Agents provide context-specific answers

---

# Ultra-Short Cram Summary

Ghost text = Inline suggestions.

Inline chat = Ctrl+i / Cmd+i.

Slash commands = Shortcuts for tasks like:
- /fix
- /doc
- /tests
- /explain

Agents:
- @workspace → whole project
- @terminal → terminal errors
- @file → single file
- @directory → folder

Implicit prompts + slash commands = Faster fixes.

Copilot helps with:
- Code
- Tests
- Docs
- Refactoring


# GH-300  
# Section 1.6 – GitHub Copilot Across Environments (High-Weightage Detailed Notes)

---

# 1️⃣ Copilot in IDE (Code Completion)

## Strongly Supported Languages
- Python
- JavaScript
- Java
- TypeScript
- Ruby
- Go
- C#
- C++

Exam Trap:
Rust is NOT listed as strongly supported.

---

## Auto Suggestions (Ghost Text)

Definition:
Inline suggestions that appear as you type.

Key Points:
- Context-aware
- Can complete line or entire function
- Accept → Tab
- Ignore → Keep typing
- Uses open files as context by default

Benefit:
Reduces syntax searching and repetitive coding.

---

## Multiple Suggestions Pane

When suggestion appears:
- Hover over suggestion
- Use arrows to cycle

Keyboard shortcuts:
Windows/Linux:
Alt + ] → Next suggestion  
Alt + [ → Previous suggestion  

Mac:
Option + ] → Next  
Option + [ → Previous  

Why Important:
Lets you compare different implementations quickly.

---

## Copilot Adapts To Your Style

Copilot learns from your project:

- Naming conventions
- Indentation style
- Bracket placement
- Comment style (inline, block, docstring)
- Design patterns used

Exam Insight:
Copilot follows project patterns — it does NOT generate random style.

---

# 2️⃣ Using Comments to Improve Suggestions

Copilot reads:

- Inline comments
- Block comments
- Docstrings
- TODO comments
- API documentation

How It Helps:

- Generates full function from description
- Suggests correct variable names
- Selects appropriate algorithms
- Follows documented logic

Important:
Clear and specific comments → More accurate code.

---

# 3️⃣ GitHub Copilot Chat (IDE)

Used for:

- Complex code generation
- Debugging
- Code explanation
- Writing tests
- Refactoring

---

## Opening Chat

Sidebar Chat → Click chat icon  
Inline Chat:
Windows → Ctrl + i  
Mac → Command + i  

Inline chat keeps you inside the file.

---

# Improving Chat Responses (Exam Focus)

## Scope Referencing

Reference specific file:

#file:controller.js explain this function

Reference whole project:

@workspace where is calculate() used?

Purpose of @workspace:
Extends context to entire project.

Exam Question Area:
@workspace = whole solution context.

---

## Important Slash Commands (Chat)

/doc → Add documentation  
/explain → Explain selected code  
/fix → Fix selected code  
/generate → Generate new code  
/optimize → Improve runtime  
/tests → Generate unit tests  

Exam Trap:
/tests is correct, not /test.

Slash commands:
- Improve precision
- Reduce need for long prompts

---

# 4️⃣ Model Selection & PRUs

Standard Model:
- 1 PRU per request
- Suitable for normal tasks

Premium Models:
- 2 PRUs per request
- Better for complex reasoning
- Used for advanced debugging, architecture decisions

Exam Focus:
PR summaries and code review consume PRUs.

---

# 5️⃣ GitHub Copilot on GitHub.com

Available in:

- Repository pages
- Pull Requests
- Issues
- Discussions
- Code Review
- GitHub Actions

---

## Repository Exploration

Copilot can:

- Explain files
- Summarize project
- Generate documentation
- Analyze architecture

---

## Pull Request Assistance

Copilot can:

- Generate PR summaries
- Suggest improvements
- Suggest documentation updates
- Help resolve merge conflicts

Billing Note:
PR summaries consume PRUs.

---

## Issue Management

Copilot can:

- Break down issues
- Suggest solutions
- Generate reproduction steps

---

## Code Review

Copilot can:

- Suggest review comments
- Identify security issues
- Suggest performance improvements

Billing Note:
Code review consumes PRUs.

---

## What Copilot Does NOT Do

- Does NOT compile applications
- Does NOT deploy applications
- Does NOT grant repository access

It assists — does not execute builds.

---

# 6️⃣ GitHub Copilot CLI (Command Line)

Copilot works in terminal.

Used for:

- Explaining commands
- Suggesting shell commands
- Revising commands
- Automating tasks

---

## Start CLI

Interactive mode:
copilot

One-shot mode:
copilot -i "explain git reset --hard HEAD"

---

## Important CLI Commands (Exam Focus)

Explain a command:
gh copilot explain <command>

Suggest command:
gh copilot suggest "<task>"

Example:
gh copilot explain git reset --hard HEAD  
gh copilot suggest "find large files"

---

## Common CLI Slash Commands

/help  
/explain  
/suggest  
/revise  
/feedback  
/exit  
/model  
/theme  

Important:
Slash commands control session settings.

---

## CLI Safety & Configuration

- Must trust directory before running
- Review commands before execution
- Manage tool permissions
- Control allowed directories
- Can choose model using /model

---

# Billing Awareness (High Exam Area)

Consumes PRUs:

- PR summaries
- Code review
- Premium model usage
- Advanced workspace analysis

Standard request → 1 PRU  
Premium request → 2 PRUs  

Exam may test PRU awareness.

---

# Quick Environment Comparison

IDE → Code completion + multiple suggestions  
Chat → Natural language + slash commands  
GitHub.com → PRs, Issues, Code review  
CLI → Explain & suggest shell commands  

---

# 2-Minute Final Revision

Alt + ] → Next suggestion  
Ctrl + i / Cmd + i → Inline chat  
/tests → Generate unit tests  
@workspace → Entire project context  
gh copilot explain → Explain CLI command  
PR summaries use PRUs  
Copilot does NOT compile or deploy apps


# GH-300  
# Section 1.7 – Management & Customization (High-Weightage Notes)

---

# 1️⃣ Copilot Plans & Features

## Plans
- Free
- Pro
- Business
- Enterprise

Free has usage limits.

---

# Management & Security Features by Plan

## Available ONLY in Business & Enterprise

- User management
- Data excluded from training by default
- Enterprise-grade security
- IP indemnity
- Content exclusions
- SAML SSO
- Usage metrics

## Enterprise Only

- Requires GitHub Enterprise Cloud
- Tailor chat to private codebase
- Attach knowledge bases to chat

Exam Focus:
Enterprise-grade security → Business & Enterprise  
IP indemnity → Business & Enterprise  
Tailored private codebase chat → Enterprise only  

---

# Public Code Filter

Purpose:
Blocks suggestions that match public code.

Why Important:
Required to activate IP indemnity.

---

## Who Controls It?

### Organization (Business/Enterprise)
- Admin controls for all members
- Must block public code for IP indemnity

### Personal Paid Account (Free/Pro/Pro+)
- User can toggle Allow or Block

### Org-Provided License
- May be locked by organization policy

Exam Insight:
IP indemnity requires blocking public code at org level.

---

# Contractual Protections

## IP Indemnity
- Legal protection against IP claims
- GitHub assumes responsibility
- Available only in Business & Enterprise
- Requires public code filter blocked

## Data Protection Agreement (DPA)
- Defines data handling & privacy compliance

## Copilot Trust Center
- Transparency on privacy, compliance, security

---

# 2️⃣ Content Exclusions

Purpose:
Prevent specific files, folders, or repos from informing Copilot suggestions.

---

## Configure at Repository Level

Repository → Settings → Copilot  
Specify files/paths to exclude.

---

## Configure at Organization Level

Organization → Settings → Copilot → Content exclusion  
Specify repos/files to exclude.

---

## Impact of Exclusion

When file is excluded:

- No code completion in that file
- File does NOT inform other file suggestions
- File does NOT inform Copilot Chat

Important:
Improves security but reduces context accuracy.

---

## Limitations of Content Exclusion

1. IDE Limitation
   - In some cases (e.g., @github chat participant), exclusion may not apply.

2. Semantic Leakage
   - Type info or hover info may still influence suggestions.

3. Scope Limitation
   - Applies only to licensed org members.
   - Others with access may still get suggestions.

Exam Trap:
Content exclusion does NOT guarantee full isolation in all IDE features.

---

# 3️⃣ Troubleshooting Common Issues

---

## Problem: No Code Suggestions

Check:

- Internet connection
- Extension updated
- IDE compatibility
- Content exclusions blocking file

Exam Answer:
Check internet connection first.

---

## Problem: Content Exclusions Not Working

Possible Causes:

- Takes up to 30 minutes to apply
- Scope not applied to all users
- IDE limitation
- Need to reload IDE

Indicator:
Copilot icon has diagonal line if excluded.

---

## Problem: Poor Suggestions

Improve by:

- Writing clearer comments
- Using meaningful variable names
- Using Copilot commands
- Adjusting prompt length
- Trigger suggestions (Ctrl+Enter in VS Code)

---

# 4️⃣ Plan Selection Considerations

When choosing plan, evaluate:

- Data privacy requirements
- Need for org policy control
- IP indemnity requirement
- Compliance requirements
- Audit logging needs
- SSO requirement

Business & Enterprise → Strongest privacy controls.

---

# 🔥 High-Probability Exam Points

- Enterprise-grade security → Business & Enterprise
- IP indemnity → Business & Enterprise
- Public code filter must be blocked for indemnity
- Content exclusion removes file from influencing suggestions
- Content exclusion may take 30 minutes to apply
- First troubleshooting step → Check internet connection
- Enterprise required for tailoring chat to private codebase

---

# 2-Minute Cram

Business & Enterprise → Security + IP indemnity  
Block public code → Required for indemnity  
Content exclusion → Removes file from Copilot context  
Exclusions may delay up to 30 min  
No suggestions? → Check internet first  
Enterprise → Private codebase chat + knowledge base   
