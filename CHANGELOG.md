# Changelog

All notable changes to `Muon_MultiFactorLogin` will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.1.0] - 2026-11-13

### Changed

- The PHP constraint is pinned to the tested range, 8.3 to 8.5 (`~8.3.0 || ~8.4.0 || ~8.5.0`),
  instead of the open `~8.3`. Tested on PHP 8.5 with Magento 2.4.9. No code changes.
- The changelog had two `[1.0.0]` headings; they are merged into one, dated at the `v1.0.0` tag.

## [1.0.0] - 2026-04-07

### Added
- Two-factor authentication for Magento 2 customer login
- Token delivery via SMS (Twilio) and/or email, configurable per store
- Configurable token length, character set, and lifetime
- Rate limiting on token requests (rolling window, configurable)
- Rate limiting on verification attempts per token
- One-time-use tokens encrypted at rest via `EncryptorInterface`
- Admin configuration under Stores → Configuration → Muon → Multi-Factor Login
- Configurable email template via Marketing → Email Templates
- Nightly cron cleanup of expired tokens
- Guard on all MFA controllers against direct URL access without pending session state
- Active tokens invalidated before a new one is issued
