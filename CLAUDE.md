# MSS Dashboard Design Project

## Project Overview
This is an interactive prototype for a Managed Security Services (MSS) dashboard designed for SonicWall partners managing multiple customers' security infrastructure. The dashboard aggregates security operations, service management, and portfolio health across multiple customers.

**Target Audience:** MSS partners, service coordinators, account managers, security operations centers (SOC), and technical staff.

---

## User Personas & Primary Use Cases

### 1. **Partner Executive / Account Owner**
- **Goal:** Understand portfolio health and identify revenue opportunities
- **Primary Pages:** Overview, Coverage, Reports
- **Key Questions:** Portfolio health? Revenue opportunities? SLA status?

### 2. **SOC Operator / Security Analyst**
- **Goal:** Triage and respond to security incidents efficiently
- **Primary Pages:** Alerts, Reports, Tickets (for incident-related cases)
- **Key Questions:** What needs immediate action? What is the threat? Which customer is affected?

### 3. **Customer Success / Support Coordinator**
- **Goal:** Manage service tickets and maintain customer satisfaction
- **Primary Pages:** MSS Tickets, Contacts, Overview
- **Key Questions:** What cases need attention? Who is waiting? What is overdue?

### 4. **Technical Operations / Infrastructure Manager**
- **Goal:** Maintain and optimize managed infrastructure
- **Primary Pages:** Firewall Management, Coverage, Reports
- **Key Questions:** Fleet health? Compliance? Utilization? EOL timeline?

### 5. **Compliance / Risk Officer**
- **Goal:** Ensure security posture and audit readiness
- **Primary Pages:** Reports, Coverage, Alerts
- **Key Questions:** Compliance violations? Threat trends? Audit evidence?

---

## Page-by-Page User Scenarios & Priorities

### **1. Overview / Dashboard** (🔴 HIGHEST PRIORITY)
**Purpose:** Partner entry point—immediate snapshot of what needs attention and portfolio health

**Ordered Critical Questions:**
1. ⚠️ What requires my immediate attention right now? (Pending replies, critical alerts, expired licenses)
2. 🚨 Are there any SLA breaches or overdue items?
3. 🔴 Do I have any critical security incidents in progress?
4. 📊 What is the aggregate security posture? (Threats blocked, detections/day)
5. 📈 How many managed services/units across portfolio?
6. 🎯 What is coverage distribution? (Which services deployed where)
7. 📉 What are 30-day trends? (Alerts trending? Ticket volume?)

**Currently Shown:**
- 3 items waiting on reply
- 4 active services, 4 customers
- 4 open MSS cases
- 1 SOC alert awaiting reply, 12 total (30d)
- 48,213 detections screened
- 18m avg time to notify (critical)
- Service table with metrics

**Missing Critical Questions:**
- ❌ Are any customer SLAs at risk of breach?
- ❌ What is ticket backlog age (avg time to resolution)?
- ❌ Which customer is consuming most MSS resources?
- ❌ Are there compliance violations or policy breaches?
- ❌ What is the MSS spend/utilization trend?
- ❌ What is the customer health score? (overall satisfaction, health)

**Recommended Additions:**
- SLA breach indicator (per customer)
- Ticket aging bucket (0-24h, 1-3d, 3-7d, 7d+)
- Top issue summary (by frequency, by revenue impact)
- Compliance status indicator
- Spend vs. budget YTD

---

### **2. Security Alerts** (🔴 HIGHEST PRIORITY)
**Purpose:** SOC triage and incident response—quickly identify what needs action

**Ordered Critical Questions:**
1. 🚨 Are there CRITICAL alerts requiring immediate escalation?
2. ⏰ Which alerts are waiting for my action vs. in-progress?
3. 🛡️ How many incidents represent breach vs. policy violation?
4. 📊 What is severity breakdown of open alerts?
5. 👥 Which customer is most affected by recent alerts?
6. 📈 Are alerts increasing or decreasing? (trend)
7. 🔍 How much noise was filtered from 48k raw detections?
8. ⏱️ What is time-to-notify metric for critical incidents?

**Currently Shown:**
- SOC ALERTS (ALL-TIME): 12
- CRITICAL: 1, MAJOR: 1, MINOR: 6
- DETECTIONS SCREENED: 48,213
- Alert table with: Ticket #, Severity, Customer, Alert description, Status, Age

**Missing Critical Questions:**
- ❌ Which alerts are part of same incident/attack chain?
- ❌ What is MTTR (Mean Time to Remediation)?
- ❌ Are there patterns (repeat alerts from same source/customer)?
- ❌ What is correlation between alerts and tickets?
- ❌ Which alerts represent compliance violations?
- ❌ What is alert resolution rate (% closed vs. active)?

**Recommended Additions:**
- Incident grouping (related alerts linked)
- Alert age indicator (fresh vs. aging)
- Repeat incident warning (if seen before)
- Remediation status per alert
- Compliance classification (breach vs. advisory)

---

### **3. MSS Tickets / Support Cases** (🔴 HIGH PRIORITY)
**Purpose:** Service ticket management—track customer requests and ensure SLA compliance

**Ordered Critical Questions:**
1. 🚨 How many cases are waiting on MY response and overdue?
2. ⏰ Are there any SLA violations in active progress?
3. 🚫 Which cases are blocking customer operations?
4. 📊 What is total open case count and age distribution?
5. 🔧 Which service type has most open cases? (Firewall, Cloud, Endpoint)
6. ⏱️ What is average resolution time?
7. 👥 Which cases are with MSS vs. awaiting customer action?
8. 🔄 Are there recurring issues from same customer/service?

**Currently Shown:**
- OPEN CASES: 4
- WAITING ON YOU: 1 (overdue a reply)
- WITH MSS: 2
- LONGEST WAIT: 2+ days
- Case table with: Case #, Service, Summary, Waiting on, Age

**Missing Critical Questions:**
- ❌ What is customer satisfaction per case?
- ❌ Which cases are escalated or marked urgent?
- ❌ What is correlation between alerts and tickets opened?
- ❌ Are there cases pending parts/third-party?
- ❌ What is typical resolution time by service type?
- ❌ What is the ticket backlog trend?

**Recommended Additions:**
- SLA timer (time remaining before breach)
- Priority indicator (by urgency, by revenue)
- Escalation history (is this case escalating?)
- Related incidents (linked alerts/tickets)
- Customer impact category (critical, high, medium, low)
- First response time metric

---

### **4. Coverage / Service Coverage** (🟠 MEDIUM-HIGH PRIORITY)
**Purpose:** Portfolio analysis—identify security gaps and upsell opportunities

**Ordered Critical Questions:**
1. 🎯 Where are biggest security gaps in portfolio? (missing services/customers)
2. 🚨 Which customers are NOT protected for critical services? (Firewall, MDR, Cloud)
3. 💰 What is revenue opportunity? (% adoption per service)
4. 📅 Which licenses are expiring soon and need renewal?
5. 📊 What is adoption rate per service across customer base?
6. 🆕 Which customers have onboarding in progress?

**Currently Shown:**
- Service coverage as circular progress meters:
  - MANAGED FIREWALL: 100% (4/4 customers - MPSS)
  - ENDPOINT: 50% (2/4 customers - Capture Client)
  - CLOUD & EMAIL: 75% (3/4 customers - Avanan)
  - NETWORK: 75% (3/4 customers - MDR for Network)
  - IDENTITY: 0% (not subscribed)
  - VULNERABILITY: 0% (not subscribed)
- LICENSES NEEDING RENEWAL: 1 expired

**Missing Critical Questions:**
- ❌ What is revenue impact of coverage gaps? ($ opportunity)
- ❌ Which customers should be prioritized for upsell? (risk score)
- ❌ Are customers under-utilizing purchased services?
- ❌ What competitive threat exists? (which customers lack services competitors offer)
- ❌ What is license renewal schedule and cost forecast?
- ❌ What is average $ value of gap per customer?

**Recommended Additions:**
- Revenue impact per gap ($)
- Upsell priority ranking per customer
- Competitive positioning (gaps vs. market standard)
- License renewal calendar with cost forecast
- Utilization metrics (deployed vs. licensed)

---

### **5. Reports (Security Operations)** (🟠 MEDIUM PRIORITY)
**Purpose:** Executive reporting—demonstrate MSS value, compliance posture, threat trends

**Ordered Critical Questions:**
1. 💵 What is ROI of MSS investment? (Threats stopped, incidents prevented, cost-per-protected-asset)
2. 📊 What is SOC efficiency? (Detection rate, false positive rate, auto-closure rate)
3. 📈 Are customers more secure than before MSS? (trend)
4. 💾 How much data ingested/processed daily/monthly?
5. 📊 What is incident escalation rate? (% of detections → alerts → critical)
6. ⏱️ What is time-to-notify for critical incidents?
7. 📋 Are all detections properly documented for audit?
8. 🎯 What is threat landscape? (top threats, attack vectors)

**Currently Shown:**
- SECURITY OPERATIONS REPORT - LAST 30 DAYS
- 2.1 TB ingested, 48,213 detections triaged, 2 needed attention
- 100% closed by SOC automation (no tickets created)
- 12 escalated to SOC analyst and triaged
- 2 critical incidents this month
- 0.4 alerts/day average, 1 on busiest day, 19 quiet days
- 2 critical alerts on Aug 15 & 17
- SOC ALERTS BY SEVERITY: Critical 2, Major 4, Minor 6

**Missing Critical Questions:**
- ❌ What is compliance posture trend? (audit findings, policy violations)
- ❌ Are there insider threats or anomalous behavior?
- ❌ What is MTTR by severity and by customer?
- ❌ Which customers have highest threat exposure?
- ❌ What are top remediation recommendations?
- ❌ What is the false positive rate?
- ❌ ROI calculation: cost saved vs. MSS spend

**Recommended Additions:**
- Compliance trend chart (violations over time)
- Top threats ranking (most common, highest impact)
- MTTR by severity level
- False positive analysis
- Customer risk ranking
- MSS ROI calculation (threats prevented, cost savings)

---

### **6. Firewall Management** (🟡 MEDIUM PRIORITY)
**Purpose:** Infrastructure management—monitor fleet health, compliance, lifecycle

**Ordered Critical Questions:**
1. 🚨 Are any firewalls out-of-compliance or at risk? (firmware, config, licenses)
2. 🆕 Are there onboarding firewalls that are blocked/delayed?
3. 📊 What is firmware currency? (% at recommended level)
4. 📈 What is total managed fleet size and distribution?
5. 🕐 What are EOL dates for models in use?
6. 🔴 Are there hardware issues or performance warnings?

**Currently Shown:**
- FIREWALLS UNDER MANAGEMENT: 5
- SERVICE TIER MPSS: 5
- CUSTOMERS: 4
- ONBOARDING: 1 in progress
- FIRMWARE: 0 (at or ahead of recommended)
- FIRMWARE DISTRIBUTION: 7.2.2-7010 (2), 7.1.3-7015 (1), 6.3.4-8th (1), 9.2.0-4002 (1)
- MODELS: SZ470, SZ3470, NSa 2700, SZ270, NSa 3700 (1 each)

**Missing Critical Questions:**
- ❌ What is firewall utilization? (CPU, memory, throughput vs. capacity)
- ❌ Are there security policy violations on firewalls?
- ❌ What is backup/recovery status per firewall?
- ❌ Which firewalls need optimization/tuning?
- ❌ What are licensing/support contract expirations?
- ❌ What is hardware refresh cycle/budget needed?

**Recommended Additions:**
- Utilization heatmap (by unit)
- Support contract expiration dates
- Performance warnings/alerts
- Backup status indicator
- Configuration compliance score per unit
- Hardware refresh forecast

---

### **7. Contacts / Notification Contacts** (🟡 LOW-MEDIUM PRIORITY)
**Purpose:** Administrative reference—maintain escalation contacts and notification preferences

**Ordered Critical Questions:**
1. 👤 Who are primary contacts for escalations and emergencies?
2. 🔔 Who should receive SOC alerts vs. business notifications?
3. ⚠️ Are all critical roles represented? (gaps in coverage)
4. ✅ Are contact details current and verified?
5. 🚫 Are there contacts on do-not-contact or on leave?

**Currently Shown:**
- CONTACTS: 4 on file
- Contact table: Name, Title, Email, Phone, Receives
- Examples: IT Director, Security Analyst, Operations Lead, Practice Manager
- Notification categories shown: SOC Alerts, SOC Emergency, After Hours Contact

**Missing Critical Questions:**
- ❌ What is escalation chain? (who escalates to whom when)
- ❌ Are notification preferences configured per service?
- ❌ How recent is contact info? (last verified date)
- ❌ Are geographic/language-specific requirements set?
- ❌ What is backup contact if primary is unavailable?

**Recommended Additions:**
- Escalation chain visualization (primary → secondary → tertiary)
- Last verified date per contact
- On-call schedule indicator
- Language preferences
- Availability status (on leave, on sabbatical)

---

## Critical Cross-Page Gaps (Design Priorities)

| Missing Insight | Impact | Affects Pages | Suggested Solution |
|---|---|---|---|
| SLA Risk Monitoring | HIGH | Overview, Tickets, Reports | Real-time SLA timer + breach predictor |
| Customer Health Score | HIGH | Overview, Coverage | Aggregate metric (threats, tickets, coverage) |
| Ticket Aging/Backlog | HIGH | Overview, Tickets | Age bucket distribution + MTTR trend |
| Incident Correlation | MEDIUM | Alerts, Tickets | Link related alerts to tickets |
| Revenue Opportunity | MEDIUM-HIGH | Coverage | $ value per gap + total upsell pipeline |
| Compliance Violations | HIGH | Alerts, Reports | Compliance classification on alerts |
| MTTR by Severity | MEDIUM | Reports, Tickets | Trend analysis over time |
| Utilization Metrics | MEDIUM | Firewall Mgmt, Coverage | % of deployed vs. licensed capacity |
| Customer Satisfaction | MEDIUM | Tickets, Overview | NPS or satisfaction score per account |
| Repeat/Pattern Issues | MEDIUM | Alerts, Tickets | Clustering/pattern detection |

---

## Design Principles for This Dashboard

1. **Action-First Layout:** Most critical questions appear above the fold; users should see what needs action immediately.

2. **Progressive Disclosure:** High-level metrics first, drill-down details on demand (linked pages, expandable sections).

3. **Color-Coded Urgency:** 
   - 🔴 Red = Immediate action required (SLA breach, critical alert, security incident)
   - 🟠 Orange = Important, needs attention soon (aging tickets, expiring licenses)
   - 🟡 Yellow = Informational, relevant for planning (trends, forecasts)

4. **Multi-Customer Context:** All pages should support filtering by customer to allow partner staff to focus on specific accounts.

5. **Notification Preferences:** Users can configure what alerts they see (severity, service, customer, type).

6. **Audit Trail:** All actions logged; timestamps and responsible party recorded for compliance.

7. **Mobile-First Responsive:** Dashboard should work on mobile for quick status checks (alerts, urgent tickets).

---

## Current Prototype Status

**File:** `mssdashboarddemo-v2.html`
- Static, fictional data (Northwind Security Group + 4 customers)
- All 7 main pages implemented
- Customer filtering supported on all pages
- UUIF 9.2 design system applied

**Pages Completed:**
✅ Overview / Dashboard
✅ Security Alerts
✅ MSS Tickets
✅ Reports
✅ Coverage
✅ Firewall Management
✅ Contacts

**Next Iteration Priorities:**
1. Add SLA monitoring to Overview + Tickets
2. Add customer health score to Overview
3. Add incident correlation (alerts → tickets)
4. Add compliance classification to Alerts
5. Add revenue upsell ranking to Coverage

---

## Reference Data Model

### Core Entities:
- **Partner Account** (Northwind Security Group)
- **Customers** (4 test accounts: Contoso Dental, Fabrikam Logistics, Tailspin Credit, Wingtip Toys)
- **Services** (MPSS Firewall, Avanan Email/Cloud, MDR Network, Capture Client Endpoint, Identity, Vulnerability)
- **Managed Units** (5 firewalls, 3 cloud tenants, 3 network devices, 190 endpoints)
- **Incidents** (SOC alerts, security events, policy violations)
- **Tickets** (Support cases, service requests, incident response)
- **Contacts** (4 per account, with roles and notification preferences)

### Key Metrics:
- Detections Screened: 48,213 (30d)
- SOC Alerts: 12 total (Critical: 2, Major: 4, Minor: 6)
- Open Cases: 4 (Waiting on partner: 1, With MSS: 2, On hold: 1)
- Avg Time to Notify (Critical): 18 minutes
- Coverage: Firewall 100%, Endpoint 50%, Cloud 75%, Network 75%, Identity 0%, Vulnerability 0%

---

## Collaboration Notes

**Design System:** UUIF 9.2 (reference: `uuif-9.2.eng.sonicwall.com`)
- Do NOT mix with other design systems
- Use design tokens for colors, spacing, typography
- Component library: nav, forms, overlays, data tables, icons

**Stack:** Static HTML/CSS prototype (standalone)
- Can convert to React + Vite for interactivity
- No backend required for demo
- Serve locally with `python3 -m http.server 8765`

**Design Tool:** Figma (when design iteration needed)
- Use `figma-use` and `figma-generate-design` skills
- Sync design-to-code via Code Connect

---

## Questions for Stakeholders

Before next iteration, clarify:
1. Should dashboard be real-time or batch-updated (daily/weekly)?
2. What is acceptable alert latency? (SoC notified in minutes vs. hours?)
3. Are there regulatory/compliance requirements that affect data display?
4. Should mobile view be limited to read-only or full functionality?
5. What is the prioritized backlog for "must-have" vs. "nice-to-have" features?
6. Is there a roadmap for multi-partner (platform view) vs. single-partner dashboard?
