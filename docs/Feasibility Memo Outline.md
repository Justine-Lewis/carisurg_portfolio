# Week 5 Interim Feasibility Memo Outline

## One-sentence verdict
The dataset appears feasible for initial triage-level modelling because it contains clinically relevant information available at the triage desk, including demographics, vital signs, and chief complaint indicators; however, modelling should proceed with caveats around sparse chief complaint features, fairness-sensitive variables, possible outliers, and the need to avoid outcome leakage.

## Dataset summary
The dataset contains de-identified adult ED encounters from the Yale EMMLC triage extract. Each row represents one emergency department encounter. The dataset is wide, with approximately 225 columns, of which around 200 are `cc_` chief complaint flags. The main target variable is `esi`, which represents the Emergency Severity Index or triage level. The major feature families are demographics, triage vital signs, chief complaint flags, and outcome-related fields.

## Clinical feature categories
- Demographics: age, gender, race, ethnicity
- Vital signs: heart rate, systolic blood pressure, diastolic blood pressure, respiratory rate, oxygen saturation, temperature, glucose
- Chief complaints: `cc_` binary flags representing the patient’s stated reason for attending the ED
- Target: `esi`
- Outcome not to use as input: `disposition`

## Top 3 quality concerns
1. The dataset is wide and sparse because most columns are chief complaint flags, so many features may have very low counts.
2. Fairness-sensitive variables such as race, ethnicity, gender, and insurance status must be handled carefully.
3. `disposition` must not be used as a model input because it is known after triage and would create leakage.

## Top 3 reasons to proceed
1. The dataset includes clinically meaningful triage inputs such as vital signs and chief complaints.
2. `esi` is a clearly defined triage target with five ordered severity levels.
3. The dataset structure supports a baseline model in Week 6 if cleaning and feature selection are documented.

## Caveats
This dataset is from a US academic hospital, so its patterns may not transfer directly to a Caribbean ED. The model should first be treated as a baseline feasibility exercise, not a deployment-ready clinical tool. Any use of race, ethnicity, gender, or insurance-related variables should be evaluated carefully for fairness and bias.
