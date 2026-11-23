# Examples

These are **synthetic learning examples**, not ready-made medical orders for a particular patient. Their content must be reviewed by a clinician before use.

| File | Demonstrates |
| --- | --- |
| [`synthetic-clinic-follow-up-instructions.asterplaybook`](synthetic-clinic-follow-up-instructions.asterplaybook) | Adding general follow-up advice without duplication. |
| [`synthetic-routine-blood-test-request.asterplaybook`](synthetic-routine-blood-test-request.asterplaybook) | Ordered catalogue investigations, a manual entry, and advice. |
| [`synthetic-bengali-follow-up-instructions.asterplaybook`](synthetic-bengali-follow-up-instructions.asterplaybook) | UTF-8 Bengali advice lines. |

## Guideline-informed clinical drafts (not prescriptions)

**DRAFT / NOT CLINICALLY APPROVED.** These independently written examples cite published clinical guidelines, but they do not constitute Aster Clinical prescriptions or patient-specific treatment decisions. [See sources, scope, and safety limitations](../docs/CLINICAL-ACS-GUIDELINE-NOTES.md).

| Draft Playbook | Scenario |
| --- | --- |
| [Suspected ACS emergency assessment](clinical-suspected-acs-emergency-assessment.asterplaybook) | Possible ACS before subtype is established |
| [Suspected STEMI emergency transfer](clinical-suspected-stemi-emergency-transfer.asterplaybook) | Possible STEMI / acute coronary occlusion |
| [Possible NSTE-ACS emergency evaluation](clinical-possible-nste-acs-emergency-evaluation.asterplaybook) | Possible NSTEMI or unstable angina |

**How to import:** open a file on GitHub → **Raw** → save it with the original `.asterplaybook` extension → in Aster use **Tools → Playbooks… → Import Playbook…**. Open a synthetic visit, then select **Preview on Active Visit…**.

The two English examples are also shipped in Aster Desktop PLAYBOOK.1 documentation and have been included here as standalone templates. All examples remain subject to Aster's built-in validation on import.
