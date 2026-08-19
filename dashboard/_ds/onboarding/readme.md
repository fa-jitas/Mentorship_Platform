# Fly Bites — Design System

Fly Bites is a mobile app concept for ordering food inside an airport terminal. You give it
your flight, it shows you what you can eat before you board: what's near your gate, how long
the wait is, whether you can still make it. The whole system is drawn for one surface — a
393 × 852 iPhone frame — and one job: **eat before the gate closes.**

Everything in this folder was extracted from the attached Figma file, `Design System.fig`
(mounted read-only; no public URL was provided). It has five pages:

| Figma page | What's in it |
| --- | --- |
| `Design Guideline: Colors, Typograhy` | The pinned palette, typeface exploration (Inter vs Lato vs Roboto), icon/nav specimen, brand lockup |
| `Hi-Fidelity Screens` | 35 frames — the finished app, and the source for the UI kit here |
| `Mid-Fidelity Screens` | 2 frames, greyboxed layout studies |
| `Low-Fidelity Screens` | 6 frames, early sketches |
| `copy` | A near-duplicate of the hi-fi page (working copy) |

Because `copy` duplicates the hi-fi page, several component families appear twice or three
times in the file inventory (Nav Bar ×3, Flight Info ×2, Order Button ×2, Button ×2). They are
the same component; this system builds one canonical version of each.

**There is no logo file in the source.** The brand appears two ways, both reproduced here: the
wordmark set in Inter — `Fly` in navy semibold + `Bites` in green — and a donut glyph bitmap
(`assets/wordmark-donut.png`, plus the green-tile version `assets/brand-mark.png`) sitting
beside it. Nothing was drawn or invented. If a real mark exists, drop it in `assets/` and it
should replace the bitmap.

---

## Content fundamentals

The voice is a friendly gate agent: short, warm, practical, and always about time.

- **Sentence case everywhere.** "Near you", "Past Orders", "Add to your order", "Order your
  favorites". Never all-caps, never Title Case On Every Word.
- **Second person, and only when it earns it.** "Your meal and flight, tracked together."
  "Add to your order." "Near you." The app never says "I".
- **Onboarding copy is two lines: a greeting, then the payoff.** "Welcome aboard!" /
  "Your meal and flight, tracked together". "Order your favorites" / "No stress, no lines.
  Just great food!" Exclamation points are allowed here and basically nowhere else.
- **Forms are blunt and literal.** "Please enter the following:", then bare field labels —
  "Flight Number", "Airport Name", "Email" — with example-style placeholders ("123NVR5",
  "Enter Airport Name"). Required rules are stated in the open: "Required - Select 1".
- **Actions are lowercase verb phrases with a direction.** "continue to payment →", "add",
  "Customize", "Next", "Skip". The arrow does the work; there's no "Submit".
- **Meta is a dot-separated fact strip, never a sentence.** `3.8 ★ (50+) · 0.2mi · 20min`.
  Distances mix units the way a person would — `0.2mi`, `877ft`. Times are abbreviated with
  no space: `20min`, `5min`, `10min`.
- **Status is stated as a promise, not a percentage.** "Ready in 15". "3:45 PM pickup".
- **Prices are numeral-then-symbol:** `15.99$` — unusual, and it's what the file says.
- **Vendor names are invented and playful** — Bwurgwers, Chickwin, Submethod, Boobas, Yum,
  Goodies, Market Fresh, Harvest, Mama's Italian, Potrero Grill, Plate Land, Bowl Land. Use
  fictional vendors in mocks; don't put real airport brands in.
- **No emoji, anywhere.** Category chips carry small multicolour glyphs instead. Two typos
  ride along in the source screens ("Cusine", "Protrero Grill") — fixed silently in new copy.

---

## Visual foundations

**Palette.** Six colours are pinned in the Figma "Color Scheme" section and they carry the
whole app: ink `#232B2B` for all text and icon strokes, navy `#082442` for primary actions and
the order bar, brand green `#8AB782` for the wordmark, hero blobs and the logo tile, white for
every page, grey `#E5E6EA` for the two filled surfaces that exist (search field, category
chip), and blue `#4CA7FF`. Secondary text is not a separate grey — it's ink at 50% opacity
(`rgba(35,43,43,0.5)`). Hairlines are `#DDDDE3`. The teals, corals and yellows in
`tokens/colors.css` are **illustration colours** living inside the category glyphs; they are
not UI states. The system has no red error colour and no green success colour — status is
communicated with words.

**Type.** Inter only, in five sizes that do almost everything: 12px (by far the most used —
all meta and chips), 16px (list titles, input values, buttons), 14px (the small label sitting
above a value), 20px (screen titles, section headers, and key values like "Gate 9A" /
"4:15 PM"), 22px/35px for the wordmark. Weights run Light 300 → Semibold 600; Semibold 20px is
the section header, Medium 20px is a data value, Regular 20px is a screen title. **Line-height
is 100% on nearly everything** — the design is built from tight single lines, with 1.5 reserved
for input values and paragraphs. The wordmark sets 0.08em letter-spacing; nothing else tracks.
Manrope Bold 18px appears in one place (map/gate labels) and is kept as `--font-display`.

**Layout.** One 393 × 852 frame. A 24px gutter on every section, a 100px bottom nav pinned to
the frame, and content stacked in full-width "sections" separated by a hairline — 1px on three
sides and **1.5px on the dividing edge**, which is the file's signature detail. Inner rhythm is
4 / 8 / 10 / 12 / 20 / 24. Horizontal card rails scroll (photo cards 200×100, gap 12) and the
category chip row scrolls; nothing else does.

**Corners.** 12px on photo cards, 20px on the 40px-tall search field, 24px on buttons, chips
and the order bar, 30px on the brand pill, and full circles for avatars, map pins and the
onboarding blobs. Nothing is square except the map plane.

**Cards.** Fly Bites cards are borderless and shadowless: a rounded photo, then text beneath
on the page background. Separation comes from the hairline sections, not from elevation.

**Elevation.** Exactly one shadow exists in the file — `0 4px 4px rgba(0,0,0,0.25)` under the
bottom nav bar. Use no others. There are no glows, no protection gradients, no blur/glass; the
one translucency in the system is ink at 50%/25% for secondary text.

**Backgrounds.** White. Photography is the only imagery: warm, saturated, top-down food shots
with shallow depth of field, cropped to fill (`center / cover`). No patterns, no textures, no
gradients, no illustration scenes. The onboarding screens are the exception — a flat green
circle (`#8AB782`, ~284–316px) sits behind the wordmark.

**Icons.** Two families, both from the source, described in detail below.

**Interaction.** The Figma file specifies states in the Icon-button set (Enabled / Hover /
Pressed / Focused / Disabled) and in the Brand button set (Default / Hover / Pressed, plus
Disabled, Loading, Skeleton flags). It does **not** specify motion — no easing curves, no
durations, no transitions are defined anywhere. So: hover darkens or fills the surface, press
uses the Pressed variant's fill (no scale), focus draws the `FocusIndicator` ring, disabled
drops opacity. If you need motion, keep it plain and short (a 150ms fade / colour step) and
flag that it isn't in the source.

---

## Iconography

Three distinct icon vocabularies, all copied out of the file rather than redrawn:

1. **Phosphor-style 24px line icons, ink-coloured** — the app's primary UI set:
   AirplaneTilt, MagnifyingGlass, ShoppingCart, ArrowRight, Star, dot separators, hamburger.
   1.5px-ish strokes, rounded joins, drawn on a 24px box with the glyph inset ~3px. These live
   inline inside the materialized screens (as `currentColor` SVG paths) and inside
   `components/*.jsx`.
2. **Flaticon "fi-rr-" uicons** — `fi-rr-utensils`, `fi-rr-arrow-up` — used as map/POI marks.
   Extracted to `components/icons/icon-data.js` and rendered via `<Icon name="fi-rr-utensils" />`.
3. **Multicolour flat glyphs (svgrepo)** — the eight category chips: Near You, Grab&Go, Dine In,
   Past Ordered, Drinks, Beauty, Convenience, Electronics. These are the only place the coral /
   teal / yellow accents appear. They are multi-path, 16px, and must not be recoloured.

`components/icons/icon-data.js` also carries `exit`, `menu` and `search`. No icon font and no
sprite sheet is used; no CDN icon set was substituted — everything is the file's own geometry.
Emoji and unicode-as-icon are never used. Star ratings are the ink-filled Phosphor star, not
a unicode ★, in product UI.

---

## Index

```
styles.css              the one file consumers link (imports only)
base.css                resets + link colours
tokens/                 colors.css · typography.css · space.css · fonts.css
guidelines/             foundation specimen cards (Design System tab)
components/             the component families from the Figma file
components/icons/        icon-data.js + <Icon>
ui_kits/onboarding/       the app recreation: 15 screens + interactive index.html
assets/                 brand-mark.png (green donut tile) · wordmark-donut.png
SKILL.md                portable Agent-Skill entry point
```

### Components

Built from the Figma component inventory (family name in the file → export here):

| Export | Figma family | Variants |
| --- | --- | --- |
| `Badge` | Badge | Type ×2 |
| `BatteryDark` | Battery / Dark | Status ×2, Level ×3 |
| `BrandButton` | Brand button | Shape, State, Disabled, Skeleton, Loading, Size, Type, Content type (360) |
| `Button` | Button | Property 1 ×2 |
| `ComponentsTextFieldPrefix` | Components/Text field prefix | Type, State |
| `ComponentsTextFieldSuffix` | Components/Text field suffix | State ×2, Type ×2 |
| `Divider` | Divider | Thickness ×2 |
| `FlightInfo` | Flight Info | Property 1 ×2 |
| `IconButtonStandard` | Icon button - standard | Type ×2, Size ×5, Width ×3, State ×5 (150) |
| `InformationCircle` | Information-circle | Type ×2 |
| `NavBar` | Nav Bar | Property 1 ×5 |
| `NavBar2` | Nav Bar (second set, hi-fi page) | Property 1 ×5 |
| `OrderButton` | Order Button | Default / Collapsed |
| `Plate` | Plate | Shape ×5 |
| `WiFiSignalDark` | WiFi Signal / Dark | Property 1 ×4 |
| `Placeholder` | Placeholder (standalone) | — |
| `Loading` | Loading (standalone) | — |
| `StarsFilled` | stars_filled (standalone) | — |
| `FocusIndicator` | Focus indicator (standalone) | — |
| `CoverPage` | Cover Page (standalone) | — |
| `Exit` | exit (standalone) | — |
| `FiRrUtensils` | fi-rr-utensils (standalone, kept as a component for the map screens) | — |
| `Icon` | wrapper over `icon-data.js` (fi-rr-utensils, fi-rr-arrow-up, exit, menu, search) | — |

## Intentional additions

These exports have no component family behind them in the Figma file and are here on purpose.
Confirmed intentional — do not rename them:

| Export | Why it exists |
| --- | --- |
| `Icon` | Thin wrapper so the extracted glyph set can be used by name. |
| `Onboarding1` | Screen frame "Onboarding 1". |
| `Onboarding2` | Screen frame "Onboarding 2". |
| `InputFlightStatus` | Screen frame "Input Flight Status". |
| `HomeV1` | Screen frame "Home V1". |
| `HomeAfterOrdering` | Screen frame "Home (after ordering)". |
| `Menu2` | Screen frame "Menu" (restaurant menu). |
| `Checkout` | Screen frame "Checkout" (item customise). |
| `Cart` | Screen frame "Cart". |
| `Approval` | Screen frame "Approval". |
| `FlightOrderStatus` | Screen frame "Flight Order Status". |
| `OrderStatusInDetail` | Screen frame "Order Status in Detail". |
| `GrabGo` | Screen frame "Grab&Go". |
| `Saved` | Screen frame "Saved". |
| `Map` | Screen frame "Map". |
| `MapDirectory` | Screen frame "Map Directory". |
| `NavBar2` | The hi-fi page's second Nav Bar variant set, kept distinct from `NavBar`. |
| `FiRrUtensils` | The fi-rr-utensils uicon, kept as a component for the map screens. |

No primitive was invented.

### UI kit screens (`ui_kits/onboarding/`)

`Onboarding1`, `Onboarding2`, `InputFlightStatus`, `HomeV1`, `HomeAfterOrdering`, `Menu2`
(restaurant menu), `Checkout` (item customise), `Cart`, `Approval`, `FlightOrderStatus`,
`OrderStatusInDetail`, `GrabGo`, `Saved`, `Map`, `MapDirectory`. `index.html` runs them as a
click-through prototype.

---

## Caveats

- Figma **Variables** in this file are a 12-variable Material-3 leftover (`Schemes/On Surface`,
  `static/body-large/…`), not the app's tokens. They're preserved verbatim in
  `components/fig-tokens.css`; the real token set is `tokens/*.css`, transcribed from the
  screens and the pinned palette.
- The file defines **no text styles and no effect styles** as Figma styles, so
  `components/fig-typography.css` is empty. Type roles here were derived from the counted
  sizes/weights and the "Final_Typeface" specimen.
- Inter and Manrope are served from Google Fonts (both open source; identical to the source
  faces). No font binaries were included in the Figma file.
- Screen components under `ui_kits/onboarding/` are machine-extracted and large; they are
  pixel-accurate transcriptions, not hand-written code.
