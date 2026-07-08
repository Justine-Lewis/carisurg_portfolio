# Week 5 Feasibility Memo: Mercer ED Triage Dataset
## 1. Verdict

One sentence only:
Proceed to a baseline triage model, with caveats around external validity, leakage exclusion, and continued clinical review.

## 2. Dataset Summary

Plain numbers:
- 55,121 ED encounters
- 226 columns/features
- 5 ESI levels
- About 200 chief-complaint flag variables
- Outcome stored in `disposition`: Admit or Discharge
- Temperature is in Fahrenheit, not Celsius
- Missingness: 0 missing values in the final loaded dataset

## 3. Top Three Concerns and Mitigations

1. External validity  
   The dataset comes from a US academic-hospital setting, so it may not fully represent Mercer General or a Caribbean ED.  
   Mitigation: Use this only as a baseline and require local validation before deployment.

2. Outcome leakage  
   `disposition` and `previousdispo` should not be used as model input because they may contain information unavailable at triage time.  
   Mitigation: Exclude leakage prone columns from the Week 6 modelling feature set.

3. Sparse chief-complaint flags  
   Many `cc_` variables are rare or near constant.  
   Mitigation: Shortlist only clinically meaningful complaint flags and test them carefully during modelling.

## 4. Top Three Reasons to Proceed

1. The dataset has a real triage target  
   ESI is available and clinically meaningful.

2. The dataset has usable triage vitals  
   Age, oxygen device use, oxygen saturation, blood pressure, heart rate, respiratory rate, temperature and glucose are all clinically interpretable.

3. The exploration pipeline is documented  
   The notebook includes dtype audit, missingness calculation, plausibility checks, visualisations and a saved top 10 feature shortlist.

## 5. Caveats and Next Steps

- This is not yet a model.
- Correlations are exploratory, not proof of prediction.
- Caribbean external validity remains untested.
- Week 6 should test a baseline logistic regression and decision tree.
- Model performance should be reviewed separately by ESI level and by demographic groups.

## 6. Top-10 Feature Shortlist

| Rank | Feature | Reason for inclusion |
|---:|---|---|
| 1 | age | Older patients may have less physiological reserve and showed strong association with ESI. |
| 2 | triage_vital_o2_device | Oxygen device use suggests respiratory support needs and higher acuity. |
| 3 | cc_chestpain | Chest pain can indicate acute coronary syndrome or other urgent cardiac conditions. |
| 4 | triage_vital_o2 | Low oxygen saturation reflects respiratory compromise. |
| 5 | cc_shortnessofbreath | Shortness of breath may indicate respiratory or cardiac deterioration. |
| 6 | cc_alteredmentalstatus | Altered mental status may reflect neurologic, metabolic, septic, or toxicologic emergencies. |
| 7 | triage_glucose | Very low or very high glucose can require urgent intervention. |
| 8 | triage_vital_sbp | Systolic blood pressure helps identify shock, hypotension or hypertensive emergency. |
| 9 | triage_vital_hr | Heart rate reflects physiologic stress, pain, infection, arrhythmia or shock. |
| 10 | triage_vital_rr | Respiratory rate is an early marker of respiratory distress or systemic deterioration. |
