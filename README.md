# Handoff: Gago Homepage

## Overview
This is a high-fidelity, production-ready marketing homepage for **Gago**, a premium baby lotion brand launching late 2026. The site is designed for mothers who read ingredient labels. It tells the origin story (formulated in Copenhagen, made for India's heat), showcases the product philosophy, and drives waitlist signups with a linear narrative flow.

The bundled HTML files are **design references** — pixel-perfect mockups showing the final look and behavior. Your task is to recreate this design in your target framework (React, Next.js, Vue, Svelte, or your existing codebase) using established patterns, libraries, and design systems from that environment. Do not copy the HTML directly; instead, port the structure, styling, interactions, and content semantics to your framework.

---

## Fidelity
**High-fidelity (hifi)**: This is a pixel-perfect mockup with final colors, typography, spacing, and interactions. Recreate it with exact measurements and visual polish, but adapt it to your framework's best practices and component patterns.

---

## Design System / Tokens

### Color Palette
```
--arctic:       #F5F2EC  (off-white, main background)
--paper:        #ECE7DB  (light beige, secondary background)
--stone:        #8A8478  (muted taupe, secondary text)
--hairline:     #D9D3C5  (light border, dividers)
--ink:          #2A2722  (dark gray, primary text)
--terra:        #A85839  (terracotta, accent, buttons)
--terra-deep:   #8B4429  (darker terra, hover state)
--terra-pale:   #DEB39B  (lighter terra, labels on dark)
--sage:         #8FA38C  (muted green, unused in current design)
--sage-deep:    #6E8170  (dark green, unused)
--sage-pale:    #C5CFBE  (light green, unused)
```

### Typography
**Font families:**
- **DM Sans** (Google Fonts, weights 200, 300, 400) — body, headings, UI text
- **DM Mono** (Google Fonts, weights 300, 400) — labels, monospace accents, upper­case labels

**Type scale:**
- **h1**: `clamp(48px, 6.6vw, 108px)`, weight 200, line-height 0.98, letter-spacing -0.04em
- **h2**: `clamp(38px, 4.6vw, 72px)`, weight 200, line-height 1.02, letter-spacing -0.03em
- **h3**: 26px, weight 300, line-height 1.2, letter-spacing -0.01em
- **Body**: 17px, weight 300, line-height 1.65
- **Eyebrow** (accent label): 11px mono, uppercase, letter-spacing 0.2em, color: terra

### Spacing
- **Gutter** (horizontal padding): 40px desktop, 24px tablet+
- **Max content width**: 1320px
- **Section padding**: 140px vertical desktop, 80px tablet+
- **Grid gaps**: 96px (sections), 28-56px (components)

### Borders & Shadows
- **Hairlines**: 1px solid `--hairline` (#D9D3C5)
- **No shadows** — design uses flat, clean layers
- **Border-radius**: 0 (no rounded corners throughout)

---

## Page Structure & Sections

### 1. **Announcement Bar** (top sticky bar)
- **Height**: ~48px
- **Background**: `--ink` (#2A2722)
- **Text**: 11px mono, uppercase, color `--arctic`, centered
- **Content**: "Pre-launch · Daily Dissolve ships late 2026 · Waitlist now open — founders' pricing for the first 500"
- **Responsive**: Text stacks to blocks on mobile; separator (·) hidden <980px

### 2. **Navigation Bar** (sticky, blurred)
- **Height**: ~68px (18px vertical padding)
- **Background**: `rgba(245,242,236,0.88)` with `backdrop-filter: blur(12px)`
- **Border-bottom**: 1px solid `--hairline`
- **Layout**: Logo left | Nav links center (hidden <980px) | CTA button right
- **Logo**: "Gago" (26px, weight 300) + small terra dot
- **Nav links**: ["Origin" → #origin, "The product" → #product, "Credentials" → #credentials, "FAQ" → #faq]
- **CTA button**: "Join waitlist →" (11px mono, terra bg, black text, hover: terra-deep)

### 3. **Hero Section** (id="waitlist")
- **Background**: `--paper` (#ECE7DB)
- **Layout**: 2-column grid (1.05fr | 1fr) desktop, single column mobile
- **Left column**:
  - Crumb: "Coming late 2026" (badge, terra bg) + "Designed in Denmark · Made for India" (stone text)
  - **h1**: "Baby Lotion for the mother who knows" (max 14ch, terra italics optional)
  - **Body text**: 20px, 44ch max-width
  - **Email form**: Input + "Join waitlist →" button, max-width 480px
  - **Form note**: 10.5px mono, terra dot, "Founders' pricing for the first 500 · No spam, ever"
  - **Success message** (hidden until submit): "You're on the list. Welcome. We'll be in touch before the first batch ships."
  - **Meta row** (4 cols desktop, 2 cols tablet):
    - Launching | Late 2026
    - Volume | 10 fl oz · 295 ml
    - For | Body & face
    - Fragrance | None
- **Right column**: 
  - Terra bg with product photo (`product-photo.jpg`)
  - **Corner labels** (absolute, white text at ~75% opacity):
    - Top-left: "Gago / Daily Dissolve"
    - Bottom-left: "Fig. 01 · The Bottle"
    - Bottom-right: "10 fl oz · 295 ml"

### 4. **Marquee Strip** (full-width)
- **Background**: `--ink`
- **Height**: ~66px (22px padding)
- **Text**: 12px mono, uppercase, `--arctic`, looping animation
- **Content**: "Designed in Denmark · Made for India · For body and face · Fragrance free · Built for the heat · Suitable from day one · Late 2026 · Founders' pricing for the first 500" (repeats seamlessly)
- **Animation**: `marquee 38s linear infinite` (translateX 0 → -50%)

### 5. **Origin Section** (id="origin", bg: arctic)
- **Section eyebrow**: "01 / Origin · Delhi, May"
- **Layout**: 2-col grid (1.1fr | 1fr) desktop, 1-col mobile
- **Left**:
  - **h2**: "The Indian mother who knows her ingredient list" (max 14ch)
  - **Lead p**: 22px, weight 300
  - **Body paragraphs**: 18px, line-height 1.7, max-width 52ch
  - Key phrase italicized in terra: "The same lotion she had trusted all winter suddenly sat heavy"
- **Right (aside)**:
  - Border-left: 1px solid `--hairline`
  - Padding-left: 56px
  - **Label**: "Pull-quote" (10.5px mono, stone)
  - **Pull**: 32px, weight 200, "The same Danish *discipline*, rewritten for Indian skin, Indian heat, Indian humidity." (terra italics on "discipline")
  - **Meta** (3 rows, 24pt top border):
    - Formulated | Copenhagen, DK
    - Made | Bangalore, IN
    - Launching | Late 2026

### 6. **Banner Section** (full-width, bg: terra)
- **Background**: `--terra` (#A85839) with subtle radial gradients
- **Text-align**: center
- **Padding**: 160px vertical
- **Eyebrow**: 11px mono, terra-pale color
- **h2**: `clamp(48px, 7vw, 132px)`, "Built for the heat. *Designed to disappear.*" (arctic italics)
- **Decoration**: Thin line (~1px, 35% opacity) below "Designed to disappear"
- **Sub p**: 17px, arctic/85% opacity, 48ch max-width

### 7. **Pillars Section** (id: pillars, bg: paper)
- **Section eyebrow**: "02 / Three non-negotiables"
- **Head** (2-col grid desktop):
  - **h2**: "Less, when less is the *rigorous* answer." (terra italics)
  - **Body**: 17px, stone, 40ch max-width
- **Grid** (3-col desktop, 1-col mobile):
  - Border-top: 1px hairline
  - Each pillar: 56px padding (right 0, left varies), right-borders between (0 on last)
  - **Pillar label**: 11px mono, terra, "01 / Discipline" format
  - **Pillar h3**: 36px, weight 200, max 12ch, terra italics optional
  - **Pillar p**: 15.5px, stone, 32ch max-width

**Pillar content:**
1. "Every ingredient, *by name.*" → "Each component is chosen..."
2. "Made for the *weather*, not the shelf." → "Formulated for 38°C Delhi..."
3. "Reviewed in *India.*" → "Before each batch leaves..."

### 8. **Product Section** (id="product", bg: arctic then terra)
- **Head** (centered):
  - Eyebrow: "The first bottle"
  - h2: "Daily Dissolve. *One lotion. Whole family.*" (terra italics)
- **Product stage** (2-col desktop, 1-col mobile):
  - **Left**: Product image (terra bg, 720px min-height desktop)
  - **Right** (terra bg, arctic text):
    - **Tag**: 11px mono, terra-pale, "Pre-launch · First batch"
    - **Product name** (h3): `clamp(48px, 5.4vw, 88px)`, "Daily Dissolve." (italic)
    - **Body**: 17px, arctic/88%, 38ch max-width
    - **Specs** (2-col grid, 420px max-width):
      - Suitable from | Day one
      - Fragrance | None
      - Volume | 10 fl oz · 295 ml
      - Texture | Featherweight

### 9. **Credentials Section** (id="credentials", bg: paper)
- **Section eyebrow**: "03 / Credentials"
- **Head h2**: "Three people you'd trust your own *skin* to." (terra italics)
- **Grid** (3-col desktop, 1-col mobile):
  - Border-top & bottom: 1px hairline
  - Each cred: 48px padding (right 0, left varies), right-borders between
  - **Label**: 11px mono, terra, "01 / Formulator"
  - **Text**: 22px, weight 300, max 26ch
  - **Location** (auto margin-top): 11px mono, stone, with terra dot

**Credentials:**
1. "A Danish cosmetic chemist with twenty years in barrier-friendly skincare." → Copenhagen, DK
2. "An Indian pediatric dermatologist who reviews every batch before it ships." → Mumbai, IN
3. "GMP-certified facility. Small, lot-traceable batches." → Bangalore, IN

### 10. **Founder Section** (bg: ink, color: arctic)
- **Grid** (2-col desktop, 1-col mobile, 96px gap):
  - **Left**: Image slot (4:5 aspect, stone bg, 320px max-width mobile)
    - Tag (absolute top-left): "Pragya · Delhi" (10.5px mono, arctic/70%)
  - **Right**:
    - **Label**: 11px mono, terra-pale, "A note from the founder"
    - **Quote** (h3-like, 28–44px): "I started Gago in a Delhi bathroom..." (terra-pale italics on "same discipline")
    - **Quotes**: Rendered as :: before/after (terra color, 1.2em size)
    - **Attribution** (flex, 16px gap):
      - Terra swatch (4px width, 44px height)
      - Name (16px, weight 400) + Role (10.5px mono, terra-pale)

### 11. **Voices Section** (bg: arctic)
- **Section eyebrow**: "04 / From the waitlist"
- **Head** (2-col grid desktop):
  - **h2**: "The people we're *building* this for." (terra italics)
  - **Body**: 17px, stone, 38ch max-width
- **Voice cards** (3-col desktop, 1-col mobile):
  - **BG**: paper, padding 36px 32px, min-height 280px
  - **Stars**: 12px mono, 0.3em spacing, terra color ("★ ★ ★ ★ ★")
  - **Quote**: 17px, weight 300, flex-grow (fills vertical space)
  - **Meta**: 10.5px mono, stone; name in ink
  - **Card 1**: Priya R., Mumbai · Mother of one
  - **Card 2**: Tanvi S., Bangalore · Mother of two
  - **Card 3**: Maya K., Delhi · Expecting

### 12. **FAQ Section** (id="faq", bg: paper)
- **Section eyebrow**: "05 / Questions"
- **Head h2**: "Ask us anything. *We'll tell you.*" (terra italics)
- **Details/Summary list**:
  - Border-top: 1px hairline
  - Each `<details>` has bottom border, 28px padding (open: expanded)
  - **Summary**: 24px, weight 300, flex (space-between), cursor pointer
  - **Toggle icon** (span): "+" (22px mono, stone), rotates 45° on open, terra color on open
  - **Answer** (div, margin-top 18px): 16px, stone, max-width 64ch
- **Questions** (all with default content visible, first open):
  1. When does Gago launch?
  2. Who is it for?
  3. Why "designed in Denmark, made for India"?
  4. Why only one product?
  5. What's on the waitlist?
  6. How much will it cost?
  7. Where will you ship?

### 13. **Final CTA Section** (bg: terra, color: arctic)
- **Background**: terra with subtle radial gradients
- **Padding**: 160px top, 140px bottom
- **Eyebrow**: 11px mono, terra-pale, "Join the waitlist"
- **h2**: `clamp(56px, 7.6vw, 132px)`, "Be one of the first *five hundred.*" (arctic italics)
- **Sub p**: 19px, arctic/88%, 44ch max-width
- **Form**: (same as hero, but `on-dark` variant)
  - Border: 1px arctic
  - BG: transparent
  - Input: arctic text, placeholder arctic/55%
  - Button: arctic bg, ink text, hover terra
- **Form note**: 10.5px mono, arctic/65%, "Spot #1,248 waiting · Of 500 founders' spots" (dynamic counter)
- **Success message** (hidden): "You're in. Welcome. Check your inbox for your waitlist number."
- **Perks** (3-col grid desktop, 1-col mobile):
  - Border-top: 1px arctic/20%
  - **Perk label**: 10.5px mono, terra-pale
  - **Perk text**: 17px, arctic, weight 400, max 24ch

### 14. **Footer** (bg: ink, color: arctic)
- **Grid** (4-col desktop: 1.4fr 1fr 1fr 1fr; 2-col tablet):
  - **Brand col**: Logo (64px, weight 200) + dot + tagline (14px, arctic/55%, 30ch max)
  - **Brand links**: Origin, Daily Dissolve, Credentials, FAQ
  - **Contact links**: hello@gago.in, Press, Stockists
  - **Origin**: "Formulated in Copenhagen / Manufactured in Bangalore"
- **Bottom** (flex, space-between, 80px top margin):
  - "© Gago 2026 · Designed in Denmark · Made for India" (mono, arctic/55%)
  - "v 2.0 · Pre-launch" (mono, arctic/55%)

---

## Interactions & Behavior

### Email Forms (2 instances: hero, final CTA)
- **Validation**: Basic email regex (`/^[^\s@]+@[^\s@]+\.[^\s@]+$/`)
- **On invalid**: Input border turns terra color
- **On valid submit**:
  1. Form hides (display: none)
  2. Form note hides
  3. Success message shows (added class `.show`)
  4. Data persisted to `localStorage` (keys: `gago_waitlist_email`, `gago_waitlist_count`)
  5. If user reloads, form stays hidden; success message shows
- **Spot counter** (#spot-num): Starts at 1248, increments by 1 per submission (demo logic; in production, query backend)

### FAQ Accordion
- **Native `<details>/<summary>`** (no custom JS needed)
- **First `<details>` opens by default** (open attribute)
- **Summary**:
  - Hover: text color → terra, cursor pointer
  - Details[open]: text → terra
  - Toggle icon: stone → terra on open, rotates 45° (transform: rotate(45deg))
- **Answer**: Slides down on open (browser default `<details>` behavior)

### Navigation
- Sticky nav (top: 0, z-index: 30)
- Anchor links: #origin, #product, #credentials, #faq
- Smooth scroll enabled (html { scroll-behavior: smooth; })

### Image Slot (Founder section)
- Custom `<image-slot>` web component (loaded from `image-slot.js`)
- Accepts drag-and-drop from user
- Placeholder text: "Drop a portrait of Pragya"
- Data persists via localStorage (component handles it)

### Marquee Animation
- CSS keyframe `marquee`: 0% { translateX(0) } → 100% { translateX(-50%) }
- Duration: 38s, linear, infinite
- Duplicated content (two spans) for seamless loop

---

## Responsive Breakpoint

**Single breakpoint: 980px**

**Desktop (>980px)**:
- Gutters: 40px
- Hero grid: 2-col (1.05fr | 1fr)
- Origin grid: 2-col (1.1fr | 1fr)
- All multi-col grids visible (3-col or 4-col as specified)
- Nav links visible
- Founder grid: 2-col

**Tablet & mobile (<980px)**:
- Gutters: 24px
- Hero grid: 1-col; h1 font-size `clamp(40px, 10vw, 64px)`; meta-row 2-col
- All multi-col grids collapse to 1-col
- Borders shift from right (desktop) to bottom (mobile)
- Nav links hidden
- Founder grid: 1-col; image max-width 320px
- Announcement bar: text stacks, separator hidden
- Section padding: 80px (vs 140px desktop)
- Banner padding: 96px (vs 160px desktop)
- Final CTA perks: 1-col grid

---

## Assets Required

- **Image**: `product-photo.jpg` — Product bottle on terracotta background (~1000×600px minimum)
- **Founder portrait**: Dropped via `<image-slot>` in the browser by user (no pre-loaded file)
- **Fonts**: DM Sans & DM Mono (loaded via Google Fonts `<link>` tags)

---

## State & Data Flow

### Waitlist Form State
```javascript
localStorage['gago_waitlist_email']  // User's email (if submitted)
localStorage['gago_waitlist_count']  // "1" if submitted, else "0"
```

- On page load, check if email exists in localStorage
- If yes, hide form & note, show success message
- Counter (#spot-num) increments: base (1247) + (1 if submitted else 0)

### Image Slot State
- `<image-slot>` persists dropped image to its own localStorage (component-managed)
- No custom JS needed; component handles it all

---

## Browser Support
- Modern browsers (Chrome, Firefox, Safari, Edge)
- CSS: Grid, Flexbox, clamp(), backdrop-filter, CSS custom properties
- JS: localStorage, basic DOM manipulation (no frameworks required for vanilla HTML version)

---

## Files Included

- `Homepage.html` — Full production HTML (all CSS inline, vanilla JS form handling)
- `image-slot.js` — Web component for image uploads (drag-and-drop, localStorage)
- `product-photo.jpg` — Product image placeholder (to be replaced)

---

## Notes for Implementation

1. **Semantic HTML**: The design uses clean semantic markup (sections, nav, header, footer, article, aside, details/summary).
2. **CSS approach**: All styles are in a single `<style>` block using CSS custom properties for colors and spacing.
3. **JavaScript**: Minimal — form validation, localStorage, and native `<details>` behavior. No frameworks required.
4. **Fonts**: External (Google Fonts). Consider self-hosting in production.
5. **Mobile-first philosophy**: Not strictly mobile-first, but responsive via single media query at 980px.
6. **Accessibility**: Semantic elements, ARIA hidden on marquee, form labels implied via placeholder, nav links are semantic `<a>` tags.
7. **Performance**: No animations except CSS marquee. Image lazy-loading can be added to the `<img>` tag.
8. **Form integration**: Currently logs to localStorage. Before launch, integrate with Mailchimp, Loops, or your email service via API.

---

## Design Intent

This homepage tells a **clear, linear story**:
1. **Announcement** — Pre-launch, waitlist open
2. **Hero** — Product and value proposition in one visual statement
3. **Origin** — Why Gago exists (founder's real pain point)
4. **Banner** — Core brand promise (built for heat, disappears)
5. **Pillars** — Three uncompromising values
6. **Product** — Detailed look at Daily Dissolve
7. **Credentials** — Trust (formulator, reviewer, maker)
8. **Founder** — Human connection (Pragya's voice)
9. **Voices** — Social proof (early waitlist testimonials)
10. **FAQ** — Objection handling
11. **Final CTA** — One last push to join
12. **Footer** — Navigation & brand info

**Visual language**: Minimal, refined, high-contrast (dark ink on light arctic/paper). Terracotta is the only accent; it draws the eye to CTAs and key phrases. Typography is generous, breathing room is intentional. No clutter, no decoration — every element earns its place.
