# Vecinal — Landing Page (Astro + Tailwind v4)

Landing page de alta conversión para el SaaS de administración de condominios **Vecinal**.

## Stack

- [Astro](https://astro.build) 5
- [Tailwind CSS](https://tailwindcss.com) v4 (configuración CSS-first, sin `tailwind.config.js`)

## Arrancar

```bash
npm install
npm run dev      # http://localhost:4321
npm run build    # salida en dist/
```

## 🎨 Cambiar los colores de toda la marca (un solo lugar)

Tailwind v4 define el tema en CSS. Abre **`src/styles/global.css`** y edita el bloque `@theme`:

```css
@theme {
  --color-brand: #0b2545; /* azul profundo */
  --color-accent: #1368ec; /* azul eléctrico (CTAs) */
  --color-success: #16a34a; /* verde (estados positivos) */
  --color-surface: #f4f6f8; /* fondos de tarjetas */
  --color-ink: #1a1f2b; /* texto principal */
  /* ... */
}
```

Todos los componentes usan clases derivadas de estos tokens (`bg-brand`, `text-accent`,
`bg-surface`, `text-ink`, ...), así que cambiar un HEX aquí actualiza la landing completa.

También hay **tokens semánticos** (alias) para nombrar por intención:

```css
--color-bg-hero: var(--color-brand);
--color-bg-close: var(--color-brand-deep);
```

## Estructura

```
src/
├── layouts/Base.astro          # HTML base + fuentes + meta
├── styles/global.css           # ← TEMA (colores, tipografía, botones, utilidades)
├── components/
│   ├── Navbar.astro
│   ├── Footer.astro
│   └── sections/
│       ├── Hero.astro
│       ├── ValueProp.astro
│       ├── Features.astro
│       ├── Roi.astro
│       ├── Testimonials.astro
│       ├── Pricing.astro
│       ├── Faq.astro
│       └── FinalCta.astro
└── pages/index.astro
```

## Notas de contenido

- Las cifras de ROI y testimonios son **placeholders** (mockup) del documento de
  estrategia; reemplázalas con datos reales antes de publicar.
- Los enlaces de CTAs apuntan a `#` / `/demo`: conéctalos a tu calendario de demos
  (Calendly, HubSpot, etc.) o formulario de registro.
