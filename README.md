# Anveshan

**Anveshan (अन्वेषण)** is a browser-based forensic investigation workbench for examining digital evidence, testing competing hypotheses, and preparing an auditable draft court report.

It ships as a single-page prototype with a fictional demonstration case:

> **Operation Ghost Ledger** — Case `2026/CY/0417`, an alleged insider data leak involving a UPI payment.

## Highlights

- **Case and evidence workspace** for reviewing evidence items, source details, hashes, and trust scores.
- **Local evidence intake**: add files from the browser or use the included sample evidence. Files are hashed with SHA-256 in the browser.
- **Custody log** with chained hashes and a Merkle root.
- **Integrity verification** and inclusion proofs for individual custody records.
- **Tamper demonstration** that shows how an edited record is detected.
- **Multi-source timeline** covering laptop, USB, firewall, phone, and bank activity.
- **Evidence graph** for exploring relationships between people, devices, events, and evidence.
- **Investigator findings** that can be approved and added to the draft report.
- **Hypothesis comparison** for weighing three possible explanations:
  1. Insider leak for money
  2. Account was hacked
  3. Normal work, misread
- **Evidence-grounded “Ask the case” assistant** that cites evidence IDs and records questions in the custody log.
- **Court report** draft based on Section 63(4) of the Bharatiya Sakshya Adhiniyam, 2023, with a print-friendly layout.
- Light/dark themes, responsive layout, reduced-motion support, and keyboard-accessible controls.

## Run locally

No installation or build step is required.

### Option 1: Open the file directly

Open [`index.html`](./index.html) in a modern browser.

### Option 2: Use a local HTTP server

Serving the folder is recommended for the most consistent browser behavior:

```bash
cd Anveshan
python3 -m http.server 8000
```

Then open <http://localhost:8000> in your browser.

## How to explore the demo

1. Start in **Case and evidence** to inspect the preloaded evidence.
2. Select an evidence row to view its source, analysis, and trust score.
3. Add a local file or use one of the sample files to see browser-side hashing and custody logging.
4. Open **Custody log** and run **Verify whole log**.
5. Use the tamper demonstration, then verify the log again to see the integrity failure.
6. Review the **Timeline**, **Evidence graph**, **Findings**, and **Hypotheses** views.
7. Approve findings before opening **Court report**.
8. Use **Print report** to create a print-friendly draft.

## Repository structure

```text
Anveshan/
├── index.html
├── Images/
│   ├── Ask_the_case.png
│   ├── Court_report.png
│   ├── Dashboard.png
│   ├── Evidence_graph.png
│   └── Hypotheses.png
└── README.md
```

The application UI, styles, demo data, and JavaScript behavior are contained in `index.html`. The images provide screenshots of the main workbench views.

## Privacy and data handling

- Files selected in the evidence intake are processed in the browser.
- SHA-256 hashes are generated with the browser Web Crypto API.
- The prototype does not upload selected files to a server.
- Theme preference is stored locally using `localStorage`.
- The case data is fictional demonstration data and should not be treated as a real investigation record.

## Important limitations

Anveshan is a front-end prototype for investigation workflows and evidence reasoning. It is not a replacement for validated forensic acquisition, expert review, legal advice, secure evidence storage, or a production chain-of-custody system.

In particular:

- Demo trust scores and hypothesis values are illustrative, not calibrated probabilities.
- The court report is a draft and must be reviewed, completed, and signed by the appropriate custodian and expert.
- Browser-side hashing demonstrates the workflow but does not establish that a file was acquired or preserved using a validated forensic process.

## Screenshots

### Dashboard

![Anveshan dashboard](./Images/Dashboard.png)

### Evidence graph

![Evidence graph](./Images/Evidence_graph.png)

### Hypotheses

![Hypotheses view](./Images/Hypotheses.png)

### Ask the case

![Ask the case](./Images/Ask_the_case.png)

### Court report

![Court report](./Images/Court_report.png)
