# uvrn-base

Open receipts rail for apps & agents — JSON schemas, signed Confidence Scores, and a validator CLI.

# 🌐 UVRN Base

**Universal Verification Receipt/Repository Network (UVRN) — Base Layer**

UVRN Base is the open foundation for **verification receipts**.
Apps and agents can emit portable, PII-safe receipts with a **Confidence Score** you can trust, share, and verify anywhere.

---

## 🚀 What’s Inside

* **Receipts:** Portable JSON artifacts, cryptographically signed with Ed25519. Confidence Score = completeness (40%) + parity (40%) + freshness (20%).
* **Schemas:** Machine-readable contracts for runs, checks, and artifacts.
* **Canonicalization:** Deterministic JSON ordering + hashing → stable, portable snapshots across systems.
* **Validator CLI:** Validate receipts locally or in CI/CD pipelines. Every merge must validate.
* **Examples & Tests:** CI recipes and acceptance tests to bootstrap integrations.

---

## 📦 Quickstart

Clone the repo and install dependencies:

```bash
git clone https://github.com/uvrn/uvrn-base.git
cd uvrn-base
pnpm install   # or npm install
```

Run the validator on a sample receipt:

```bash
pnpm validate -s schemas/receipt.v0.1.schema.json -d examples/receipts/sample-receipt-001.json
```

---

## 📜 Receipt Example

```json
{
  "uvrn_version": "0.1",
  "workspace_id": "ws_demo",
  "run": {
    "id": "run_01H...",
    "started_at": "2025-09-28T10:00:00Z",
    "confidence_score": 82
  },
  "checks": [
    {"name":"ga4_reachable","status":"pass"},
    {"name":"conversion_parity","status":"warn","details":{"ga4":12,"ads":15},"source_link":"https://ga4.google.com/..."}
  ],
  "signing": {
    "algo": "ed25519",
    "signature": "base64..."
  }
}
```

---

## 🛠 For Developers

* **Schemas** → `/schemas`
* **Examples** → `/examples`
* **Simulator** → `/simulator` (deterministic healthy/unhealthy states)
* **API Stub** → `/server`

---

## 🤝 Contributing

UVRN Base is public infrastructure. Contributions are welcome!

* Follow CONTRIBUTING.md for guidelines.
* All receipts must validate against schemas before merge.
* Every merge emits a signed receipt.

---

## 🔒 License

Licensed under the Apache 2.0 License.
See LICENSE for details.

---

## 🧭 Why UVRN?

Dashboards assume correctness. AI and apps need proof, not promises.

**Analytics gave visibility. Verification gives confidence.**

UVRN is the receipts rail — the SSL of verification.
Every run emits a receipt. Every receipt is portable, verifiable, and actionable.

**Test → Validate → Canonize → Share.**
