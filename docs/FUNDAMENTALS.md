# Playbook fundamentals

An Aster Playbook is a **sequence of actions**, written as a plain-text JSON file with the `.asterplaybook` extension.

- **Playbook:** The complete file, with a title, an optional description, and an `actions` list.
- **Action:** One supported, declarative change to the active visit.
- **Preview:** Aster shows what will be added, what already exists, and what requires a decision.
- **Apply:** The clinician explicitly accepts the proposed edits into the **unsaved** visit.
- **Save:** A separate, normal Aster operation. Applying never saves or prints.

Unlike Ansible Playbooks, Aster Playbooks do not execute tasks on hosts, run shell commands, call network services, or deploy applications. They edit only supported sections of the open clinical document.

## The workflow

```text
Write or download a .asterplaybook
        |
        v
Import into Aster's local Playbook library
        |
        v
Open a synthetic visit; Preview on Active Visit
        |
        v
Review proposed changes and answer every conflict
        |
        +-- Cancel --> no visit changes
        |
        v
Apply to this visit --> unsaved document edits
        |
        v
Review / edit the visit --> Save when ready
```

If an investigation is already on the visit, Aster avoids duplicate orders. If details such as preparation differ, you must choose whether to keep the existing details or use the Playbook's details. There is **no automatic conflict resolution**.

### Library and trust

Importing stores a checked copy in the active Aster profile's Playbook library. Import does not execute a Playbook or change clinical data. Aster checks file structure and supported Actions, but cannot verify who authored the text. Treat every imported file as untrusted clinical content until you have reviewed it.

### What makes a good Playbook?

A good Playbook is narrow, understandable, and easy to review. Keep the title specific, use familiar investigation catalogue keys, and write only prepared instructions suitable for clinician review. Do not pre-fill patient findings or make diagnosis or treatment decisions.
