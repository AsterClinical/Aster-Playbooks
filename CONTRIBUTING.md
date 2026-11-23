# Contributing Playbooks

We welcome clear, small, human-reviewed example Playbooks.

1. Follow [the authoring guide](docs/WRITING-PLAYBOOKS.md). Use `.asterplaybook` and UTF-8 JSON; `schema_version` must be `1`.
2. Put contributed files in `examples/`, using clear lowercase hyphenated names. Prefer one narrowly scoped purpose per file.
3. State what the example changes in its `description`. Make examples **synthetic** by default.
4. Never submit patient identifiers or records, copyrighted clinical guideline text, third-party proprietary datasets, secrets, commands, or references that look like executable Actions.
5. Validate JSON syntax, then test import and preview in an isolated **synthetic Aster environment**, including duplicate/conflict behavior. JSON syntax checks alone cannot certify compatibility.
6. Include in the pull request: intended use, relevant Aster PLAYBOOK.1 version, what was tested, and any limits or risks.

A Playbook cannot determine whether a test or instruction is clinically appropriate. Contributors and clinicians must review those decisions. Changes to the Aster application Action vocabulary are out of scope for this repository.

By contributing, you agree to license your contribution under this repository's Apache License 2.0. Contributions must be your own or otherwise legally redistributable.
