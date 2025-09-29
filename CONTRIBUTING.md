# Contributing to UVRN Base

Thanks for your interest in contributing! UVRN Base is public infrastructure — every contribution strengthens the receipts rail.

---

## 🚦 Contribution Workflow

1. **Fork & Branch**

   * Fork the repo and create a feature branch: `feature/your-change`.

2. **Make Changes**

   * Follow existing code style and directory structure.
   * Add or update schemas, examples, or CLI logic as needed.

3. **Validation Required**

   * Every receipt, schema, and example **must validate** before commit:

     ```bash
     pnpm validate -s schemas/receipt.v0.1.schema.json -d examples/receipts/sample-receipt-001.json
     ```
   * PRs that fail validation checks will not be merged.

4. **Tests & Examples**

   * Add acceptance tests for new schemas or features.
   * Update `/examples` to include sample receipts covering new use cases.

5. **Commit & PR**

   * Use clear commit messages.
   * Open a PR against `main`. Template will ask for schema validation proof.

6. **Signed Receipts**

   * Every merge emits a signed receipt in CI.

---

## 📜 Guidelines

* Keep contributions minimal and composable.
* No PII or sensitive identifiers in receipts or examples.
* Use **Ed25519** for signing.
* Follow semantic versioning (`v0.1.x`, `v0.2.x`).

---

## 🧭 Code of Conduct

* Be respectful and constructive.
* Treat this as shared public infrastructure.
* Violations may result in removal of contributions.

---

## 🔍 Checklist Before PR

* [ ] Receipts validate against schemas.
* [ ] New examples/tests included.
* [ ] CI passes (lint + validate + test).
* [ ] No PII or secrets in code or receipts.

---

**Reminder:** UVRN Base is the receipts rail — contributions here shape the standard. Thank you for helping build proof-first infrastructure.
