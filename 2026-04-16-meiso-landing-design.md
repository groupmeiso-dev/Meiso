# MĒISØ Landing Page — Design Spec

## Overview

Landing page for MĒISØ — architecture and design studio. Single-page site with 5 sections, dark theme, Swiss brutalism aesthetic with numbered sections.

**Tech stack:** Vanilla HTML / CSS / JS (no frameworks)
**Language:** Russian
**Brand:** MĒISØ — architecture & design (meiso.team)

---

## Brand Identity

### Logo
- Graphic mark: black hole / orbital brush-stroke circle with diagonal slash
- Wordmark: MĒISØ (geometric sans-serif, macron over E, slashed O)
- Subtitle variant: "architecture & design"
- Logo files: `assets/logo/LOGO/` — PNG with alpha, animation assets (AE, MOV, MP4), individual letter PNGs

### Color Palette
| Token        | Value              | Usage                          |
|--------------|--------------------|--------------------------------|
| `--bg`       | `#141416`          | Main background                |
| `--text`     | `#FFFFFF`          | Headings, primary text         |
| `--text-secondary` | `rgba(255,255,255,0.65)` | Body text, descriptions |
| `--text-muted` | `rgba(255,255,255,0.5)` | Labels, captions         |
| `--text-subtle` | `rgba(255,255,255,0.45)` | Footer, minor elements  |
| `--accent`   | `#C75B3B`          | Terracotta — CTA, highlights   |
| `--divider`  | `rgba(255,255,255,0.08)` | Section borders, lines  |
| `--surface`  | `#1e1e20`          | Card backgrounds               |

### Typography
- **Headings:** Bold grotesque (Inter Black or similar), uppercase, tight letter-spacing (-1px)
- **Body / Labels:** Monospace (JetBrains Mono or Courier New), uppercase for labels, 9-10px with wide letter-spacing
- **Section numbers:** 48px, font-weight 900, very low opacity (0.06) — decorative element

---

## Sections

### 1. Header + Hero
- **Nav:** Logo mark (circle + slash) + "MĒISØ" wordmark left, menu links right (Услуги, О студии, Проекты, Контакты — last one in terracotta)
- **Hero headline:** Large (56px+) uppercase: "Архитектура, как искусство создания жизни" — last line in terracotta
- **Right column:** Short description with terracotta left-border: "Проектируем пространства, в которых будут жить люди, решения и эмоции." + CTA link "Оставить заявку →"
- **Decorative divider:** Horizontal line + "architecture & design" + terracotta accent line

### 2. Section 01 — Услуги (Services)
- **Section header:** Large faded "01" + "Услуги" heading + terracotta underline
- **First row (3 columns):** Проектирование, 3D-визуализация, Рабочая документация
- **Second row (4 columns):** Комплектация и надзор, Международные проекты, Айдентика и брендинг, Motion-анимация
- Each service has: terracotta number (01-07), uppercase title, monospace description
- Separated by thin vertical dividers

**Service details:**
1. **Проектирование** — Эскизное проектирование зданий, архитектура и фасады, благоустройство и генплан
2. **3D-визуализация** — Интерьеры/экстерьеры, концепции и идеи, девелоперские проекты, визуалы для продаж
3. **Рабочая документация** — Комплекты чертежей, спецификации материалов и мебели, технические узлы
4. **Комплектация и надзор** — Подбор материалов/мебели/освещения, поставщики, авторский надзор
5. **Международные проекты** — Адаптация под зарубежные нормы, ведение проектов за рубежом, международные подрядчики
6. **Айдентика и брендинг** — Логотип, фирменный стиль, бренд-видео, контент для соцсетей
7. **Motion-анимация** — Видео архитектуры, 3D-анимация, промо-ролики, VR-туры

### 3. Section 02 — О студии (About)
- **Section header:** Faded "02" + "О студии" + terracotta underline
- **Left column:** Main text — "MĒISØ создаёт историю..." with key phrase highlighted in white bold
- **Right column:** "Как мы работаем" label + process description + terracotta-bordered quote block: "Проект с нами — это управляемая система..."

**Full about text from client:**
> MĒISØ создаёт историю. Не проект. Не интерьер. Не объект. Историю пространства, в котором будут жить люди, решения и эмоции. Мы не делаем «как у всех». Мы делаем так, чтобы через 10 лет это выглядело так же сильно, как в день сдачи.
>
> Вы приходите с задачей. Мы уходим в процесс: концепция, проектирование, визуализация, документация, реализация. Проект с нами — это управляемая система. Мы берём сложное на себя, чтобы для вас всё выглядело легко.

### 4. Section 03 — Проекты (Portfolio)
- **Section header:** Faded "03" + "Проекты" + terracotta underline
- **Asymmetric grid:** 2fr + 1fr, 2 rows
  - Large left card spans 2 rows (main project)
  - Top-right card (secondary project)
  - Bottom-right card with terracotta background (accent project)
- Each card: dark surface bg, project label on bottom-left with terracotta or glass-morphism badge
- "Все проекты →" link aligned right

### 5. Section 04 — Контакты (Contacts + Footer)
- **Section header:** Faded "04" + "Контакты" + terracotta underline
- **Left column:** Email (hello@meiso.team), phone (+7 700 900 7576), social links (Telegram / Instagram)
- **Right column:** Contact form — Name, Email/Phone, Message textarea, terracotta submit button
- **Footer:** Copyright "© 2026 MĒISØ" left, "ARCHITECTURE & DESIGN" right, thin divider above

---

## Interactions & Animations

- **Scroll reveal:** Sections fade-in on scroll (IntersectionObserver)
- **Hover effects:** Portfolio cards scale slightly, service items get subtle highlight
- **Smooth scroll:** Anchor links smooth-scroll to sections
- **Nav:** Fixed on top, transparent initially

---

## Responsive Behavior

- **Desktop (1200px+):** Full layout as described
- **Tablet (768px-1199px):** Services collapse to 2-column grid, hero text scales down
- **Mobile (<768px):** Single column, hamburger menu, stacked sections, hero text ~32px

---

## File Structure

```
web_claude/
├── index.html
├── css/
│   └── style.css
├── js/
│   └── main.js
├── assets/
│   └── logo/
│       └── LOGO/          (extracted brand assets)
└── docs/
```

---

## Verification

1. Open `index.html` in browser — all 5 sections render correctly
2. Check responsive layout at 1440px, 768px, 375px
3. Verify smooth scroll navigation works
4. Test contact form field states (focus, placeholder)
5. Confirm logo displays correctly in header
6. Validate text readability on dark background
