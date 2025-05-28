# 3-Week MVP Sprint

**Lightning-fast, production‑ready MVPs built with Node.js **22.15** (current LTS), React 18, TypeScript & fully *serverless* AWS CDK — delivered in ≤ 21 days.**

|               |                                                                                                                  |
| ------------- | ---------------------------------------------------------------------------------------------------------------- |
| **Status**    | `🚀 OPEN: 2 free pilot slots`                                                                                    |
| **Flat Rate** | **\$32,000** (after pilots)                                                                                      |
| **Stack**     | Node 22.15 · React 18 · AWS CDK v2 (Lambda + API GW + Cognito) · Dynamo or Aurora Serverless · Stripe Billing |
| **Contact**   | **david @ mackerrichersoftware.com**                                                                                          |

---

## 1 · What is this?

> Compress a typical **3‑month agency build** into **3 weeks** by combining 10 years of full‑stack experience with modern AI scaffolding (Replit AI, GitHub Copilot, etc.).

This repo documents the process, templates, and infrastructure used for every sprint. Two seed‑stage founders will road‑test the workflow **free** in exchange for public case studies and referral(s).

---

## 2 · Sprint Deliverables

* **GitHub repo** with clean, typed monorepo code (apps/ + packages/)
* **Live URL** (AWS Amplify → CloudFront) + custom domain
* **CI/CD** via GitHub Actions → AWS Lambda/Edge
* **Auth** AWS Cogntio
* **Billing** integrated with **Stripe Checkout / Customer Portal**
* **Observability**: CloudWatch dashboards + Log Insights presets
* **Docs**: README, architecture diagram, 60‑min recorded hand‑off
* **Full IP transfer** on final payment (free for first 2 founders)

---

## 3 · AWS Account & Security Hand‑Off

1. **Client‑owned account** → Create a fresh AWS account *or* sub‑account inside your AWS Organization (recommended).
2. **IAM Role Method (preferred)**
   • In the AWS console, create an IAM role named `MvpSprintAdmin`.
   • Select **AWS Account → Another AWS account**, enter my 12‑digit ID (shared privately).
   • Attach the `AdministratorAccess` policy (*scoped least‑privilege policies can be added after hand‑off*).
   • Provide the generated **Role ARN** — no long‑lived keys shared.
3. **Fallback Key Method** → If roles aren’t possible, create an **Admin user**, download temporary AWS access keys, and share via 1Password/LastPass vault.
4. **Local development** uses `AWS_PROFILE=mvp-sprint` plus short‑lived credentials from the role.
5. **At hand‑off** you disable/rotate the role or user; all infra state files, CDK stacks, and Terraform back‑ends remain in *your* account.

---

## 4 · Timeline

| Day | Milestone                                     |
| --: | --------------------------------------------- |
|   0 | Kick‑off call · Scope lock · AWS role granted |
|   3 | Skeleton repo pushed · CI/CD green            |
|   7 | First epic complete · Demo #1                 |
|  14 | Second/third epics · Demo #2                  |
|  18 | Polish · Load test · Security sweep           |
|  21 | Hand‑off · Docs · Founder testimonial         |

---

## 5 · Folder Structure

```
├── apps/
│   └── web/               # React SPA with Amplify library
├── packages/
│   ├── api/               # individual node js lambdas
│   ├── ui/                # shared React components
│   └── stripe/            # Stripe helpers & webhooks
├── infra/                 # AWS CDK stacks (Lambda, API GW, Dynamo, Cognito)
├── .github/workflows/     # CI/CD pipelines
├── docs/
│   ├── architecture.png
│   └── checklist.md       # Readiness checklist
└── scripts/
    └── bootstrap.sh       # local dev setup (npm install & env prep)
```

---

## 6 · Quick Start (Local)

```bash
# 1. Clone
$ git clone https://github.com/your‑org/3week‑mvp.git && cd 3week‑mvp

# 2. Install deps
$ npm install   # uses package‑lock.json for reproducibility

# 3. Dev stack
$ npm run dev    # concurrently runs web + api + CDK watcher
```

> **Note:** First run will prompt CDK bootstrapping into the profile linked to your `AWS_PROFILE` env var.

---

## 7 · Free Pilot Criteria

1. Pre‑seed/Seed founder ≤ 90 days post‑raise
2. ≤ 4 scoped epics (auth, CRUD dashboard, 1 Custom Feature (or Stripe billing), etc.)
3. Daily Slack presence, 30‑min reviews Mon/Wed/Fri
4. Agree to public case study + 3‑sentence testimonial, and a least 1 referral

*Ping* **david @ mackerrichersoftware.com** with subject `PILOT` or open an issue.

---

## 8 · License

Template code in this repo is MIT‑licensed. Client code is owned by the client upon final payment **first 2 clients free transfer**.
