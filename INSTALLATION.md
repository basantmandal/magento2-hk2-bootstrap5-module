# HK2 AddBootstrap5 Magento 2 Module — Installation Guide

This guide explains how to install and configure the **HK2 AddBootstrap5** module in Magento 2.

---

## System Requirements

* **Magento Open Source / Adobe Commerce:** 2.4.x
* **PHP:** 8.1 or higher
* **Database:** MySQL 5.7+ or compatible

> Note: Magento 2.3.x is not supported.

---

## Installation Methods

### Method 1: Composer (Recommended)

1. Navigate to your Magento 2 root directory via terminal.
2. Run the following command:

```bash
composer require hk2/addbootstrap5
```

1. Enable and configure the module:

```bash
php bin/magento module:enable HK2_AddBootstrap5
php bin/magento setup:upgrade
php bin/magento setup:di:compile
php bin/magento setup:static-content:deploy -f
php bin/magento cache:clean
```

---

### Method 2: Manual Installation

1. Download or clone the module repository.
2. Create the directory structure:

```
app/code/HK2/AddBootstrap5/
```

1. Copy all module files into the folder above.
2. Enable and configure the module using the commands in Method 1.

---

## Post-Installation Steps

### 1. Clear Cache

```bash
php bin/magento cache:flush
```

### 2. Deploy Static Content (if in production)

```bash
php bin/magento setup:static-content:deploy -f
```

---

## Admin Configuration

1. Log in to the Magento Admin Panel.
2. Navigate to **Stores → Configuration → HK2 → AddBootstrap5**.
3. Configure the following settings:

| Setting               | Description                                           |
| --------------------- | ----------------------------------------------------- |
| **Enable Module**     | Toggle to enable or disable Bootstrap asset injection |
| **Bootstrap Version** | Select your desired version (Bootstrap 4.x or 5.x)    |
| **Debug Mode**        | Enable to output debug logs in the browser console    |

1. Save the configuration. Changes take effect immediately on the storefront.

---

## Demo Pages

After enabling the module, you can verify Bootstrap integration via the included demo pages:

* **Bootstrap 5 Demo:**

  ```
  https://yourstore.com/bootstrap5demo/demo/index/version/5
  ```

* **Bootstrap 4 Demo:**

  ```
  https://yourstore.com/bootstrap5demo/demo/index/version/4
  ```

> Replace `yourstore.com` with your actual domain.

---

## Troubleshooting

* **Bootstrap not loading:**

  * Ensure the module is enabled in **Admin → Configuration**.
  * Flush the Magento cache (`php bin/magento cache:flush`).
  * Check browser console for 404 errors or blocked CDN assets.

* **Debug Mode:**

  * Enable “Debug Mode” in configuration to log Bootstrap version, CDN URL, and other diagnostics.

---

## Notes

* No theme files are overridden.
* Assets are loaded via CDN for performance and security.
* Fully compliant with Magento 2.4.x CSP.

---
