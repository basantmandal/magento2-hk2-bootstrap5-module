# Installation Guide

**HK2 AddBootstrap5 for Magento 2**

This document explains how to install and activate the **HK2 AddBootstrap5** extension, including its required dependency **HK2 Core**.

---

## Prerequisites

Before installation, ensure your system meets the following requirements:

* Magento Open Source / Adobe Commerce **2.4.x**
* PHP **8.1 or higher**
* Composer **2.x**
* Command-line access to the Magento root directory

> ⚠ Magento 2.3.x is end-of-life and not supported.

---

## Required Dependency

This module depends on **HK2 Core**.

* Package name: `hk2/core`
* Namespace: `HK2_Core`
* Required for both **Composer** and **manual** installations

---

## Installation Methods

### Option 1: Composer Installation (Recommended)

Composer will automatically install **HK2 Core** as a dependency.

From the Magento root directory, run:

```bash
composer require hk2/addbootstrap5
```

After installation, proceed to Enable the Module.

---

### Option 2: Manual Installation

Use this method only if Composer is not available. You can install it from any one from below urls.

---

#### Step 1: Install HK2 Core

* **Download HK2 Core** - <https://github.com/basantmandal/magento2-hk2-core/archive/refs/tags/1.0.0.zip>
  
Ensure the following directory exists:

```
app/code/HK2/Core
```

If not, copy the **HK2 Core** module into this location.

#### Step 2: Install HK2 AddBootstrap5

* **Download HK2 AddBootstrap5** - <https://github.com/basantmandal/magento2-addbootstrap5/archive/refs/tags/3.0.0.zip>
  
Create the module directory:

```bash
app/code/HK2/AddBootstrap5
```

Copy all module files into this directory.

---

## Enable the Module

After installing both modules, run the following commands from the Magento root:

```bash
php bin/magento module:enable HK2_Core HK2_AddBootstrap5
php bin/magento setup:upgrade
php bin/magento cache:flush
```

---

### Production Mode (Optional)

If your store is in production mode, also run:

```bash
php bin/magento setup:di:compile
php bin/magento setup:static-content:deploy
```

---

## Verify Installation

1. Log in to the Magento Admin Panel.

2. Navigate to:

   **Stores → Configuration → HK2 → AddBootstrap5**

3. Enable the extension and select the desired Bootstrap version.

4. Save configuration and refresh cache if prompted.

---

## Demo Pages (Optional Verification)

The module provides demo routes for testing:

**Bootstrap 5**

```
https://yourstore.com/bootstrap5demo/demo/index/version/5
```

**Bootstrap 4**

```
https://yourstore.com/bootstrap5demo/demo/index/version/4
```

> Demo routes are intended for validation and can be disabled in production environments.

---

## Troubleshooting

If the extension does not appear or Bootstrap assets are not loading:

1. Confirm both modules are enabled:

   ```bash
   php bin/magento module:status HK2_Core HK2_AddBootstrap5
   ```

2. Flush cache:

   ```bash
   php bin/magento cache:flush
   ```

3. Check `var/log/system.log` and browser console for errors.

4. Ensure Content Security Policy (CSP) is not blocking CDN assets.

---

## Uninstallation

### Composer

```bash
composer remove hk2/addbootstrap5
php bin/magento setup:upgrade
php bin/magento cache:flush
```

### Manual

1. Disable the module:

   ```bash
   php bin/magento module:disable HK2_AddBootstrap5
   ```

2. Remove the directory:

   ```
   app/code/HK2/AddBootstrap5
   ```

3. Run:

   ```bash
   php bin/magento setup:upgrade
   php bin/magento cache:flush
   ```

---

## Support

For issues related to installation:

* Email: [support@basantmandal.in](mailto:support@basantmandal.in)
* Website: [https://www.basantmandal.in](https://www.basantmandal.in)
* LinkedIn: [https://www.linkedin.com/in/basantmandal](https://www.linkedin.com/in/basantmandal)

---
