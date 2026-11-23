# Aster Playbooks

**Official, text-based Playbook examples and authoring guides for Aster Clinical.**

An Aster Playbook is a portable `.asterplaybook` file containing an ordered list of **Actions**. Aster previews those Actions on the **currently open visit** before the clinician chooses whether to apply them. Think of it as a reusable checklist of document edits, not an executable script.

> **Important:** A Playbook is not a treatment protocol, a diagnosis, a prescription, or an autonomous decision-maker. Review every proposed investigation and instruction for the individual patient. Nothing is saved, printed, exported, or issued automatically by applying a Playbook.

## Start here

1. Browse [`examples/`](examples/) and download a `.asterplaybook` file (use the file's **Raw** view, then save it with the `.asterplaybook` extension).
2. In Aster Desktop, open **Tools → Playbooks… → Import Playbook…**.
3. Open a **synthetic test visit**, select the imported Playbook, and choose **Preview on Active Visit…**.
4. Read every change. Resolve any conflict deliberately; **Apply to this visit** is unavailable until you do.
5. Apply only if appropriate, inspect the resulting document, and **Save** manually when satisfied.

Importing a Playbook **never** changes a visit. You may also import and inspect Playbooks with no visit open.

## Learn

- [Playbook fundamentals](docs/FUNDAMENTALS.md) — Playbooks, Actions, and the preview/apply workflow.
- [Create your own Playbook](docs/WRITING-PLAYBOOKS.md) — small JSON example, supported Actions and common errors.
- [Examples](examples/README.md) — ready-to-import, synthetic files.
- [Contributing](CONTRIBUTING.md) — how to submit a safe, reviewable example.

## Current compatibility

This library initially targets **Aster Desktop PLAYBOOK.1**, `schema_version: 1`.

Supported Actions:

| Action | Purpose |
| --- | --- |
| `investigations.add` | Propose catalogue-based or manual investigation orders. |
| `advice.add_lines` | Append plain-text advice lines to the open visit. |

Aster does **not** currently accept Playbook Actions for prescribing medicines, diagnoses, examination findings, running commands, accessing the network, saving, or printing.

Examples are plain UTF-8 JSON. Download and import manually. Aster validates the file locally; **files are not cryptographically signed or author-authenticated**.

## Project boundaries

This is the **Playbook content and documentation** repository—not the source repository of Aster Desktop. The application itself has separate licensing and release requirements. A public Playbook does not imply that its clinical content is approved for every patient or healthcare setting.

## License

The content in this repository is released under the **[Apache License, Version 2.0](LICENSE)**. Copyright notices and attribution requirements apply; Aster Desktop and any third-party clinical terminology or data remain under their own licenses. See [NOTICE](NOTICE).
