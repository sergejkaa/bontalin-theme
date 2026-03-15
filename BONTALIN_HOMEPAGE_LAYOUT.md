# Bontalin — Homepage Layout

## Project Overview

**Client:** Bontalin
**Store type:** Refurbished Apple devices (iPhones, iPads, Screen Protectors, Charging Accessories)
**Market:** Germany / German-speaking Europe (DE / AT / CH)
**Style:** Modern, clean, professional. Blue tones. NOT colorful or kitschy.
**Upsell:** Customers should easily add accessories (screen protector, charging cable) when buying a phone.

---

## Theme Info

All required `.liquid` section files already exist in `/sections/` — no new files need to be created. Only `templates/index.json` needs to be updated.

Color schemes are already configured in `config/settings_data.json`:
| Scheme | Background | Text | Use for |
|--------|-----------|------|---------|
| scheme-1 | `#ffffff` | dark | neutral/white sections |
| scheme-2 | `#BEE3F8` | `#1D3557` | accent-light sections |
| scheme-3 | `#1D3557` | `#EAF6FF` | navy/dark sections |
| scheme-4 | `#EAF6FF` | dark | page background sections |

---

## Design System

### Colors
| Hex | Usage |
|-----|-------|
| `#EAF6FF` | Page background, light sections |
| `#BEE3F8` | Highlights, subtle backgrounds |
| `#4EA8DE` | Price tags, CTAs, accents |
| `#1D3557` | Header, Footer, dark sections |

### Style Rules
- Rounded corners: 8–12px
- Buttons: solid `#1D3557` / `#EAF6FF` text
- No gradients unless specified
- Price/accent text: `#4EA8DE`

---

## Collections (confirmed handles)

| Collection | Handle |
|-----------|--------|
| iPhones | `apple-iphones` |
| iPads | `ipads` |
| Screen Protectors | `displayschutzfolien` |
| Charging Accessories | `ladezubehor` |

## Product handles (looping marquee)

- `iphone-11-refurbished`
- `iphone-12-refurbished`
- `apple-iphone-14-refurbished`
- `apple-iphone-15-refurbished`
- `iphone-se-2020-schwarz-generaluberholt`

---

## Schema Constraints (range fields — critical for index.json)

Shopify rejects values that don't match the step. Use only valid values:

| Section | Setting | Min | Max | Step | Valid values (examples) |
|---------|---------|-----|-----|------|------------------------|
| hero-elite | `content_max_width` | 320 | 1200 | 40 | 760, 800, 840, **880**, 920 |
| hero-elite | `overlay_opacity` | 0 | 90 | 5 | 55, 60, 65 |
| hero-elite | `height_desktop` | 20 | 100 | 5 | 85, 90, 95 |
| hero-elite | `height_mobile` | 20 | 100 | 5 | 80, 85, 90 |
| hero-elite | `content_padding` | 16 | 120 | 8 | 40, 48, 56 |
| hero-elite | `content_gap` | 4 | 60 | 2 | 20, 24, 28 |
| hero-elite | `animation_duration` | 400 | 1600 | 100 | 700, 800, 900 |
| metrics-bar | `pad_top/pad_bottom` | 0 | 120 | 2 | 36, 48 |
| metrics-bar | `kicker_size` | 12 | 28 | 1 | 16, 18 |
| metrics-bar | `kicker_weight` | 300 | 900 | 10 | 600 |
| metrics-bar | `value_size` | 24 | 80 | 1 | 42, 48 |
| metrics-bar | `sub_size` | 10 | 22 | 1 | 13, 14 |
| metrics-bar | `stars_size` | 12 | 24 | 1 | 18, 21 |
| metrics-bar | `anim_duration` | 400 | 3000 | 100 | 1200 |
| testimonials-slider | `padding_top/bottom` | 0 | 120 | 4 | 24, 48 |
| testimonials-slider | `max_chars` | 80 | 400 | 10 | 180, 220 |
| testimonials-slider | `content_max` | 800 | 1400 | 20 | 1200 |
| testimonials-slider | `nav_opacity` | 20 | 100 | 5 | 80 |
| looping-products | `padding_top/bottom` | 0 | 120 | 4 | 32 |
| looping-products | `marquee_speed` | 8 | 60 | 1 | 23 |
| looping-products | `item_gap` | 0 | 60 | 2 | 14 |
| multicolumn | `padding_top/bottom` | 0 | 100 | 4 | 36, 48 |
| rich-text | `padding_top/bottom` | 0 | 100 | 4 | 20, 56 |
| newsletter | `padding_top/bottom` | 0 | 100 | 4 | 32, 56 |
| waves | `desktop_wave_height` | 30 | 230 | 2 | 36 |
| waves | `mobile_wave_height` | 8 | 120 | 2 | 14 |
| waves | `wave_speed` | 4 | 24 | 1 | 14 |

---

## Homepage Section Order (templates/index.json)

Sections in exact order:

1. `hero-elite`
2. `looping-products`
3. `collection-list`
4. `featured-collection`
5. `metrics-bar`
6. `multicolumn`
7. `rich-text`
8. `testimonials-slider`
9. `newsletter`
10. `waves`

---

### 1. Hero Elite

- Eyebrow: `"Refurbished. Tested. Certified."` / color `#bee3f8`
- Heading: `"Erinnerungen erschaffen, nicht Ressourcen verschwenden."`
- Subheading: `"Refurbished iPhones & smartphones — up to 50% cheaper than new."`
- Button 1: `"Shop iPhones"` → `shopify://collections/apple-iphones` (pill-solid)
- Button 2: `"Learn More"` → `shopify://pages/about` (outline)
- Trust badges: Professional Refurbishment / 24-Month Warranty / Free DHL Shipping — icon color `#4ea8de`
- `overlay_color`: `#1d3557`, `overlay_opacity`: 60, `overlay_gradient`: none
- `color_scheme`: scheme-3, `animation_style`: fade-up, `animation_duration`: 800
- `content_max_width`: 880, `content_padding`: 48, `content_gap`: 24

---

### 2. Looping Products Marquee

- `marquee_heading`: `"SMARTPHONES AT THE BEST PRICE"`
- Products: 5 iPhones (see handles above)
- `price_color`: `#4ea8de`, `marquee_speed`: 23
- `color_scheme`: scheme-4, `hide_price`: false

---

### 3. Collections Grid

- `title`: `"Our top categories"`
- 4 collections: apple-iphones, ipads, displayschutzfolien, ladezubehor
- `columns_desktop`: 4, `columns_mobile`: "2"
- `color_scheme`: scheme-1

---

### 4. Featured Products

- `title`: `"Offers for you"`, `collection`: apple-iphones
- `products_to_show`: 6, `columns_desktop`: 4, `columns_mobile`: "2"
- `color_scheme`: scheme-4

---

### 5. Metrics / Trust Bar

- `kicker`: `"Trusted by thousands of customers across Europe."`
- metric1: `4.9` suffix `★` sub `"Customer rating"`
- metric2: `50` suffix `%` sub `"cheaper than new"`
- `color_scheme`: scheme-3, `value_color`: `#4ea8de`, `kicker_color`: `#eaf6ff`

---

### 6. Why Bontalin? (4 columns)

- `title`: `"Why is it worth it for you?"`
- Col 1: 24-Month Warranty
- Col 2: Professionally Tested
- Col 3: Free DHL Shipping
- Col 4: Save up to 50%
- `columns_desktop`: 4, `color_scheme`: scheme-4

---

### 7. For a Sustainable Future

- Heading: `"For a Sustainable Future"`
- Body: `"By purchasing a refurbished smartphone, you contribute to reducing electronic waste and extending the lifespan of electronic devices. At Bontalin, we are proud to offer you sustainable solutions without compromising on quality. Together, we protect the environment — one refurbished device at a time."`
- `color_scheme`: scheme-2, centered

---

### 8. Customer Reviews

- `heading`: `"Real customer stories"`, `color_scheme`: scheme-4
- 7 reviews, all 5 stars, about iPhone purchases, in German or English
- Reviewers: Klaus M. (Munich), Marie S. (Hamburg), Thomas B. (Berlin), Laura K. (Vienna), Felix W. (Zurich), Anna P. (Frankfurt), Markus R. (Cologne)

---

### 9. Newsletter

- Heading: `"Subscribe to our newsletter and secure a €10 welcome voucher!"`
- Subheading: `"Be the first to know about new arrivals, exclusive deals and refurbishment tips."`
- `color_scheme`: scheme-3

---

### 10. Wave Divider (pre-footer)

- All wave colors: `#1d3557` (must match footer background)
- `flip_wave`: false, `color_scheme`: scheme-4
- `wave1_opacity`: 100 (front solid floor: true)

---

### 11. Footer (configured separately, not in index.json order)

- `color_scheme`: scheme-3
- 4 columns: Brand | Quick Links | Customer Service | Contact
- Social: Instagram, Facebook
- Copyright: `"© 2025 Bontalin. All rights reserved."`
