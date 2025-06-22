# 📌 **Product Planning**

---

# 1️⃣ Features

## 📂 **Transactions**

| Subitem | Explanation | Dev Notes | MoSCoW |
|---------|--------------|-----------|--------|
| Budgeting | Transactions (income or expense) | Unified CRUD; amount sign or explicit type field | Must |
| Frequency | Set one-time or recurring | Custom recurrence rules | Must |
| Composition | Add breakdown items (e.g., salary + bonus) | Auto-sum gross/net | Should |
| Deductions & Tax | Specify deductions/taxes at transaction or item level | Server computes net | Should |
| Attachments | Upload receipts/invoices | Store in the cloud | Should |
| Category | Tag transaction (salary, food, rent, etc.) | Custom tags | Must |
| Currency Conversion | Convert between different currencies | Subset of ISO 4217 | Should |
| Gross/Net | View gross vs net per transaction | Handled by backend | Must |
| Hourly Rate | Track hourly wage & compute expected pay | Optional helper for gig workers | Should |
| Bank Account | Link each transaction to a bank account | Allows balance tracking per account | Should |
| Installments | Support transactions split over multiple periods | e.g., paying phone in 12x | Should |

---

## 📂 **Overview**

| Subitem | Explanation | Dev Notes | MoSCoW |
|---------|--------------|-----------|--------|
| Overview | View budgets, income, expenses by time | Aggregate from transactions | Must |
| Trends | Charts for time-series | Use chart lib (Victory/Recharts) | Must |
| Export | Download or email CSV/PDF of transactions | Server-side generation | Should |
| Output Control | Classify expenses as Essential, Wants, Savings, Investing | Helpful for planning & reports | Should |
| Financial Goals | Track goals (short, medium, long term) | Use targets + progress bar | Should |
| Financial Planning | Simulate hypothetical changes: salary raise, mortgage | Separate simulation module | Could |

---

## 📂 **Notifications**

| Subitem | Explanation | Dev Notes | MoSCoW |
|---------|--------------|-----------|--------|
| Alerts | Get notified on paydays, overspending, goal progress | In-app & email | Should |
| Payday Reminders | Notify before recurring income date | Use scheduler + FCM | Should |
| Budget/Spending Alerts | Notify if expenses exceed budget | Dynamic rules | Should |
| Goal Reminders | Remind user of goal milestones | Tie with progress tracking | Should |
| Email Recaps | Monthly transaction summaries | Use SendGrid/Firebase | Could |

---

## 📂 **Cross-Platform & Sync**

| Subitem | Explanation | Dev Notes | MoSCoW |
|---------|--------------|-----------|--------|
| Multi-device Sync | Data available on web & mobile | Firebase Firestore | Must |
| Offline Mode | Log transactions offline, sync later | Local storage + sync queue | Must |

---

## 📂 **Security & Auth**

| Subitem | Explanation | Dev Notes | MoSCoW |
|---------|--------------|-----------|--------|
| Account | Register, login, logout | Firebase Auth | Must |
| Encryption | Protect data at rest and in transit | Cloud provider + HTTPS | Must |
| 2FA | Optional extra security | If feasible | Could |

---

# 2️⃣ Milestones

## ✅ **Milestone 1: Core**

**Weeks 1–4** — Users sign up/login and log any transactions (income/expense, composed or not); can link bank accounts and specify hourly rate if needed.

**How to Validate:**  
- Register/login on web and mobile.  
- Add simple/composed transactions with hourly rate and bank account.  
- Verify CRUD operations persist to Firestore.  
- Test frequency and installment settings.

---

## ✅ **Milestone 2: Dashboard, Trends & Budgets**

**Weeks 5–8** — Users view summarized dashboards, trend charts, and plan budgets. Classify outputs as Essential/Wants/Savings/Investing. Create goals.

**How to Validate:**  
- Create budgets, log transactions, check real-time budget usage.  
- Tag expenses correctly as Essential, Wants, etc.  
- Visual charts match transaction data.  
- Set a goal, watch progress bar update.

---

## ✅ **Milestone 3: Notifications & Exports**

**Weeks 9–11** — Enable push/email reminders for recurring transactions, budget alerts, goal reminders. Add CSV/PDF exports.

**How to Validate:**  
- Set payday frequency, verify reminders.  
- Overspend test budgets, confirm push/email alerts.  
- Download CSV/PDF — check accuracy.
- Get reminders about goal due dates.

---

## ✅ **Milestone 4: Planning & Offline-first Polishing**

**Weeks 12–13** — Finalize offline storage, sync conflict handling, add simulation module for planning salary changes, mortgage, etc. QA and pre-release fixes.

**How to Validate:**  
- Log transactions offline, reconnect — ensure no duplicates/conflicts.  
- Simulate hypothetical changes — verify dashboard adjusts.  
- Test on different devices for data consistency.  
- Security review: token validity, encryption.

