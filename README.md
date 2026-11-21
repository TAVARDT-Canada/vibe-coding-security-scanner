# Vibe Coding Security Scanner & AI-Generated App Auditor | TAVARDT Canada

[![Licence MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Vibe Coding Security](https://img.shields.io/badge/Vibe%20Coding-Security%20Hardened-00d26a.svg)](README.md)
[![Language](https://img.shields.io/badge/Language-English%20(Canada)-green.svg)](README.md)
[![Engineering](https://img.shields.io/badge/TAVARDT-Cybersecurity-5b3cf5.svg)](https://ag.tavardt.com/ca/cybersecurity/)

Open-source security scanner auditing live applications built with vibe coding tools (Cursor, Lovable, Bolt, v0). Detects leaked frontend API keys, Supabase RLS gaps, exposed sourcemaps, and sensitive files.

Engineered and maintained by the cybersecurity engineering practice at **[TAVARDT Canada](https://ag.tavardt.com/ca/cybersecurity/)**.

---

## 1. Vibe Coding Security Scanner Overview

AI-augmented development and *vibe coding* allows founders to deploy functioning web platforms using **Cursor, Lovable.dev, Bolt.new, v0, and Replit**.

Without security boundary reviews, frontend JavaScript bundles often harbor sensitive credentials, unprotected database tables, and unminified source code.

This repository delivers an automated Python utility to audit **the public perimeter of any deployed web application**, generating actionable findings instantly.

---

## 2. Audited Vulnerabilities & Attack Vectors

| Risk Vector | How It Happens in Vibe Coding | Technical Impact |
| :--- | :--- | :--- |
| **Frontend API Key Leaks** | Private OpenAI (`sk-...`), Stripe, or AWS keys placed in client-accessible `.env` configs. | Unauthenticated visitors extract keys and consume paid API allowances. |
| **Unprotected Supabase RLS** | Supabase database tables created without enabling Row Level Security. | Attackers use the public `anon_key` to query or delete customer tables via REST. |
| **Exposed Production Sourcemaps** | Frontend bundlers deploying `.js.map` files directly to production hosts. | Full application source code is publicly accessible for reverse engineering. |
| **Leaked Infrastructure Files** | Misconfigured edge rules exposing `/.env` or `/.git/HEAD`. | Unauthorized disclosure of production credentials and secrets. |
| **Missing Security Headers** | Missing Content-Security-Policy (CSP), HSTS, and X-Frame-Options. | Vulnerability to Clickjacking and client-side code injection. |

---

## 3. Installation & Quickstart Guide

### Quick Installation

```bash
git clone https://github.com/TAVARDT-Canada/vibe-coding-security-scanner.git
cd vibe-coding-security-scanner
```

### Scan a Target URL

```bash
python scanner.py https://your-app.vercel.app
```

### CLI Arguments

```bash
# Export results as JSON
python scanner.py https://your-app.vercel.app --json

# Skip sourcemap checking
python scanner.py https://your-app.vercel.app --no-sourcemaps
```

---

## 4. Security Engineering & Technical Support

If your diagnostic identified leaked credentials, unprotected database tables, or requires professional hardening:

* **Corporate Portal:** [TAVARDT Canada](https://ag.tavardt.com/ca/cybersecurity/)
* **Technical Contact:** [Contact Engineering Team](https://ag.tavardt.com/ca/contact/)

---

## Licence

Distributed under the open-source MIT Licence. Refer to the [`LICENSE`](LICENSE) file for more information.  
Copyright (c) 2026 TAVARDT Canada.
