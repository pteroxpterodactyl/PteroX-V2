PteroX V2

PteroX V2 is a modern frontend theme for Pterodactyl Panel featuring a redesigned dark interface, custom navigation, server management UI, and configurable branding.

Compatibility
Pterodactyl Panel: 1.14.x
Recommended version: 1.14.1
Node.js: Required
Yarn: Required
PHP: Required
Composer: Required
curl: Required
Python 3: Required by the installer

PteroX V2 is designed for Pterodactyl 1.14.x. Other versions are not guaranteed to work.

PteroX V2.0.2
What's included
Redesigned PteroX V2 frontend
Custom sidebar navigation
Custom header branding
Separate configurable logos for:
Main panel sidebar
Main panel header
Login page main logo
Login page header
Configurable brand name and email
Automatic frontend dependency installation
Automatic timestamped backups
Pterodactyl 1.14.x compatibility check
Frontend production build
Laravel cache clearing

The installer automatically installs:

@fontsource/poppins
@fortawesome/free-brands-svg-icons

Customers do not need to install these packages manually.

Installation
1. Upload PteroX V2

Upload the complete PteroX-V2 folder to your server, for example:

/tmp/PteroX-V2/

Do not manually copy the contents of files/. The installer handles this automatically.

2. Run the installer
cd /tmp/PteroX-V2
chmod +x install.sh
sudo ./install.sh

The installer automatically:

Checks that Pterodactyl 1.14.x is installed.
Creates a timestamped backup.
Installs the PteroX files.
Installs required frontend dependencies.
Builds the frontend.
Clears Laravel caches.

After installation, hard-refresh the panel:

Ctrl + Shift + R
Automatic Backups

Backups are stored in:

/var/www/pterodactyl/storage/pterox-backups/

Keep your backup until you have confirmed that the installation works correctly.

Branding & Customization

PteroX V2 provides a central configuration file:

/var/www/pterodactyl/resources/scripts/pterox.config.ts

You can edit it with:

nano /var/www/pterodactyl/resources/scripts/pterox.config.ts
Default configuration
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

All four logo locations can be changed from this configuration file.

Brand Name

Change:

name: 'pterox',

to your brand:

name: 'WebPool',

The configured name is used in supported PteroX branding locations.

Sidebar Email

Change:

email: 'pterox@webpool.tech',

to your own email:

email: 'support@webpool.tech',
Logo Configuration

Upload your custom logos to:

/var/www/pterodactyl/public/images/

For example:

/var/www/pterodactyl/public/images/webpool-sidebar.webp
/var/www/pterodactyl/public/images/webpool-header.webp
/var/www/pterodactyl/public/images/webpool-login.webp
/var/www/pterodactyl/public/images/webpool-login-header.webp

Then configure them:

export const PTEROX_CONFIG = {
    name: 'WebPool',
    email: 'support@webpool.tech',

    sidebarLogo: '/images/webpool-sidebar.webp',
    headerLogo: '/images/webpool-header.webp',
    loginLogo: '/images/webpool-login.webp',
    loginHeaderLogo: '/images/webpool-login-header.webp',
};
Logo locations
Configuration	Location
sidebarLogo	Main panel sidebar
headerLogo	Main panel header
loginLogo	Login page main logo
loginHeaderLogo	Login page header

You normally do not need to edit the component files to change these logos.

Rebuild After Branding Changes

After changing pterox.config.ts:

cd /var/www/pterodactyl
yarn build:production
php artisan optimize:clear

Then hard-refresh your browser:

Ctrl + Shift + R
Uninstallation

Enter the PteroX package directory:

cd /tmp/PteroX-V2

Run:

chmod +x uninstall.sh
sudo ./uninstall.sh

The uninstaller restores the most recent PteroX backup.

Afterward:

cd /var/www/pterodactyl
php artisan optimize:clear

Then hard-refresh the panel.

Troubleshooting
Unsupported Pterodactyl Version

PteroX V2 requires:

Pterodactyl 1.14.x

Do not bypass the version check.

Frontend Build Problems

Check your installed versions:

node -v
npm -v
yarn -v
php -v

Then:

cd /var/www/pterodactyl
yarn build:production
php artisan optimize:clear
Branding Changes Not Showing

Run:

cd /var/www/pterodactyl
php artisan optimize:clear
yarn build:production

Then hard-refresh the browser with:

Ctrl + Shift + R
Important Notes
PteroX V2 is designed for Pterodactyl 1.14.x.
Keep your PteroX backups.
PteroX V2 does not install Pterodactyl, Node.js, Yarn, PHP, or Composer for you.
Future PteroX updates may overwrite custom frontend modifications.
Normal branding changes should be made through pterox.config.ts.
The four supported logo locations are independently configurable.
Support

Before requesting support, check your:

node -v
yarn -v
php -v

and your Pterodactyl version.

When contacting support, provide:

Pterodactyl version
PteroX V2 version
Node.js version
Yarn version
PHP version
Exact error message
PteroX V2

Modern Pterodactyl. Built for a cleaner experience.
