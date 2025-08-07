# RestrictViewOnlyPDF

A simple WordPress plugin that restricts access to specific pages unless the user has purchased corresponding WooCommerce products. Great for delivering **PDFs or private content** only to paying customers.

---

## Features

- Restrict any page based on WooCommerce product purchase
- Custom redirect URL if user is not authorized
- Admin panel to manage page-product mappings
- Supports multiple page restrictions
- Clean and lightweight with FontAwesome UI

---

## Use Case

Perfect for:

- Paid PDF downloads
- Private course or resource pages
- Membership content access
- View-only resources tied to WooCommerce

---

## Installation

1. Download or clone this repository
2. Upload the folder to your WordPress site under `/wp-content/plugins/`
3. Activate the plugin from the **Plugins** menu
4. Go to **RestrictViewOnlyPDF** in the admin sidebar
5. Add your access rules:
   - **Page Slug** (e.g., `private-pdf-page`)
   - **WooCommerce Product ID**
   - **Optional Redirect URL**

---

## How It Works

- If a user tries to visit a restricted page:
  - Not logged in? ➜ Redirects to `/my-account/`
  - Logged in but hasn't purchased? ➜ Redirects to the page you set (or `/shop` by default)

---
## Dependencies
WordPress 5.0+

WooCommerce 4.0+

PHP 7.0+

## 👤 Author
Dev.shubho
Crafted with ❤️ for content protection.

## Developer Notes

### Filter Hook for Custom Logic (Optional)
You can hook into this plugin to extend its behavior if needed.

```php
add_filter('restrict_pdf_access_check', function($allowed, $user_id, $product_id) {
    // Custom logic...
    return $allowed;
}, 10, 3);


