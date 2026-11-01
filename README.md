# ☀️ Solar E-Commerce Website

A complete **WordPress + WooCommerce** online store for **solar energy products**, built during the **MICTSETA internship** and deployed on **Hostinger**.

**Repository:** [`DestrO-source/public_html`](https://github.com/DestrO-source/public_html)

---

## Table of Contents

1. [About the Project](#about-the-project)
2. [About the Solar Store](#about-the-solar-store)
3. [Features](#features)
4. [Technology Stack](#technology-stack)
5. [Repository Structure](#repository-structure)
6. [Product & Media Library](#product--media-library)
7. [Installation (Local Development)](#installation-local-development)
8. [Deployment (Production)](#deployment-production)
9. [Database](#database)
10. [Security & Local Configuration](#security--local-configuration)
11. [License](#license)

---

## About the Project

This repository contains the full **WordPress website source code** — the entire `public_html` document root — for the solar e-commerce website created as an **individual task assigned to the MICTSETA internship interns**.

The deliverable includes:

- **WordPress core** — `wp-admin/`, `wp-includes/` and the root PHP bootstrap files (`index.php`, `wp-load.php`, `wp-config-sample.php`, …)
- **`wp-content/`** — all installed themes, plugins and uploaded media
- **Server-level configuration** — root `.htaccess` (Apache / LiteSpeed rewrite rules) and `.gitignore`

> **Important:** WordPress pages, products, categories, menus and settings are stored in the **MySQL database**, which is **not** part of this repository. A matching database export is required to reproduce the complete site locally.

---

## About the Solar Store

The website is an **e-commerce storefront selling solar energy products** for residential and small-scale off-grid / hybrid solar setups.

### Catalogue highlights

| Category | Examples |
|---|---|
| Solar panels | Grid-tie and bifacial modules, product explainers |
| Hybrid solar inverters | 5 kW hybrid inverter (48 V) |
| Solar storage | Battery packs / solar storage units |
| Charge controllers & power electronics | Freedom, Kinetix, Solis, SunSynk, Jackery power stations, converters |
| Electrical & mechanical parts | DC cables (e.g. 16 mm), mounting brackets / rails / clamps, accessories |
| Bundles | "This Solar System Can Power Your Entire Home" kits |

Product imagery is stored under `wp-content/uploads/` organised in `YYYY/MM` folders
(for example `wp-content/uploads/2026/08/`), including size variants such as
`-100x100`, `-150x150`, `-300x300`, `-600x600` and hero/banner images.

---

## Features

### Storefront

- **WooCommerce** product catalogue rendered through dedicated **WordPress block templates**, notably:
  - `wp-content/themes/hostinger-ai-theme/templates/archive-product.html` — product grid, results count, catalog sorting, pagination and empty-state handling
  - `wp-content/themes/hostinger-ai-theme/templates/single.html` — single product view
  - `wp-content/themes/hostinger-ai-theme/templates/front-page.html` — store front page
- Product image rendering with custom sizing (e.g. `thumbnail`) and styled add-to-cart buttons
- Cart & checkout flows through dedicated block templates:
  - `wp-content/themes/hostinger-ai-theme/templates/cart.html`
  - `wp-content/themes/hostinger-ai-theme/templates/checkout.html`
  - `wp-content/themes/hostinger-ai-theme/templates/order-confirmation.html`

### Commerce & marketing extensions

- **WooCommerce** — core selling: products, orders, coupons, stock, tax
- **WooCommerce Payments** — checkout payments
- **Power Coupons** — promotional coupons / sale pricing
- **Modern Cart** — cart management UI
- **Variation Swatches for WooCommerce** — product variations
- **Cart Abandonment Recovery** — abandoned cart recovery
- **CartFlows** — checkout / marketing automation flows

### Performance, SEO, support & AI

- **LiteSpeed Cache** (with matching `.htaccess` cache directives)
- **Hostinger Smart Auto Updates** + **Hostinger Tools**
- **Hostinger Image Optimization**, **SureRank** (SEO), **SureForms** (forms), **SureMail** (email), **SureCookie**, **SureMails**
- **WP Live Chat Support**
- **Hostinger AI Assistant** / **AI Builder** / **Easy Onboarding** / **Reach**

---

## Technology Stack

| Layer | Technology |
|---|---|
| CMS | **WordPress 7.1.4** |
| PHP | **≥ 7.4** (recommended **8.3**) |
| Database | **MySQL ≥ 5.5.5** (recommended **MySQL 8.0** / **MariaDB 10.11**) |
| Web server | Apache `mod_rewrite` + **LiteSpeed** |
| E-commerce | **WooCommerce 11.2.0** (+ WooCommerce Payments, Cart Abandonment Recovery) |
| Theme | **Hostinger AI theme**, **Astra 4.14.0**, Twenty Twenty-Five/Four/Three block themes |
| Page building | Word blocks (WooCommerce blocks), Elementor, Astra Blocks, CartFlows, Power Coupons, Modern Cart, Variation Swatches |
| Cache & performance | LiteSpeed Cache 7.9.2, Hostinger Image Optimization, Hostinger Smart Auto Updates |
| Hosting | **Hostinger** |
| License (core) | **GPLv2-or-later** |

---

## Repository Structure

```
├── .htaccess               # LiteSpeed cache + WordPress rewrite rules
├── .gitignore               # local secrets / runtime artefacts
├── README.md                # this file
├── default.php              # Hostinger AI onboarding placeholder page
├── index.php                # WordPress front controller
├── license.txt              # GPLv2-or-later
├── readme.html              # WordPress installer readme
├── wp-activate.php
├── wp-admin/                # WordPress admin core
├── wp-includes/             # WordPress core
└── wp-content/
    ├── liteSpeed/           # LiteSpeed runtime files
    ├── mu-plugins/          # must-use / network plugins
    ├── plugins/             # installed plugins (WooCommerce, Astra, Hostinger, …)
    ├── themes/              # installed themes (Astra, Hostinger AI, Twenty Twenty*)
    ├── uploads/             # media library (year/month folders)
    └── …
```

### Notable `wp-content/` areas

| Path | Purpose |
|---|---|
| `wp-content/themes/` | Astra, Hostinger AI theme, Twenty Twenty-Five/Four/Three block themes |
| `wp-content/plugins/` | WooCommerce, WooCommerce Payments, CartFlows, Power Coupons, Modern Cart, Variation Swatches, Cart Abandonment Recovery, LiteSpeed Cache, Hostinger*, Sure*, Elementor, Astra Sites, … |
| `wp-content/mu-plugins/` | Network / must-use plugins (Hostinger auto-updates, preview domain, …) |
| `wp-content/uploads/` | Media library (`YYYY/MM`), product imagery, logs |
| `wp-content/litespeed/` | LiteSpeed cache runtime files |

---

## Product & Media Library

- Media is stored under `wp-content/uploads/<year>/<month>/`.
- Solar product imagery lives under e.g. `wp-content/uploads/2026/08/`, including:
  - Hybrid solar inverter imagery — *5 kW hybrid solar inverter, 48 V*
  - Battery / solar storage imagery
  - Charge controller and power station imagery
  - DC cable, bracket / rail / clamp imagery
  - "This Solar System Can Power Your Entire Home" bundle imagery
  - Bifacial solar module explainer imagery
- WooCommerce generates size variants from base file names (e.g. `…-300x300.jpg`).

---

## Installation (Local Development)

1. Copy the repository contents into the document root of a **PHP-enabled web server** with a **MySQL-compatible database**.
2. Create a database and configure local connection details in `wp-config.php` (copy from `wp-config-sample.php`).
   - ⚠️ **Never commit** `wp-config.php` or credentials — both are excluded via `.gitignore`.
3. Import a matching WordPress database backup if available.
4. Run the famous 5-minute install (`wp-admin/install.php`) or restore from the database export.
5. Complete setup via the admin dashboard (themes, plugins, menus, products, settings).

### Requirements

- **PHP ≥ 7.4** (recommended **8.3**)
- **MySQL ≥ 5.5.5** (recommended **MySQL 8.0** / **MariaDB 10.11**)
- Apache `mod_rewrite`
- HTTPS recommended

---

## Deployment (Production)

- The site is hosted on **Hostinger**.
- Hostinger manages **auto-updates** for core, themes and plugins (via `wp-content/mu-plugins/hostinger-auto-updates.php`).
- LiteSpeed caching is enabled through the `.htaccess` `LSCACHE` block and the LiteSpeed Cache plugin.
- Hostinger-specific plugins (`hostinger`, `hostinger-ai-assistant`, `hostinger-easy-onboarding`, `hostinger-reach`, `hostinger-auto-updates`, `hostinger-preview-domain`) are installed and network-activated as needed.

---

## Database

The live database holds:

- Pages and posts
- WooCommerce products, categories, tags, orders, coupons, settings
- Menus, widgets, customizer options, user accounts

This repository intentionally excludes the database and credentials.

---

## Security & Local Configuration

`.gitignore` excludes local-only artefacts:

```
/wp-config.php
/.private/
/.user.ini
/wp-content/.user.ini
/.env
/.env.*
/wp-content/uploads/cartflows-logs/
/wp-content/uploads/wc-logs/
/wp-content/uploads/suremails/
/wp-content/uploads/woocommerce_uploads/
/wp-content/uploads/2026/08/cart-abandonment-recovery*.json
/wp-content/uploads/ast-block-templates-json/
/wp-content/uploads/astra-sites/json/
/wp-content/cache/
/wp-content/upgrade/
```

- Never commit `wp-config.php`, salts or local credentials.
- Never commit `.env` files.
- Runtime logs and backups (`*.log`, `*.bak`, `*.old`) are ignored.

---

## License

WordPress core and bundled themes/plugins are released under the **GNU General Public License v2 or later** — see [`license.txt`](https://github.com/DestrO-source/public_html/blob/main/license.txt).

---

## Acknowledgements

- **WordPress.org** and the WordPress community
- **WooCommerce / Automattic**
- **Astra / Brainstorm Force**
- **Hostinger** and the Hostinger AI / hosting toolchain
- **MICTSETA internship program**
