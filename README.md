# Hard Guard Security

**WP Hard Guard – WordPress Security Hardening Plugin**

Free WordPress Security Plugin

<img width="1536" height="1024" alt="Hard Guard Security for WordPress" src="https://github.com/user-attachments/assets/dd49d241-8c31-43df-a1c7-5c64e5034e24" />

**WordPress Security, 2FA, Malware Scanner, Vulnerability Monitoring & Audit Log**

Hard Guard Security is a free and open-source WordPress security and diagnostic plugin that combines authentication protection, activity monitoring, local malware scanning, vulnerability monitoring, file integrity checks, antispam, GeoIP access controls, SSL diagnostics and security hardening in one administration interface.

All included features are available without payment, a license key, a subscription, a trial period or usage quotas. The plugin does not send telemetry, usage statistics, settings, scan results or website files to its author.

## Main features

### Authentication protection

Protect the WordPress login process with progressive lockouts, explicit trusted-proxy handling, custom login controls and recovery mechanisms.

- Progressive login lockouts by IP address, username or a combined IP-and-username key.
- Optional IP-wide counting to prevent bypassing limits by rotating usernames.
- IPv4 and IPv6 whitelist, blacklist and CIDR support.
- Hardened client-IP resolution with explicit support for `REMOTE_ADDR`, `X-Forwarded-For`, `X-Real-IP`, `CF-Connecting-IP` and RFC 7239 `Forwarded`.
- Forwarded proxy chains are evaluated from the trusted server side toward the visitor and malformed chains fail safely to `REMOTE_ADDR`.
- Proxy diagnostics showing the direct peer, trust state, selected source, received headers, resolved visitor IP and fallback reason.
- Optional custom WordPress login URL with a five-minute safety test and automatic rollback.
- Optional 404 response for direct `wp-login.php` access after the safety test succeeds.
- Single-use emergency recovery URL and documented `wp-config.php` recovery constants.
- Configurable login and lockout notifications with cooldown controls.
- Optional Cloudflare Turnstile for WordPress and WooCommerce login forms, including compatible custom forms using `wp_signon()`.

### Two-factor authentication

Add an additional authentication layer using email codes or RFC 6238-compatible TOTP authenticator applications.

- Email verification codes and TOTP authenticator apps.
- Local QR-code generation and manual authenticator setup key.
- Ten single-use recovery codes.
- Independent per-user 2FA configuration.
- Administrator 2FA status overview and secure administrator reset.
- Required-role policies with a configurable setup grace period.
- Recovery-only fallback when a configured method becomes unavailable, preventing silent 2FA bypass.
- Encrypted TOTP secret storage when Sodium or OpenSSL is available.
- User-specific email 2FA messages follow the recipient's selected interface or WordPress language.

### Advanced Audit Log

Monitor security-relevant WordPress activity from a dedicated Audit Log workspace.

- Overview dashboard, searchable and filterable events and detailed event information.
- Severity, category, action and result classifications.
- User, role, session and administrator-privilege activity.
- Plugin, theme and WordPress Core changes.
- Post, page, supported custom post type and optional comment activity.
- Selected WordPress and Hard Guard Security setting changes.
- Alert rules with thresholds, grouping and cooldowns.
- Severity-specific retention.
- CSV and JSON export with optional IP masking.
- Protection against spreadsheet-formula injection and secret/credential redaction.
- Dedicated login/IP-block statistics, trends, suspicious-IP ranking and active lockout details.
- Aggregated WordPress Multisite network view.

### Application Password management

Control and monitor native WordPress Application Passwords used by REST API clients, integrations, scripts and external applications.

- Global and role-based Application Password policies.
- Central credential inventory with inactive-credential filtering.
- Individual credential revocation and revocation of all credentials for a selected user.
- Optional inactivity cleanup.
- Alerts for credential creation, revocation, first use, new-IP use and failed authentication.
- Credentials blocked by policy remain stored but cannot authenticate until policy allows them again.
- Plaintext Application Password values and password hashes are never stored in Hard Guard Security logs, emails or exports.

### Malware Scanner

Inspect WordPress files for selected patterns and file structures associated with malicious or suspicious code. Scanner findings are diagnostic and require administrator review.

- Quick Scan and Full Scan modes.
- **Manual** and **Automatic** Scanner modes.
- Automatic Full Scan interval configurable from 1 to 365 days; default is 7 days.
- Automatic scans run in bounded WP-Cron batches and continue through scheduled steps instead of requiring one long PHP request.
- Advisory locking prevents overlapping automatic workers from processing the same scan concurrently.
- Next automatic scan status and warning when WordPress cron spawning is disabled.
- Manual Quick and Full scans remain available while Automatic mode is enabled.
- Live 0–100% progress, current stage, checked-file count, findings count and current path.
- Batched AJAX processing with stop and resume controls for manual scans.
- Scan history with Manual/Automatic run labels.
- Per-scan result cleanup and one-click result/history clearing while preserving quarantine and exact-hash ignore decisions.
- JSON report export with translated known finding reasons.
- Dangerous execution-chain and request-controlled execution detection.
- Hidden PHP inside static/media files, executable files in uploads and double-extension detection.
- Unexpected executable additions to WordPress Core directories.
- Exact SHA-256 ignore rules.
- Administrator-password-protected quarantine and restoration.
- Optional high- and critical-severity notifications.

Files are analysed locally. Website file contents are not sent to an external malware-scanning service. Hard Guard Security never automatically deletes suspicious files.

### Vulnerability Monitoring

Full and Automatic scans include a dedicated **Vulnerabilities & updates** stage for WordPress Core, installed plugins and installed themes.

- Separate `Vulnerable` and `Outdated` findings.
- Local matching against a signed Hard Guard threat-intelligence database.
- Signed feed verification using Ed25519.
- HTTPS-only database downloads with size limits, schema validation and fail-safe retention of the previous verified database.
- Automatic threat-database update scheduling and manual refresh controls.
- Local inventory matching for WordPress Core, plugins and themes, including active/inactive status.
- HGSA/CVE identifiers and advisory references when available.
- CVSS score and Critical / High / Medium / Low severity.
- Fixed-version information when available.
- Known-exploited indicators when available.
- Signed current-version index for WordPress.org Core, plugins and themes.
- Outdated detection prefers the downloaded version index and falls back to WordPress' existing local update cache only when a component is not covered.
- Vulnerable components may simultaneously be reported as Outdated.
- New/changed vulnerability state tracking prevents duplicate alerts for unchanged findings.
- Dedicated vulnerability/outdated counts in scan status, history, JSON exports and completion notifications.
- Consistency checks reconcile summary counters with stored findings before a scan completes.

**Privacy:** Hard Guard downloads the signed public database, but vulnerability matching is performed locally. Requests do not transmit the site URL, installed plugin/theme inventory, installed versions, file names, scan results or file contents to Hard Guard.

### WordPress file integrity

Compare security-relevant WordPress root, `wp-admin` and `wp-includes` files with official checksum data for the installed WordPress version and locale.

- Detect modified or missing WordPress Core files.
- Detect unexpected files directly in the WordPress root, `wp-admin` and `wp-includes`.
- Detect executable PHP-like files inside uploads.
- Preserve first-detected timestamps for unresolved findings.
- Report symbolic links separately.
- Read-only operation.

The check sends only the installed WordPress version and locale to WordPress.org to retrieve official checksum data. Website files and their contents are not sent to WordPress.org.

### Read-only file-permissions scan

Review important WordPress paths and recursively inspect Core, plugin and theme directories without changing `chmod` values.

- World-writable paths are reported as Critical.
- Group-writable paths, executable regular files, symbolic links and broadly readable `wp-config.php` configurations are reported as warnings.
- Results include localized status, item type and explanation text.
- Safe permission values remain dependent on server ownership, group membership, PHP handler and deployment model.

### Antispam protection

Protect native WordPress comments, WooCommerce reviews using the WordPress comment system and native WordPress registration.

- Honeypot fields, signed timing tokens and JavaScript confirmation.
- Submission rate limits and link limits.
- Phrase and safe wildcard rules plus email-domain rules.
- Local reputation data and heuristic language filtering.
- Configurable moderation, spam and rejection thresholds.
- Quarantine reasons, false-positive handling, statistics and retention controls.
- Digest emails and spam-outbreak alerts.
- Optional country filtering through the `country.is` API, including risk-score mode and strict allowlist/blocklist policies.
- Separate direct actions for detected languages outside the allowlist and unknown language.

Comment and registration content is analysed locally and is not sent to an external antispam service.

### GeoIP country access

Configure site-wide country access for requests processed by WordPress, including public pages, login, administration and API endpoints.

- Country blocklist and allowlist policies using ISO 3166-1 alpha-2 country codes.
- Country detection through the `country.is` IP-to-country API.
- Successful lookup cache: 24 hours; failed lookup cache: 10 minutes.
- Country-detection test before enabling a policy.
- IP and CIDR recovery exceptions.
- Administrator, WP-Cron and WP-CLI bypasses.
- Custom HTTP 403 page title, message and optional help link.
- Fail-open handling when a country cannot be determined.
- Emergency `wp-config.php` bypass.

The resolved visitor IP address is sent to `country.is` only when an enabled country rule requires a lookup.

### SSL and HTTPS diagnostics

Review selected SSL, HTTPS and browser-security settings from a dedicated administration page.

- PHP-based HTTPS redirects and managed Apache-compatible `.htaccess` redirects.
- Quick database mixed-content scan and deep front-end mixed-content scan.
- Same-host mixed-content repair.
- SSL certificate health checks and live security-header scans.
- HSTS configuration.
- Content Security Policy `upgrade-insecure-requests`.
- Permissions-Policy controls for camera, microphone, geolocation and payment features.
- MIME-sniffing protection, Referrer-Policy and frame protection.
- `X-Powered-By` removal.
- Apache and Nginx configuration examples.

SSL certificate and security-header diagnostics perform HTTP or TLS requests only to the administrator's own website.

### System hardening and data hiding

Reduce exposure of selected common WordPress endpoints and sensitive paths.

- Block XML-RPC access.
- Hide the anonymous REST Users API.
- Block public author enumeration and remove the native WordPress user sitemap.
- Protect selected sensitive files and disable directory indexes.
- Block direct PHP requests in uploads, with optional blocking in plugin and theme directories.
- Disable the built-in plugin and theme file editor.
- Suppress public PHP/startup-error display after WordPress loads without disabling error logging.
- Hide selected WordPress generator and discovery links.
- Optionally remove asset version query strings from public CSS and JavaScript URLs.
- Managed Apache-compatible `.htaccess` rules with HTTP 5xx loopback safety checks and automatic rollback.
- Generated Nginx configuration examples for manual review and installation.

High-risk options should be enabled one at a time and tested on a staging website.

### Settings export and import

- Export creates a JSON file containing the plugin configuration and package version.
- Turnstile Secret keys and SMTP passwords are blanked before export.
- User authenticator secrets and recovery codes are not included.
- Import validates supported settings before saving and preserves the existing configuration when validation fails.
- For safety, import preserves destination-site secrets, disables direct `wp-login.php` blocking and does not automatically activate server-level System Tweaks.

### Notifications and SMTP

Security alerts can use the standard WordPress mail system or SMTP settings dedicated to Hard Guard Security.

Notifications can cover:

- Login lockouts, blacklist blocks and failed login attempts.
- Administrator logins.
- 2FA failures and recovery-code use.
- Application Password activity.
- Malware Scanner findings.
- Vulnerability findings and scan completion status.
- Audit Log alert rules.
- Antispam digests and outbreak alerts.

A global email language can be selected for background alerts and reports. SMTP settings affect only messages sent by Hard Guard Security and do not replace email delivery for the entire WordPress website. SMTP passwords are encrypted when Sodium or OpenSSL is available.

## Privacy-conscious operation

Hard Guard Security is primarily designed to operate locally and does not send telemetry, usage statistics, settings, scan results or personal data to the plugin author.

External connections are limited to features that require them:

- **Hard Guard signed vulnerability feed:** downloads signed threat-intelligence and version-index data. The request does not include the site URL, installed software inventory, installed versions, scan results, file names or file contents. Matching is performed locally.
- **WordPress.org:** Core and supported integrity checks retrieve official checksum information. Only the installed WordPress version/locale or data required by the corresponding WordPress mechanism is used.
- **country.is:** site-wide GeoIP access and Antispam country rules send the resolved visitor IP only when a lookup is required.
- **Cloudflare Turnstile:** communicates with Cloudflare only after an administrator explicitly enables and configures the feature.
- **Administrator-configured SMTP:** communication occurs only after an administrator configures SMTP.
- **PayPal:** contacted only after an administrator clicks the voluntary donation button; no PayPal scripts, images or tracking pixels load when a Hard Guard Security page is opened.
- **Administrator's own website:** SSL, redirect, mixed-content and security-header diagnostics make HTTP/TLS requests only to the configured website.

Hard Guard Security stores security data locally. Depending on enabled modules, this can include IP addresses, usernames, login results, event times, administrative actions, request paths without query strings, antispam incident details, file paths, checksums, matched scanner rules and short escaped excerpts.

Known password, token, nonce, cookie, authorization and API-key fields are redacted before Audit Log storage. Plaintext Application Passwords and their hashes are not written to Hard Guard Security logs. TOTP secrets and SMTP passwords are encrypted when Sodium or OpenSSL is available; recovery codes are stored as one-way hashes.

WordPress personal-data export and erasure callbacks are registered under **Tools**. Matching Audit Log events are anonymized so non-personal security metadata can be retained.

## WordPress Multisite

Hard Guard Security supports WordPress Multisite. Authentication settings, plugin tables and data are maintained per site, while shared filesystem and server-level hardening settings are available only from the main site to an authorized network administrator.

The Audit Log can provide an aggregated network view across up to 100 sites.

## Languages

The administration interface, Help content, security messages, email content and Scanner finding descriptions include:

- English
- Polish
- German
- Spanish
- French
- Italian

Each administrator can use the WordPress dashboard language or independently force one of the bundled Hard Guard Security interface languages without changing the website language for other users.

## Requirements

- WordPress **7.0 or newer**.
- Tested up to WordPress **7.0**.
- PHP **7.4 or newer**.
- JavaScript enabled in the browser for interactive administration tools and selected antispam checks.
- HTTPS strongly recommended.
- Apache, LiteSpeed or Nginx web server.
- Nginx server-level rules require manual configuration.
- PHP read access to WordPress files for scanning.
- Filesystem write access is required for quarantine and managed server-rule features.
- Sodium or OpenSSL is recommended for encrypted secret storage.
- Outbound HTTPS access is required for the signed Hard Guard vulnerability feed, WordPress.org checksum services and `country.is` lookups when the corresponding features are used.
- Email-based 2FA and security notifications require working WordPress mail delivery or properly configured SMTP.

## Installation

1. Download the latest package from [GitHub Releases](https://github.com/endriu7777/WP-Hard-Guard/releases).
2. In WordPress, open **Plugins → Add New → Upload Plugin**.
3. Upload the Hard Guard Security ZIP and activate the plugin.
4. Open **Hard Guard Security → Settings** and select the interface and email language.
5. Configure trusted proxies before relying on forwarded client-IP headers.
6. Test email delivery before enabling email-based 2FA.
7. Store recovery codes outside WordPress.
8. Create a complete backup and test high-risk changes on a staging website whenever possible.

## Emergency recovery

Hard Guard Security provides a single-use emergency recovery URL and temporary `wp-config.php` constants for restoring access after a configuration problem.

Available recovery controls include disabling login hiding, 2FA, GeoIP enforcement, HTTPS redirect and login rate limiting/active lockouts. Recovery constants should be removed immediately after access is restored and the underlying configuration is corrected.

## Uninstallation and data cleanup

Deactivation keeps settings and stored data but clears the daily plugin cron hook and removes managed server rules where the configuration file is writable.

When **Delete all Hard Guard Security data during uninstall** is enabled, uninstall removes plugin options, transients, user metadata including 2FA data, network metadata, plugin database tables, logs, scan records and safely validated Scanner quarantine files.

## Important limitations

Hard Guard Security reduces selected security risks but does not guarantee complete protection against all attacks, vulnerabilities, configuration errors, compatibility problems or data loss.

The Malware Scanner, vulnerability monitoring and integrity tools are diagnostic. False positives and false negatives are possible.

Hard Guard Security is not a replacement for:

- Regular, tested backups.
- WordPress, plugin and theme updates.
- Secure hosting and server configuration.
- A web application firewall.
- Server monitoring.
- Malware removal performed by a security specialist.
- Professional incident response.
- An independent security audit.

Before changing login URLs, access rules, HTTPS settings, file permissions, quarantine state or hardening options, create a complete backup and test the configuration in a staging environment.

## Free and open-source edition

Hard Guard Security is a free and open-source repository edition. Every included feature is available to every user without payment, feature activation, a license key, a subscription, a trial period or usage quotas.

A voluntary PayPal donation option is displayed only on Hard Guard Security administration screens and in the plugin row. A donation does not unlock features, services, priority support or any other benefit.

## Community support

The free edition may receive installation guidance, basic configuration help, clarification of documented features and investigation of reproducible Hard Guard Security errors as the author's available time permits. No response time, service level or ongoing individual support is guaranteed.

Community support does not include custom development, website repair, malware removal, server administration, third-party plugin customization or emergency incident response. Support requests must never include passwords, recovery codes, API secrets or other confidential credentials.

## Project and author

**Author:** Andrzej Kupis  
**Downloads and releases:** https://github.com/endriu7777/WP-Hard-Guard/releases  
**Voluntary donation:** https://www.paypal.com/donate?hosted_button_id=PWTVTARRF9Q2A

wordpress.org: https://wordpress.org/plugins/hard-guard-security

Website: https://wp-hard-guard.ma7.eu/

## License

GNU General Public License v2 or later. See the plugin package for the complete license text and third-party notices.
