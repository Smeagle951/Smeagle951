<div align="center">

<br/>

<img src="https://img.shields.io/badge/FORT-SMART-1a6b3c?style=for-the-badge&labelColor=0d3320&logo=leaf&logoColor=4ade80" height="42" alt="FortSmart"/>

<br/><br/>

# Precision Agriculture Intelligence Platform

**Structured agronomic intelligence from field data.**

<br/>

[![Build](https://img.shields.io/github/actions/workflow/status/fortsmart/app/ci.yml?branch=main&style=flat-square&label=build&color=22c55e)](https://github.com/fortsmart/app/actions)
[![Version](https://img.shields.io/badge/version-1.0.0-3b82f6?style=flat-square)](https://github.com/fortsmart/app/releases)
[![License](https://img.shields.io/badge/license-MIT-8b5cf6?style=flat-square)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-iOS%20%7C%20Android-f97316?style=flat-square)](https://fortsmart.app)
[![Status](https://img.shields.io/badge/status-active-10b981?style=flat-square)](https://github.com/fortsmart/app)
[![Flutter](https://img.shields.io/badge/built%20with-Flutter-54c5f8?style=flat-square&logo=flutter&logoColor=white)](https://flutter.dev)

<br/>

> **Offline-first. Data-driven. Field-ready.**

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #4ade80, transparent);" />

<img src="https://placehold.co/900x420/0d3320/4ade80?text=FortSmart+Platform+Dashboard&font=montserrat" width="860" alt="FortSmart Dashboard"/>

<br/><br/>

</div>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #4ade80, transparent);" />

<br/>

## 🌿 What is FortSmart?

**FortSmart** is a precision agriculture intelligence platform designed to support agronomic decision-making across the entire crop lifecycle.

It enables field technicians, agronomists, and producers to collect, structure, and interpret field data with high reliability — regardless of connectivity conditions.

Rather than operating as a simple field application, FortSmart functions as a **decision-support platform**: transforming raw observations into consistent, traceable, and actionable agronomic intelligence.

The platform is built to operate under real-world agricultural constraints — intermittent connectivity, large-scale operations, multi-crop environments, and increasing regulatory demands.

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #22c55e, transparent);" />

<br/>

## 🎬 Platform Preview

<div align="center">

| Field Map | Agronomic Reports | Stage Monitoring |
|:---------:|:-----------------:|:----------------:|
| <img src="https://placehold.co/260x180/0d3320/4ade80?text=Field+Map&font=montserrat" width="260" alt="Field Map"/> | <img src="https://placehold.co/260x180/0a2540/60a5fa?text=Reports&font=montserrat" width="260" alt="Reports"/> | <img src="https://placehold.co/260x180/1e1b4b/a78bfa?text=Phenology&font=montserrat" width="260" alt="Phenology"/> |

</div>

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #22c55e, transparent);" />

<br/>

## ⚡ Core Capabilities

### 🗺️ Spatial Intelligence
- **Plot-level management** — complete geospatial control at the talhão level
- **Interactive field mapping** — draw, edit, and navigate plots with precision
- **GPS-based georeferencing** — every record anchored to verified coordinates

### 📊 Agronomic Analytics
- **Structured agronomic reports** — consistent, professional, auto-generated documentation
- **Phenological stage tracking** — crop development monitoring from planting through harvest
- **Historical data analysis** — season-over-season comparison and trend identification

### 📡 Operational Reliability
- **Complete offline operation** — fully functional without network access
- **Intelligent sync engine** — automatic conflict resolution upon reconnection
- **Local-first database** — SQLite as operational ground truth; Supabase as cloud layer

### 🔗 Data & Integration
- **Field data structuring** — standardized input from scouting, sampling, and field observations
- **Role-based collaboration** — team access with granular permission control
- **Structured exports** — report delivery in PDF, JSON, and structured formats

### 🔐 Compliance & Security
- **Encrypted local storage** — data protected at rest on the device
- **Full audit trail** — complete activity log per operation and user
- **LGPD-aligned** — designed in accordance with Brazilian data regulation standards

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #22c55e, transparent);" />

<br/>

## 🏆 Why FortSmart?

FortSmart is engineered for environments where traditional software fails — remote fields, unstable networks, and operational complexity at scale.

It prioritizes **data integrity**, **spatial accuracy**, and **decision reliability** over superficial feature sets.

<br/>

| Differentiator | Description |
|----------------|-------------|
| 🤖 **Agronomic AI Layer** *(roadmap)* | Predictive recommendations derived from historical field data and crop behavior models |
| 📶 **Offline-First Architecture** | Designed ground-up for zero-connectivity environments — not adapted as an afterthought |
| 🧱 **Enterprise-Grade Data Model** | Relational schema that scales from 10 to 10,000 plots without structural compromise |
| 🌍 **Geospatial Precision** | Spatial data management with PostGIS and native GeoJSON standards throughout |
| 📱 **Unified Cross-Platform** | Single codebase. Identical, native-grade experience on iOS and Android |
| ⚡ **Conflict-Safe Sync** | Vector-based diffing ensures no silent data overwrites — ever |

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #22c55e, transparent);" />

<br/>

## 🏗️ System Architecture

FortSmart is built around a distributed, offline-first architecture that ensures uninterrupted field operation while maintaining full consistency with cloud systems upon reconnection.

```
┌─────────────────────────────────────────────────────────────────┐
│                      FortSmart Platform                          │
├────────────────┬─────────────────────┬──────────────────────────┤
│   Client App   │     API Layer       │      Data Layer           │
│                │                     │                           │
│  Flutter       │  Node.js            │  Supabase (Cloud)         │
│  Dart          │  Express / Fastify  │  PostgreSQL + PostGIS     │
│  Riverpod      │  JWT Auth           │  SQLite (Local)           │
│  go_router     │  WebSockets         │  Offline Sync Engine      │
└────────────────┴─────────────────────┴──────────────────────────┘
```

<br/>

**Offline-First** — The client treats local SQLite as the primary operational database. All writes are local-first. Sync executes in the background when connectivity is restored, never interrupting user workflow.

**Modular Domain Structure** — Each business domain (plots, reports, monitoring, users) is fully encapsulated with its own data layer, business logic, and interface. Independent development, testing, and deployment per module.

**Conflict-Safe Sync Engine** — Timestamp and vector-based diffing determines source of truth on every sync cycle. Conflicts surface explicitly — no silent overwrites, no data loss.

**Geospatial Core** — Spatial data stored in GeoJSON, processed server-side with PostGIS, rendered client-side via native map engines. All spatial operations maintain geometric integrity end-to-end.

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #22c55e, transparent);" />

<br/>

## 🗺️ Roadmap

### ✅ Phase 1 — Foundation *(Current)*
- [x] Flutter project with clean architecture and domain separation
- [x] SQLite local database with full relational schema
- [x] Offline-first sync engine with conflict resolution
- [x] Authentication via JWT + Supabase Auth
- [x] Plot (talhão) management with geospatial support
- [x] Agronomic report generation — base version

### 🔄 Phase 2 — Intelligence *(In Progress)*
- [ ] Advanced phenological stage tracking per crop and region
- [ ] Multi-season historical data comparison
- [ ] PDF export engine for agronomic reports
- [ ] Push notifications and field alerts
- [ ] Team collaboration with granular permission layers

### 🔭 Phase 3 — AI & Expansion *(Planned)*
- [ ] Agronomic AI recommendation engine
- [ ] Predictive yield modeling per plot
- [ ] Satellite imagery integration with NDVI analysis
- [ ] Weather data overlay correlated by plot
- [ ] API layer for third-party agronomic system integrations

### 🌐 Phase 4 — Platform Scale *(Vision)*
- [ ] Web dashboard for back-office and management teams
- [ ] Multi-tenant SaaS architecture with white-label support
- [ ] Regulatory compliance module — CAR, e-DAA
- [ ] Agronomic data marketplace

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #22c55e, transparent);" />

<br/>

## 🚀 Getting Started

### Prerequisites

```bash
flutter --version    # ≥ 3.19.0
dart --version       # ≥ 3.3.0
node --version       # ≥ 20.0.0
```

### Installation

```bash
# Clone the repository
git clone https://github.com/fortsmart/app.git
cd app

# Install client dependencies
flutter pub get

# Configure environment
cp .env.example .env

# Install and initialize backend
cd backend && npm install && npm run migrate

# Start API server
npm run dev

# Launch the platform client
cd ../app && flutter run
```

### Environment Configuration

```env
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_ANON_KEY=your-anon-key
API_BASE_URL=http://localhost:3000
MAPS_API_KEY=your-maps-api-key
```

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #22c55e, transparent);" />

<br/>

## 📖 Operational Flow

```
Onboarding       →  Account creation → Farm registration → Team setup

Plot Setup       →  Boundary mapping → Crop assignment → Cycle configuration

Field Operation  →  Open plot → Record observation → Attach media → Save locally

Reporting        →  Generate report → Review data → Export or share

Synchronization  →  Connectivity restored → Auto-sync → Cloud updated
```

<br/>

| Term | Definition |
|------|------------|
| **Talhão** | Individual field plot — the primary unit of all agronomic records |
| **Ciclo** | Crop cycle — binds all records to a defined planting season |
| **Estágio Fenológico** | Crop growth stage used to contextualize field observations |
| **Sync Queue** | Local buffer of pending writes processed upon connectivity restoration |

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #22c55e, transparent);" />

<br/>

## 🤝 Contributing

Contributions are welcome from developers and agronomic professionals.

All contributions must follow established architectural and code quality standards to ensure system consistency and long-term maintainability.

```bash
# Create a feature branch
git checkout -b feature/your-feature-name

# Commit following Conventional Commits specification
git commit -m "feat: add phenological stage selector"

# Open a Pull Request with clear description of scope and motivation
git push origin feature/your-feature-name
```

For architectural changes or new modules, open an issue before implementation to align on design decisions.

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #22c55e, transparent);" />

<br/>

## 📄 License

Distributed under the MIT License. See [LICENSE](LICENSE) for full terms.

<br/>

<hr style="border: none; height: 1px; background: linear-gradient(to right, transparent, #4ade80, transparent);" />

<br/>

<div align="center">

<img src="https://img.shields.io/badge/FORT-SMART-1a6b3c?style=for-the-badge&labelColor=0d3320&logo=leaf&logoColor=4ade80" height="36" alt="FortSmart"/>

<br/><br/>

**FortSmart Platform**

Precision agriculture infrastructure built for reliability, scalability, and real-world field conditions.

<br/>

[![Website](https://img.shields.io/badge/fortsmart.app-visit-10b981?style=flat-square)](https://fortsmart.app)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-FortSmart-0077b5?style=flat-square&logo=linkedin)](https://linkedin.com/company/fortsmart)
[![Contact](https://img.shields.io/badge/hello@fortsmart.app-8b5cf6?style=flat-square)](mailto:hello@fortsmart.app)

<br/>

*© 2025 FortSmart · Precision agriculture infrastructure.*

<br/>

</div>
