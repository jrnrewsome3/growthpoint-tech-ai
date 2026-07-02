# Handoff: LifeQuestAI Landing Page

## Overview

Marketing landing page for **LifeQuestAI**, a small-business consultancy that helps organizations pick the right Microsoft 365, Copilot, and AI licensing package. The page's job is lead generation — driving qualified visitors to book a free consultation.

**Primary CTA:** Schedule a Free Microsoft 365 & AI Consultation
**Secondary CTA:** Request Pricing / Compare Packages

Target audience: small business owners, consultants, nonprofits, legal/healthcare/financial firms, and government contractors evaluating Microsoft 365 + Copilot licensing.

---

## About the Design Files

The HTML/CSS in `reference/` is a **design prototype**, not production code. It exists to show the intended look, layout, typography, spacing, colors, and interaction states.

**Your job as the developer:** recreate this design inside the target codebase's existing environment (React/Next.js, Vue/Nuxt, Astro, WordPress, Webflow, etc.) using its established component patterns, design tokens, and libraries.

If no codebase exists yet, the recommended stack for this specific project is:
- **Astro** or **Next.js (App Router)** for static-first performance
- **Tailwind CSS** if you want utility-first, or plain CSS variables (already tokenized in the reference — see Design Tokens below)
- Deploy target: Cloudflare Pages (already configured — see project root `DEPLOY.md`)

The reference HTML is intentionally dependency-free and fully static — it can be shipped as-is if a framework rewrite isn't wanted, but it's not componentized.

---

## Fidelity

**High-fidelity (hifi).** Colors, typography, spacing, and interaction states are all final. Recreate pixel-perfectly. Every hex value, font size, and radius in this doc is deliberate.

Two things the developer should treat as flexible:
1. **Testimonials** — the 3 quotes are placeholders. Real client quotes will replace them.
2. **Trust bar items** (Microsoft 365, Copilot, SharePoint, Intune, Defender, Power Platform) — these are certification claims; verify with client before shipping.

---

## Design Tokens

All tokens are defined as CSS custom properties in `reference/styles.css`. Port these to your framework's token system (Tailwind config, CSS variables, theme object, etc.).

### Colors

| Token | Hex | Usage |
|---|---|---|
| `--navy-900` | `#0B1F3A` | Primary dark backgrounds (hero, final CTA, footer top) |
| `--navy-800` | `#102A54` | Hero gradient bottom, secondary dark surfaces |
| `--navy-700` | `#12284C` | Heading text, brand text |
| `--navy-600` | `#1B3A6B` | *(reserved — currently unused)* |
| `--gold-500` | `#D4AF37` | Primary accent, primary button bg, gold underlines |
| `--gold-400` | `#E5C76B` | Hover accent, headings on dark bg, icon accents |
| `--gold-100` | `#F5E9C4` | *(reserved — currently unused)* |
| `--white` | `#FFFFFF` | Base background |
| `--off-white` | `#FBFBFC` | Reserved |
| `--gray-50` | `#F7F8FA` | Alternating section background (Packages, Setups, Testimonials) |
| `--gray-100` | `#EEF0F4` | Nav border, subtle dividers |
| `--gray-200` | `#E1E4EB` | Card borders |
| `--gray-300` | `#C8CDD6` | Card border on hover |
| `--gray-500` | `#6E7684` | Secondary text, lead paragraphs |
| `--charcoal` | `#2B2B2B` | Body text |

**Accent colors used in strategy section (semantic only, do not extend palette):**
- Bad-approach card: bg `#FEF6F5` → `#FDFAF9`, border `#F4D9D4`, label bg `#FCE5E1`, label text `#A63B2A`
- Good-approach card: bg `#F5F9F6` → `#FAFCFA`, border `#C7DED0`, label bg `#DBEDE0`, label text `#216B3A`

**Footer background:** `#071426` (one shade darker than `--navy-900`)

### Typography

| Family | Weights | Usage |
|---|---|---|
| **Manrope** | 400, 500, 600, 700, 800 | Display / headlines / button labels |
| **IBM Plex Sans** | 400, 500, 600 | Body text |
| **IBM Plex Mono** | 400, 500 | Eyebrows, technical labels, stack tags, tier names |

Google Fonts URL (currently used):
```
https://fonts.googleapis.com/css2?family=Manrope:wght@400;500;600;700;800&family=IBM+Plex+Sans:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap
```

**Type scale (fluid via `clamp`):**

| Element | Size | Weight | Line-height | Letter-spacing |
|---|---|---|---|---|
| Hero H1 | `clamp(40px, 5.6vw, 72px)` | 700 | 1.02 | -0.025em |
| H2 | `clamp(32px, 4vw, 52px)` | 700 | 1.1 | -0.02em |
| H3 | `clamp(20px, 1.6vw, 24px)` | 600 | 1.1 | -0.02em |
| Package name | 24px | 700 | 1.1 | -0.015em |
| Testimonial quote | 18px | Manrope 400 | 1.5 | normal |
| Body | 17px | 400 | 1.55 | normal |
| Lead paragraph | 18px | 400 | 1.55 | normal |
| Button | 15–16px | 600 | — | 0.01em |
| Eyebrow / mono labels | 12px | Mono 500 | — | 0.14em, UPPERCASE |
| Footer body | 14px | 400 | 1.6 | normal |

**Special treatments:**
- Body defaults to `text-wrap: pretty`
- Headings default to `text-wrap: balance`
- Hero H1 contains an italic gold accent word: `.gold-word { color: var(--gold-400); font-style: italic; font-weight: 500; }`
- Gold underline effect (used on H2 emphasis): background-linear-gradient behind text at `88%` from top, `8px` tall

### Spacing scale

Section vertical padding: `clamp(72px, 10vw, 120px)`
Container horizontal padding: `clamp(20px, 4vw, 40px)`
Max content width: **1240px**
Card interior padding: 28–40px
Gap between cards in grids: 20–24px

### Border radius

| Token | Value | Usage |
|---|---|---|
| Small | 6px | Stack tags |
| Base (`--radius`) | 14px | Cards |
| Large (`--radius-lg`) | 20px | Hero visual |
| Button | 10–12px | All buttons |
| Pill | 999px | Audience tags, "Most Popular" badge, hero check icons |

### Shadows

```css
--shadow-sm: 0 1px 2px rgba(11, 31, 58, 0.06), 0 1px 3px rgba(11, 31, 58, 0.04);
--shadow-md: 0 8px 24px -8px rgba(11, 31, 58, 0.12), 0 2px 6px rgba(11, 31, 58, 0.05);
--shadow-lg: 0 24px 48px -16px rgba(11, 31, 58, 0.22), 0 4px 12px rgba(11, 31, 58, 0.06);
--shadow-gold: 0 20px 40px -18px rgba(212, 175, 55, 0.55);
```

---

## Screens / Views

This is a single-page landing site. Nine distinct sections top to bottom:

---

### 1. Nav (sticky)

- **Purpose:** Persistent access to sections + CTAs while scrolling.
- **Layout:** Full-width sticky header, 72px tall. Three groups: brand (left), section links (center), CTA pair (right). Flex space-between.
- **Background:** `rgba(255,255,255,0.78)` with `backdrop-filter: blur(14px) saturate(150%)` — frosted glass over content.
- **Border-bottom:** 1px solid `--gray-100`.
- **Brand:** 32×32 rounded-8px navy gradient tile with gold "LQ" monogram + "LifeQuestAI" wordmark in Manrope 700, 18px.
- **Nav links:** 6 links (Packages, Copilot Strategy, Solutions, Why Us, Clients), 14px Plex Sans 500. Hover: color shift to `--navy-900`.
- **CTAs:**
  - "Request Pricing" — ghost button (transparent, gray border)
  - "Free Consultation" — primary gold button with right-arrow icon
- **Responsive:** nav links hide below 860px; CTAs remain.

---

### 2. Hero

- **Purpose:** Primary headline, value prop, and primary CTA above the fold.
- **Background:**
  ```css
  background:
    radial-gradient(ellipse 900px 500px at 85% -10%, rgba(212,175,55,0.10), transparent 60%),
    linear-gradient(180deg, #0B1F3A 0%, #102A54 100%);
  ```
- **Grid overlay:** 60×60px CSS grid lines at 3% white opacity, masked with radial ellipse for softness.
- **Layout:** Two-column grid `1.15fr 0.85fr`, gap 72px. Stacks to single column below 980px.
- **Padding:** `clamp(80px, 12vw, 140px)` top, `clamp(80px, 10vw, 120px)` bottom.

**Left column (hero copy):**
- Eyebrow: "Microsoft 365 · Copilot · AI Strategy" in gold-400, with 24px gold hairline before it
- H1 (3 lines, hand-broken with `<br>`):
  ```
  Build Your [AI-Powered]  ← italic gold
  Workplace Without
  Overpaying.
  ```
- Subheadline in `rgba(255,255,255,0.72)`, 17–20px fluid, max-width 560px
- 6 feature bullets in a 2-column grid, each with a 20×20 gold-tinted check icon (rounded-6px, `rgba(212,175,55,0.15)` bg, `rgba(212,175,55,0.35)` border)
- Two CTAs: primary gold + ghost-dark

**Right column (hero visual — "AI Orbital"):**
- Aspect ratio 4:5, max-width 460px, right-aligned
- Radial gold glow + navy gradient bg, gold-tinted border, large shadow
- Contains:
  - SVG with concentric circles (radii 90, 140, 190px) and connection lines from center to each floating node, using linear-gradient stroke `#E5C76B → #D4AF37`
  - 5 floating "nodes" — small frosted-glass rectangles labeled "Teams", "Copilot", "SharePoint", "Defender", "Outlook", each with a pulsing gold dot
  - **Pulsing core** — 140×140 radial-gradient gold blob at center, `animation: pulse 4s ease-in-out infinite` (scale 1 → 1.1, opacity 0.85 → 1)
  - Center label: 68×68 circle with white-to-gold gradient, "AI" text in Manrope 800 22px, navy text color
- **Interaction:** No user interaction — purely decorative animation.

**Trust bar (bottom of hero):**
- Divider: 1px top border in `rgba(255,255,255,0.1)`, 72px margin-top, 32px padding-top
- Flex row of one label + 6 items: "Certified expertise in — Microsoft 365 · Copilot · SharePoint · Intune · Defender · Power Platform"
- Mono 13px, letter-spacing 0.08em, uppercase

---

### 3. Package Comparison

- **Purpose:** Four-tier pricing/package comparison. Central conversion element.
- **Background:** `--gray-50` (`#F7F8FA`)
- **Layout:** 4-column grid, 20px gap. Breakpoints: 4 → 2 cols at 1080px → 1 col at 600px.

**Section head:**
- Eyebrow "Package Comparison"
- H2: "Four packages. One that fits **your business**." (last two words wrapped in gold-underline span)
- Lead paragraph explaining the value prop

**Each package card:**
- White bg, 14px radius, 1px gray-200 border, 32×28px padding
- Hover: `translateY(-4px)`, `--shadow-md`, border-color `--gray-300`
- Contents:
  1. **Tier row** — colored swatch (14×14 gradient chip) + mono uppercase tier name
  2. **Package name** — Manrope 700, 24px, navy-700
  3. **Tag line** — gray-500, 14px
  4. **"Best for" label** — mono 12px uppercase gray-500
  5. **Audience pills** — small gray-50 pills with gray-200 border, one per audience type
  6. **Divider** — 1px gray-100 line
  7. **Includes list** — 6 items, each with a small gold checkmark SVG (16×16, gold-500 stroke)
  8. **CTA button** — full-width, 13×20px padding, 10px radius

**Per-tier variations:**

| Tier | Swatch gradient | Tier label color | Card style | Button style | Button text |
|---|---|---|---|---|---|
| **Bronze** | `#B08560 → #7A4E2E` | `#7A4E2E` | Standard | White bg, navy border, navy text | Learn More |
| **Silver** | `#E0E3E8 → #A8ADB5` | `#6E7684` | Standard | Same | Learn More |
| **Gold** | `#E5C76B → #D4AF37` | `#A8801E` | **Gold border + gold shadow + `translateY(-6px)` (elevated). "Most Popular" badge (navy pill with gold text and gold border) offset at `top: -12px, left: 24px`.** | Gold bg, navy text | Request Pricing |
| **Platinum** | `#12284C → #D4AF37` | `--navy-700` | Standard | Navy bg, gold text | Schedule Demo |

**Card content per tier:** see `reference/index.html` for exact bullet lists and audience tags. Do not paraphrase — these are the finalized value props.

---

### 4. Smart Copilot Strategy

- **Purpose:** Educational section positioning LifeQuestAI's differentiator (don't buy Copilot for everyone).
- **Background:** white
- **Section head:** Eyebrow "Smart Copilot Strategy" + H2 "Not everyone needs Copilot." + lead paragraph.

**Comparison grid** (2 columns, 24px gap, stacks below 820px):
- Each card: 40px padding, 14px radius
- **Bad card:** warm pink gradient bg (`#FEF6F5 → #FDFAF9`), pink border, pink pill label "EXPENSIVE APPROACH", H3 "Buy Copilot for everyone", body copy. Top-right 40×40 circle with red "✕".
- **Good card:** warm mint gradient bg (`#F5F9F6 → #FAFCFA`), green border, green pill label "SMART APPROACH", H3 "Right license, right role", body copy. Top-right 40×40 circle with green "✓".

**Benefits strip** (below comparison):
- Dark navy (`--navy-900`) full-width panel, 14px radius, 32px padding
- 5-column grid (2 cols below 900px)
- Each item:
  - **Big number** in gold-400, Manrope 700, 26px, letter-spacing -0.02em
  - **Label** in white 72% opacity, 13px, line-height 1.4
- Content:
  - 40–60% — Lower licensing costs
  - 3× — Faster adoption
  - Better — Measurable ROI
  - Easier — Training & rollout
  - Day 1 — Productivity gains

---

### 5. Common Business Setups

- **Purpose:** Show real-world configurations for 6 industries. Builds credibility + helps buyer self-identify.
- **Background:** `--gray-50`
- **Layout:** 3-column grid (2 below 900px, 1 below 600px), 20px gap.

**Each card:**
- White bg, 14px radius, 1px gray-200 border, 28px padding
- Hover: border becomes gold-500, `translateY(-2px)`, medium shadow
- Contents:
  1. **Icon tile** — 44×44 navy gradient square, 10px radius, gold icon (Lucide-style stroke SVGs, 22×22)
  2. **H4** — Manrope 600, 18px, navy-700
  3. **Description** — gray-500, 14px
  4. **Stack tag** — mono 12px on gray-50 bg with gray-100 border, 8×12px padding, 6px radius

**Card content:**

| Icon | Name | Description | Stack |
|---|---|---|---|
| User | Solo Consultant | Independent professional running their own book of business. | Business Basic + Copilot Chat |
| Shield | Insurance Agency | Small team where the owner drives most of the client work. | Business Standard + Copilot for Owner |
| Building | Law Firm | Partners need heavy AI drafting; support staff needs security. | Business Premium + Copilot for Partners |
| Heart | Nonprofit | Mission-driven org with tight budgets and leadership-heavy AI needs. | Business Basic/Premium + Leadership AI |
| Chart-up | Growing Service Business | Scaling operations team that lives in workflows and reporting. | Business Premium + Copilot for Operations |
| Lock | Government Contractor | Compliance-first environments with strict data handling requirements. | Microsoft 365 E5 + Copilot + Compliance |

Icon SVG paths are in `reference/index.html` — Lucide icon set style, 2px stroke.

---

### 6. Why LifeQuestAI

- **Purpose:** Six-feature explanation of the service offering.
- **Background:** white
- **Section head:** Eyebrow "Why LifeQuestAI" + H2 "More than a software subscription." + lead paragraph.
- **Layout:** 3-column grid (2 below 900px, 1 below 600px), 24px gap.

**Each card:**
- gray-50 bg, 14px radius, 1px gray-100 border, 32×28px padding
- Hover: white bg, gold-500 border, medium shadow. **Icon tile inverts** to navy bg + gold icon.
- Icon tile: 48×48, 12px radius, white bg with gray-200 border by default, navy-700 icon.
- H4 in Manrope 600 18px, navy-700
- Body in gray-500 14px

**Card content:**
1. **Microsoft 365 Licensing** — We audit your current licenses, identify overspend, and right-size your stack to what your team actually uses.
2. **AI Readiness Assessments** — A clear-eyed look at your data, workflows, and team before you spend a dollar on AI — so the rollout actually sticks.
3. **Copilot Adoption** — Prompt libraries, playbooks, and hands-on training so your team stops fumbling and starts producing real work.
4. **SharePoint Solutions** — Custom intranets, document libraries, and workflows that turn SharePoint from a file dump into a nerve center.
5. **Cybersecurity Guidance** — Practical security posture reviews and Defender/Intune configurations sized for small business — not Fortune 500.
6. **Automation & Workflow Design** — Power Automate flows and Copilot agents that quietly eliminate the manual busywork your team hates.

---

### 7. Testimonials

- **Purpose:** Social proof. **Placeholder content — replace before launch.**
- **Background:** `--gray-50`
- **Section head:** Eyebrow "Client Results" + H2 "What clients say."
- **Layout:** 3-column grid (1 col below 900px), 24px gap.

**Each card:**
- White bg, 14px radius, 1px gray-200 border, 32px padding
- **Stars row** — 5 gold ★ characters, 16px, letter-spacing 2px, gold-500
- **Quote** — Manrope 400, 18px, navy-700, line-height 1.5, `text-wrap: pretty`
- **Person row** — separated by 1px gray-100 top border
  - **Avatar** — 44×44 navy gradient circle with initials in Manrope 700 15px gold-400
  - **Name** — 15px 600 navy-700
  - **Business type** — 13px gray-500

Three placeholder testimonials in `reference/index.html`. **Replace all three with real quotes before shipping.**

---

### 8. Final CTA

- **Purpose:** Second, more emphatic conversion push.
- **Background:**
  ```css
  radial-gradient(ellipse 800px 400px at 20% 20%, rgba(212,175,55,0.15), transparent 60%),
  radial-gradient(ellipse 600px 400px at 90% 80%, rgba(212,175,55,0.08), transparent 60%),
  linear-gradient(180deg, #0B1F3A, #102A54);
  ```
- **Grid overlay:** Same 60×60px subtle grid as hero, masked with radial fade.
- **Layout:** Two-column grid `1.2fr 1fr`, gap 64px. Stacks below 900px.

**Left column:**
- Gold eyebrow "Free Consultation"
- H2 in gold-400: "Ready to Build Your AI-Powered Workplace?"
- Lead in white/75%
- CTA row: primary gold button "Book Your Free Consultation" + mono footnote "No credit card · No obligation"

**Right column — benefits list:**
- 5 items, each in a rounded-10px card with:
  - Background: `rgba(255,255,255,0.04)`
  - Border: 1px `rgba(212,175,55,0.2)`
  - 16×20px padding
  - 28×28 rounded-8px gold-tinted icon tile with gold checkmark (3px stroke)
  - Text in Manrope 500 17px, white
- Items: License Review · AI Readiness Assessment · Security Evaluation · Cost Savings Recommendations · Copilot Strategy

---

### 9. Footer

- **Background:** `#071426` (darker than navy-900)
- **Text:** `rgba(255,255,255,0.6)` base
- **Padding:** 64px top, 32px bottom

**Top row (4 columns → 2 below 820px → 1 below 500px, 40px gap):**
- **Brand column** — Brand mark + wordmark in white, then description: "Helping organizations work smarter with Microsoft 365, AI, Automation, and Secure Digital Workplaces." (14px, max-width 320px, line-height 1.6)
- **Services** column — 5 links (Microsoft 365 Licensing, AI Strategy, Copilot Adoption, SharePoint, Cybersecurity)
- **Packages** column — 4 links (Bronze, Silver, Gold, Platinum)
- **Company** column — 4 links (About, Client Results, Contact, Privacy)
- Column headings in Manrope 600, 14px, white
- Links in 14px, hover: gold-400

**Bottom row** (top border 1px `rgba(255,255,255,0.08)`, 24px padding-top):
- Left: copyright "© 2026 LifeQuestAI. Microsoft partner. All rights reserved." (13px)
- Right: three social icons (LinkedIn, X, YouTube)
  - Each 36×36, 8px radius, `rgba(255,255,255,0.04)` bg, subtle border
  - Hover: gold-500 bg, navy icon, gold border
  - SVGs use `fill="currentColor"` (not stroke)

---

## Interactions & Behavior

### Navigation
- **Anchor scroll** — all in-page nav links (`#packages`, `#strategy`, etc.) should use smooth scroll. Add `html { scroll-behavior: smooth; }` or a scroll handler in your framework.
- **Sticky nav** — position sticky, z-index 50, top 0. Blur-backdrop should remain performant on scroll.

### Hover states (all use 150–250ms ease transitions)

| Element | Default | Hover |
|---|---|---|
| Primary button | gold bg, navy text | navy bg, gold-400 text, gold border, `translateY(-1px)` |
| Ghost button (light) | transparent, gray border | navy border, white bg |
| Ghost button (dark) | transparent, white/28% border | gold-400 border + text |
| Nav link | charcoal | navy-900 |
| Package card | gray-200 border | gray-300 border, `translateY(-4px)`, shadow-md |
| Business Setup card | gray-200 border | gold-500 border, `translateY(-2px)`, shadow-md |
| Why LifeQuestAI card | gray-50 bg, gray icon | white bg, gold border, **navy icon tile with gold icon** |
| Footer social icon | subtle gray bg | gold bg, navy icon |
| Arrow icon inside button | — | translates 3px right |

### Animations

**Hero core pulse** (`@keyframes pulse`) — 4s ease-in-out infinite:
```css
0%, 100% { transform: translate(-50%,-50%) scale(1);   opacity: 0.85; }
50%      { transform: translate(-50%,-50%) scale(1.1); opacity: 1;    }
```

No scroll-triggered animations are implemented. If you want to add reveal-on-scroll for polish, use Intersection Observer with 30ms stagger — but this is optional.

### Forms
There are no forms in this design. All CTAs are anchor links currently pointing to `#final` or `#`. **Developer must wire real destinations:**
- All "Book Consultation" / "Free Consultation" CTAs → real booking system (Calendly, HubSpot Meetings, native form)
- "Compare Packages" → scroll to `#packages` (already correct)
- "Request Pricing" (nav + Gold card) → same as booking OR dedicated pricing-inquiry form
- "Schedule Demo" (Platinum) → booking system
- Footer social links → real profile URLs

### Responsive breakpoints

| Breakpoint | Behavior |
|---|---|
| ≤ 1080px | Packages grid → 2 columns |
| ≤ 980px | Hero grid → single column, visual moves below copy |
| ≤ 900px | Why LifeQuestAI, Setups → 2 columns. Testimonials → 1 column. Benefits strip → 2 columns. Final CTA → 1 column. |
| ≤ 860px | Nav center links hide (brand + CTAs remain). **Developer should add a mobile menu / hamburger — not implemented in reference.** |
| ≤ 820px | Strategy comparison → 1 column. Footer → 2 columns. |
| ≤ 600px | Packages, Setups, Why → 1 column. |
| ≤ 500px | Footer → 1 column. |

---

## State Management

Site is fully static. No state management required unless the developer adds:
- Mobile menu open/closed toggle
- Form submission state (once real forms are wired)
- Cookie/consent banner (recommended for GDPR — not in current design)

---

## Assets

**No image assets** are used in the reference. Everything is CSS gradients, SVG icons, and typography.

**Icons:** All icons in the reference are inline SVGs using Lucide-icon style paths (24×24 viewBox, 2–2.5px stroke, `stroke-linecap: round`). Developer can either:
- Copy the inline SVGs from `reference/index.html` (fastest, no dependency)
- Install `lucide-react` / `lucide-vue-next` and use named components (recommended for consistency)
- Icons currently used: `arrow-right`, `check`, `user`, `shield`, `building`, `heart`, `trending-up`, `lock`, `grid`, `clock`, `zap`, `message-square`, `shield-check`, `git-branch`

**Brand logo:** Currently text-only ("LQ" monogram in a rounded-square tile + "LifeQuestAI" wordmark). If the client provides a real logo mark, swap the `.brand-mark` div for an `<img>` or inline SVG at the same 32×32 size.

**Hero visual:** Fully CSS + SVG — no image asset needed. If desired, replace with a real product screenshot or brand illustration at 4:5 aspect ratio.

**Fonts:** Load via Google Fonts CDN (URL in Design Tokens section). Optionally self-host via `fontsource` packages for privacy/performance:
- `@fontsource/manrope`
- `@fontsource/ibm-plex-sans`
- `@fontsource/ibm-plex-mono`

---

## Accessibility notes

- All interactive elements are semantic (`<a>`, `<button>`, `<nav>`, `<header>`, `<footer>`, `<section>`) — preserve when porting.
- Nav has `aria-label="Primary"`.
- Brand link has `aria-label="LifeQuestAI home"`.
- Hero visual is marked `aria-hidden="true"` (decorative).
- Social icons have `aria-label` for each platform.
- **Color contrast** — all text/bg combos meet WCAG AA. Do not lower opacity on body text below current values without re-checking.
- Focus states — reference uses browser defaults. **Developer should add visible focus rings** (recommend 2px gold-500 outline with 2px offset on all interactive elements).

---

## Files

Reference implementation in this bundle:

- `reference/index.html` — Complete single-page HTML with all 9 sections
- `reference/styles.css` — All styling with CSS custom properties for the design tokens

Both files are dependency-free (only external resource is the Google Fonts stylesheet). Open `reference/index.html` in any browser to see the intended output.

The source project also contains `DEPLOY.md` (deployment instructions for Cloudflare Pages) and `README.md` — those are for the operator, not the developer, but worth a glance for context on the target deployment environment.
