# Navis Protocol: Dual-Guard Architecture & Security Specification

## 1. Overview
Navis Protocol is built on a scalable macro-architecture designed to serve both amateur and advanced users securely and efficiently. To balance accessibility with absolute sovereignty, Navis implements the **Navis Dual-Guard Architecture™**.

## 2. Dual-Mode Authentication & Security
- **Absolute Control (Native Self-Custody):** 
  - Designed for Web3-native and advanced users.
  - Direct wallet connection via cryptographic message signing (`Sign Message`).
  - Private keys remain exclusively on the user's device with zero server-side exposure.
- **Safe Recovery (Protected Blind Vault):** 
  - Designed for mainstream/amateur users utilizing seamless social or email onboarding.
  - Implements a client-side **3-share Shamir's Secret Sharing (SSS)** model:
    1. *Browser Active Share:* Stored locally in IndexedDB, secured via Passkey/derived PIN.
    2. *Server Blind Vault:* Stored as an encrypted, blind string in the cloud database (server lacks complete keys).
    3. *Recovery Share:* An encrypted backup file held exclusively by the user.

## 3. Modular Engineering Principles
All cryptographic operations (Web Crypto API, key derivation, and share management) are isolated within client-side modules to ensure a strict non-custodial guarantee, even when hosted on scalable cloud infrastructures like Google Cloud Platform (GCP).
