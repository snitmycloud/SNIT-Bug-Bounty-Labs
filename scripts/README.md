# SNIT Bug Bounty Scripts

## 1. Introduction

This directory contains helper scripts developed for SNIT Bug Bounty Hunting and Web Application Security Labs.

The scripts are intended to help students organize assessment data, maintain asset inventories, analyze results, and prepare documentation.

All scripts must be used only with authorized targets and approved training environments.

## 2. Planned Scripts

| Script | Purpose |
|---|---|
| `asset_inventory.py` | Organize authorized assets |
| `scope_checker.py` | Compare listed assets against an approved scope list |
| `recon_notes.py` | Store reconnaissance observations |
| `http_header_analyzer.py` | Review saved HTTP response headers |
| `report_generator.py` | Generate a vulnerability report from structured data |
| `evidence_organizer.py` | Organize assessment evidence files |

These are planned helper scripts. Add each Python file only when its implementation has been created and tested.

## 3. Recommended Directory Structure

```text
scripts/
├── README.md
├── asset_inventory.py
├── scope_checker.py
├── recon_notes.py
├── http_header_analyzer.py
├── report_generator.py
└── evidence_organizer.py
```

## 4. Script Descriptions

### 4.1 Asset Inventory

**Filename:** `asset_inventory.py`

Purpose:

- Store authorized asset details.
- Organize domains and subdomains.
- Record asset type and verification status.
- Export an inventory for assessment documentation.

Example inventory fields:

```text
Asset
Asset Type
Program
Scope Status
Verification Date
Notes
```

### 4.2 Scope Checker

**Filename:** `scope_checker.py`

Purpose:

- Compare an asset against a manually maintained approved scope list.
- Identify exact matches.
- Flag unmatched assets for manual review.
- Help prevent accidental out-of-scope testing.

Important: A simple text comparison is not a substitute for reviewing the official program policy. Wildcards, exclusions, redirects, third-party services, and policy changes require careful human verification.

### 4.3 Reconnaissance Notes

**Filename:** `recon_notes.py`

Purpose:

- Record reconnaissance observations.
- Store DNS and technology information.
- Maintain assessment notes.
- Export structured records.

### 4.4 HTTP Header Analyzer

**Filename:** `http_header_analyzer.py`

Purpose:

- Read saved HTTP response headers.
- Identify security-related headers.
- Organize observations.
- Prepare a review summary.

The script should analyze saved evidence rather than automatically probe arbitrary websites.

### 4.5 Report Generator

**Filename:** `report_generator.py`

Purpose:

- Create structured vulnerability reports.
- Include affected assets and endpoints.
- Add severity and impact descriptions.
- Include remediation recommendations.
- Export Markdown reports.

### 4.6 Evidence Organizer

**Filename:** `evidence_organizer.py`

Purpose:

- Organize screenshots and supporting files.
- Apply consistent filenames.
- Maintain evidence references.
- Help students prepare report attachments.

Do not store passwords, session tokens, or unnecessary personal information in evidence folders.

## 5. Recommended Data Formats

Use simple formats that students can understand and edit.

| Format | Use |
|---|---|
| CSV | Asset inventories |
| JSON | Structured assessment information |
| Markdown | Reconnaissance notes and reports |
| TXT | Basic tool output |
| PNG | Screenshots and evidence |

## 6. Python Environment Setup

Check Python:

```bash
python3 --version
```

Create a virtual environment from the repository root:

```bash
python3 -m venv .venv
```

Activate it on Kali Linux:

```bash
source .venv/bin/activate
```

Upgrade pip:

```bash
python -m pip install --upgrade pip
```

When scripts require third-party packages, document them in a `requirements.txt` file and install only the required dependencies.

## 7. Script Development Guidelines

Every script should:

- Have a clear purpose.
- Validate its input.
- Handle errors gracefully.
- Avoid unnecessary network requests.
- Avoid modifying target systems.
- Store output in an organized format.
- Include usage instructions.
- Be tested with sample or fictional data.

## 8. Suggested Development Roadmap

| Stage | Development Task |
|---|---|
| 1 | Asset Inventory Script |
| 2 | Scope Checker |
| 3 | Reconnaissance Notes Manager |
| 4 | HTTP Header Analyzer |
| 5 | Vulnerability Report Generator |
| 6 | Evidence Organizer |

## 9. Safety Guidelines

- Use only authorized assessment data.
- Do not automate testing outside approved scope.
- Do not perform destructive actions.
- Do not store real credentials or session tokens.
- Review script output before using it in a report.
- Keep sensitive assessment evidence secure.

## 10. Expected Learning Outcome

After completing the scripts exercises, students should be able to:

- Organize authorized asset information.
- Maintain structured reconnaissance notes.
- Review saved HTTP response headers.
- Generate vulnerability reports.
- Organize assessment evidence.
- Understand safe scripting practices.

**SNIT Training Institute | Bug Bounty Hunting & Web Application Security Labs**
