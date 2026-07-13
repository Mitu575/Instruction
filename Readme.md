# QA Copilot Instruction Repository

This repository contains reusable GitHub Copilot instructions and prompt templates for QA activities, especially for fuel station and POS-related projects.

The main purpose of this repository is to help GitHub Copilot generate more consistent, complete, and project-aware QA outputs such as checklists, requirement analyses, bug reports, and log reviews.

## GitHub Copilot Setup

This repository is already configured for GitHub Copilot through:

- `.github/copilot-instructions.md`
- `.github/instructions/checklist.instructions.md`
- `.github/prompts/checklist.prompt.md`

To use it:

1. Open this repository in VS Code, Visual Studio, or GitHub.
2. Make sure GitHub Copilot and Copilot Chat are enabled in your editor or account.
3. Start Copilot Chat in this repository context.
4. Paste a requirement and ask Copilot to follow the repository QA instructions.

Example request:

```text
Generate a QA checklist for this requirement and follow the instructions in .github/copilot-instructions.md and .github/instructions/checklist.instructions.md.
```

## Purpose

This repository is designed to:

- Standardize QA checklist generation
- Improve requirement analysis
- Reduce missing negative and regression scenarios
- Keep QA outputs consistent across the team
- Reuse the same Copilot guidance across multiple projects
- Support GPOS, TPOS, FCS, Pump Simulator, NearPay, NAMI, Vehicle Wallet, and Dashboard testing activities

## Repository Structure

```text
.github/
├── copilot-instructions.md
├── instructions/
│   ├── checklist.instructions.md
│   ├── common/
│   └── common-tasks/
├── prompts/
│   └── checklist.prompt.md
└── docs/
```

### File Overview

#### `.github/copilot-instructions.md`

This is the main repository-level instruction file.

It defines the overall QA role, project domain, expected behavior, and global rules that GitHub Copilot should follow.

#### `.github/instructions/checklist.instructions.md`

This file contains detailed rules for generating QA checklists.

It guides Copilot to include:

- Requirement analysis
- Functional scenarios
- UI validation
- Positive scenarios
- Negative scenarios
- Boundary scenarios
- Integration validation
- Database validation
- Log validation
- Recovery scenarios
- Regression coverage
- Performance checks
- Device-specific checks
- Localization checks

Each checklist item should begin with:

```text
Verify that...
```

#### `.github/prompts/checklist.prompt.md`

This file contains a reusable prompt template for generating QA checklists.

Replace the placeholder requirement with the actual requirement before using it.

## How to Use

### GitHub.com Copilot Chat

1. Open this repository on GitHub.
2. Open GitHub Copilot Chat.
3. Select this repository as the active context, when available.
4. Paste the requirement.
5. Ask Copilot to follow the QA checklist instructions in this repository.

Example:

```text
Generate a QA checklist for the following requirement.

Requirement:
After TPOS receives an OK response for the STOP command, replace
“Fueling in Progress” with:
“Pump Stopped. Please put the nozzle back. Waiting for basket.”

Follow the QA checklist standards defined in this repository.

Include:
- Requirement summary
- Clarification questions
- Preconditions
- Functional
- UI
- Integration
- Negative
- Boundary
- Recovery
- Logging
- Regression

Each checklist item must start with “Verify that...”
```

### VS Code or Visual Studio

To use these instructions inside another project:

1. Copy the `.github` folder from this repository.
2. Paste it into the root of the target project repository.
3. Open the target project in VS Code or Visual Studio.
4. Use GitHub Copilot Chat normally.
5. Copilot will use `.github/copilot-instructions.md` as repository context.

## Checklist Output Standard

Copilot should generate checklists under relevant sections such as:

```text
Functional
UI
Integration
Negative
Boundary
Recovery
Logging
Regression
Performance
Environment
```

Checklist items should be clear, specific, testable, and non-duplicated.

Good example:

```text
Verify that the waiting message is displayed only after TPOS receives an OK response for the STOP command.
```

Bad example:

```text
Check stop message.
```


## Maintenance

The instruction files should be reviewed regularly.

Update them when:

- A new QA pattern is introduced
- Copilot repeatedly misses the same scenario
- A project flow changes
- New integrations are added
- The same review comment appears multiple times
- Existing rules become outdated

Suggested review frequency:

```text
Quarterly
```

## Contribution Guidelines

When updating this repository:

1. Make one logical change at a time.
2. Use clear commit messages.
3. Keep instructions specific and testable.
4. Include both correct and incorrect examples where useful.
5. Avoid duplicate rules.
6. Update the relevant file rather than adding the same rule in multiple places.

Suggested commit message format:

```text
feat: add QA checklist Copilot instructions
docs: update checklist usage guide
fix: clarify negative scenario rules
refactor: reorganize QA instruction files
```

