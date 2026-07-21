# LACT Blueprint

> **THIS REPOSITORY IS THE OFFICIAL BLUEPRINT OF THE LACT PROJECT.**

This repository contains the architecture, standards, rules, and documentation that define how the LACT Project must be developed.

It is **NOT** a source code repository.

---

# Mandatory Instructions for AI Assistants

If you are an AI software engineer (Devin, Codex, Claude Code, Cursor AI, ChatGPT, GitHub Copilot, or any other coding assistant), you MUST follow these instructions before writing or modifying any code.

## Step 1

Read **README.md** completely.

## Step 2

Read every document inside the `/docs` directory in the following order.

```
docs/

00_PROJECT_CONSTITUTION.md
01_PRODUCT_VISION.md
02_PRODUCT_REQUIREMENTS.md
03_SYSTEM_ARCHITECTURE.md
04_DEVELOPMENT_RULES.md
05_ROADMAP.md
06_TASK_BOARD.md
07_BACKLOG.md
08_DECISION_LOG.md
09_TESTING_STANDARD.md
10_AI_DEVELOPMENT_GUIDE.md
11_MODULE_ARCHITECTURE.md
12_DATABASE_SCHEMA.md
```

Do not skip any document.

---

## Required Understanding

Before writing any code you must understand:

- Project goals
- Product requirements
- System architecture
- Development rules
- Database architecture
- Module responsibilities
- Decision history
- Testing standards

If you have not read these documents, do not continue.

---

# Development Rules

Always follow these principles.

- Documentation First
- Database First
- Requirement First
- Minimal Change Principle
- Single Source of Truth
- Reuse Before Create
- No Unnecessary Refactor
- Respect Module Boundaries

---

# AI Workflow

Every task must follow this workflow.

Read README

↓

Read all documents

↓

Understand architecture

↓

Analyze existing implementation

↓

Identify root cause

↓

Design minimal solution

↓

Implement

↓

Test

↓

Update documentation if required

---

# Documentation Priority

When documentation conflicts with existing code, documentation is considered the official architecture unless a newer decision has been recorded in the Decision Log.

Priority:

1. Project Constitution
2. Product Requirements
3. System Architecture
4. Development Rules
5. Decision Log
6. Module Architecture
7. Database Schema
8. Existing Implementation

---

# Scope

This repository defines:

- Project Architecture
- Development Standards
- Database Design
- Module Responsibilities
- AI Development Rules
- Testing Standards

This repository does **NOT** contain the application source code.

---

# Goal

The purpose of this repository is to ensure that every developer and AI assistant shares the same understanding of the LACT Project before making any implementation decisions.
