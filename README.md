# HK2 AddBootstrap5 for Magento 2

## Description

**HK2 AddBootstrap5** is a Magento 2 extension that allows store administrators to load the Bootstrap frontend
framework (Bootstrap 4 and 5) into the storefront **without modifying theme files or deploying custom child themes**.

This is especially useful for stores that require Bootstrap for third-party integrations, CMS content styling, or rapid
frontend prototyping while maintaining upgrade-safe Magento themes.

> ⚠ **Note:** For manual installation, the **HK2 Core package** is required. Install `hk2/core` before using this
> module.

---

## Key Features

* **Bootstrap Version Selection**
  Supports Bootstrap versions **4.x and 5.x** (including latest 5.3 releases).

* **Admin Configuration**
  Enable or disable Bootstrap loading directly from the Magento Admin Panel.

* **CDN-Based Delivery**
  Loads assets via trusted CDN providers for optimal performance and reduced local asset footprint.

* **Debug Mode (Optional)**
  Outputs non-intrusive diagnostic information to the browser console to assist with frontend troubleshooting.

* **Demo Pages Included**
  Provides example frontend routes to verify Bootstrap integration after installation.

* **No Theme Overrides Required**
  Uses Magento’s standard layout and page configuration APIs.

* **Non-Intrusive by Design**
  Does not override Magento Luma styles, templates, or UI components. Only registers Bootstrap assets; usage is entirely
  up to the storefront.

---

## System Requirements

* **Magento Open Source / Adobe Commerce:** 2.4.x
* **PHP:** 8.1 or higher
* **Database:** MySQL 8.0 / MariaDB 10.4+ (compatible with Magento 2.4.x)
* **Dependencies:** `hk2/core` v1.0+ (required for manual installation)

> Magento 2.3.x is end-of-life and not supported.

---

## Installation

### Option 1: Composer (Recommended)

Run the following command from your Magento root directory:

```bash
composer require hk2/addbootstrap5
```

This will automatically install the required **HK2 Core** package.

### Option 2: Manual Installation

1. Ensure the **HK2 Core** module is installed:

   ```
   app/code/HK2/Core
   ```

2. Create the module directory:

   ```
   app/code/HK2/AddBootstrap5
   ```

3. Copy the module files into the directory.

---

### Enable the Module

After installation, run:

```bash
php bin/magento module:enable HK2_AddBootstrap5
php bin/magento setup:upgrade
php bin/magento cache:flush
```

> In production mode, optionally run:
>
> ```bash
> php bin/magento setup:di:compile
> php bin/magento setup:static-content:deploy
> ```

---

## Configuration

1. Log in to the Magento Admin Panel.
2. Navigate to **Stores → Configuration → HK2 → AddBootstrap5**.

### Admin Configuration Options

| Setting                  | Description                                               |
|--------------------------|-----------------------------------------------------------|
| Enable Extension         | Enables or disables Bootstrap injection on the storefront |
| Select Bootstrap Version | Choose Bootstrap version (4.x or 5.x)                     |
| Select CDN Provider      | Choose CDN provider for Bootstrap assets                  |
| Enable Debug Mode        | Outputs diagnostic info to the browser console            |

---

### Demo & Links

The module includes admin-visible demo links:

* **Bootstrap 5 Demo** – Admin link: *Bootstrap 5 Demo*
* **Bootstrap 4 Demo** – Admin link: *Bootstrap 4 Demo*

Frontend demo routes for validation:

* **Bootstrap 5 Demo:**

  ```
  https://yourstore.com/bootstrap5demo/demo/index/version/5
  ```

* **Bootstrap 4 Demo:**

  ```
  https://yourstore.com/bootstrap5demo/demo/index/version/4
  ```

> Demo routes are provided for testing only and can be disabled in production.

---

## Frontend Asset Injection

When enabled, the module registers the following assets using Magento’s page configuration system:

* Bootstrap CSS (remote CDN)
* Bootstrap JavaScript bundle (remote CDN)
* Optional debug JavaScript (local, RequireJS-based)

Assets are added in a **CSP-compliant and production-safe manner**.

---

## Content Security Policy (CSP)

This extension includes a `csp_whitelist.xml` file to allow Bootstrap assets in compliance with Magento 2.4.x CSP
enforcement.

The module **does not use**:

* Inline JavaScript
* `unsafe-inline` or `unsafe-eval`
* Dynamic script injection

**Included CSP directives**:

* `script-src` – trusted CDNs
* `style-src` – trusted CDNs
* `font-src` – trusted CDNs (required for Bootstrap fonts)
* `connect-src` – trusted CDNs
* `img-src` – your own domain or allowed external hosts

---

## Privacy

This extension **does not collect, transmit, or store any personal or usage data**.

No outbound network requests are made other than loading Bootstrap assets from configured CDN providers.

---

## Troubleshooting

If Bootstrap styles or scripts do not load:

1. Verify the module is enabled in **Stores → Configuration**.

2. Flush Magento cache:

   ```bash
   php bin/magento cache:flush
   ```

3. Check browser console for CSP or network errors.

4. Ensure your store is running Magento 2.4.x with CSP enabled.

5. Enable **Debug Mode** for diagnostic output.

---

## Compatibility & Performance

* Compatible with Magento 2.4.x frontend architecture
* Uses Magento PageConfig and RequireJS
* Safe for production mode
* Compatible with static content deployment
* No direct theme overrides

---

## Known Limitations

* The module does **not automatically restyle Magento UI components** to Bootstrap.
* Theme-level styling conflicts are the responsibility of the storefront implementation.
* Bootstrap JavaScript components require compatible markup to function correctly.

---

## Support

For bug reports or feature requests, please use the extension’s repository issue tracker or contact the maintainer via
the Magento Marketplace listing.

---

## License

This extension is licensed under the **Open Software License (OSL-3.0)**, in accordance with Magento Marketplace
requirements.

---

## Marketplace Readiness Summary

* Magento 2.4.x compatible
* CSP-compliant (`script-src`, `style-src`, `font-src`, `connect-src`, `img-src`)
* No inline JavaScript
* Composer-installable
* HK2 Core dependency documented
* Privacy disclosure included
* Admin-configurable
* Demo links included
* Non-intrusive to theme and UI

---
