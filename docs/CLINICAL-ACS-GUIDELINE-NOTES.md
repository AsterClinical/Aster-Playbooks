# Guideline-referenced ACS / AMI Playbooks

**DRAFT ONLY. These are independent educational summaries informed by published guidelines, NOT an Aster Clinical prescription, individualized treatment plan, substitute for medical judgment, or an endorsement by any guideline publisher.** Aster does not automatically diagnose ACS, select a drug, perform emergency treatment, or determine whether investigations are appropriate. The clinician must select, preview, amend and apply the content, then separately Save if appropriate.

## Sources

1. **2025 ACC/AHA/ACEP/NAEMSP/SCAI Guideline for the Management of Patients With Acute Coronary Syndromes.** JACC, DOI: https://doi.org/10.1016/j.jacc.2024.11.009 ; AHA publication: https://doi.org/10.1161/CIR.0000000000001309
2. **2025 Australian Clinical Guideline for Diagnosing and Managing Acute Coronary Syndromes**, National Heart Foundation of Australia / Cardiac Society of Australia and New Zealand: https://www.heartfoundation.org.au/for-professionals/acs-guideline

References establish traceability to the sources, **not** copyright permission for republishing guideline text or official endorsement. The guidance below uses newly written short wording; no guideline figures, tables, diagrams, algorithms, or extensive passages have been reproduced. Check the original guidelines and current local protocols.

## Three alternative scenarios

| Draft | What it adds | Notes |
|---|---|---|
| [Suspected ACS](../examples/clinical-suspected-acs-emergency-assessment.asterplaybook) | Manual 12-lead ECG and local hs-cTn investigation entries plus urgent emergency assessment advice | Used when ACS is clinically suspected at first medical contact |
| [Suspected STEMI / acute coronary occlusion](../examples/clinical-suspected-stemi-emergency-transfer.asterplaybook) | 12-lead ECG entry and urgent transfer advice | Must not delay emergency transfer / reperfusion evaluation waiting for troponin |
| [Possible NSTE-ACS](../examples/clinical-possible-nste-acs-emergency-evaluation.asterplaybook) | Manual ECG and hs-cTn entries with urgent hospital and serial-testing awareness | NSTEMI or unstable angina must be assessed with clinical context and appropriate serial tests |

**ACS** includes STEMI, NSTEMI and unstable angina; **AMI** includes STEMI and NSTEMI. These are alternative clinician-selected workflows, not three templates that should automatically all be applied to one patient.

## Clinician-only safety review notes

- Review symptoms, vitals, ECG, stability and competing emergencies. Early ECG acquisition/interpretation is crucial; the ACC/AHA guideline describes a 10-minute first-medical-contact goal.
- If ECG is nondiagnostic and suspicion persists, subsequent ECG assessment may be necessary. A normal single ECG or one negative early troponin cannot alone rule out ACS.
- Use high-sensitivity cardiac troponin, where available, within a **validated assay-specific serial testing protocol** at the appropriate emergency facility. Avoid treating a single point-of-care test as a definitive rule-out.
- STEMI or suspected acute coronary occlusion requires immediate emergency reperfusion-pathway evaluation; do not delay referral or ambulance transfer for lab results.
- High-risk or unstable NSTE-ACS requires urgent hospital care. Serial test intervals, monitoring, reperfusion, invasive strategy, medications and definitive diagnosis are **not** provided by the Playbook.
- At an outpatient chamber, do not keep a suspected ACS patient waiting for an investigation if arranging the test delays transfer.
- **No medicines are included.** In particular, this template does not prescribe antiplatelets, anticoagulants, oxygen, nitrates, thrombolytic therapy or their doses; these require case-specific assessment and local protocols.

The current Aster PLAYBOOK.1 format supports only `investigations.add` and `advice.add_lines`. ECG and troponin are `manual_name` investigations because the current built-in catalogue does not provide dedicated ECG/hs-cTn keys. Local assay selection must be verified. The advice becomes patient-facing if the clinician chooses Apply, so check it carefully. No file is safe to use as a conditional decision tree.

## Publication/validation status

- Authored as **draft examples** only; not an approved Aster Clinical clinical guideline or medical product.
- JSON syntax and basic structural limits must be checked.
- **Pending:** actual import, preview, duplicate/conflict and cancel/apply behaviour in an isolated synthetic test profile; independent clinician review and local workflow suitability.
- Any change to referenced guidelines requires a fresh review and new Playbook version.
