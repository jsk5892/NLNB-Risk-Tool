# NLNB IT Risk Assessment Tool

An interactive application and infrastructure risk assessment tool for **NLNB**, built for the ETI 302 case study. It runs entirely in the browser as a single `index.html` file, with no install, build step, or server.

## Features

- **33 questions** across 8 risk domains drawn from the case:
  1. Legacy Core Infrastructure (AS400, Windows Server, FIN/BODPS)
  2. Integration, Middleware & APIs
  3. AI Model Risk & Explainability (XAI, bias, drift, agentic AI)
  4. Third- & Fourth-Party Risk (AI-enabled vendors, foundation models)
  5. Data Governance & Privacy
  6. Cybersecurity & Access Control
  7. Operational Resilience & Availability
  8. Regulatory Compliance & Governance (DORA, FDIC, agile transition)
- **Business Impact Analysis.** Rates disruption impact for 7 critical bank functions: retail deposits & payments, digital banking, mortgage lending, commercial lending, Sun Investments, fraud/AML, and onboarding/KYC.
- **Live calculations.** Scores update with every answer.
- **Scoring and severity.** Each domain is rated Low, Moderate, High, or Critical.
- **Results dashboard.** Includes a 5×5 heat map, a risk register, disruption exposure for each bank function, key findings, and a top-3 strategic plan with owners and timeframes.
- **Export.** Download the results as CSV, or use Print / Save as PDF.
- Answers are saved automatically in the browser (localStorage).
- A **"Load NLNB sample answers"** button fills in a demo based on the case.

## Scoring methodology

| Measure | Calculation |
|---|---|
| Likelihood (1–5) | Average answer value in the domain (1 = strong control, 5 = weak or absent; "Not sure" = 4) |
| Function impact (1–5) | 0.5 × worst impact + 0.2 × average impact + 0.3 × time sensitivity (max tolerable downtime) |
| Domain impact (1–5) | Highest impact among the functions that depend on the domain (critical = 100%, supporting = 80%) |
| Risk score (1–25) | Likelihood × Impact |
| Disruption exposure (1–25) | Function impact × weighted likelihood of the domains it depends on |
| Overall risk index (0–100) | Average domain risk score ÷ 25 × 100 |

**Severity bands:** Low < 5 · Moderate 5–9.9 · High 10–15.9 · Critical ≥ 16

## Publishing on GitHub Pages

1. Create a new repository on GitHub (for example, `nlnb-risk-assessment`).
2. Click **Add file → Upload files**, add `index.html` and `README.md`, then commit.
3. Go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, then select the `main` branch and the `/ (root)` folder, and click **Save**.
4. After a minute or so, the site is live at `https://<your-username>.github.io/nlnb-risk-assessment/`.

To use the tool locally, open `index.html` in any modern browser.
