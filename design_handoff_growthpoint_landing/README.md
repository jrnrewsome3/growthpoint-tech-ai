# Handoff: GrowthPoint Tech AI — Marketing Landing Page

## Overview

Marketing homepage for **GrowthPoint Tech AI**, an independent consulting practice specializing in Microsoft 365, SharePoint, and Copilot adoption for small businesses, nonprofits, and consultancies. The page's job is lead generation — driving qualified visitors to book a **Strategy Call** or **Consultation**.

**Primary CTA:** *Book a Strategy Call* (also *Schedule a Consultation* on final CTA)
**Secondary CTA:** *See What We Help With*

Target audience: small business owners (5–50 people), nonprofit leaders, independent consultants, and small agencies evaluating their Microsoft 365 investment and AI/Copilot adoption strategy.

**Aesthetic reference:** Stripe.com · Microsoft.com · Linear.app — clean, modern, high-contrast, multi-color, professional SaaS.

---

## About the Design Files

The HTML/CSS in `reference/` is a **design prototype**, not production code. It exists to show the intended look, layout, typography, spacing, color usage, and interaction states.

**Your job as the developer:** recreate this design inside the target codebase's existing environment (React/Next.js, Vue/Nuxt, Astro, WordPress, Webflow, etc.) using its established component patterns, design tokens, and libraries.

If no codebase exists yet, the recommended stack for this specific project is:
- **Next.js (App Router)** or **Astro** for static-first performance and SEO
- **Tailwind CSS** with a custom theme, OR plain CSS variables (already tokenized in the reference — see Design Tokens below)
- Deploy target: **Cloudflare Pages** or **Vercel**

The reference HTML is intentionally dependency-free — it can be shipped as-is if a framework rewrite isn't wanted, but it's not componentized. Every section is currently one big HTML block.

---

## Fidelity

**High-fidelity (hifi).** Colors, typography, spacing, and interaction states are all final. Recreate pixel-perfectly. Every hex value, font size, and radius in this doc is deliberate.

Two placeholders to be aware of:
1. **All CTA buttons currently `href="#"`** — must be wired to a real booking system (Calendly, TidyCal, HubSpot Meetings, etc.)
2. **`hello@growthpointtech.ai`** placeholder email is referenced in the design source but not currently in the visible page — swap for the real address if you add a contact section.

---

## Design Tokens

All tokens are defined as CSS custom properties in `reference/styles.css` (top of file, in `:root`). Port these to your framework's token system.

### Colors — full palette (all in use)

**Neutrals**
| Token | Hex | Usage |
|---|---|---|
| `--white` | `#FFFFFF` | Page background, cards, "white" button, text on dark sections |
| `--gray-50` | `#F8FAFC` | Alternating section background (Services, Audience) |
| `--gray-100` | `#F1F5F9` | Reserved (currently unused, keep for hover states) |
| `--gray-200` (`--border`) | `#E2E8F0` | Card borders, section dividers |
| `--gray-300` (`--border-strong`) | `#CBD5E1` | Stronger borders (ghost button), hover borders |
| `--gray-400` (`--text-slate`) | `#94A3B8` | Subtext on dark backgrounds (hero subhead, quick-wins body) |
| `--gray-500` | `#64748B` | Reserved |
| `--gray-600` (`--text-muted`) | `#475569` | Description/subtext on light backgrounds |
| `--gray-700` | `#334155` | Reserved |
| `--gray-800` (`--text`) | `#1E293B` | Primary body/heading text on light backgrounds |
| `--gray-900` (`--navy`) | `#0F172A` | Nav, hero, quick-wins section, final CTA, footer |

**Brand**
| Token | Hex | Usage |
|---|---|---|
| `--ms-blue` | `#0078D4` | **Microsoft blue** — primary CTA buttons, eyebrows, service card left-border (odd cards), stat #1, service #1 & #3 accents, icon on About value #1 |
| `--ms-blue-hover` | `#106EBE` | Primary button hover state |
| `--teal` | `#00B4D8` | Bright teal accent — hero "twice" highlight, quick-wins numbers, service card left-border (even cards), stat #2, brand-mark gradient stop, service #2 & #4 accents |
| `--teal-hover` | `#0096B7` | Teal text hover / darker teal usage |
| `--navy` / `--navy-800` | `#0F172A` / `#1E293B` | Dark backgrounds, About value #3 icon, stat #3 |

### Typography

**Single font family: Inter.** No serifs, no italics, no decorative fonts anywhere.

Google Fonts URL:
```
https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap
```

**Type scale (fluid via `clamp`):**

| Element | Size | Weight | Line-height | Letter-spacing |
|---|---|---|---|---|
| Hero H1 | `clamp(40px, 5.8vw, 72px)` | 700 | 1.02 | -0.035em |
| Section H2 | `clamp(30px, 3.8vw, 48px)` | 700 | 1.1 | -0.03em |
| CTA H2 | `clamp(32px, 4.4vw, 56px)` | 700 | 1.1 | -0.03em |
| H3 (service/audience/win) | `clamp(20px, 2vw, 26px)` | 600 | 1.15–1.25 | -0.025em |
| Stat number | `clamp(44px, 5vw, 60px)` | 700 | 1 | -0.03em |
| Win number | `clamp(36px, 4vw, 48px)` | 700 | 1 | -0.03em |
| Value item H4 | 19px | 600 | 1.3 | — |
| Hero subhead | `clamp(17px, 1.5vw, 20px)` | 400 | 1.55 | — |
| Section head body | 18px | 400 | 1.55 | — |
| Approach body | 17px | 400 | 1.65 | — |
| Card body | 15.5px | 400 | 1.6 | — |
| Value item body | 14.5px | 400 | 1.5 | — |
| Body | 16px | 400 | 1.6 | — |
| Eyebrow | 13px | 600 | — | 0.1em, UPPERCASE |
| Tech strip label | 12px | 600 | — | 0.14em, UPPERCASE |
| Button | 15–16px | 600 | — | -0.005em |
| Nav link | 14px | 500 | — | — |

Font feature settings on body: `"cv11", "ss01"` (Inter's alternate glyphs — the tabular numerals and open 6/9). Keep these on for polish.

### Spacing scale

- Section vertical padding: `clamp(72px, 8vw, 112px)`
- Hero padding: `clamp(80px, 10vw, 128px)` top, `clamp(56px, 7vw, 96px)` bottom
- CTA padding: `clamp(80px, 10vw, 128px)` top & bottom
- Container horizontal padding: `clamp(20px, 4vw, 40px)`
- Max content width: **1200px**
- Card interior padding: 32–36px
- Grid gaps: 16–24px between cards, 48–96px between columns

### Border radius

| Token | Value | Usage |
|---|---|---|
| Button | 8px | All buttons |
| `--radius` | 8px | Service cards, value items |
| `--radius-lg` | 12px | Stat cards, audience cards |
| Icon tile | 8–10px | Icon backgrounds in audience/about |
| Pill | 999px | Tech strip pills, audience tags |

### Shadows

```css
--shadow-sm:          0 1px 2px rgba(15, 23, 42, 0.05);
--shadow-card:        0 1px 3px rgba(15, 23, 42, 0.06), 0 1px 2px rgba(15, 23, 42, 0.04);
--shadow-card-hover:  0 8px 24px -8px rgba(15, 23, 42, 0.12), 0 2px 4px rgba(15, 23, 42, 0.06);
```

Primary button also has a **blue-tinted hover shadow**: `0 4px 12px -2px rgba(0, 120, 212, 0.35)`.
White CTA button (on dark) has a **darker hover shadow**: `0 8px 20px -4px rgba(0, 0, 0, 0.3)`.

---

## Screens / Views

Single-page marketing site. **10 distinct sections**, alternating between dark navy and light backgrounds to create rhythm.

---

### 1. Nav (sticky)

- **Purpose:** Persistent brand + section links + primary CTA while scrolling.
- **Layout:** Full-width sticky header, 72px tall. Flex row, `justify-content: space-between`. Three groups: brand (left), section links (center), CTA pair (right).
- **Background:** `#0F172A` (dark navy) — solid, no blur.
- **z-index:** 50
- **Brand:** 28×28 rounded-6px gradient tile (`linear-gradient(135deg, #0078D4 → #00B4D8)`) containing a small white hexagon (12×12 clip-path polygon), followed by "GrowthPoint Tech AI" wordmark in Inter 700, 17px, white.
- **Nav links:** 4 links (Services, Approach, Quick Wins, About) — 14px Inter 500, `rgba(255,255,255,0.72)`, hover → `#FFFFFF`.
- **CTAs:**
  - "See What We Help With" — ghost-dark button (transparent, 24%-opacity white border, white text)
  - "Book a Strategy Call" — primary Microsoft-blue button with right-arrow icon
- **Responsive:** nav links hide below 960px; ghost CTA hides below 560px.

---

### 2. Hero

- **Purpose:** Immediate value prop + primary CTA above the fold.
- **Background:** `#0F172A` (dark navy) with two subtle radial-gradient glows:
  ```css
  radial-gradient(ellipse at center, rgba(0, 180, 216, 0.08) 0%, transparent 60%)  /* top-right, teal */
  radial-gradient(ellipse at center, rgba(0, 120, 212, 0.12) 0%, transparent 60%)  /* bottom-left, blue */
  ```
  Applied as pseudo-elements (`::before` top-right, `::after` bottom-left).
- **Padding:** `clamp(80px, 10vw, 128px)` top, `clamp(56px, 7vw, 96px)` bottom.
- **Contents (all left-aligned, single column):**
  1. **Eyebrow** — "Microsoft 365 · SharePoint · Copilot · AI Adoption" in `#00B4D8` teal, 13px uppercase 0.1em spacing
  2. **H1** — "Most small businesses are paying for Microsoft 365 **twice** — and using it half." The word "twice" wrapped in `.highlight` span colored `#00B4D8` teal. Max 20ch width.
  3. **Subhead** — Full paragraph from brief in `#94A3B8` slate, 17–20px, max 62ch.
  4. **CTA row** —
     - Primary: "Book a Strategy Call" (Microsoft blue) with arrow
     - Ghost-dark: "See What We Help With"

---

### 3. Tech strip (thin band)

- **Purpose:** Establish practice areas with pill badges.
- **Background:** `#0F172A` (same navy, seamless continuation from hero) with a 1px top border in `rgba(255,255,255,0.08)`.
- **Padding:** 28px top/bottom.
- **Layout:** Flex row, `align-items: center`, 24px gap, wraps.
- **Contents:**
  - Label: "PRACTICE AREAS" in 12px 0.14em uppercase slate
  - Pills (7): `Microsoft 365 · SharePoint · Copilot · Teams · Power Automate · OneDrive · Defender`
- **Pill styling:** `rgba(255,255,255,0.05)` bg, `rgba(255,255,255,0.1)` border, `rgba(255,255,255,0.85)` text, 14px, 500 weight, 6×14px padding, 999px radius.

---

### 4. §01 Services

- **Purpose:** Four core service offerings.
- **Background:** `#F8FAFC` (light gray) — first light-background section.
- **Section head:**
  - Eyebrow "WHAT WE DO" in `#0078D4` (Microsoft blue)
  - H2: "Practical Microsoft 365 and SharePoint consulting for teams that need clarity, not complexity."
  - Max 720px width, 56px bottom margin
- **Grid:** 2×2 (`repeat(2, 1fr)`), 24px gap. Collapses to 1 column below 780px.

**Service card structure:**
- White bg, 1px `#E2E8F0` border, **4px left border in accent color**, 8px radius, `--shadow-card`, 36×32px padding, flex column
- Left border alternates: cards 1 & 3 use `#0078D4` (Microsoft blue); cards 2 & 4 use `#00B4D8` (teal)
- Hover: `translateY(-3px)`, `--shadow-card-hover`
- **Card 01** — number pill (blue-tinted), title "Microsoft 365 Subscription Strategy", body, foot "Licensing & cost review →"
- **Card 02** — number pill (teal-tinted), title "Copilot Rollout With a Business Case", body, foot "AI adoption planning →"
- **Card 03** — number pill (blue-tinted), title "SharePoint Cleanup and Knowledge Structure", body, foot "Information architecture →"
- **Card 04** — number pill (teal-tinted), title "Quick-Win Automation and AI Features", body, foot "Automation & adoption →"

**Number pill** (top of each card): 12px 700-weight, 0.1em spacing, uppercase, 4×10px padding, 4px radius, color-tinted background matching the border.

**Foot row:** Top border 1px `#E2E8F0`, 24px margin-top, 20px padding-top, 14px 500-weight text in the accent color, arrow SVG that translates 4px right on card hover.

**Card body copy** (all verbatim from brief):
1. "Stop overpaying. Match every license to how your team actually works."
2. "Know which roles should get Copilot first and how to make adoption stick."
3. "Turn SharePoint from a file dump into a system people actually open."
4. "Use Teams, Forms, OneDrive, Power Automate, and SharePoint together to save time starting this week."

---

### 5. §02 Approach

- **Purpose:** Point-of-view section with supporting stats.
- **Background:** `#FFFFFF` (white).
- **Layout:** Two columns, `1fr 1fr`, gap `clamp(48px, 6vw, 96px)`, `align-items: center`. Collapses to 1 column below 900px.

**Left column:**
- Eyebrow "OUR APPROACH" in Microsoft blue
- H2: "A better way to adopt AI inside Microsoft 365" (max 18ch)
- Body paragraph 1: "Most small businesses do not need the most expensive licenses. They need the right mix of subscriptions, a practical rollout plan, and a SharePoint structure that makes AI tools useful instead of frustrating."
- Body paragraph 2: "GrowthPoint Tech AI helps you get there without enterprise-level complexity."

**Right column — 3 stat cards, stacked vertically, 16px gap:**
- White bg, 1px `#E2E8F0` border, 12px radius, 32px padding, subtle shadow
- Layout: flex row, `align-items: baseline`, 24px gap. Number left (min-width 140px), label right.
- **Card 1:** `80%` in `#0078D4` (Microsoft blue) — "of **Microsoft 365 features** go unused in small organizations"
- **Card 2:** `$0` in `#00B4D8` (teal) — "additional cost for **AI features already included** in your subscription"
- **Card 3:** `1 week` in `#0F172A` (navy) — "typical time to see **quick wins** after a strategy session"
- Numbers: `clamp(44px, 5vw, 60px)`, 700 weight, letter-spacing -0.03em
- Label bolded words use `#1E293B` text color
- Below 500px: card layout goes vertical (column direction, 8px gap)

---

### 6. §03 Quick Wins

- **Purpose:** Four tactical improvements.
- **Background:** `#0F172A` (dark navy) — **second dark section, breaks up the flow**. Has same subtle teal radial glow as hero.
- **Section head:**
  - Eyebrow "QUICK WINS" in teal
  - H2 in white: "Simple changes that create immediate value"
  - Body in slate: "Four practical improvements using tools already on your Microsoft invoice. No new licenses required."

**Wins list:** Vertical stack, no gap between rows.
- Border-top: 1px `rgba(255,255,255,0.1)` on the list container
- Each row: 32px top/bottom padding, 1px `rgba(255,255,255,0.1)` bottom border
- Grid: `90px 1fr`, 32px gap, `align-items: baseline`
- **Hover state:** row gets `rgba(255,255,255,0.03)` bg, and the row's inline padding expands from 0 to 16px (with matching negative margin) — subtle "pop out" effect.

**Row contents:**
- **Number** — `clamp(36px, 4vw, 48px)`, 700 weight, `#00B4D8` teal, -0.03em letter-spacing
- **Heading** — 20–24px, 600 weight, white, max 32ch
- **Description** — 16px, `#94A3B8` slate, line-height 1.6, max 62ch

**Row copy:**
1. **Smarter SharePoint Structure** — "Build a document structure so teams find files faster and AI has better content to work with."
2. **Right-Sized Copilot Licensing** — "Identify which roles actually benefit from Copilot before buying licenses broadly."
3. **Automated Internal Workflows** — "Use Forms, Power Automate, and SharePoint lists to streamline requests and reduce manual follow-up."
4. **Better Collaboration Setup** — "Improve Teams, OneDrive, and shared knowledge spaces instead of scattered email attachments."

**Below 640px:** grid becomes `60px 1fr`, gap 16px.

---

### 7. §04 Audience (Who this is for)

- **Purpose:** Establish target audience credibility.
- **Background:** `#F8FAFC` (light gray).
- **Section head:**
  - Eyebrow "WHO THIS IS FOR" in Microsoft blue
  - H2: "Built for organizations that want real results, not more software."
- **Grid:** 3 columns, 24px gap. Collapses to 1 column below 860px.

**Card structure:**
- White bg, 1px `#E2E8F0` border, 12px radius, 36×32px padding, `--shadow-card`
- Hover: `translateY(-3px)`, `--shadow-card-hover`, border → `#CBD5E1`

**Contents (all cards follow same structure):**
1. **Icon tile** (44×44, 10px radius) with a Lucide-style outline SVG icon inside
2. **H3** (22px 600 weight, `#1E293B`)
3. **Body** (`#475569`, 15.5px, line-height 1.6)
4. **Tag pill** (999px radius, 6×12px padding, 12px 600 uppercase 0.08em)

**Per-card accent colors:**
| Card | Icon bg | Icon color | Tag bg | Tag color |
|---|---|---|---|---|
| **Small Businesses** | `rgba(0,120,212,0.1)` | `#0078D4` | `rgba(0,120,212,0.08)` | `#0078D4` |
| **Nonprofits** | `rgba(0,180,216,0.12)` | `#0096B7` | `rgba(0,180,216,0.1)` | `#0096B7` |
| **Consultants & Agencies** | `rgba(15,23,42,0.08)` | `#0F172A` | `rgba(15,23,42,0.08)` | `#0F172A` |

**Card copy:**
- **Small Businesses** — "Teams of 5–50 that need Microsoft 365 to actually work for them." Tag: `5–50 people`
- **Nonprofits** — "Organizations that need to maximize every license dollar and reduce IT burden." Tag: `Mission-driven`
- **Consultants & Agencies** — "Independent firms that want to use Microsoft tools more effectively for client work." Tag: `Client-facing`

**Icon SVGs:** Lucide-style paths (24×24 viewBox, 2px stroke, `stroke-linecap: round`). See `reference/index.html` for exact path data. Icons used: building/office grid, heart/gift, briefcase.

---

### 8. §05 About

- **Purpose:** Founder/practice credibility.
- **Background:** `#FFFFFF` (white).
- **Layout:** Two columns, `5fr 7fr`, gap `clamp(48px, 6vw, 88px)`, `align-items: start`. Collapses to 1 column below 900px.

**Left column (about content):**
- Eyebrow "ABOUT" in Microsoft blue
- H2: "Led by a consultant who teaches as well as implements." (max 20ch)
- Two body paragraphs (verbatim from brief), 17px, `#475569`, line-height 1.65

**Right column (three value items, stacked, 16px gap):**
- `#F8FAFC` bg, 1px `#E2E8F0` border, 8px radius, 20px padding
- Grid: `40px 1fr`, 16px gap, `align-items: start`
- 40×40 icon tile (white bg, 1px border, 8px radius) with Lucide-style icon
- H4 (16px 600, `#1E293B`) + body (14.5px, `#475569`)

**Value items:**
1. **Right-size before you upgrade** — "The answer is usually fewer licenses, not more. Audit first, buy second." (Blue check-circle icon)
2. **Structure content before deploying AI** — "Copilot is only as good as the data underneath it. Fix the storage first." (Teal grid/layout icon)
3. **Train the humans, then hand over the keys** — "Every engagement is designed to end. Your team runs it after we leave." (Navy people icon)

---

### 9. §06 Final CTA

- **Purpose:** Second, stronger conversion push.
- **Background:** `#0F172A` (dark navy), **third and final dark section**, with dual radial glows:
  ```css
  radial-gradient(ellipse at center, rgba(0, 120, 212, 0.15) 0%, transparent 60%)  /* top-right, blue */
  radial-gradient(ellipse at center, rgba(0, 180, 216, 0.08) 0%, transparent 60%)  /* bottom-left, teal */
  ```
- **Padding:** `clamp(80px, 10vw, 128px)` top & bottom.
- **Layout:** Single left-aligned column, max 780px width.

**Contents:**
- H2 in white: "Get more from Microsoft 365 without adding more confusion." (max 22ch)
- Body in slate: "If your organization is paying for Microsoft 365 but still wrestling with file chaos, weak adoption, or unclear AI decisions, GrowthPoint Tech AI can help you build a smarter path forward."
- **CTA row:**
  - Primary: "**Schedule a Consultation**" — white button (`#FFFFFF` bg, `#0F172A` text) with arrow. Hover: `#F1F5F9` bg, `translateY(-1px)`, dark shadow.
  - Note text (slate, 14px): "30 minutes · No sales pressure"

---

### 10. Footer

- **Purpose:** Minimal footer — brand line + copyright + social.
- **Background:** `#0F172A` (dark navy) with 1px top border in `rgba(255,255,255,0.08)`.
- **Padding:** 48px top, 32px bottom.
- **Layout:** Single flex row, `justify-content: space-between`, `align-items: center`, 24px gap, wraps.

**Left (footer-brand):** Brand mark + wordmark (white), pipe separator (`|` in 24%-opacity white), tagline "Microsoft 365 · SharePoint · Copilot Consulting" in `rgba(255,255,255,0.6)`.

**Right (footer-right):** "© 2026" text + social icons row (LinkedIn, X). Icons: 32×32, 1px `rgba(255,255,255,0.12)` border, 6px radius, `rgba(255,255,255,0.6)` icon color. Hover: `rgba(255,255,255,0.08)` bg, white icon, brighter border.

---

## Interactions & Behavior

### Navigation
- All in-page nav links use anchor scrolling (`#services`, `#approach`, `#wins`, `#about`, `#cta`)
- `html { scroll-behavior: smooth; }` is already set — replicate in your framework

### Hover states (all 150–200ms ease)

| Element | Default | Hover |
|---|---|---|
| Primary button | `#0078D4` bg, white text | `#106EBE` bg, `translateY(-1px)`, blue-tinted shadow |
| White button (on dark) | White bg, navy text | `#F1F5F9` bg, `translateY(-1px)`, dark shadow |
| Ghost button (light) | Transparent, `#CBD5E1` border | `#F8FAFC` bg, `#94A3B8` border |
| Ghost-dark button | Transparent, 24%-white border | 8%-white bg, 50%-white border |
| Nav link | 72%-white | 100%-white |
| Service card | Border-only card | `translateY(-3px)`, larger shadow, arrow in foot translates 4px right |
| Stat card | Standard border | Border darkens to `#CBD5E1` |
| Audience card | Standard | `translateY(-3px)`, larger shadow, border darkens |
| Quick-win row | Standard | `rgba(255,255,255,0.03)` bg, inline padding expands 16px |
| Social icon | Subtle border | 8%-white bg, white icon, brighter border |
| Arrow icon in button | Static | Translates 3–4px right |

### Animations
No scroll-triggered animations are implemented. All motion is hover-based, 150–200ms ease.

If you want to add reveal-on-scroll for polish, use Intersection Observer with 30–50ms stagger — but this is optional and not in the reference.

### Forms
No forms are in this design. **All CTAs are `href="#"` placeholders** — developer must wire real destinations:

| Button | Destination |
|---|---|
| Nav "Book a Strategy Call" | Booking system |
| Nav "See What We Help With" | `#services` anchor (already correct) |
| Hero "Book a Strategy Call" | Booking system |
| Hero "See What We Help With" | `#services` anchor (already correct) |
| CTA "Schedule a Consultation" | Booking system |

Recommended booking integrations: **Calendly**, **TidyCal**, **HubSpot Meetings**, or **SavvyCal**. All support direct link-outs or embedded modals.

### Responsive breakpoints

| Breakpoint | Behavior |
|---|---|
| ≤ 960px | Nav center links hide (brand + CTAs remain). **Developer should add a mobile menu / hamburger — not implemented in reference.** |
| ≤ 900px | Approach section (content + stats) → 1 column stacked. About section (content + values) → 1 column stacked. |
| ≤ 860px | Audience grid → 1 column. |
| ≤ 780px | Services grid → 1 column. |
| ≤ 640px | Quick-wins row grid → `60px 1fr` narrower. |
| ≤ 560px | Nav ghost-dark CTA hides (only primary CTA remains). |
| ≤ 500px | Stat cards → vertical (column direction, number stacks above label). |

---

## State Management

Site is fully static. No state management required unless the developer adds:
- Mobile menu open/closed toggle
- Form submission state (once real forms are wired)
- Cookie/consent banner (recommended for GDPR — not in current design)

---

## Assets

**No image assets** are used. Everything is CSS gradients, SVG icons (inline), and typography.

### Icons

All icons in the reference are **inline SVGs using Lucide-icon style paths** (24×24 viewBox, 2px stroke, `stroke-linecap: round`, `stroke-linejoin: round`). Developer can either:
- Copy the inline SVGs from `reference/index.html` (fastest, no dependency)
- Install `lucide-react` / `lucide-vue-next` / `@lucide/svelte` and use named components (recommended for consistency)

**Icons used in the reference:**
- `arrow-right` — CTA buttons and service card foot rows
- `building` (custom path) — Small Businesses audience card
- `heart` — Nonprofits audience card
- `briefcase` — Consultants & Agencies audience card
- `check-circle` — About value #1
- `layout-grid` (custom) — About value #2
- `users` — About value #3

### Brand mark

The logo mark (`.brand-mark`) is a **28×28 gradient tile with an inline hexagon**:
- Background: `linear-gradient(135deg, #0078D4 0%, #00B4D8 100%)`
- Inner shape: A 12×12 white hexagon created via `clip-path: polygon(0 30%, 50% 0, 100% 30%, 100% 70%, 50% 100%, 0 70%)`
- 6px border-radius on the outer tile

If the client provides a real logo mark, swap `.brand-mark` for an `<img>` or inline SVG at the same 28×28 size.

### Fonts

**Inter only.** Load via Google Fonts (URL in Design Tokens section). Optionally self-host via `@fontsource/inter` for privacy/performance.

Font feature settings: `"cv11"` (alternate 6/9) and `"ss01"` (alternate g). Enable on `body`.

---

## Accessibility notes

- All interactive elements use semantic HTML (`<a>`, `<button>`, `<nav>`, `<header>`, `<footer>`, `<section>`, `<article>`) — preserve when porting.
- Nav has `aria-label="Primary"`.
- Brand link has `aria-label="GrowthPoint Tech AI home"`.
- Brand mark and decorative dots have `aria-hidden="true"`.
- Social icons have `aria-label` for each platform.
- **Color contrast:**
  - White on `#0F172A` navy: 17.5:1 (AAA) ✓
  - `#94A3B8` slate on `#0F172A` navy: 6.7:1 (AAA) ✓
  - `#1E293B` text on `#FFFFFF`: 15.6:1 (AAA) ✓
  - `#475569` muted text on `#FFFFFF`: 8.4:1 (AAA) ✓
  - `#0078D4` blue on `#F8FAFC` gray-50: 4.8:1 (AA) ✓
  - `#0078D4` blue button with white text: 4.6:1 (AA) ✓
- Focus states — reference uses browser defaults. **Developer should add visible focus rings** (recommend 2px `#0078D4` outline with 2px offset on all interactive elements, or 2px `#00B4D8` teal outline for elements on dark backgrounds).

---

## Files

Reference implementation in this bundle:

- `reference/index.html` — Complete single-page HTML with all 10 sections
- `reference/styles.css` — All styling with CSS custom properties for the design tokens

Both files are dependency-free (only external resource is the Google Fonts Inter stylesheet). Open `reference/index.html` in any browser to see the intended output.

The source project also contains `README.md` and `DEPLOY.md` at the project root, which give operator-focused deployment instructions for Cloudflare Pages — worth a glance for context on the intended deployment environment.

---

## Implementation checklist

For the developer starting from this handoff:

- [ ] Set up the project (Next.js/Astro/Vue/other) with Inter loaded via `@fontsource/inter` or Google Fonts
- [ ] Port design tokens to your theme system (Tailwind config, CSS variables, theme object, styled-components theme, etc.)
- [ ] Implement the 10 sections as separate components (Nav, Hero, TechStrip, Services, Approach, QuickWins, Audience, About, CTA, Footer)
- [ ] Wire all 5 booking CTAs to a real scheduling link (Calendly/TidyCal/HubSpot)
- [ ] Add a mobile menu below 960px (hamburger + drawer or overlay)
- [ ] Add visible focus rings for keyboard navigation
- [ ] Set up analytics on CTA clicks (recommend tracking each of the 5 CTA locations separately)
- [ ] Add Open Graph / Twitter Card meta tags for social sharing
- [ ] Add JSON-LD structured data (`Organization` schema at minimum, `ProfessionalService` ideally)
- [ ] Test at 1440px, 1024px, 768px, 375px viewports
- [ ] Test with a screen reader (VoiceOver / NVDA) to verify heading hierarchy and landmark navigation
