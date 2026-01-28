# HK2 AddBootstrap5 for Magento 2

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue?style=for-the-badge)
[![Website](https://img.shields.io/badge/website-000?style=for-the-badge)](https://www.basantmandal.in/)
[![LinkedIn](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge\&logo=linkedin)](https://www.linkedin.com/in/basantmandal/)

</div>

---

## Overview

**HK2 AddBootstrap5** is a Magento 2 extension that enables administrators to load **Bootstrap 4 or Bootstrap 5** on the storefront **without modifying theme files or creating child themes**.

The extension is designed for:

* CMS content styling
* Third-party frontend integrations
* Rapid UI prototyping

All assets are injected using Magento’s standard layout and page configuration mechanisms, ensuring upgrade safety and compatibility with Magento 2.4.x.

> ⚠ **Important:**
> For manual installation, the **HK2 Core** package (`hk2/core`) must be installed first.

---

## Key Features

* **Bootstrap Version Selection**
  Supports Bootstrap **4.x** and **5.x** (including 5.3).

* **Admin-Controlled Enablement**
  Enable or disable Bootstrap loading from the Magento Admin Panel.

* **CDN-Based Asset Loading**
  Loads Bootstrap assets from trusted CDN providers for optimal performance.

* **Optional Debug Mode**
  Outputs non-intrusive diagnostic information to the browser console.

* **Demo Pages Included**
  Frontend demo routes are provided to verify correct integration.

* **No Theme Overrides**
  Uses Magento’s PageConfig and layout system—no template or theme modifications.

* **Non-Intrusive Design**
  Does not alter Magento core styles or UI components.

---

## System Requirements

* **Magento Open Source / Adobe Commerce:** 2.4.x
* **PHP:** 8.1 or higher
* **Database:** MySQL 8.0 / MariaDB 10.4+
* **Dependency:** `hk2/core` v1.0+ (required)

> Magento 2.3.x is end-of-life and not supported.

---

## Installation

### Composer (Recommended)

From the Magento root directory:

```bash
composer require hk2/addbootstrap5
```

This automatically installs the required **HK2 Core** dependency.

---

### Manual Installation

1. Install **HK2 Core**:

```bash
app/code/HK2/Core
```

1. Create the module directory:

```bash
app/code/HK2/AddBootstrap5
```

1. Copy the module files into the directory.

---

### Enable the Module

```bash
php bin/magento module:enable HK2_AddBootstrap5
php bin/magento setup:upgrade
php bin/magento cache:flush
```

Optional (production mode):

```bash
php bin/magento setup:di:compile
php bin/magento setup:static-content:deploy
```

---

## Configuration

Navigate to:

**Stores → Configuration → HK2 → AddBootstrap5**

### Available Options

| Setting           | Description                               |
| ----------------- | ----------------------------------------- |
| Enable Extension  | Enable or disable Bootstrap injection     |
| Bootstrap Version | Select Bootstrap 4.x or 5.x               |
| CDN Provider      | Choose the CDN source                     |
| Debug Mode        | Output diagnostic logs to browser console |

---

## Demo Pages

Admin-visible demo links are included for validation.

Frontend demo routes:

**Bootstrap 5**

```bash
https://yourstore.com/bootstrap5demo/demo/index/version/5
```

**Bootstrap 4**

```bash
https://yourstore.com/bootstrap5demo/demo/index/version/4
```

> Demo routes are intended for testing and can be disabled in production.

---

## Frontend Asset Injection

When enabled, the extension registers:

* Bootstrap CSS (CDN)
* Bootstrap JavaScript bundle (CDN)
* Optional debug JavaScript (RequireJS-based)

All assets are injected using Magento’s PageConfig system and are **production-safe and CSP-compliant**.

---

## Content Security Policy (CSP)

This extension includes a `csp_whitelist.xml` configuration compatible with Magento 2.4.x.

The module **does not use**:

* Inline JavaScript
* `unsafe-inline`
* `unsafe-eval`

### Allowed Directives

* `script-src`
* `style-src`
* `font-src`
* `connect-src`
* `img-src`

Only trusted CDN sources are permitted.

---

## Privacy & Data Usage

* No personal data is collected, stored, or transmitted
* No tracking, analytics, or background requests
* External requests are limited to configured CDN assets only

This extension is **fully GDPR-safe by design**.

---

## Compatibility & Performance

* Compatible with Magento 2.4.x frontend architecture
* Safe for production mode
* Compatible with static content deployment
* No impact on checkout or admin performance

---

## Known Limitations

* The module does **not restyle Magento UI components**
* Any styling conflicts must be handled at the theme or CMS level
* Bootstrap JavaScript components require proper markup to function

---

## Support & Contribution

Contributions are welcome:

1. Fork the repository
2. Create a feature branch
3. Commit and push your changes
4. Open a pull request

Support availability may vary.

---

## Disclaimer

This extension is provided **as-is**, without warranty of any kind.
The author is not liable for damages resulting from the use of this module.

---

## License

**Open Software License (OSL-3.0)**
[https://opensource.org/licenses/OSL-3.0](https://opensource.org/licenses/OSL-3.0)

---

## Author

**Basant Mandal**
HK2 – Hash Tag Kitto

* Website: [https://www.basantmandal.in](https://www.basantmandal.in)
* LinkedIn: [https://www.linkedin.com/in/basantmandal](https://www.linkedin.com/in/basantmandal)
* Email: [support@basantmandal.in](mailto:support@basantmandal.in)

---
