# Sentinel: The Smart Contract "Watchdog"

[![License: MIT](https://img.shields.io/badge/License-MIT-red.svg)](https://opensource.org/licenses/MIT)
[![Ecosystem: Stellar/EVM](https://img.shields.io/badge/Ecosystem-Stellar%20%7C%20EVM-purple.svg)](https://stellar.org)
[![Security: Real--Time](https://img.shields.io/badge/Security-Real--Time%20Monitoring-orange.svg)](#)

**Sentinel** is an open-source, lightweight mempool monitoring bot designed to provide an "Early Warning System" for smart contract protocols. By detecting suspicious activities before they are finalized on-chain, Sentinel gives developers and stakeholders the critical seconds needed to react to potential threats.

---

### 1. Executive Summary
Security audits are essential, but they only capture a single moment in time. Sentinel provides **Continuous Operational Security** by listening to unconfirmed transactions in the mempool. It identifies "danger" signatures—such as unauthorized ownership changes, large liquidity removals, or malicious contract upgrades—and immediately alerts your team via Discord, Telegram, or custom Webhooks.

### 2. The Problem
Most security incidents are only discovered *after* the hack is finalized on-chain, at which point the funds are usually gone. 
* **The Monitoring Gap:** Enterprise-grade monitoring is often too expensive for smaller teams or independent developers.
* **The "Finality" Trap:** On-chain alerts are "too little, too late." Reactive security fails against modern, high-speed exploits.
* **Mempool Blindness:** Developers often lack visibility into pending transactions that could signal a front-running attack or a rug-pull attempt.

### 3. Key Features
* **🕵️ Mempool Signature Scanning:** Detects unconfirmed transactions matching specific malicious patterns (e.g., `renounceOwnership` or `drainLiquidity`).
* **⚡ Instant Multi-Channel Alerts:** Real-time notifications sent to Discord, Telegram, or PagerDuty within milliseconds of detection.
* **🌌 Hybrid Ecosystem Support:** Native monitoring for both **Stellar (Soroban)** and **EVM-compatible** networks.
* **🛡️ "Circuit Breaker" Hooks:** Programmatic webhooks that can trigger an "Emergency Pause" on your contracts if a critical threat is detected.

### 4. Roadmap for this Wave
* **Phase 1:** Core Mempool Listener for Stellar/Soroban and Ethereum Mainnet.
* **Phase 2:** Launch the Sentinel Dashboard for easy "No-Code" alert configuration.
* **Phase 3:** Implement "Simulation Mode" to predict the impact of a pending transaction before it lands.

### 5. Why Sentinel belongs in Drips Wave
Sentinel brings **enterprise-grade security** to the public good. 
* **Public Good:** We ensure that every protocol, regardless of budget, has access to real-time defense tools.
* **Sustainability:** We utilize Drips to share 15% of our funding with the core node providers and infrastructure libraries (like `ethers.js` and `stellar-sdk`) that keep our watchdog running.

---

## 🛠 Project Structure (Monorepo)

```text
Sentinel/
├── apps/
│   ├── bot/           # The core monitoring service (Node.js/Rust)
│   └── dashboard/     # Frontend for managing alert rules
├── libs/
│   ├── scanners/      # Logic for detecting "Danger Signatures"
│   └── notify/        # Integration for Discord, Telegram, and Webhooks
├── packages/
│   └── shared-utils/  # Common logic for Stellar and EVM parsing
└── LICENSE            # MIT Licensed


Sentinel/
├── .github/
│   ├── ISSUE_TEMPLATE/ # Templates for Bug Reports and Features
│   └── workflows/      # CI/CD for testing
├── apps/
│   ├── bot/           # Core monitoring service
│   └── dashboard/     # Frontend rule manager
├── libs/
│   ├── scanners/      # "Danger Signature" detection logic
│   └── notify/        # Discord/Telegram/Webhook providers
├── docs/
│   └── architecture.md # Deep dive into how Sentinel works
├── CONTRIBUTING.md     # Guidelines for contributors
├── SECURITY.md         # Vulnerability reporting process
├── LICENSE             # MIT License
└── README.md           # You are here!
