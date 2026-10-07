Here’s the simplest way to install **PHP + Composer on Windows**.

### 1. Install PHP

Go to the official PHP Windows download page:

[PHP for Windows](https://windows.php.net/download/?utm_source=chatgpt.com)

Download the latest [**x64 Thread Safe ZIP**](https://downloads.php.net/~windows/releases/archives/php-8.5.11-Win32-vs17-x64.zip) version.

Example:

```text
php-8.x.x-Win32-vs17-x64.zip
```

Extract it to:

```text
C:\php
```

Inside `C:\php`, you should see files such as:

```text
php.exe
php.ini-development
php.ini-production
```

### 2. Create `php.ini`

Copy:

```text
C:\php\php.ini-development
```

and rename the copy to:

```text
C:\php\php.ini
```

### 3. Add PHP to Windows PATH

Search Windows for:

```text
Environment Variables
```

Open:

**Edit the system environment variables → Environment Variables**

Under **System variables**, select:

```text
Path
```

Click **Edit → New** and add:

```text
C:\php
```

Click **OK** on all windows.

Close and reopen Command Prompt or PowerShell.

### 4. Check PHP

Run:

```powershell
php -v
```

You should see something similar to:

```text
PHP 8.x.x (cli)
```

You can also check the PHP configuration:

```powershell
php --ini
```

### 5. Enable common PHP extensions

Open:

```text
C:\php\php.ini
```

Find:

```ini
;extension=curl
;extension=fileinfo
;extension=mbstring
;extension=openssl
;extension=pdo_mysql
;extension=mysqli
```

Remove the `;`:

```ini
extension=curl
extension=fileinfo
extension=mbstring
extension=openssl
extension=pdo_mysql
extension=mysqli
```

Also make sure this is configured:

```ini
extension_dir = "ext"
```

Then verify:

```powershell
php -m
```

### 6. Install Composer

Download the official Windows installer:

[Composer Windows Installer](https://getcomposer.org/Composer-Setup.exe?utm_source=chatgpt.com)

Run:

```text
Composer-Setup.exe
```

When it asks for the PHP executable, select:

```text
C:\php\php.exe
```

Continue through the installer.

### 7. Check Composer

Close and reopen PowerShell, then run:

```powershell
composer --version
```

You should get something like:

```text
Composer version 2.x.x
```

### 8. Final check

Run:

```powershell
php -v
composer --version
```

If both commands work, you're ready.

For a **Laravel** development machine, the next usual step is:

```powershell
composer global require laravel/installer
```

Then:

```powershell
laravel new my-project
```

Or create a Laravel project directly:

```powershell
composer create-project laravel/laravel my-project
```