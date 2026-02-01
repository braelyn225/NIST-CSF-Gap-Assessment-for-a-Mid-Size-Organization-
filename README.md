# NIST CSF Gap Assessment for a Mid-Size Organization

## Project purpose
This project delivers an audit-ready NIST Cybersecurity Framework (CSF) gap assessment workbook tailored for a mid-size enterprise (500–2,000 employees). The workbook enables governance, risk, and compliance (GRC) teams to evaluate current controls, quantify maturity gaps, prioritize remediation, and track progress using a repeatable scoring model aligned to NIST CSF v1.1/v2.0.

## NIST CSF methodology
The workbook is structured across the five NIST CSF functions:
- Identify
- Protect
- Detect
- Respond
- Recover

Each control is mapped to its CSF category and subcategory (e.g., ID.AM-1, PR.AC-3). The assessment aligns controls to internal policies, evidence requirements, and accountable owners to support audit readiness and governance reporting.

## Scoring model
- **Current State Score (0–5):** Assesses present control maturity.
- **Target State Score (0–5):** Defines the desired maturity aligned to enterprise risk appetite.
- **Gap Score:** `Target − Current` (auto-calculated).
- **Inherent Risk Score:** `Likelihood × Impact` (auto-calculated, 1–25 scale).
- **Risk Level:**
  - 1–5 = Low
  - 6–11 = Medium
  - 12–19 = High
  - 20–25 = Critical
- **Residual Risk Score:** `MAX(0, Inherent Risk − Mitigation Effectiveness)` (auto-calculated).

## Workbook structure
All sheets are designed for Excel and Google Sheets, with formulas and conditional formatting to auto-update without macros.

### 1) NIST_CSF_Control_Mapping.csv
Authoritative mapping of NIST CSF subcategories to internal controls, policy references, evidence, and ownership.

### 2) Gap_Assessment_Worksheet.csv
Primary assessment worksheet with maturity scoring, risk scoring, and documented rationale.

### 3) Risk_Scoring_Logic.csv
Definitions for likelihood, impact, and risk classification thresholds used by the assessment.

### 4) Remediation_Action_Plan.csv
Action plan tied to gaps with recommended remediation, priority, and status tracking.

### 5) Executive_Dashboard.csv
KPI summaries and auto-updating metrics (function summaries, risk distribution, top 10 gaps). Add pivot tables and slicers on top of these ranges.

### 6) Lookup_Lists.csv
Standardized lists for data validation (risk levels, status, priority, maturity scores, functions).

## How to use the workbook
1. Import each CSV into Excel/Google Sheets as separate tabs using the file name as the sheet name.
2. Apply the conditional formatting rules (below) in the Gap Assessment sheet.
3. Build pivot tables and slicers on the Executive Dashboard sheet using the Gap Assessment data range.
4. Review the Remediation Action Plan for prioritized gaps and track progress over time.

## Required conditional formatting (Gap Assessment Worksheet)
Apply these rules to the **Risk Level** column:
- **Critical**: fill #8B0000, font white
- **High**: fill #FF4C4C, font white
- **Medium**: fill #FFD966, font black
- **Low**: fill #C6E0B4, font black

Apply a 3-color scale to **Gap Score**:
- Min: green
- Midpoint: yellow
- Max: red

Apply data validation lists:
- Risk Level → `Lookup_Lists` table
- Status / Priority / Function → `Lookup_Lists` table
- Maturity Scores → numeric list 0–5

## Executive dashboard guidance
- Create pivot tables grouped by **Function**, **Risk Level**, and **Gap Score**.
- Add slicers for **Function**, **Risk Level**, and **Owner**.
- Build a heat map using conditional formatting on a pivot table summarizing Risk Level by Function.

## Skills demonstrated
- NIST CSF control mapping and maturity analysis
- Risk quantification and residual risk modeling
- Audit-ready documentation and evidence tracking
- Excel/Google Sheets automation with formulas and conditional formatting
- GRC reporting and executive dashboard design