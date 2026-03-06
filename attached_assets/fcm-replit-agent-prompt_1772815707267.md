# FCM INTELLIGENCE PWA — REPLIT AGENT PROMPT
# 
# Instructions: Copy everything below the line into Replit Agent.
# The prompt is structured to give Agent maximum context in one shot.
# After Agent builds the scaffold, export to GitHub and hand to Claudia
# for brand refinement and agent system integration.
#
# ═══════════════════════════════════════════════════════════════════

Build me a full-stack Progressive Web App called "FCM Intelligence" using the following specification. This is a real business application for a UK Post Office franchise operator with 40+ branches.

## Tech Stack (REQUIRED — do not substitute)

- Framework: Next.js 14+ with App Router (NOT Pages Router)
- Language: TypeScript
- Styling: Tailwind CSS
- Authentication: NextAuth.js with Email Magic Link provider
- Database: Supabase (PostgreSQL)
- PWA: next-pwa or Serwist for service worker
- Charts: Recharts
- Deployment target: Vercel

## Brand Design (STRICT — apply everywhere)

This is a premium, dark-themed brand. Apply these rules to EVERY page:

Colors:
- Background: #000000 (primary), #1A1A1A (cards/secondary)
- Text: #FFFFFF (primary), #888888 (muted/secondary)
- Accent/CTA: #FFD700 (gold — ALL buttons, highlights, active states, key data)
- Alert/Brand: #FF0000 (alerts only, used sparingly)
- Gold hover: #E6C200
- Card border: #333333

Typography:
- Import Google Fonts: Inter (400, 500, 600, 700) and JetBrains Mono (400, 500)
- Headings: Inter, weight 700
- Body: Inter, weight 400
- ALL financial data, numbers, metrics, scores: JetBrains Mono in gold (#FFD700)

Buttons:
- Primary: Gold background (#FFD700), black text (#000000), rounded-md
- Primary hover: #E6C200
- Secondary: Transparent, 1px gold border, gold text
- Secondary hover: Gold fill with black text
- Min touch target: 44x44px

Cards:
- Background: #1A1A1A
- Border: 1px solid #333333
- Border-radius: 0.5rem
- Padding: 1.5rem
- Hover: border transitions to gold

## Three-Layer Architecture

This app has THREE access levels. Authentication determines what each user sees.

### Layer 1: Public Pages (no login required)

**Homepage (/):**
- Hero section: "40+ Post Offices. One Intelligence System." with two CTAs: "Become an FCM Insider" (gold primary button) and "Learn More" (secondary button)
- Stats bar: "40+ Branches | 17+ Years Experience | £1m+ Invested" — numbers in JetBrains Mono gold
- "What is FCM Intelligence?" section with 3 feature cards: Opportunity Scanning, Market Intelligence, Thought Leadership
- Latest Insights section showing 3 most recent blog posts
- FCM Insider CTA section
- Footer with logo space, nav links, contact (mikesh@interimenterprises.co.uk), and disclaimer

**About (/about):**
- Mikesh's story (founder section with large text quote)
- FCM by the numbers (stats in JetBrains Mono gold)
- Values section (3 real values, NOT placeholders)
- Contact CTA

**Services (/services):**
- Grid of service cards: Application Support, Training, Retail Support, Recruitment, Holiday Cover, Auditing, Full Office Management, Insurance, Business Support, Buying & Selling
- Each card has an icon, title, brief description

**Blog (/blog):**
- Grid of blog post cards with title, excerpt, date, category tag
- Filter by category: "PO Insider" and "UK Business Strategy"
- Individual post pages (/blog/[slug])

**Contact (/contact):**
- Contact form: Name, Email, Phone, Message, Report Package dropdown
- Direct contact: mikesh@interimenterprises.co.uk
- Response time: "Within 24 hours"

### Layer 2: Mikx Dashboard (/dashboard — admin only)

Protect all /dashboard routes. Only the admin email (mikeshparekh@gmail.com) can access.

**Dashboard Home (/dashboard):**
- Agent Status panel: 6 agents shown as status cards with name, status indicator (green/yellow/red), last output timestamp, hours since output. Use sample data for now:
  - Henry: Active, 2h ago
  - Claudia: Active, 1h ago  
  - Harper: Idle, on-demand
  - Rex: Idle, awaiting submissions
  - Sentinel: Idle, awaiting submissions
  - Watchtower: Active, monitoring

- Today's Brief panel: Weather, calendar events count, urgent emails count, top opportunity summary

- Opportunity Pipeline: Horizontal kanban-style bar showing counts for NEW, WATCH, PURSUE, CLOSED stages. Clickable to go to /dashboard/opportunities

- Content Pipeline: Shows items in Draft → Review → Approval stages with count badges

- Cost Tracker panel: Today's spend, this week, projected monthly — all in JetBrains Mono gold. Mini sparkline chart.

- Quick Actions: 4 buttons — "Trigger Scan", "Request Content", "Ask Harper", "Check Website"

**Opportunities (/dashboard/opportunities):**
- Table/card view of opportunities with columns: ID, Business Name, Location, Type (Post Office/Forecourt/Convenience), Annual Fees, Sessions, Asking Price, Score (/100 in gold), Confidence tag, Status
- Action buttons on each: Pursue (gold), Watch (secondary), Dismiss (ghost/red)
- Filter by: type, region, score range, status
- Clicking an opportunity opens a detail panel/modal

**Content (/dashboard/content):**
- Pipeline view: Draft → Rex Review → Your Approval → Published
- Each content item shows: title, type (LinkedIn/Blog/Email), author (Henry), Rex's score, date
- Approve/Edit/Reject buttons on items in "Your Approval" stage

**Costs (/dashboard/costs):**
- Daily cost chart (Recharts line chart, last 30 days)
- Cost by model: pie chart (Sonnet, Haiku, Gemini, Other)
- Cost by agent: bar chart (Main, Henry, Claudia, Harper, Rex, Sentinel, Watchtower)
- Current month total, daily average, projected month-end — all JetBrains Mono gold
- Alert threshold indicator (flag if daily > £20)

**Agents (/dashboard/agents):**
- Card for each of 7 agents showing: name, role, model, status, last output, uptime % (last 30 days)
- Uptime displayed as a small bar chart or heatmap
- Click to expand for detailed health history

**HR (/dashboard/hr):**
- List of past HR cases with: date, type, risk level, status (Resolved/Escalated/Ongoing)
- "New HR Query" button that opens a form
- Case detail view with Harper's full guidance

**Settings (/dashboard/settings):**
- Model assignments table (agent → model mapping)
- Notification preferences (toggle push notifications)
- Auto-approve threshold slider (default 90%)

### Layer 3: FCM Insiders (/insiders — members only)

Any authenticated user who is NOT admin sees this area. Registration is open to anyone.

**Insiders Home (/insiders):**
- Welcome message with name
- "X new opportunities since your last visit" and "X new insights published" counters
- Latest Opportunities: 3 most recent listing cards with key financials in gold
- Market Intelligence: summary card with latest market stats
- Latest Insights: 3 most recent approved content pieces

**Listings (/insiders/listings):**
- Grid of opportunity listing cards, similar to public live listings but with more detail
- Each card: Business type, location, annual fees, sessions, asking price, FCM score
- Filter by: type, region, price range
- Card click opens detail page
- CTA on each: "Get Intelligence Report" → links to contact form

**Market (/insiders/market):**
- Market overview cards: Average PO branch fees (trending), Crown conversions available, Forecourt market update
- Regional breakdown table
- Monthly trend charts (Recharts)

**Insights (/insiders/insights):**
- Blog-style feed of approved content
- Category filter: "PO Insider" / "UK Business Strategy"
- Each post shown as a card with title, excerpt, date, read time

**Profile (/insiders/profile):**
- Member name, email, join date
- Notification preferences
- Saved listings (future feature — show empty state)

## Authentication Setup

Use NextAuth.js with these providers:
- Email Magic Link (primary) — sends login link via email
- No password authentication

Role logic:
- If email === "mikeshparekh@gmail.com" → role: "admin" → redirect to /dashboard
- All other authenticated users → role: "insider" → redirect to /insiders
- Unauthenticated → public pages only

Middleware:
- /dashboard/* → require admin role, redirect to /login if not
- /insiders/* → require any authenticated user, redirect to /login if not
- All other routes → public

## Database Schema (Supabase)

Create these tables:

```sql
-- Users (extends NextAuth)
-- Handled by NextAuth adapter

-- Opportunities
CREATE TABLE opportunities (
  id TEXT PRIMARY KEY, -- format: OPP-YYYY-MMDD-NNN
  business_name TEXT NOT NULL,
  business_type TEXT NOT NULL, -- post_office, forecourt, convenience_store, newsagent
  location TEXT,
  region TEXT,
  annual_fees DECIMAL,
  sessions_per_month INTEGER,
  asking_price DECIMAL,
  weekly_turnover DECIMAL,
  yearly_turnover DECIMAL,
  score INTEGER, -- 0-100
  confidence TEXT, -- HIGH, MODERATE, SPECULATIVE, FLAG
  status TEXT DEFAULT 'new', -- new, watch, pursue, closed, dismissed
  source TEXT, -- RightBiz, Daltons, etc.
  source_url TEXT,
  notes TEXT,
  insider_visible BOOLEAN DEFAULT false,
  created_at TIMESTAMPTZ DEFAULT NOW(),
  updated_at TIMESTAMPTZ DEFAULT NOW()
);

-- Content
CREATE TABLE content (
  id SERIAL PRIMARY KEY,
  title TEXT NOT NULL,
  body TEXT,
  content_type TEXT NOT NULL, -- linkedin, blog, email, pdf
  track TEXT, -- po_insider, uk_business_strategy
  author TEXT DEFAULT 'Henry',
  rex_score INTEGER,
  rex_verdict TEXT, -- pass, conditional_pass, return
  status TEXT DEFAULT 'draft', -- draft, review, approval, published, rejected
  published_at TIMESTAMPTZ,
  created_at TIMESTAMPTZ DEFAULT NOW()
);

-- Agent Health
CREATE TABLE agent_health (
  id SERIAL PRIMARY KEY,
  agent_name TEXT NOT NULL,
  status TEXT NOT NULL, -- active, silent, idle, error
  last_output TIMESTAMPTZ,
  hours_since_output DECIMAL,
  checked_at TIMESTAMPTZ DEFAULT NOW()
);

-- Cost Records
CREATE TABLE cost_records (
  id SERIAL PRIMARY KEY,
  date DATE NOT NULL,
  total_cost DECIMAL NOT NULL,
  sonnet_cost DECIMAL DEFAULT 0,
  haiku_cost DECIMAL DEFAULT 0,
  gemini_cost DECIMAL DEFAULT 0,
  opus_cost DECIMAL DEFAULT 0,
  main_agent_cost DECIMAL DEFAULT 0,
  henry_cost DECIMAL DEFAULT 0,
  claudia_cost DECIMAL DEFAULT 0,
  harper_cost DECIMAL DEFAULT 0,
  rex_cost DECIMAL DEFAULT 0,
  sentinel_cost DECIMAL DEFAULT 0,
  watchtower_cost DECIMAL DEFAULT 0,
  created_at TIMESTAMPTZ DEFAULT NOW()
);

-- HR Cases
CREATE TABLE hr_cases (
  id SERIAL PRIMARY KEY,
  case_type TEXT NOT NULL,
  description TEXT,
  risk_level TEXT, -- low, medium, high
  guidance TEXT,
  outcome TEXT, -- resolved, escalated, tribunal, ongoing
  created_at TIMESTAMPTZ DEFAULT NOW(),
  resolved_at TIMESTAMPTZ
);

-- Feedback Log
CREATE TABLE feedback_log (
  id SERIAL PRIMARY KEY,
  feedback_type TEXT NOT NULL, -- content, opportunity
  signal TEXT NOT NULL, -- strong_positive, learning_signal, negative, silent_dismiss
  agent TEXT,
  details JSONB,
  created_at TIMESTAMPTZ DEFAULT NOW()
);
```

## PWA Configuration

Create manifest.json:
- name: "FCM Intelligence"
- short_name: "FCM Intel"
- theme_color: "#FFD700"
- background_color: "#000000"
- display: "standalone"
- orientation: "portrait-primary"
- Generate placeholder icons at 192x192 and 512x512 (black background, gold "FCM" text)

Service worker caching:
- App shell: cache first
- API data: network first, cache fallback
- Images: cache first
- Blog content: stale while revalidate

## Sample Data

Seed the database with realistic sample data so the app looks populated:

- 8-10 sample opportunities (mix of Post Offices, forecourts, convenience stores across UK regions, with realistic financial data)
- 5 sample content items (2 published LinkedIn posts, 1 published blog, 1 in review, 1 draft)
- 7 agent health records (one per agent with realistic statuses)
- 14 days of cost records (daily costs between £12-20, realistic model splits)
- 3 HR cases (1 resolved, 1 ongoing, 1 escalated)

## Responsive Design

Mobile first. Three breakpoints:
- Mobile (< 768px): Single column, bottom navigation bar with 4 tabs (Dashboard/Opportunities/Content/More)
- Tablet (768-1024px): Two columns where appropriate
- Desktop (> 1024px): Full layout with sidebar navigation

## Important Rules

1. DARK THEME EVERYWHERE. No white backgrounds. No light mode toggle.
2. Gold (#FFD700) is the ONLY accent colour. Do not introduce blue, purple, or green.
3. ALL financial numbers must be in JetBrains Mono font in gold.
4. No placeholder text anywhere — "Lorem ipsum", "Coming soon", "Value 1" etc. If content isn't ready, show a clean empty state.
5. Every page must have a consistent header (logo area left, nav right) and footer.
6. The contact email is mikesh@interimenterprises.co.uk — use this in every CTA.
7. Mobile bottom nav for authenticated pages (dashboard and insiders).
8. Smooth page transitions and subtle hover animations on all interactive elements.

Build the complete application now. Start with the project structure, then build each layer in order: public pages first, then dashboard, then insiders area.
