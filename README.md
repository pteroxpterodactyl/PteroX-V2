# 🚀 PteroX V2

PteroX V2 is a **modern frontend theme for Pterodactyl Panel** featuring a redesigned dark interface, custom navigation, server management UI, and fully configurable branding. ✨

## 🛠️ Compatibility

- 🐧 **Pterodactyl Panel:** `1.14.x`
- ⭐ **Recommended version:** `1.14.1`
- 🟢 **Node.js:** Required
- 🧶 **Yarn:** Required
- 🐘 **PHP:** Required
- 📦 **Composer:** Required
- 🌐 **curl:** Required
- 🐍 **Python 3:** Required by the installer

PteroX V2 is designed for **Pterodactyl 1.14.x**. Other versions are not guaranteed to work.

## ✨ PteroX V2.0.2

PteroX V2.0.2 includes the redesigned PteroX interface, custom navigation, automatic frontend dependency installation, automatic timestamped backups, and **four independently configurable logo locations**: the main panel sidebar, main panel header, login page main logo, and login page header logo.

The installer automatically installs:

- `@fontsource/poppins`
- `@fortawesome/free-brands-svg-icons`

Customers do not need to install these packages manually.

---

## 📥 Installation

### 1. Upload PteroX V2

Upload the complete `PteroX-V2` folder to your server, for example:

```text
/tmp/PteroX-V2/
```

Do **not** manually copy the contents of `files/`. The installer does this automatically.

### 2. Run the installer

```bash
cd /tmp/PteroX-V2
chmod +x install.sh
sudo ./install.sh
```

The installer automatically:

- Checks Pterodactyl `1.14.x` compatibility.
- Creates a timestamped backup.
- Installs the PteroX files.
- Installs required frontend dependencies.
- Builds the frontend.
- Clears Laravel caches.

After installation, hard-refresh the panel with `Ctrl + Shift + R`.

---

## 💾 Automatic Backups

Backups are stored in:

```text
/var/www/pterodactyl/storage/pterox-backups/
```

Keep your backup until you have confirmed the installation works correctly.

---

## 🎨 Branding & Customization

Normal PteroX branding is controlled by:

```text
/var/www/pterodactyl/resources/scripts/pterox.config.ts
```

Edit it with:

```bash
nano /var/www/pterodactyl/resources/scripts/pterox.config.ts
```

### Default configuration

```ts
export const PTEROX_CONFIG = {
    name: 'pterox',
    email: 'pterox@webpool.tech',

    // Main panel sidebar logo
    sidebarLogo: '/images/pterox-sidebar-logo.webp',

    // Main panel header logo
    headerLogo: '/images/pterox-header-logo.webp',

    // Login page main logo
    loginLogo: '/images/pterox-login-logo.webp',

    // Login page header logo
    loginHeaderLogo: '/images/pterox-login-header-logo.webp',
};
```

### 🏷️ Brand Name

Change `name: 'pterox'` to your brand, for example `name: 'WebPool'`.

### 📧 Sidebar Email

Change `email: 'pterox@webpool.tech'` to your own support email, for example `email: 'support@webpool.tech'`.

### 🖼️ Logo Configuration

Upload your custom logos to:

```text
/var/www/pterodactyl/public/images/
```

For example:

```text
/var/www/pterodactyl/public/images/webpool-sidebar.webp
/var/www/pterodactyl/public/images/webpool-header.webp
/var/www/pterodactyl/public/images/webpool-login.webp
/var/www/pterodactyl/public/images/webpool-login-header.webp
```

Then update the corresponding values in `pterox.config.ts`:

```ts
export const PTEROX_CONFIG = {
    name: 'WebPool',
    email: 'support@webpool.tech',

    sidebarLogo: '/images/webpool-sidebar.webp',
    headerLogo: '/images/webpool-header.webp',
    loginLogo: '/images/webpool-login.webp',
    loginHeaderLogo: '/images/webpool-login-header.webp',
};
```

| Configuration | Location |
|---|---|
| `sidebarLogo` | 🟣 Main panel sidebar |
| `headerLogo` | 🔵 Main panel header |
| `loginLogo` | 🟢 Login page main logo |
| `loginHeaderLogo` | 🟠 Login page header |

**All four logo locations are independently configurable.** Customers normally do not need to edit the component files directly.

---

## 🔨 Rebuild After Branding Changes

After changing `pterox.config.ts`:

```bash
cd /var/www/pterodactyl
yarn build:production
php artisan optimize:clear
```

Then hard-refresh the browser with `Ctrl + Shift + R`.

---

## 🗑️ Uninstallation

Enter the PteroX package directory:

```bash
cd /tmp/PteroX-V2
```

Run:

```bash
chmod +x uninstall.sh
sudo ./uninstall.sh
```

The uninstaller restores the most recent PteroX backup.

Afterward:

```bash
cd /var/www/pterodactyl
php artisan optimize:clear
```

Then hard-refresh the panel.

---

## 🔧 Troubleshooting

### Unsupported Pterodactyl Version

PteroX V2 requires **Pterodactyl 1.14.x**. Do not bypass the version check.

### Frontend Build Problems

Check:

```bash
node -v
npm -v
yarn -v
php -v
```

Then:

```bash
cd /var/www/pterodactyl
yarn build:production
php artisan optimize:clear
```

### Branding Changes Not Showing

Run:

```bash
cd /var/www/pterodactyl
php artisan optimize:clear
yarn build:production
```

Then hard-refresh with `Ctrl + Shift + R`.

---

## 📌 Important Notes

- 🚀 PteroX V2 is designed for **Pterodactyl 1.14.x**.
- 💾 Keep your PteroX backups.
- 🎨 Branding should normally be changed through `pterox.config.ts`.
- 🖼️ All four PteroX logo locations can be customized independently.
- 🔄 Future PteroX updates may overwrite custom frontend modifications.
- 📦 PteroX V2 does **not** install Pterodactyl, Node.js, Yarn, PHP, or Composer for you.

---

## 🆘 Support

Before requesting support, check your Pterodactyl, Node.js, Yarn, and PHP versions and review the troubleshooting section.

When contacting support, provide:

- Pterodactyl version
- PteroX V2 version
- Node.js version
- Yarn version
- PHP version
- Exact error message

---

# 💙 PteroX V2

**Modern Pterodactyl. Built for a cleaner experience.** 🚀
