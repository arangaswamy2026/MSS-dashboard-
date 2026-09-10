# Project Context Document

**Project:** MSS Dashboard (Managed Security Services Portal)  
**Date:** 2026-09-04  
**Source:** Static HTML prototype (mssdashboarddemo.html) — 5.6 MB demo interface built with UUIF 9.2 design system, fictional MSP partner "Northwind"  
**Version:** 1.0

---

## 1. Problem Statement

Managed Security Services (MSS) partners and their enterprise customers need a unified, multi-tenant portal to monitor and manage security services across their customer base. Currently, partners lack a cohesive interface to view alerts, manage firewall and network devices, track support tickets, manage customer contacts, and view service coverage—forcing them to toggle between disparate tools, reducing operational efficiency and visibility.

## 2. ICP (Ideal Customer Profile)

Managed Security Services (MSS) partners who provide security services to enterprise customers. These are typically:
- Mid-to-large MSPs managing multiple enterprise customer accounts
- Partners with dedicated security operations teams (SOC staff) who monitor alerts and manage incidents
- Organizations offering SonicWall security solutions (firewalls, cloud, endpoint protection, network security) to their customers
- Users with responsibility for multi-tenant management, service delivery, and customer support
- Teams accustomed to enterprise security management tools but lacking integrated partner-specific dashboards

## 3. Pain Points

- **Fragmented visibility:** Partner teams must navigate multiple tools to see alerts, device status, and customer service information
- **Alert noise without context:** Raw detections (48,213 screened down to 12 actionable SOC alerts in the demo) create fatigue; partners need meaningful filtering
- **Manual customer filtering:** Inability to quickly pivot between customer views slows response time and increases operational overhead
- **Support ticket fragmentation:** Tickets are scattered across multiple systems with unclear ownership (waiting on partner, waiting on MSS, scheduled/on-hold states)
- **Incomplete service coverage visibility:** Partners lack clear insight into which security services are deployed across which customer units
- **Device management complexity:** Firewall units and other infrastructure lack unified dashboard visibility

## 4. Proposed Solution

An MSS partner portal dashboard that enables:
- **Single sign-on multi-tenant access:** View alerts, devices, and tickets across all managed customer accounts
- **Intelligent alert triage:** Curated SOC alerts ranked by severity with context on raw detection volume screened
- **Customer-scoped filtering:** Quick pivot between customers (Contoso, Fabrikam, Tailspin, Wingtip in demo) to see customer-specific data
- **Device inventory and health:** Visual overview of firewall units, network devices, and cloud services with onboarding and health status
- **Unified ticket management:** Centralized support ticket tracking with state indicators (waiting on you, with MSS, scheduled/on hold, closed)
- **Service coverage dashboard:** View which security offerings are active for each customer
- **Contact management:** Maintain and organize customer contact information by group or customer
- **Flexible reporting:** Generate and export security reports by offering type and customer

## 5. Success Metrics

- **Adoption:** ≥60% of partner SOC team members use the dashboard daily within 60 days of launch
- **Alert response time:** Reduce time from alert discovery to ticket creation from avg. 2 hours to <30 minutes
- **Customer visibility:** Partner teams can identify and remediate service coverage gaps within 24 hours
- **Operational efficiency:** 50% reduction in time spent navigating multiple tools for partner management tasks
- **Device onboarding:** New firewall units reach "active" status within 1 business day of deployment
- **Ticket resolution:** 80% of partner-owned tickets resolved within SLA (currently variable across multiple systems)

## 6. Design Constraints

**Platform:** Web, desktop-first (secondary: responsive tablet support)  
**Target browsers:** Chrome, Firefox, Edge (enterprise standard)  
**Accessibility:** WCAG 2.1 AA (enterprise requirement)  
**Multi-tenancy:** Support unlimited customer accounts per partner with secure role-based access controls  
**Data scope:** Supports multiple service offerings (Firewall, Network, Cloud, CaptureClient endpoint security)  
**Design system:** UUIF 9.2 (SonicWall enterprise design system)  
**Performance:** Dashboard load <2 seconds; alert table pagination support for 50K+ raw detections  
**Authentication:** SSO integration (SAML/OAuth — method TBD)  
**Technical integrations:** Backend APIs for alerts, device inventory, tickets, contacts, service coverage data  
**Language & localization:** English (US/UK) as primary; EU locale support for GDPR-compliant customers

## 7. Open Questions

1. **Real-time vs. polling:** Should the alert feed update in real-time or on a scheduled refresh interval? What is the acceptable latency for alert notifications?
2. **Custom dashboards:** Should partners be able to create personalized dashboard views (e.g., pin frequently viewed customers or alerts)?
3. **Export/reporting:** Should partners export raw data, or only pre-built report formats? What compliance formats are required (SOC 2, PCI-DSS)?
4. **Role hierarchy:** What role levels exist (e.g., partner admin, SOC lead, tier-1 analyst)? Which views should each role access?
5. **Mobile support:** Is a mobile-optimized interface (iOS/Android) required for on-call scenarios, or web-responsive sufficient?
6. **Escalation workflows:** Should the dashboard trigger auto-escalation to SonicWall if a ticket reaches SLA deadline?
7. **Historical data:** How many months of alert and ticket history should be retained? Is data export for compliance audits required?
8. **Alert routing rules:** Should partners define custom alert routing rules (e.g., critical Firewall alerts → specific team)?

## 8. Gaps

1. **User research:** No mention of partner or SOC user interviews. Recommend 8–10 user interviews with target partners before final design to validate pain points and workflows.
2. **Competitive landscape:** No mention of competitor MSP portals (e.g., Fortinet FortiSOC, Check Point Harmony, CrowdStrike) or how this dashboard differentiates.
3. **Data model & API spec:** Exact backend API endpoints, data structures, and performance requirements not documented. Recommend API spec review before frontend build.
4. **Authentication & RBAC:** Role definitions, permission matrix, and SSO integration method not defined. Recommend security design doc.
5. **Rollout & support:** No launch timeline, partner support plan, or training material strategy defined.
6. **Localization scope:** Only English (US) confirmed; EU/GDPR compliance and multi-language support not addressed.
7. **Analytics & telemetry:** No mention of feature usage tracking, performance monitoring, or A/B testing strategy.
8. **Incident response runbooks:** Partner escalation procedures, handoff workflows to SonicWall support, and incident response SLAs not documented.

---

*Generated by project-context skill on 2026-09-04. Add to this document as decisions are made and questions are resolved.*

---

## Next Steps

**Before design finalization:**
1. Prioritize which gaps should be addressed first (recommend user research and API spec review).
2. Validate that the problem statement and success metrics align with product leadership goals.
3. Schedule working session to clarify role hierarchy, data retention policy, and mobile requirements.

**Design phase:**
4. Conduct 8–10 user interviews with target MSS partners to refine workflows.
5. Create wireframes for each dashboard page using UUIF 9.2 component library.
6. Review competitive dashboards to identify differentiation opportunities.
7. Prototype alert triage and customer filtering workflows.

**What gaps should we prioritize addressing before design begins?**
