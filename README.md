# AndroidArmour

![SIH2024](https://img.shields.io/badge/Smart%20India%20Hackathon-2024-blue) ![Status](https://img.shields.io/badge/Status-Prototype-yellow)

**One-line summary**

AndroidArmour — a cloud-assisted, AI-enabled Runtime Application Self‑Protection (RASP) and security-integration platform that adds robust, crash-proof security layers to Android apps (API level 34 / Android 14+) via (a) developer libraries, (b) automated source-level instrumentation, and (c) APK-level automated hardening.


### Links

You can view the full SIH2024 presentation, videos and libraries here:

- [PPT Link](https://www.canva.com/design/DAGQ46cw3EA/W2GJRDT-B1tdrIfp8CzfGg/view?utm_content=DAGQ46cw3EA&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=he5e2789626)

- Videos : [Demo](https://www.youtube.com/watch?v=U6lXrkNMoNs), [Intro](https://www.youtube.com/watch?v=7oMJ0Kxa58k0)

- Libraries (GitHub) : [Android_Security_Library](https://github.com/akashmeruva9/Android_Security_Library), [Android_FIntech_Security_library](https://github.com/akashmeruva9/Android_FIntech_Security_library), [Android_Social_Media_Security_Librar](https://github.com/akashmeruva9/Android_Social_Media_Security_Librar), [Android_Ecommerce_Security_Library](https://github.com/akashmeruva9/Android_Ecommerce_Security_Library), [Android_Streaming_Security_Library](https://github.com/akashmeruva9/Android_Streaming_Security_Library), [Android_Gaming_Security_Library](https://github.com/akashmeruva9/Android_Gaming_Security_Library).

## Table of Contents

* [Problem Statement](#problem-statement)
* [Motivation & Impact](#motivation--impact)
* [Proposed Solution](#proposed-solution)
* [Key Features](#key-features)
* [Target Users](#target-users)
* [Technology Stack](#technology-stack)
* [System Architecture](#system-architecture)
* [Data & Privacy](#data--privacy)
* [Implementation Plan & Timeline](#implementation-plan--timeline)
* [Evaluation & Success Metrics](#evaluation--success-metrics)
* [Demo & Artifacts](#demo--artifacts)
* [How to Run (Prototype)](#how-to-run-prototype)
* [Contributing](#contributing)
* [Team](#team)
* [References](#references)
* [License](#license)
* [Contact](#contact)

## Problem Statement : [SIH 2024 - PS 1747](https://www.sih.gov.in/sih2024PS?technology_bucket=QWxs&category=U29mdHdhcmU=&organization=QWxs&organization_type=QWxs)

Many Android applications (especially social, gaming, fintech, streaming, and e‑commerce apps) lack adequate runtime protection and are vulnerable to reverse engineering, tampering, cheating, rooting, memory-dumps, and in-app fraud. Existing protection workflows are often manual, brittle, or require source-code access. The Smart India Hackathon problem (PS ID SIH‑1747) asks for improved Android application security for Android 14+; AndroidArmour answers this need by providing flexible integration paths and runtime protections.

## Motivation & Impact

* Protects sensitive user data across high-impact sectors (fintech, healthcare, e‑commerce).
* Reduces breach risk and regulatory exposure; improves user trust and app retention.
* Enables smaller developer teams to adopt enterprise-grade protections via automation.
* Future-proofs apps to meet Android 14+ requirements and upcoming data-protection regulations.

## Proposed Solution

AndroidArmour provides three integration modes for a target application:

1. **Developer Library (recommended)** — drop-in Kotlin/Java libraries (MVVM-safe, crash‑proof) with APIs for integrity checks, anti‑debug, anti‑memory-dump, rooting detection, biometric transaction protection, DRM hooks and encryption.

2. **Source-level automated instrumentation** — AI-assisted code modification of project sources to insert secure APIs and hardening code paths (uses GitHub-hosted project files, Codex/ChatGPT‑style code generation, and deterministic unit tests).

3. **APK-level automated hardening** — decompile (JADX/apktool), automated secure patching (insertion of protection hooks), recompile, and sign — with safeguards to preserve app functionality and to avoid crashes. Built-in static & dynamic checks (MobSF, QARK) verify changes.

## Key Features

* Anti‑debugging & anti‑decompilation protections
* Integrity protection (hash validation, tamper detection)
* Anti‑memory dump & memory access detection
* Root / emulator / cheat tool detection
* In‑app purchase anti‑cheat and DRM/content access controls
* Biometric + transaction encryption for fintech flows
* Crash‑proof library design (MVVM architecture)
* Cloud‑based pipeline for decompilation, patching, build and distribution
* Scalable real‑time threat analytics dashboard

(Features & target app categories documented in the original slides.)

## Target Users

* App developers and engineering teams (startups → enterprise)
* Security engineers and SDET teams
* App marketplaces and enterprise mobility teams
* Organizations needing compliance (PCI‑DSS, data protection laws)

## Technology Stack

**Frontend:** Next.js / React (admin console + dashboard)

**Mobile:** Android (library targets: API 34+, Kotlin/Java)

**Backend:** Node.js / Express (automation workers, API)

**Decompilation & Analysis:** JADX, apktool, MobSF, QARK

**AI Assist / Codegen:** OpenAI GPT family (Codex/ChatGPT), custom heuristics

**Cloud / CI:** AWS (Amplify for web, S3 for artifact storage), GitHub (repo & releases), Docker

**Monitoring & Analytics:** Elastic/Prometheus/Grafana or cloud equivalents

These choices and tool integrations are taken from the presentation's technical approach slide.

## System Architecture

1. User uploads project or APK via the web UI.
2. Backend validates and stores artifact (S3/GitHub) and spins an isolated worker.
3. Worker runs static analysis (MobSF/QARK) and -- depending on chosen flow -- either: a) injects library code into source, b) applies AST-level source transforms, or c) decompiles APK, patches smali/java, and rebuilds.
4. Post‑processing runs unit/smoke tests and dynamic checks; if safe, the new artifact is produced and delivered to the user.
5. RASP components in the delivered library communicate (optionally) to the cloud analytics engine for threat telemetry.



<table style="border: 1px solid black;">
            <tr>
                <td  style="border: 1px solid black ;">
                    <img src="https://github.com/user-attachments/assets/514e1535-44f4-495a-ba5b-3dc6ede8ca34"   width="1920">
                </td>
            </tr>
</table>

<table style="border: 1px solid black;">
            <tr>
                <td  style="border: 1px solid black ;">
                    <img src="https://github.com/user-attachments/assets/a97e511e-88b5-413d-b26a-62686d6345cf"   width="1920">
                </td>
            </tr>
</table>
