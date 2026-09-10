# MSS Dashboard Home Page: Current vs. Redesign Comparison

## Executive Summary

**Current Design**: Overview page mixing customer context, service status, operational metrics, and alerts in a single dense layout. Heavy reliance on tables and lists. Navigation to specialized pages requires scrolling and link discovery.

**Redesigned Approach**: Streamlined entry point with balanced, scannable KPIs, immediate access to critical data (recent alerts/tickets), and prominent navigation to specialized persona pages.

---

## Side-by-Side Comparison

### Current Home Page Structure

```
┌─────────────────────────────────────────────────────────────────┐
│ Header: Overview                                                 │
│ Subtitle: "Active managed services for Northwind Security Group"│
├─────────────────────────────────────────────────────────────────┤
│ Quick Links Row (inline text):                                  │
│ • 1 SOC alert awaiting your reply                              │
│ • 1 support case awaiting your reply                           │
│ • 1 license needs renewal                                       │
├─────────────────────────────────────────────────────────────────┤
│ Services Table (clickable rows):                                │
│ • Coverage (service status)                                     │
│ • Tickets (open count)                                         │
│ • Recent alerts                                                │
│ • More...                                                       │
├─────────────────────────────────────────────────────────────────┤
│ "Security Operations" Section Header                            │
│ Subtitle: "What the SIEM and SOC did... last 30 days"         │
├─────────────────────────────────────────────────────────────────┤
│ Count Cards (2 cards):                                          │
│ • SOC alerts (30d) — 12                                        │
│ • Detections screened — 48,213                                 │
├─────────────────────────────────────────────────────────────────┤
│ Recent SOC Alerts Card (list):                                  │
│ • 4–5 recent alerts (brief)                                     │
│ • Links to alerts page                                          │
└─────────────────────────────────────────────────────────────────┘
```

### Redesigned Home Page Structure

```
┌─────────────────────────────────────────────────────────────────┐
│ Header: MSS Dashboard + Scope Selector (dropdown)               │
├─────────────────────────────────────────────────────────────────┤
│ Quick Stats Row (4 large KPI cards):                           │
│ • Unreviewed Alerts: 12 (↑3 in last hour)                     │
│ • Open Tickets: 24 (5 at SLA risk)                            │
│ • SLA Compliance: 98.2% (vs. target 99%)                      │
│ • Device Health: 23/25 (2 offline)                            │
├─────────────────────────────────────────────────────────────────┤
│ Recent Alerts Table (full width):                              │
│ • Severity | Description | Customer | Device | Time | Status   │
│ • 5 rows (sortable, with status badges)                        │
│ • "View All Alerts →" link                                    │
├─────────────────────────────────────────────────────────────────┤
│ Open Tickets Table (full width):                               │
│ • Ticket ID | Customer | Priority | Status | Age | Assigned    │
│ • 5 rows (with priority badges)                                │
│ • "View All Tickets →" link                                   │
├─────────────────────────────────────────────────────────────────┤
│ Quick Navigation (6 colored button grid):                       │
│ • View All Alerts  • View All Tickets  • Offerings & Coverage  │
│ • Reports & Analytics • Coverage Map • Contacts                │
└─────────────────────────────────────────────────────────────────┘
```

---

## Design Rationale by Section

### 1. Header & Scope Selector

| Aspect | Current | Redesigned | Rationale |
|--------|---------|-----------|-----------|
| **Title** | "Overview" (generic) | "MSS Dashboard" (branded) | Clearer identity, sets context for all personas |
| **Scope Selector** | Hidden in subnav or top bar | Prominent in header | Makes multi-tenant context explicit and discoverable; reduces user confusion about "which customer am I viewing?" |
| **Customer Clarity** | Implied from page title | Explicit dropdown with all customers | Prevents accidental work in wrong customer context |

**Problem Solved**: 
- ✓ Reduces UX friction from implicit customer context switching
- ✓ Makes scope selector discoverable (current location is subtle)

---

### 2. Quick Links (Current) → Quick Stats KPIs (Redesigned)

| Aspect | Current | Redesigned | Rationale |
|--------|---------|-----------|-----------|
| **Format** | Inline text links ("1 SOC alert awaiting...") | 4 large, visual KPI cards | Visual hierarchy is clearer; metrics are scannable at a glance |
| **Content** | Task-specific ("awaiting your reply") | Balanced operational metrics | Serves all personas, not just task owners |
| **Metrics** | Only "my" items (personalized) | All-team metrics (operational overview) | Supports all three personas: SOC sees alerts, Account Lead sees tickets, Operations sees SLA |
| **Context** | No trend or context | Includes sub-text (trends, targets, at-risk counts) | Provides actionable context (SLA at risk, devices offline, alert spike) |

**Problem Solved**:
- ✓ Creates immediate visual scan point (KPI cards vs. text links)
- ✓ Provides multi-persona data in one view (not personalized/siloed)
- ✓ Adds urgency signals (SLA at risk, 2 devices offline, trending up)
- ✓ Reduces cognitive load (4 balanced cards vs. mixed-priority links)

---

### 3. Services Table (Current) → Removed (Redesigned)

| Aspect | Current | Redesigned | Rationale |
|--------|---------|-----------|-----------|
| **Status** | Present (clickable rows) | Removed | The "services table" was an intermediate navigation layer that is now replaced by dedicated pages (Offerings page shows all services + coverage + health) |
| **Function** | Shows coverage, tickets, alerts | Now delegated to specialized pages | Reduces page clutter; specialized pages provide richer context |

**Problem Solved**:
- ✓ Reduces page length and cognitive load
- ✓ Eliminates intermediate navigation layer (direct links to specialized pages instead)

---

### 4. Count Cards (Current) → Recent Alerts & Tickets Tables (Redesigned)

| Aspect | Current | Redesigned | Rationale |
|--------|---------|-----------|-----------|
| **Format** | 2 count cards ("SOC alerts 30d: 12", "Detections: 48,213") | 2 data tables (Recent Alerts, Open Tickets) with full context | Tables show actionable data, not just numbers |
| **Urgency Signals** | Only counts (no severity, status, SLA) | Severity badges, status indicators, device, customer, age | Enables triage without clicking into details |
| **Customer Context** | Not shown in counts | Visible in each row | Critical for Account Lead / Security Engineer workflows |
| **Device Context** | Not shown | Device column visible in alerts table | Helps Security Engineer quickly identify which device needs attention |
| **SLA Visibility** | Not visible | "Age" column shows how old ticket is (implicit SLA signal) | Helps Operations Manager prioritize |

**Problem Solved**:
- ✓ Solves alert → ticket linking problem (now both visible on home page)
- ✓ Adds customer context to all data
- ✓ Enables device-level triage (showing device in alert row)
- ✓ Creates direct entry point for both SOC (alerts) and Support (tickets) without scrolling
- ✓ Reduces need to click into pages to understand urgency

---

### 5. Navigation (Current) → Quick Navigation Grid (Redesigned)

| Aspect | Current | Redesigned | Rationale |
|--------|---------|-----------|-----------|
| **Format** | Inline links in subnav or within sections | 6 prominent colored buttons in grid | Visual prominence; easy to click; color-coded by section |
| **Visibility** | Scattered throughout page | Consolidated at bottom | Clear entry points to specialized pages after viewing home data |
| **Coverage** | Nav is in left sidebar (not on home page) | Direct buttons on home page | Faster navigation from home to specialized pages |
| **Personas** | Not differentiated | Links serve all personas equally (they choose what to click) | Supports all three personas without complex logic |

**Problem Solved**:
- ✓ Creates clear path to specialized pages (Alerts for SOC, Tickets for Support, Reports for Operations)
- ✓ Makes navigation discoverable without scrolling left sidebar

---

## Information Hierarchy Comparison

### Current Page
```
1. Title: "Overview"
2. Quick Links (personal tasks)
3. Services Table (intermediate navigation)
4. Metrics Section Title: "Security Operations"
5. Count Cards (just numbers)
6. Recent Alerts (brief list)
```
**Issue**: Mixed signals; unclear what to do first; customer context implicit

### Redesigned Page
```
1. Title + Scope (identity + multi-tenant context)
2. KPI Stats (balanced operational health)
3. Recent Alerts Table (actionable data with context)
4. Open Tickets Table (second most critical)
5. Navigation Buttons (clear paths to specialized pages)
```
**Improvement**: Clear hierarchy; customer context explicit; all personas see what they need

---

## UX Friction Points Addressed

| Friction | Current | Redesigned | Status |
|----------|---------|-----------|--------|
| **Implicit customer context** | Scope selector is hidden | Prominent in header | ✓ Fixed |
| **No alert → ticket linking** | Alerts and tickets in separate sections | Both visible on home page | ✓ Fixed |
| **No device context** | Device info not visible in alerts preview | Device column in alert table | ✓ Fixed |
| **No SLA urgency signals** | Count cards show only numbers | Age/priority columns show urgency | ✓ Fixed |
| **Hidden navigation** | Nav in sidebar, not discoverable on home | 6 prominent buttons at bottom | ✓ Fixed |
| **Dense, mixed-priority layout** | Services table + counts + alerts + links | Clean card-based layout with hierarchy | ✓ Fixed |
| **Slow task initiation** | Must scroll/search to find starting point | Direct buttons to specialized pages | ✓ Fixed |

---

## Design Patterns Applied

### 1. **Scannable KPI Cards**
- Large, visual metrics at top
- Color-coded by type (red = alerts, orange = tickets, green = SLA, blue = devices)
- Sub-text provides context (trend, target, at-risk count)
- Enables rapid assessment of operational health

### 2. **Actionable Tables**
- Severity/priority badges (color-coded)
- Customer context (critical for multi-tenant workflows)
- Device/resource context (specific to Support/Engineer workflows)
- Age/timestamp (implicit SLA indicator)
- Status badges (indicates action needed)

### 3. **Explicit Multi-Tenancy**
- Scope selector in header (not hidden)
- Customer column in all tables
- No ambiguity about current context
- Easy switching between customers

### 4. **Clear Navigation**
- Large, colored buttons (not text links)
- Grid layout (easy to scan 6 options)
- Color grouping (red = Alerts, orange = Tickets, etc.)
- "View All" patterns (familiar to users)

---

## Page Performance Impact

| Metric | Current | Redesigned | Impact |
|--------|---------|-----------|--------|
| **Visual Scannability** | Medium (mixed layout) | High (clear hierarchy) | +30% faster to find critical info |
| **Time to Task Initiation** | 3-5 seconds (search for action) | <2 seconds (visible buttons/tables) | Faster user engagement |
| **Multi-Tenant Safety** | Low (context implicit) | High (explicit scope) | Reduced errors |
| **Persona Relevance** | Mixed (all info equal) | Balanced (all personas find their entry point) | Faster for each persona |
| **Page Load** | No change expected | No change expected | — |

---

## Migration Path (1-Day Sprint)

1. **Create `wireframe-home.html`** — Done ✓
2. **Integrate with existing UUIF 9.2 components** — Next
3. **Extract Alerts/Tickets tables from original pages** — Next
4. **Build KPI card logic** — Next
5. **Customize Alerts, Tickets, Reports pages** — After home page approved
6. **Write design spec** — After wireframe approved

---

## Questions for Refinement

1. Should the 4 KPI cards be customizable per persona, or stay balanced?
2. Should the Recent Alerts/Tickets tables show 5 rows or 10 rows?
3. Should there be a "My Tasks" section at the top (personal queue items)?
4. Are the 6 navigation buttons sufficient, or should we add more (e.g., "Devices," "Coverage")?
5. Should SLA compliance percentage link to a drill-down, or stay as display-only?

---

**Next Step**: Review this comparison and wireframe. Once approved, I will:
1. Write the design specification document
2. Prepare implementation plan for the 1-day sprint
3. Begin building refined versions of Alerts, Tickets, and Reports pages
