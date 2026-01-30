# SKILL: Research Protocol Writing

## Overview
This skill guides the generation of high-quality clinical research protocols for AI-based diagnostic studies, validation trials, and retrospective analyses.

## Protocol Structure

### 1. Title Page
- Full protocol title (descriptive, includes study design)
- Protocol version and date
- Principal investigator(s) and affiliations
- Funding sources
- Ethics approval reference (if applicable)

### 2. Synopsis
One-page summary containing:
- Study title
- Objectives (primary, secondary, exploratory)
- Study design
- Population (inclusion/exclusion)
- Sample size
- Primary endpoint
- Timeline

### 3. Introduction

**Structure:**
1. **Clinical context** (2-3 sentences): Disease burden, current diagnostic standard
2. **Knowledge gap** (2-3 sentences): What is unknown or suboptimal
3. **Proposed solution** (1-2 sentences): How AI/technology addresses the gap
4. **Study rationale** (1-2 sentences): Why this study is needed now

**Style:**
- No headers within introduction
- Flow naturally from problem to solution
- Cite key statistics (prevalence, mortality, diagnostic accuracy)
- Avoid overpromising

### 4. Literature Review / Background

**Structure:**
1. Disease pathophysiology (brief)
2. Current diagnostic approaches and limitations
3. Prior AI/ML work in this domain
4. Foundation models or methods being leveraged
5. Knowledge gaps justifying the study

**Style:**
- Concise paragraphs, not exhaustive
- Focus on directly relevant prior work
- Identify specific gaps your study addresses
- 1-2 pages maximum

### 5. Objectives and Hypotheses

**Format:**
```
3.1 Primary Objective
To [verb] the [metric] of [intervention/model] for [outcome] using [comparator].

3.2 Secondary Objectives
- To develop/validate [model B, C, etc.]
- To assess performance stratified by [subgroups]
- To evaluate [additional endpoints]

3.3 Exploratory Objectives
- To investigate [mechanistic questions]
- To explore [hypothesis-generating analyses]
```

**Rules:**
- One primary objective only
- Objectives are measurable and time-bound
- Match each objective to evaluation criteria

### 6. Evaluation Criteria

**Format as table:**
| Objective | Evaluation Criteria | Justification |
|-----------|---------------------|---------------|
| Primary | AUROC, sensitivity, specificity, PPV, NPV | Standard diagnostic metrics |
| Secondary | Subgroup AUROC, calibration | Generalizability assessment |

**Standard metrics for diagnostic AI:**
- AUROC, AUPRC
- Sensitivity at fixed specificity (80%, 90%)
- Specificity at fixed sensitivity (80%, 90%)
- PPV, NPV
- Calibration (observed vs. predicted)
- Net reclassification improvement (NRI)

### 7. Study Design and Population

**7.1 Design Statement**
Single sentence: "This is a [retrospective/prospective] [cohort/validation/diagnostic accuracy] study..."

**7.2 Population**
- Source population and setting
- Timeframe
- Label definitions (positive, negative, extended controls)

**7.3 Inclusion Criteria**
- Numbered list
- Age, diagnosis, data availability requirements
- Be specific about imaging/ECG quality standards

**7.4 Exclusion Criteria**
- Conditions that confound the outcome
- Prior treatments affecting the index test
- Data quality exclusions

### 8. Variables and Data Sources

**Format as table:**
| Category | Variable | Source | In Biobank? |
|----------|----------|--------|-------------|
| Demographics | Age, sex | EHR | Yes |
| Clinical | BMI, comorbidities | Clinic DB | No |

**Categories:**
- Demographics/Clinical
- Genetic
- ECG parameters
- Imaging (Echo, CMR)
- Outcomes/Labels

### 9. Outcomes

**9.1 Primary Outcome**
- Clear definition with thresholds
- Source of ascertainment
- Adjudication process (if applicable)

**9.2 Secondary Outcomes**
- List with definitions

**9.3 Label Definitions (for AI studies)**
| Label | Definition |
|-------|------------|
| Positive | [Specific criteria] |
| Negative | [Specific criteria] |
| Extended Negative | [Controls without disease] |

### 10. Methods

**10.1 Data Collection**
- Sources, extraction process, quality control
- Reference biobanks/registries used

**10.2 Data Preprocessing**
- Signal processing (filtering, normalization)
- Image preprocessing (resolution, cropping)
- Missing data handling

**10.3 Modeling**
For each model, specify:

```
Model [X]: [Name]
- Architecture: [backbone, layers]
- Input: [data type, dimensions]
- Pretraining: [foundation model, if applicable]
- Fine-tuning strategy: [frozen layers, learning rate]
- Output: [prediction type]
- Loss function: [BCE, MSE, etc.]
```

**Hyperparameter Table:**
| Parameter | Value | Rationale |
|-----------|-------|-----------|
| Optimizer | AdamW | Weight decay regularization |
| Learning rate | 1e-4 | Conservative for fine-tuning |
| Batch size | 64 | Memory/stability tradeoff |
| Epochs | 100 | Early stopping, patience=15 |

**Ablation Experiments Table:**
| Experiment | Description |
|------------|-------------|
| A1 | [Variation to test] |
| A2 | [Variation to test] |

### 11. Statistical Analysis

**11.1 Sample Size**
- Power calculation or justification for available sample
- Expected prevalence, desired precision

**11.2 Primary Analysis**
- Metrics computed with 95% CI (bootstrap or DeLong)
- Comparison to reference standard

**11.3 Secondary Analyses**
- Subgroup analyses (prespecified)
- Sensitivity analyses

**11.4 Software**
- Python (scikit-learn, PyTorch), R, SAS
- Version numbers

### 12. Training and Validation Strategy

| Parameter | Value |
|-----------|-------|
| Data split | 70% train / 15% val / 15% test |
| Cross-validation | 5-fold stratified |
| Stratification | By outcome and key confounders |
| Random seed | Fixed (e.g., 42) |

### 13. Ethics and Data Governance

- IRB/REB approval status
- Consent requirements (or waiver justification)
- Data security measures
- Reference to data governance framework (e.g., Cadre de Gestion)

### 14. Timeline

| Phase | Activities | Duration |
|-------|------------|----------|
| 1 | Data preparation | Months 1-3 |
| 2 | Model development | Months 4-8 |
| 3 | Validation | Months 9-12 |
| 4 | Prospective pilot | Months 13-18 |

### 15. Feasibility

Brief section addressing:
- Data availability and sample size adequacy
- Computational resources
- Team expertise
- Funding

### 16. References

Standard citation format (Vancouver or APA)

---

## Style Guidelines

**General:**
- Use active voice
- Be specific and quantitative
- Avoid jargon; define abbreviations
- No em dashes; use commas or parentheses
- No excessive hedging

**Tables over prose:**
- Hyperparameters → table
- Variables → table
- Timeline → table
- Inclusion/exclusion → bulleted list

**Scientific precision:**
- Report thresholds (e.g., "≥70% stenosis" not "significant stenosis")
- Specify units
- Define all acronyms at first use

**Formatting:**
- Numbered sections (1, 1.1, 1.1.1)
- Bold for section headers
- Minimal use of italics
- No bullet points in flowing text; reserve for lists

---

## Quick Reference: Section Lengths

| Section | Target Length |
|---------|---------------|
| Synopsis | 1 page |
| Introduction | 0.5-1 page |
| Background | 1-2 pages |
| Objectives | 0.5 page |
| Methods | 3-5 pages |
| Statistical Analysis | 1-2 pages |
| Ethics | 0.5 page |
| Timeline/Feasibility | 0.5 page each |

---

## Checklist Before Submission

- [ ] Primary objective is single and measurable
- [ ] Inclusion/exclusion criteria are specific
- [ ] Outcomes have clear definitions with thresholds
- [ ] Sample size justified
- [ ] All models have architecture and hyperparameters specified
- [ ] Ablation experiments defined
- [ ] Data sources and biobank coverage clarified
- [ ] Ethics/consent addressed
- [ ] Timeline realistic
- [ ] All abbreviations defined
