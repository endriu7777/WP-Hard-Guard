# WP-Hard-Guard-Security
WP Hard Guard – WordPress Security Hardening Plugin
<img width="1536" height="1024" alt="wp-hard-guard-website-baner" src="https://github.com/user-attachments/assets/dd49d241-8c31-43df-a1c7-5c64e5034e24" />

WordPress Security, 2FA, Malware Scanner & Audit Log

Overview:

Protect WordPress authentication, monitor security-relevant activity, manage two-factor authentication and Application  

Passwords, scan files, review permissions and integrity, control country access, harden common endpoints, diagnose  

SSL/HTTPS issues, and investigate suspicious changes from one comprehensive administration panel. 



Detailed feature description:



Protect, monitor and investigate your WordPress website 



Hard Guard Security is a free and open-source WordPress security and diagnostic plugin focused on authentication  

protection, activity monitoring, file analysis, system hardening and administrator-controlled recovery. 



It combines progressive login protection, two-factor authentication, an advanced Audit Log, Application Password  

controls, local malware scanning, WordPress Core integrity verification, a read-only file-permissions scan, antispam  

tools, country access rules, SSL diagnostics, browser-security headers, system tweaks, settings backup tools, privacy  

tools and Multisite support in one administration interface. 



All included functionality is available without payment, a license key, a subscription, a trial period or usage quotas. The  

plugin is designed to help website administrators reduce common WordPress security risks and investigate suspicious  

activity without automatically deleting files or sending website file contents to an external malware-scanning service. 



Free and open-source edition: 



Hard Guard Security 1.10.35 is prepared as a free repository edition. Every included feature is available to every user  

without payment, feature activation, a license key, a subscription, a trial period or a usage quota. 



A voluntary PayPal donation option is displayed only on Hard Guard Security administration screens and in the plugin row.  

A donation does not unlock features, services, priority support or any other benefit. 



Current release highlights: 



    Prepared the free WordPress.org submission edition and reduced repository documentation to the files required for distribution. 

   Added an optional PayPal donation panel that does not load PayPal scripts, images or tracking pixels before the administrator clicks the button. 

   Added WordPress personal-data exporter and eraser integration for locally stored plugin data. 

    Expanded external-service and privacy disclosures for country.is, Cloudflare Turnstile, WordPress.org checksum services, PayPal, 
      administrator-configured SMTP and diagnostics of the administrator’s own website. 

    Updated the English, Polish, German, Spanish, French and Italian translation catalogs for the free edition. 

   The plugin does not send telemetry, usage statistics, settings, scan results or personal data to its author. 



Authentication protection: 



Protect the WordPress login process with progressive lockouts, IP and username-based limits, trusted proxy detection,  

custom login URLs and configurable notifications. 



Features include: 



    Progressive login lockouts by IP address, username or a combined IP-address-and-username key. 

    Optional IP-wide counting to stop attackers bypassing limits by changing usernames. 

    IPv4 and IPv6 whitelist, blacklist and CIDR support. 

   Trusted proxy configuration; forwarded client-IP headers are ignored unless the direct proxy address is trusted. 

    Optional custom WordPress login URL with a five-minute safety test and automatic rollback. 

    Optional 404 response for direct wp-login.php access after the safety test succeeds. 

    Single-use emergency recovery URL and documented wp-config.php recovery constants. 

    Configurable login and lockout notifications with cooldown controls. 
  
     Cloudflare Turnstile for WordPress and WooCommerce login forms, including compatible custom forms using wp_signon(). 

     Duplicate-copy protection that stops a later-loaded copy from declaring duplicate constants, classes or hooks. 

  Two-factor authentication 



Add an additional authentication layer using email codes or RFC 6238-compatible TOTP applications such as Google  

Authenticator. 



Two-factor authentication features include: 



    Email verification codes and TOTP authenticator applications. 

    Local QR-code generation and a manual authenticator setup key; the TOTP secret is not sent to an external QR-code  

    service. 

   Ten single-use recovery codes. 

    Independent per-user 2FA configuration. 

   Administrator 2FA status overview and secure administrator reset. 

    Required-role policies with a configurable setup grace period. 

    Recovery-only fallback when a configured method becomes disabled or unavailable, preventing silent 2FA bypass. 

    Encrypted TOTP secret storage when Sodium or OpenSSL is available. 

    User-specific email 2FA messages follow the recipient’s selected interface or WordPress language. 

 Advanced Audit Log: 



Monitor security-relevant WordPress activity from a dedicated Audit Log workspace. The main dashboard also displays  

the 10 most recent Audit Log events. 


The Audit Log includes: 



   Overview dashboard, searchable and filterable events, and detailed event information. 

   Severity, category, action and result classifications. 

    User, role, session and administrator-privilege activity. 

    Plugin, theme and WordPress Core changes. 

    Post, page, supported custom post type and optional comment activity. 

   Selected WordPress and Hard Guard Security security-setting changes. 

   Alert rules with thresholds, grouping and cooldowns. 

   Severity-specific retention. 

    CSV and JSON export with optional IP masking. 

    Protection against spreadsheet-formula injection and secret/credential redaction. 

    Dedicated Audit Log capabilities and an aggregated WordPress Multisite network view. 

    Language-neutral plugin event messages that follow the current Hard Guard Security interface language when displayed. 

Application Password management: 



Control and monitor native WordPress Application Passwords used by REST API clients, integrations, scripts and  

external applications. 



Features include: 



   Global and role-based Application Password policies. 

    Central credential inventory with inactive-credential filtering. 

    Individual credential revocation and revocation of all credentials belonging to a selected user. 

   Optional inactivity cleanup. 

   Alerts for credential creation, revocation, first use, new-IP use and failed authentication. 

    Credentials blocked by policy remain stored but cannot authenticate until the policy allows them again. 

    Plaintext Application Password values and password hashes are never stored in Hard Guard Security logs, emails or exports. 

Malware scanner: 



Inspect WordPress files for selected patterns and file structures associated with malicious or suspicious code. Scanner  

findings are diagnostic and require administrator review. 



Scanner features include: 



   Quick Scan and Full Scan modes. 

    Live 0-100% progress, current stage, checked-file count, findings count and the path currently being analysed. 

    Batched AJAX processing with stop and resume controls. 

   Scan history, per-scan result cleanup and one-click clearing of results/history while preserving quarantine and exact- 

     hash ignore decisions. 

   JSON report export with translated known finding reasons. 

    Dangerous execution-chain and request-controlled execution detection. 

    Hidden PHP inside static or media files, executable files inside uploads and double-extension detection. 

    Unexpected executable additions to WordPress Core directories. 
 
    Exact SHA-256 ignore rules. 

   Administrator-password-protected quarantine and restoration. 

    Optional high- and critical-severity notifications. 

Files are analysed locally. Website file contents are not sent to an external malware-scanning service, and the plugin  

does not include ClamAV integration. Hard Guard Security never automatically deletes suspicious files. 

WordPress file integrity: 



Compare security-relevant WordPress root, wp-admin and wp-includes files with official checksum data for the installed  

WordPress version and locale. 



File-integrity tools can identify: 



    Modified or missing WordPress Core files. 

    Unexpected files directly in the WordPress root, wp-admin and wp-includes. 

    Executable PHP-like files inside uploads. 

    Persistent first-detected timestamps for unresolved findings. 

The Core integrity check intentionally excludes bundled themes, plugins, language packs, common configuration files  

and optional WordPress documentation files to reduce false alarms. Symbolic links are reported separately and the  

integrity check is read-only. 



The check sends only the installed WordPress version and locale to WordPress.org to retrieve official checksum data.  

Website files and their contents are not sent to WordPress.org. 

Read-only file permissions scan: 



Review important WordPress paths and recursively inspect Core, plugin and theme directories without changing chmod  

values. 



   World-writable paths are reported as Critical. 

    Group-writable paths, executable regular files, symbolic links and broadly readable wp-config.php configurations are  

     reported as warnings. 

    Results include localized status, item type and explanation text. 

    Safe permission values remain dependent on server ownership, group membership, PHP handler and deployment model. 

 Antispam protection: 



Protect native WordPress comments, WooCommerce reviews that use the WordPress comment system, and native  

WordPress registration. 



Antispam features include: 



    Honeypot fields, signed timing tokens and JavaScript confirmation. 

    Submission rate limits and link limits. 

    Phrase and safe wildcard rules, plus email-domain rules. 

    Local reputation data and local heuristic language filtering. 

    Configurable moderation, spam and rejection thresholds. 

    Quarantine reasons, false-positive handling, statistics and retention controls. 

    Digest emails and spam-outbreak alerts. 

    Optional country filtering through the country.is API, including risk-score mode, strict allowlist/blocklist policies and  

     configurable handling when the country cannot be determined. 

    Separate direct actions for detected languages outside the allowlist and for unknown language. 

Strict country and language decisions cannot be weakened by trusted-email score reductions or custom score  

thresholds. Comment and registration content is analysed locally and is not sent to an external antispam service. 

GeoIP country access: 



Configure site-wide country access for requests processed by WordPress, including public pages, login, administration  

and API endpoints. 



Available policies and controls include: 



    Country blocklist and country allowlist policies using ISO 3166-1 alpha-2 country codes. 

    Country detection exclusively through the country.is IP-to-country API. 

    Successful results cached for 24 hours and failed lookups cached for 10 minutes. 

   Test country detection action before enabling a policy. 

    IP and CIDR recovery exceptions, plus administrator, WP-Cron and WP-CLI bypasses. 

    Custom HTTP 403 page title, message and optional contact/help link. 

    Fail-open site-wide handling when a country cannot be determined. 

    Emergency wp-config.php bypass. 

Cloudflare country headers, server GeoIP variables and local GeoIP databases are not used. The resolved visitor IP  

address is sent to country.is only when an enabled country rule needs a lookup. 

SSL and HTTPS diagnostics 



Review selected SSL, HTTPS and browser-security settings from a dedicated administration page. 



Tools include: 



    PHP-based HTTPS redirects and managed Apache-compatible .htaccess redirects. 

   Quick database mixed-content scan and deep front-end mixed-content scan. 

   Same-host mixed-content repair. 

   SSL certificate health checks and live security-header scans. 

    HSTS configuration. 

   Content Security Policy upgrade-insecure-requests. 

    Permissions-Policy controls for camera, microphone, geolocation and payment features. 

    MIME-sniffing protection, Referrer-Policy and frame protection. 

   X-Powered-By removal. 

   Apache and Nginx configuration examples. 

SSL certificate and security-header diagnostics perform HTTP or TLS requests to the administrator’s own website. 

System hardening and data hiding: 



Reduce exposure of selected common WordPress endpoints and sensitive paths. High-risk options should be enabled  

one at a time and tested on a staging website. 



Available controls include: 



    Block XML-RPC access. 

    Hide the anonymous REST Users API. 

    Block public author enumeration and remove the native WordPress user sitemap. 

    Protect selected sensitive files and disable directory indexes. 

    Block direct PHP requests in uploads, with optional blocking in plugin and theme directories. 

    Disable the built-in plugin and theme file editor. 

   Suppress public PHP and startup-error display after WordPress loads without disabling error logging. 

    Hide selected WordPress generator and discovery links. 

   Optionally remove asset version query strings from public CSS and JavaScript URLs. 

    Managed Apache-compatible .htaccess rules with an HTTP 5xx loopback safety check and automatic rollback. 

   Generated Nginx configuration examples for manual review and installation. 

Settings export and import: 



    Export creates a JSON file containing the plugin configuration and package version. 

   Turnstile Secret keys and SMTP passwords are blanked before export; user authenticator secrets and recovery  

    codes are not included. 

    Import validates supported settings before saving and preserves the existing configuration when validation fails. 

    For safety, import preserves destination-site secrets, disables direct wp-login.php blocking and does not activate server-level System Tweaks automatically. 


Notifications and SMTP: 



Send security alerts using the standard WordPress mail system or SMTP settings dedicated to Hard Guard Security. 



Notifications can cover: 



    Login lockouts, blacklist blocks and failed login attempts. 

   Administrator logins. 

   2FA failures and recovery-code use. 

   Application Password activity. 

    Malware scanner findings. 

   Audit Log alert rules. 

   Antispam digests and outbreak alerts. 

A global email language can be selected for security notifications, Scanner findings, Antispam reports, Audit Log alerts  

and test messages. SMTP sender address/name settings and a test message are available. SMTP settings affect only  

messages sent by Hard Guard Security and do not replace email delivery for the entire WordPress website. SMTP  

passwords are encrypted when Sodium or OpenSSL is available. 

Privacy-conscious operation: 



Hard Guard Security is primarily designed to operate locally and does not send telemetry, usage statistics, settings, scan  

results or personal data to the plugin author. 

External connections are limited to features that require them: 



   WordPress Core and supported WordPress.org plugin integrity checks retrieve official checksum information from WordPress.org. 

   SSL, redirect, mixed-content and security-header diagnostics connect only to the administrator’s own website. 

   Site-wide GeoIP access and Antispam country rules send the resolved visitor IP address to country.is when a country lookup is required. 

    Cloudflare Turnstile communicates with Cloudflare only after an administrator explicitly enables and configures the  

    feature. 

   SMTP communication occurs only after an administrator configures the SMTP service. 

    PayPal is contacted only after an administrator clicks the voluntary donation button; no PayPal scripts, images or tracking pixels load when a Hard Guard Security page is opened. 

Successful country lookups are cached for 24 hours and failures for 10 minutes. Comment, registration and scanned-file  

contents are not included in country lookups. The plugin includes suggested privacy-policy information describing stored  

security data and optional external services. 



WordPress personal-data export and erasure callbacks are registered under Tools. Erasure removes user-specific plugin  

metadata and matching Antispam and lockout records. Matching Audit Log events are anonymized so non-personal  

security metadata can be retained. 

WordPress Multisite: 



Hard Guard Security supports WordPress Multisite. Authentication settings, plugin tables and data are maintained per site,  

while shared filesystem and server-level hardening settings are available only from the main site to an authorised  

network administrator. The Audit Log can provide an aggregated network view across up to 100 sites. 

Language support: 



The complete administration interface, Help content, security messages, email content and Scanner finding descriptions  

include: 



    English. 

    Polish. 

    German. 

   Spanish. 

    French. 

    Italian. 

Each administrator can use the WordPress dashboard language or independently force one of the bundled languages for  

the Hard Guard Security interface without changing the website language or another administrator’s settings. 

Plugin uninstallation and data cleanup: 



Deactivation keeps settings and stored data but clears the daily plugin cron hook and removes managed server rules  

where the configuration file is writable. 



When the explicit permanent cleanup option is enabled, uninstall permanently removes all Hard Guard Security options,  

transients, user metadata including 2FA data, network metadata, all eight plugin database tables, logs, scan records and  

safely validated Scanner quarantine files. In Multisite, the main-site preference is applied across the network. Empty  

standard quarantine directories and plugin-created protection files are also removed where safe. 



Important limitations: 



Hard Guard Security reduces selected security risks, but does not guarantee complete protection against all attacks,  

vulnerabilities, configuration errors, compatibility problems or data loss. 



The malware scanner and integrity tools are diagnostic. A detected file is not necessarily malicious, and a file that is not  

detected is not necessarily safe. False positives and false negatives are possible. 



Hard Guard Security is not a replacement for: 



    Regular, tested backups. 

   WordPress, plugin and theme updates. 

   Secure hosting and server configuration. 

   A web application firewall. 

   Server monitoring. 

    Malware removal performed by a security specialist. 

    Professional incident response. 

   An independent security audit. 

Before changing login URLs, access rules, HTTPS settings, file permissions, quarantine state or hardening options,  

create a complete backup and test the configuration in a staging environment. 



Some server-level options require Apache or LiteSpeed. For Nginx, the plugin provides configuration examples that must  

be reviewed and installed manually by a server administrator. GeoIP and Antispam country functionality require outbound  

HTTPS access to country.is. Cloudflare Turnstile requires administrator-provided Cloudflare site and secret keys. Email- 

based 2FA and security notifications require working WordPress email delivery or properly configured SMTP. 

Requirements:

   Tested up to WordPress 7.0. 

   PHP 7.4 or newer. 

   JavaScript enabled in the browser for interactive administration tools and selected antispam checks. 

   HTTPS strongly recommended. 

   Apache, LiteSpeed or Nginx web server. 

   Nginx server-level rules require manual configuration. 

   PHP read access to WordPress files for scanning; filesystem write access is required for quarantine and managed  

    server-rule features. 

   Sodium or OpenSSL recommended for encrypted secret storage. 

   Outbound HTTPS access is required for WordPress.org checksums and country.is lookups when the corresponding features are used. 

Installation and initial setup: 



   Install the Hard Guard Security ZIP from Plugins > Add New > Upload Plugin, or install it from WordPress.org after the plugin has been accepted and      published. 

   Open Hard Guard Security > Settings and choose either the WordPress dashboard language or one of the bundled interface languages for the current administrator. 

   Select the global email language for background alerts and reports; user-specific 2FA codes follow the recipient language. 

   Configure trusted proxies before relying on forwarded client-IP headers, test email delivery before enabling email 2FA, and store recovery codes         outside WordPress. 

   Create a complete backup and test high-risk changes on a staging website whenever possible. 

Emergency recovery: 



The plugin provides a single-use emergency recovery URL and temporary wp-config.php constants for restoring direct  

wp-login.php access, bypassing Hard Guard Security 2FA, disabling the plugin HTTPS redirect, or disabling login rate  

limiting and active lockouts. A recovery constant should be removed immediately after access is restored and the  

underlying configuration is corrected. 



Community support scope: 



The free edition may receive installation guidance, basic configuration help, clarification of documented features, and  

investigation of reproducible Hard Guard Security errors as the author’s available time permits. No response time, service  

level or ongoing individual support is guaranteed. 



Community support does not include custom development, website repair, malware removal, server administration, third- 

party plugin customization or emergency incident response. Support requests must never include passwords, recovery  

codes, API secrets or other confidential credentials. 

Included files:



   Installable WordPress plugin directory and ZIP package. 

   WordPress.org readme.txt with installation, privacy, external-service and frequently asked questions sections. 

   changelog.txt containing the historical release notes. 

   English, Polish, German, Spanish, French and Italian administration interface resources. 

   GNU GPL v2-or-later license text. 

   Third-party library notices and the applicable MIT and Apache 2.0 license information for the included local QR-code component. 



Project and author: 

Author: Andrzej Kupis 

Download: https://github.com/endriu7777/WP-Hard-Guard/releases

Voluntary donation: https://www.paypal.com/donate?hosted_button_id=PWTVTARRF9Q2A 
