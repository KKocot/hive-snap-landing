# Design Brief: Hive Wallet MetaMask Snap Landing Page

**Prepared by:** Design Engineer
**Date:** 2026-05-12
**Version:** 1.0
**Site type:** MARKETING
**Snap version:** 1.7.0

---

## 1. Site Type Classification

**Type: MARKETING**

| Pytanie diagnostyczne | Odpowiedz | Wynik |
|---|---|---|
| Kto jest userem? | Developer / user Hive blockchain szukajacy integracji z MetaMask | MARKETING (potencjalny klient) |
| Cel? | Konwersja -- zainstalowanie Snapa, zbudowanie zaufania do bezpieczenstwa | MARKETING (konwersja) |
| Frequency? | Raz lub kilka razy -- odwiedza landing, instaluje, przechodzi do uzycia w dapp | MARKETING |
| Dlugosc sesji? | 30-120 sekund -- skanuje hero, features, klika Install | MARKETING |

Uzasadnienie: klasyczny produktowy landing page z jednym glownym celem konwersji (Install Snap). Uzytkownik nie wraca na landing po instalacji. Cala interakcja z produktem odbywa sie wewnatrz MetaMask, nie na tej stronie.

---

## 2. Design Tokens

### 2.1 Colors

```
/* Background */
--bg-primary:       #0a0a0a;
--bg-card:          #111111;
--bg-elevated:      #1a1a1a;
--bg-code:          #0d0d0d;

/* Accent */
--accent-hive:      #e31337;          /* Hive red -- primary CTA, glow, highlights */
--accent-hive-hover:#ff1a42;          /* Hive red lighter -- hover state */
--accent-hive-glow: rgba(227,19,55,0.15);  /* Radial glow behind hero */
--accent-hive-subtle: rgba(227,19,55,0.08); /* Card border glow on hover */
--accent-metamask:  #f6851b;          /* MetaMask orange -- secondary accents, MM icon */
--accent-metamask-subtle: rgba(246,133,27,0.10);

/* Text */
--text-primary:     #ffffff;
--text-secondary:   #a0a0a0;
--text-muted:       #666666;
--text-code:        #e2e8f0;
--text-code-keyword:#e31337;

/* Borders */
--border-subtle:    rgba(255,255,255,0.08);
--border-hover:     rgba(255,255,255,0.15);
--border-focus:     rgba(227,19,55,0.5);

/* States */
--success:          #22c55e;
--warning:          #eab308;
--error:            #ef4444;
```

### 2.2 Typography

```
/* Font families */
--font-heading:     "Inter", system-ui, -apple-system, sans-serif;
--font-body:        "Inter", system-ui, -apple-system, sans-serif;
--font-mono:        "JetBrains Mono", "Fira Code", ui-monospace, monospace;

/* Font loading: Inter variable (wght 400..700), subset latin + latin-ext */
/* JetBrains Mono variable (wght 400..500), subset latin */
/* Preload: <link rel="preload" as="font" type="font/woff2"> */

/* Scale (desktop) */
--text-xs:          0.75rem;    /* 12px -- badges, labels */
--text-sm:          0.875rem;   /* 14px -- body small, nav links */
--text-base:        1rem;       /* 16px -- body default */
--text-lg:          1.125rem;   /* 18px -- lead text, card descriptions */
--text-xl:          1.25rem;    /* 20px -- card titles */
--text-2xl:         1.5rem;     /* 24px -- sub-section headings */
--text-3xl:         2rem;       /* 32px -- section headings mobile */
--text-4xl:         2.5rem;     /* 40px -- section headings desktop */
--text-5xl:         3rem;       /* 48px -- hero heading mobile */
--text-6xl:         4rem;       /* 64px -- hero heading desktop */

/* Line heights */
--leading-tight:    1.1;        /* headings */
--leading-snug:     1.3;        /* sub-headings */
--leading-normal:   1.6;        /* body */
--leading-relaxed:  1.75;       /* lead text */

/* Letter spacing */
--tracking-tight:   -0.02em;    /* hero heading */
--tracking-normal:  0;          /* body */
--tracking-wide:    0.05em;     /* badges, overlines */
--tracking-widest:  0.1em;      /* labels uppercase */

/* Font weights */
--weight-regular:   400;
--weight-medium:    500;
--weight-semibold:  600;
--weight-bold:      700;
```

### 2.3 Spacing

```
/* 4px base scale */
--space-1:   0.25rem;   /* 4px */
--space-2:   0.5rem;    /* 8px */
--space-3:   0.75rem;   /* 12px */
--space-4:   1rem;       /* 16px */
--space-5:   1.25rem;   /* 20px */
--space-6:   1.5rem;    /* 24px */
--space-8:   2rem;       /* 32px */
--space-10:  2.5rem;    /* 40px */
--space-12:  3rem;       /* 48px */
--space-16:  4rem;       /* 64px */
--space-20:  5rem;       /* 80px */
--space-24:  6rem;       /* 96px */
--space-32:  8rem;       /* 128px */

/* Section vertical padding */
--section-py-mobile:   var(--space-16);  /* 64px */
--section-py-desktop:  var(--space-24);  /* 96px */

/* Container max widths */
--container-sm:    640px;
--container-md:    768px;
--container-lg:    1024px;
--container-xl:    1200px;
--container-content: 720px;    /* text content max-width */
```

### 2.4 Border Radius

```
--radius-sm:    6px;
--radius-md:    8px;
--radius-lg:    12px;
--radius-xl:    16px;
--radius-2xl:   24px;
--radius-full:  9999px;   /* pill buttons, badges */
```

### 2.5 Shadows & Effects

```
/* Shadows */
--shadow-card:       0 1px 3px rgba(0,0,0,0.4), 0 0 0 1px rgba(255,255,255,0.05);
--shadow-card-hover: 0 8px 32px rgba(0,0,0,0.5), 0 0 0 1px rgba(255,255,255,0.1);
--shadow-btn:        0 1px 2px rgba(0,0,0,0.3);

/* Glow effects */
--glow-hive:         0 0 80px 20px rgba(227,19,55,0.15);
--glow-hive-strong:  0 0 120px 40px rgba(227,19,55,0.20);
--glow-card-hover:   0 0 40px rgba(227,19,55,0.06);

/* Glassmorphism (cards) */
--glass-bg:          rgba(17,17,17,0.6);
--glass-backdrop:    blur(12px) saturate(150%);
--glass-border:      rgba(255,255,255,0.08);

/* Gradients */
--gradient-hive:     linear-gradient(135deg, #e31337 0%, #ff1a42 100%);
--gradient-hive-glow:radial-gradient(ellipse at 50% 0%, rgba(227,19,55,0.15) 0%, transparent 70%);
--gradient-hero-bg:  radial-gradient(ellipse at 50% 30%, rgba(227,19,55,0.12) 0%, transparent 60%);
--gradient-card-border: linear-gradient(135deg, rgba(227,19,55,0.2) 0%, rgba(255,255,255,0.05) 100%);
--gradient-fade-bottom: linear-gradient(to bottom, transparent, #0a0a0a);
```

---

## 3. Layout Structure (per sekcja)

### 3.1 Navbar

```
Pozycja:     sticky top-0, z-50
Wysokosc:    64px (mobile), 72px (desktop)
Background:  transparent -> bg-primary/80 + backdrop-blur(12px) on scroll (>50px)
Border:      none -> border-bottom: 1px solid var(--border-subtle) on scroll
Container:   max-width: var(--container-xl), mx-auto, px-4 (mobile) px-6 (desktop)
Layout:      flex, justify-between, align-center

Left:        Logo icon (SVG z icon.svg, 28x28) + "Hive Wallet" text (font-semibold, text-sm)
             Logo icon color: var(--accent-hive)
             Text color: var(--text-primary)

Right:       Desktop: "Features" | "Security" | "Developers" | "FAQ" (text-sm, text-secondary, hover:text-primary)
             + "Install Snap" button (gradient-hive, text-sm, font-medium, px-4 py-2, radius-full)
             Mobile: hamburger icon (24x24) -> overlay menu fullscreen

Scroll behavior:
- transform: translateY(0) normalnie
- Dodaj transition: background 200ms ease, border-color 200ms ease
- Klasa .scrolled po scroll > 50px
```

### 3.2 Hero

```
Padding:     pt-32 (128px top, uwzglednia navbar) pb-24 (96px bottom)
             Mobile: pt-24 pb-16
Layout:      flex, flex-col, items-center, text-center
Max-width:   var(--container-content) (720px) dla tekstu

Badge:       "NEW v1.7.0" -- inline-flex, items-center, gap-2
             bg: rgba(227,19,55,0.1), border: 1px solid rgba(227,19,55,0.2)
             text: var(--accent-hive), text-xs, font-medium, tracking-wide, uppercase
             px-3 py-1, radius-full
             Ikona: maly dot/sparkle SVG 6x6

Heading:     "Your keys. Your MetaMask. Your Hive."
             font-size: var(--text-6xl) desktop, var(--text-5xl) tablet, var(--text-4xl) mobile
             font-weight: var(--weight-bold)
             letter-spacing: var(--tracking-tight)
             line-height: var(--leading-tight)
             color: var(--text-primary)
             mt-6

Subtext:     "Sign Hive transactions, derive keys, and encrypt data --
              all secured inside MetaMask. Private keys never leave the sandbox."
             font-size: var(--text-lg)
             color: var(--text-secondary)
             line-height: var(--leading-relaxed)
             max-width: 560px, mx-auto
             mt-6

CTA group:   flex, gap-4, mt-10
             Wrap: flex-wrap on mobile (full-width buttons)

Primary:     "Install Snap" -- bg: var(--gradient-hive), color: white
             px-8 py-3.5, radius-full, font-medium, text-base
             shadow: var(--shadow-btn)
             hover: brightness(1.1), shadow 0 4px 20px rgba(227,19,55,0.3)
             active: scale(0.98)
             Ikona: MetaMask fox icon (16x16) po lewej stronie tekstu

Secondary:   "View on GitLab" -- bg: transparent, border: 1px solid var(--border-subtle)
             color: var(--text-secondary), hover: color var(--text-primary), border-color var(--border-hover)
             px-8 py-3.5, radius-full, font-medium, text-base
             Ikona: GitLab icon (16x16) po lewej

Glow:        Pseudo-element ::before na sekcji hero
             var(--gradient-hero-bg)
             position: absolute, top: -200px, left: 50%, transform: translateX(-50%)
             width: 800px, height: 600px, pointer-events: none
             z-index: -1
```

### 3.3 Trusted By (Logo Strip)

```
Padding:     py-16 (mobile), py-20 (desktop)
Border:      border-top: 1px solid var(--border-subtle)
             border-bottom: 1px solid var(--border-subtle)

Label:       "Trusted by the ecosystem" -- text-xs, uppercase, tracking-widest
             color: var(--text-muted), text-center, mb-8

Logos:       flex, justify-center, items-center, gap-12 (desktop), gap-8 (mobile)
             flex-wrap on mobile
             Loga: Hive (hexagon), MetaMask (fox), npm (logo), GitLab (tanuki)
             Kazde logo: max-height 28px, SVG inline
             Default: filter grayscale(1) opacity(0.4)
             Hover: filter grayscale(0) opacity(1), transition 300ms ease

             Alternatywa mobile: horizontal scroll z overflow-x-auto, no scrollbar
```

### 3.4 Features Grid

```
Padding:     var(--section-py-mobile) / var(--section-py-desktop)

Heading:     "Built for security. Designed for simplicity."
             text-4xl desktop, text-3xl mobile, font-bold, text-center
             color: var(--text-primary)
             mb-4

Subheading:  "Four core capabilities, zero compromises."
             text-lg, color: var(--text-secondary), text-center
             mb-12

Grid:        grid, grid-cols-2 (desktop), grid-cols-1 (mobile), gap-6
             max-width: 900px, mx-auto

Cards (x4):  bg: var(--glass-bg), backdrop-filter: var(--glass-backdrop)
             border: 1px solid var(--glass-border)
             radius: var(--radius-xl)
             padding: var(--space-8) (32px)
             transition: all 300ms ease

             Hover: transform translateY(-4px),
                    border-color: rgba(227,19,55,0.15),
                    box-shadow: var(--glow-card-hover)

Card content:
  Icon:      48x48, color: var(--accent-hive), mb-5
             bg: rgba(227,19,55,0.08), p-3, radius: var(--radius-lg)
  Title:     text-xl, font-semibold, color: var(--text-primary), mb-2
  Desc:      text-sm, color: var(--text-secondary), line-height: var(--leading-normal)

Feature 1:  "Sign Transactions"
            Icon: pen-line / signature
            "Authorize Hive transactions with user confirmation dialogs.
             Multi-operation support with clear previews."

Feature 2:  "Derive Keys"
            Icon: key-round / fingerprint
            "BIP44 key derivation (m/44'/3054') for owner, active, posting,
             and memo keys. On-demand, never stored."

Feature 3:  "Encrypt & Decrypt"
            Icon: lock / shield-check
            "End-to-end buffer encryption using memo keys.
             SHA-256 digest signing for data integrity."

Feature 4:  "Zero Key Storage"
            Icon: eye-off / vault
            "Private keys derived, used, and immediately cleared.
             WASM sandbox isolation. No persistence."
```

### 3.5 How It Works

```
Padding:     var(--section-py-mobile) / var(--section-py-desktop)
Background:  var(--bg-card) -- cala sekcja

Heading:     "Get started in three steps"
             text-4xl desktop, text-3xl mobile, font-bold, text-center
             mb-16

Layout:      flex (desktop: row), flex-col (mobile)
             max-width: 900px, mx-auto, gap-8
             relative (for connecting line)

Connecting line (desktop only):
             Pseudo-element, position absolute
             top: 40px (center of step number)
             left: calc(16.67% + 24px), right: calc(16.67% + 24px)
             height: 1px
             bg: linear-gradient(to right, var(--accent-hive), var(--border-subtle), var(--accent-hive))

Step (x3):   flex-1, text-center, position relative

  Number:    width 48px, height 48px, radius-full, mx-auto
             bg: var(--gradient-hive), color: white
             font-bold, text-lg, flex center
             mb-6
             relative z-10 (above line)

  Title:     text-xl, font-semibold, color: var(--text-primary), mb-2
  Desc:      text-sm, color: var(--text-secondary), max-width: 240px, mx-auto

Step 1:      "Install" -- "Add Hive Wallet Snap to your MetaMask with one click."
Step 2:      "Approve" -- "Grant permission for BIP44 key derivation. You stay in control."
Step 3:      "Sign" -- "Approve transactions in familiar MetaMask dialogs. Done."
```

### 3.6 Security

```
Padding:     var(--section-py-mobile) / var(--section-py-desktop)

Layout:      2 kolumny (desktop), 1 kolumna (mobile)
             max-width: var(--container-xl), mx-auto
             gap-16

Left column (text):
  Overline:  "SECURITY FIRST" -- text-xs, uppercase, tracking-widest
             color: var(--accent-hive), font-semibold, mb-4
  Heading:   "Your keys never leave MetaMask"
             text-4xl, font-bold, color: var(--text-primary), mb-6
  Paragraph: text-base, color: var(--text-secondary), mb-8, max-width: 480px

Right column (feature list):
  Lista 5 items, flex-col, gap-4

  Item:      flex, items-start, gap-4
             padding: var(--space-4)
             bg: var(--bg-elevated), radius: var(--radius-lg)
             border: 1px solid var(--border-subtle)

    Icon:    20x20, color: var(--accent-hive), flex-shrink-0, mt-0.5
    Text wrapper:
      Title: text-base, font-medium, color: var(--text-primary), mb-1
      Desc:  text-sm, color: var(--text-secondary)

Security items:
  1. Shield    "BIP44 Derivation"     "Industry-standard HD wallet path m/44'/3054' (coin type 0xBEE)"
  2. Lock      "No Key Storage"       "Keys derived on-demand, used once, immediately cleared from memory"
  3. Box       "WASM Sandbox"         "Cryptographic operations run in isolated WebAssembly environment"
  4. CheckCircle "User Confirmation"  "Every sensitive operation requires explicit MetaMask dialog approval"
  5. ScanEye   "CI Security Audits"   "Automated Snapper security analysis on every build pipeline"
```

### 3.7 For Developers

```
Padding:     var(--section-py-mobile) / var(--section-py-desktop)
Background:  var(--bg-card)

Heading:     "Built for developers"
             text-4xl, font-bold, text-center, mb-4
Subheading:  "Four RPC methods. One npm install. Full Hive integration."
             text-lg, color: var(--text-secondary), text-center, mb-12

Layout:      max-width: 900px, mx-auto

RPC Cards:   grid, grid-cols-2 (desktop), grid-cols-1 (mobile), gap-4, mb-12

  Mini card: bg: var(--bg-elevated), border: 1px solid var(--border-subtle)
             radius: var(--radius-lg), padding: var(--space-5)

    Method:  font-mono, text-sm, color: var(--accent-hive), font-medium, mb-1
    Desc:    text-sm, color: var(--text-secondary)

  Card 1:    hive_getPublicKeys -- "Derive owner, active, posting, memo public keys"
  Card 2:    hive_signTransaction -- "Sign and broadcast Hive transactions"
  Card 3:    hive_encrypt -- "Encrypt buffers with memo key pairs"
  Card 4:    hive_decrypt -- "Decrypt previously encrypted data"

Code block:  bg: var(--bg-code), border: 1px solid var(--border-subtle)
             radius: var(--radius-lg), overflow: hidden

  Header:    flex, justify-between, items-center
             bg: var(--bg-elevated), px-4 py-3
             border-bottom: 1px solid var(--border-subtle)
    Left:    "Terminal" -- text-xs, color: var(--text-muted), font-mono
    Right:   Copy button -- "Copy" text-xs, color: var(--text-muted)
             hover: color var(--text-primary)
             On click: text zmienia sie na "Copied!" na 2s, color: var(--success)

  Code:      padding: var(--space-6), font-mono, text-sm, color: var(--text-code)
             line-height: 1.7
             overflow-x: auto
             ```
             npm install @hiveio/metamask-snap
             ```
             Kolorowanie: "npm" -> var(--text-code-keyword), reszta -> var(--text-code)

Docs link:   text-center, mt-8
             "Read the full documentation" -> arrow-right icon
             color: var(--accent-hive), hover: underline
             href: https://gitlab.syncad.com/hive/metamask-snap
```

### 3.8 FAQ

```
Padding:     var(--section-py-mobile) / var(--section-py-desktop)

Heading:     "Frequently asked questions"
             text-4xl, font-bold, text-center, mb-12

Container:   max-width: var(--container-content), mx-auto

Accordion:   flex-col, gap-0
             Kazdy item: border-bottom 1px solid var(--border-subtle)
             Pierwszy item: border-top 1px solid var(--border-subtle)

  Trigger:   flex, justify-between, items-center, w-full
             py-5 px-0, cursor-pointer
             text-base (desktop), text-sm (mobile), font-medium
             color: var(--text-primary)
             hover: color var(--accent-hive)

    Icon:    ChevronDown 20x20, color: var(--text-muted)
             rotate(0) -> rotate(180deg) when open
             transition: transform 300ms ease

  Content:   overflow hidden, max-height 0 -> auto (animated)
             pb-5, text-sm, color: var(--text-secondary)
             line-height: var(--leading-normal)

FAQ items:
  Q1: "Is this officially made by Hive?"
  A1: "Yes. This Snap is developed and maintained by the Hive community under the @hiveio
       organization. Source code is fully open on GitLab."

  Q2: "Are my private keys safe?"
  A2: "Absolutely. Private keys are derived from your MetaMask seed phrase using BIP44 standard,
       used for a single operation, and immediately cleared from memory. Keys never leave
       the MetaMask sandbox environment."

  Q3: "Which Hive key types are supported?"
  A3: "All four: owner, active, posting, and memo keys. Each is derived from the HD wallet
       path m/44'/3054' with the corresponding role index."

  Q4: "Does it work with hardware wallets?"
  A4: "If your MetaMask is connected to a hardware wallet (Ledger, Trezor), the Snap uses
       MetaMask's BIP44 entropy API which abstracts the key source. Hardware wallet support
       depends on MetaMask's own integration."

  Q5: "What happens if MetaMask updates?"
  A5: "The Snap follows MetaMask's platform versioning (currently v6.14.0). Updates are tested
       against the latest MetaMask releases in CI before publishing."

  Q6: "How do I use this in my dApp?"
  A6: "Install the Snap via npm (@hiveio/metamask-snap), connect using MetaMask's Snap API,
       and call RPC methods like hive_signTransaction. See our GitLab documentation for
       full integration guides."
```

### 3.9 Final CTA

```
Padding:     py-24 (desktop), py-16 (mobile)
Background:  position relative

Glow:        Pseudo-element ::before
             var(--gradient-hero-bg) ale z wiekszym spread
             radial-gradient(ellipse at 50% 50%, rgba(227,19,55,0.10) 0%, transparent 60%)
             width: 100%, height: 100%, position absolute, z-index: -1

Layout:      text-center, max-width: var(--container-content), mx-auto

Heading:     "Ready to connect Hive to MetaMask?"
             text-4xl (desktop), text-3xl (mobile), font-bold
             color: var(--text-primary), mb-6

Subtext:     "Join the Hive ecosystem with secure, seamless MetaMask integration."
             text-lg, color: var(--text-secondary), mb-10

Button:      Identyczny jak hero primary CTA
             "Install Snap" z MetaMask fox icon
             bg: var(--gradient-hive), radius-full
             px-10 py-4, text-lg, font-medium
             hover: brightness(1.1), scale(1.02), shadow glow
```

### 3.10 Footer

```
Padding:     pt-16 pb-8
Border:      border-top: 1px solid var(--border-subtle)

Layout:      max-width: var(--container-xl), mx-auto, px-6

Top row:     flex (desktop), flex-col (mobile), justify-between, items-start
             gap-8

  Left:      Logo (SVG 24x24 + "Hive Wallet" text-sm font-semibold)
             mt-1: "MetaMask Snap for Hive blockchain" text-sm color: var(--text-muted)

  Right:     flex, gap-12

    Col 1 "Resources":
      - Documentation  -> gitlab link
      - npm Package    -> npmjs.com/package/@hiveio/metamask-snap
      - Source Code    -> gitlab repo

    Col 2 "Community":
      - Hive Blog      -> hive.blog
      - PeakD          -> peakd.com
      - GitLab Issues  -> gitlab issues

  Link style: text-sm, color: var(--text-secondary), hover: color var(--text-primary)
              transition 150ms ease

Bottom row:  flex, justify-between, items-center
             mt-12, pt-6
             border-top: 1px solid var(--border-subtle)

  Left:      "MIT License" -- text-xs, color: var(--text-muted)
  Right:     "(c) 2024-2026 Hive Community" -- text-xs, color: var(--text-muted)
```

---

## 4. Motion Spec

### 4.1 Global Defaults

```
/* Duration scale */
--duration-instant:   100ms;     /* micro feedback: button press, copy */
--duration-fast:      150ms;     /* hover states, focus rings */
--duration-normal:    250ms;     /* state changes, accordion */
--duration-medium:    400ms;     /* enter/exit, cards, modals */
--duration-slow:      600ms;     /* hero entrance, section reveals */
--duration-brand:     800ms;     /* hero heading stagger */

/* Easing */
--ease-out:           cubic-bezier(0.16, 1, 0.3, 1);      /* enter (deceleration) */
--ease-in:            cubic-bezier(0.55, 0, 1, 0.45);     /* exit (acceleration) */
--ease-in-out:        cubic-bezier(0.65, 0, 0.35, 1);     /* spatial transitions */
--ease-spring:        cubic-bezier(0.34, 1.56, 0.64, 1);  /* playful bounce (badge) */
```

### 4.2 Per-Element Animations

| Element | Trigger | Animation | Duration | Easing | Notes |
|---|---|---|---|---|---|
| **Navbar** bg change | scroll > 50px | opacity 0->1 on bg + border | 200ms | ease | CSS only, no JS anim |
| **Hero badge** | page load | opacity 0->1, translateY(-8px)->0 | 400ms | ease-out | delay: 100ms |
| **Hero heading** | page load | opacity 0->1, translateY(16px)->0 | 600ms | ease-out | delay: 200ms |
| **Hero subtext** | page load | opacity 0->1, translateY(16px)->0 | 600ms | ease-out | delay: 400ms |
| **Hero CTAs** | page load | opacity 0->1, translateY(16px)->0 | 600ms | ease-out | delay: 600ms |
| **Hero glow** | page load | opacity 0->0.15, scale(0.8)->1 | 800ms | ease-out | delay: 300ms |
| **Logo strip** items | scroll into view | opacity 0->0.4, translateY(8px)->0 | 400ms | ease-out | stagger: 50ms per logo |
| **Feature cards** | scroll into view | opacity 0->1, translateY(24px)->0 | 500ms | ease-out | stagger: 80ms per card |
| **Feature card** hover | hover | translateY(-4px), border glow | 250ms | ease-out | GPU: transform only |
| **Step numbers** | scroll into view | opacity 0->1, scale(0.5)->1 | 500ms | ease-spring | stagger: 150ms |
| **Connecting line** | scroll into view | scaleX(0)->1, transform-origin left | 600ms | ease-in-out | delay: 200ms after numbers |
| **Security items** | scroll into view | opacity 0->1, translateX(-16px)->0 | 400ms | ease-out | stagger: 60ms |
| **RPC cards** | scroll into view | opacity 0->1, translateY(16px)->0 | 400ms | ease-out | stagger: 60ms |
| **Code block** | scroll into view | opacity 0->1, translateY(8px)->0 | 400ms | ease-out | delay: after RPC cards |
| **Copy button** click | click | text swap "Copy"->"Copied!" | instant | -- | return after 2000ms |
| **FAQ accordion** | click toggle | height 0->auto (calc), chevron rotate | 250ms | ease-in-out | CSS grid trick: grid-rows 0fr->1fr |
| **Final CTA glow** | scroll into view | opacity 0->0.1, scale(0.9)->1 | 800ms | ease-out | subtle pulse loop optional |
| **All buttons** | hover | brightness(1.1) | 150ms | ease | -- |
| **All buttons** | active | scale(0.98) | 100ms | ease | -- |

### 4.3 Scroll-Triggered Animation Config

```
Intersection Observer config:
  threshold: 0.15          /* 15% widoczne */
  rootMargin: "0px 0px -60px 0px"   /* trigger nieco wczesniej */

Klasyfikacja:
  .animate-on-scroll      -- base: opacity 0, transform translateY(24px)
  .animate-on-scroll.visible -- opacity 1, transform translateY(0)
  Transition: opacity var(--duration-medium) var(--ease-out),
              transform var(--duration-medium) var(--ease-out)

  data-delay="100" / data-delay="200" etc. -- transition-delay per element
  data-stagger="true" -- parent, children get auto-delay 50ms * index
```

### 4.4 Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }

  .animate-on-scroll {
    opacity: 1 !important;
    transform: none !important;
  }
}
```

OBOWIAZKOWE: kazdy animated element musi respektowac prefers-reduced-motion. Brak wyjatkow.

---

## 5. Responsive Breakpoints

```
/* Mobile first approach */
--bp-sm:   480px;    /* large phones */
--bp-md:   768px;    /* tablets */
--bp-lg:   1024px;   /* small desktop */
--bp-xl:   1280px;   /* desktop */

/* Breakpoint map */
@media (min-width: 480px)  { /* sm  */ }
@media (min-width: 768px)  { /* md  */ }
@media (min-width: 1024px) { /* lg  */ }
@media (min-width: 1280px) { /* xl  */ }
```

### Responsive Behavior Summary

| Element | Mobile (320-479) | SM (480-767) | MD (768-1023) | LG (1024+) |
|---|---|---|---|---|
| Container px | 16px | 20px | 24px | auto (centered) |
| Hero heading | 32px (text-3xl) | 40px (text-4xl) | 48px (text-5xl) | 64px (text-6xl) |
| Hero CTAs | stack vertical, full-w | stack vertical | inline flex | inline flex |
| Features grid | 1 col | 1 col | 2 cols | 2 cols |
| How it works | vertical stack | vertical stack | horizontal row | horizontal row |
| Security | 1 col stacked | 1 col stacked | 2 cols side-by-side | 2 cols side-by-side |
| RPC cards | 1 col | 1 col | 2 cols | 2 cols |
| Footer cols | stacked | stacked | row | row |
| Navbar links | hamburger menu | hamburger menu | visible | visible |
| Section py | 64px | 64px | 80px | 96px |
| Logo strip | 2 rows wrap | inline scroll | inline flex | inline flex |

### Mobile-Specific Notes

- Touch targets: minimum 44x44px na wszystkie interaktywne elementy
- CTA buttons na mobile: min-height 48px, width 100%
- Hamburger menu: overlay z animacja slide-down, 300ms ease-out
- FAQ accordion trigger: caly wiersz klikalny (nie tylko tekst)
- Code block: horizontal scroll z -webkit-overflow-scrolling: touch
- Navbar: bez transition na scroll (performance na mobile)

---

## 6. Accessibility Checklist

### 6.1 Color Contrast (WCAG AA minimum)

| Pair | Foreground | Background | Ratio | Status |
|---|---|---|---|---|
| Primary text on bg | #ffffff | #0a0a0a | 19.4:1 | PASS AAA |
| Secondary text on bg | #a0a0a0 | #0a0a0a | 9.0:1 | PASS AAA |
| Muted text on bg | #666666 | #0a0a0a | 3.9:1 | FAIL AA -- uzyj jako dekoracja, NIE dla informacyjnego tekstu |
| Hive red on bg | #e31337 | #0a0a0a | 4.8:1 | PASS AA (large text ok, small text borderline) |
| White on Hive red btn | #ffffff | #e31337 | 4.6:1 | PASS AA |
| Secondary text on card | #a0a0a0 | #111111 | 7.5:1 | PASS AAA |
| Muted text on card | #666666 | #111111 | 3.3:1 | FAIL AA -- dekoracja only |

Wnioski:
- `#666666` (--text-muted) uzywac WYLACZNIE jako dekoracyjny (np. "Terminal" label w code block, separatory). NIE dla tresci informacyjnej.
- `#e31337` na `#0a0a0a` -- OK dla buttonow (large text), ale unikac jako kolor small body text. Dla linkow inline uzywaj raczej --accent-hive-hover (#ff1a42) ktory ma lepszy kontrast.

### 6.2 Keyboard Navigation

```
Tab order (logiczny flow):
1. Skip link (hidden, first focusable) -> "#main-content"
2. Navbar: Logo (link) -> Nav links (Features, Security, Developers, FAQ) -> Install Snap button
3. Hero: Install Snap CTA -> View on GitLab CTA
4. Features: karty NIE sa focusable (nie sa interaktywne)
5. How it works: brak interaktywnych elementow
6. Security: brak interaktywnych elementow
7. For Developers: Copy button -> Docs link
8. FAQ: kazdy accordion trigger (button role)
9. Final CTA: Install Snap button
10. Footer: wszystkie linki w reading order

Focus ring:
  outline: 2px solid var(--accent-hive);
  outline-offset: 2px;
  border-radius: inherit;

  NIE UZYWAJ outline:none bez zamiennika.
  :focus-visible (nie :focus) -- unikaj ring na mouse click.
```

### 6.3 ARIA & Semantic HTML

```html
<!-- Skip link -->
<a href="#main-content" class="sr-only focus:not-sr-only">Skip to main content</a>

<!-- Navbar -->
<nav aria-label="Main navigation">
  <button aria-expanded="false" aria-controls="mobile-menu" class="md:hidden">
    <span class="sr-only">Open menu</span>
  </button>
</nav>

<!-- Hero -->
<main id="main-content">
  <section aria-labelledby="hero-heading">
    <h1 id="hero-heading">Your keys. Your MetaMask. Your Hive.</h1>
  </section>

<!-- Features -->
<section aria-labelledby="features-heading">
  <h2 id="features-heading">...</h2>
  <!-- Karty: uzyj <article> lub <div> z heading hierarchy -->

<!-- FAQ -->
<section aria-labelledby="faq-heading">
  <h2 id="faq-heading">...</h2>
  <div role="region">
    <h3>
      <button aria-expanded="false" aria-controls="faq-1-content">
        Question text
        <svg aria-hidden="true"><!-- chevron --></svg>
      </button>
    </h3>
    <div id="faq-1-content" role="region" aria-labelledby="faq-1-trigger" hidden>
      Answer text
    </div>
  </div>

<!-- Code block -->
<pre><code aria-label="npm install command">...</code></pre>
<button aria-label="Copy install command to clipboard">Copy</button>

<!-- Footer -->
<footer aria-label="Site footer">
  <nav aria-label="Footer navigation">
```

### 6.4 Other A11y Requirements

- `lang="en"` na `<html>`
- Wszystkie obrazy/SVG dekoracyjne: `aria-hidden="true"`, `role="presentation"`
- SVG ikony w features: `aria-hidden="true"` (tekst obok opisuje funkcje)
- Logo images w "Trusted by": alt text z nazwa firmy
- Minimum font size: 12px (badges), 14px (body small)
- Line height minimum: 1.5 dla body text
- Animated elements: `prefers-reduced-motion` fallback (Sekcja 4.4)
- No autoplay video/audio
- Link text: opisowy (nie "click here"). "Read the full documentation" zamiast "Read more"
- Button vs link: `<button>` dla akcji in-page (accordion, copy), `<a>` dla nawigacji

---

## 7. Performance Budget

| Metric | Target | Notes |
|---|---|---|
| LCP | <= 2.0s | Hero heading jest LCP element. Preload Inter font. |
| CLS | <= 0.05 | Font swap: `font-display: swap` + explicit dimensions na logo SVG |
| INP | <= 150ms | FAQ accordion, copy button -- obie operacje < 50ms |
| FCP | <= 1.2s | Inline critical CSS, defer non-critical |
| Total page weight | <= 400KB | Bez hero image -- tekst + SVG site |
| HTML | <= 15KB gzipped | Single page, semantic |
| CSS | <= 20KB gzipped | Tailwind purge / minimal custom |
| JS | <= 30KB gzipped | Intersection Observer + accordion + navbar scroll + copy |
| Fonts | <= 60KB total | Inter variable subset (latin, wght 400-700) ~35KB, JetBrains Mono subset ~20KB |
| SVG icons | <= 10KB total | Inline SVG, no icon font |

### Font Loading Strategy

```html
<!-- Preload critical fonts -->
<link rel="preload" href="/fonts/inter-variable-latin.woff2" as="font" type="font/woff2" crossorigin>

<!-- Font-face declarations -->
@font-face {
  font-family: "Inter";
  src: url("/fonts/inter-variable-latin.woff2") format("woff2");
  font-weight: 400 700;
  font-display: swap;
  unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6,
                 U+02DA, U+02DC, U+0304, U+0308, U+0329, U+2000-206F,
                 U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215,
                 U+FEFF, U+FFFD;
}

/* JetBrains Mono: load async (not critical path) */
<link rel="preload" href="/fonts/jetbrains-mono-variable-latin.woff2" as="font" type="font/woff2" crossorigin>
```

### Asset Strategy

- Zero raster images (all SVG + CSS gradients)
- Inline SVG for icons (no sprite sheet for <10 icons)
- CSS custom properties for theming (no runtime JS for colors)
- Intersection Observer for scroll animations (native API, no library)
- No external tracking scripts in initial load

---

## 8. SVG Icon Recommendations

Rekomendowany zrodlo: **Lucide Icons** (https://lucide.dev) -- MIT license, consistent 24x24 grid, 1.5px stroke.

| Sekcja | Ikona | Lucide name | Fallback name |
|---|---|---|---|
| Feature 1: Sign Transactions | Pen signing | `pen-line` | `file-signature` |
| Feature 2: Derive Keys | Key | `key-round` | `key` |
| Feature 3: Encrypt/Decrypt | Lock shield | `shield-check` | `lock` |
| Feature 4: Zero Storage | Hidden eye | `eye-off` | `shield-off` |
| Security 1: BIP44 | Shield | `shield` | `fingerprint` |
| Security 2: No Storage | Lock | `lock` | `database-zap` |
| Security 3: WASM Sandbox | Box isolated | `box` | `container` |
| Security 4: User Confirm | Check circle | `circle-check-big` | `check-circle` |
| Security 5: CI Audits | Scan | `scan-eye` | `radar` |
| Navbar: logo | Hive hexagon | Custom SVG (z icon.svg projektu) | -- |
| Hero CTA: MetaMask | Fox | Custom MetaMask SVG (brand asset) | -- |
| Hero CTA: GitLab | Tanuki | Custom GitLab SVG (brand asset) | -- |
| Code block: copy | Clipboard | `clipboard` | `copy` |
| Code block: copied | Check | `clipboard-check` | `check` |
| FAQ: chevron | Chevron | `chevron-down` | `arrow-down` |
| Footer: external links | Arrow | `external-link` | `arrow-up-right` |
| Docs link | Arrow right | `arrow-right` | `chevron-right` |

### Custom SVG Assets

**Hive Logo** -- uzyj istniejacego icon.svg z projektu (2 paths, fill #e31337). Przeskaluj do 28x28 dla navbar, 48x48 dla trusted-by.

**MetaMask Fox** -- oficjalny brand asset: https://metamask.io/press-kit/. Uzyj uproszczony outline fox (nie full-color 3D). Grayscale w trusted-by, kolorowy w CTA button.

**npm Logo** -- prosty "npm" wordmark SVG.

**GitLab Tanuki** -- oficjalny SVG z GitLab press kit.

---

## 9. Handoff Notes

### 9.1 Priority

**HIGH** -- landing page jest public-facing, jedyny touchpoint przed instalacja Snapa.

### 9.2 Recommended Stack

Framework i narzedzia do implementacji (zgodne z safe-design-tools-whitelist):

| Tool | Purpose | Notes |
|---|---|---|
| **Astro 5** | Static site generator | Idealne dla marketing landing -- zero JS by default, islands architecture |
| **Tailwind CSS v4** | Utility-first styling | Design tokens mapuja 1:1 na Tailwind config |
| **Inter (Google Fonts / self-hosted)** | Typography | Self-hosted woff2 preferred for performance |
| **Lucide Icons** | SVG icons | Tree-shakeable, MIT license |
| **Brak frameworka animacji** | Scroll animations | Natywny Intersection Observer + CSS transitions. Strona jest prosta -- nie potrzeba framer-motion/GSAP |

### 9.3 Implementation Notes

1. **Single HTML page** -- wszystkie 10 sekcji na jednej stronie. Smooth scroll do anchor sections z navbar.
2. **No client-side routing** -- pure static, Astro output: "static".
3. **CSS approach** -- Tailwind utilities + minimal custom CSS dla glassmorphism, gradients, glow. Custom properties w `:root`.
4. **JS budget** -- jedyny JS: Intersection Observer (scroll animations), FAQ accordion toggle, navbar scroll detection, clipboard API (copy button). Szacunek: ~3KB minified.
5. **Smooth scroll** -- `scroll-behavior: smooth` na `html`, ale respektuj `prefers-reduced-motion: reduce` -> `scroll-behavior: auto`.
6. **Navbar scroll** -- `IntersectionObserver` na sentinel element na gorze strony (bardziej wydajne niz scroll event).
7. **FAQ accordion** -- native `<details>/<summary>` z CSS animation (grid-template-rows trick) LUB custom JS z ARIA attributes. Prefer custom JS for full ARIA control.
8. **Copy button** -- `navigator.clipboard.writeText()` z fallback na `document.execCommand('copy')`.
9. **Meta tags** -- Open Graph + Twitter Card. Title: "Hive Wallet -- MetaMask Snap for Hive Blockchain". Description: snap.manifest.json description.
10. **Favicon** -- uzyj icon.svg z projektu, dodaj `<link rel="icon" type="image/svg+xml">`.

### 9.4 Next Steps (TODO for frontend-developer)

- [ ] Scaffold Astro 5 project w `/websites/hive-snap-landing/`
- [ ] Configure Tailwind v4 z design tokens z tego briefu
- [ ] Self-host Inter + JetBrains Mono (woff2, subset latin)
- [ ] Implement all 10 sections per layout spec
- [ ] Implement scroll animations (Intersection Observer + CSS)
- [ ] Implement FAQ accordion z pelnym ARIA
- [ ] Implement navbar scroll behavior
- [ ] Implement copy-to-clipboard
- [ ] Add meta tags (OG, Twitter, favicon)
- [ ] Test reduced-motion
- [ ] Test keyboard navigation (full tab-through)
- [ ] Lighthouse audit: Performance >= 95, Accessibility >= 95, Best Practices >= 95
- [ ] Test na: Chrome, Firefox, Safari, Edge (last 2 versions)
- [ ] Test responsive: 320px, 375px, 428px, 768px, 1024px, 1280px, 1440px

---

## 10. References

- Inspiracja: jet.framer.website (dark SaaS landing pattern)
- Snap manifest: `snap.manifest.json` v1.7.0
- Snap icon: `src/assets/icon.svg` (Hive hexagon, #e31337)
- Package: `@hiveio/metamask-snap` on npm
- Repository: https://gitlab.syncad.com/hive/metamask-snap
- BIP44 coin type: 3054 (0xBEE)
- MetaMask Snaps docs: https://docs.metamask.io/snaps/
- Lucide Icons: https://lucide.dev
- WCAG 2.1 AA: https://www.w3.org/WAI/WCAG21/quickref/
