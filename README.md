<div align="center">

<img src="https://raw.githubusercontent.com/agstack/inatrace/main/.github/inatrace-logo.png" alt="INATrace" width="200" onerror="this.style.display='none'"/>

# INATrace

### Open-Source Blockchain-Based Track & Trace for Agricultural Supply Chains

[![Backend](https://img.shields.io/badge/Backend-Java_17-orange?style=for-the-badge&logo=openjdk)](https://github.com/agstack/inatrace-backend)
[![Frontend](https://img.shields.io/badge/Frontend-Angular-red?style=for-the-badge&logo=angular)](https://github.com/agstack/inatrace-frontend)
[![Mobile](https://img.shields.io/badge/Mobile-React_Native-blue?style=for-the-badge&logo=react)](https://github.com/agstack/inatrace-mobile)
[![Blockchain](https://img.shields.io/badge/Blockchain-Hyperledger_Fabric-2F3134?style=for-the-badge&logo=hyperledger)](https://github.com/agstack/inatrace-coffee-network)

[![Google Play](https://img.shields.io/badge/Google_Play-Download-green?style=flat-square&logo=google-play)](https://play.google.com/store/apps/details?hl=en-US&id=com.sunesis.inatrace)
[![App Store](https://img.shields.io/badge/App_Store-Download-blue?style=flat-square&logo=apple)](https://apps.apple.com/us/app/inatrace/id6572305162)
[![License: MPL-2.0](https://img.shields.io/badge/License-MPL_2.0-brightgreen?style=flat-square)](LICENSE)
[![Part of AgStack](https://img.shields.io/badge/Part_of-AgStack_Foundation-2ea44f?style=flat-square)](https://github.com/agstack)

*INATrace is a digital open-source solution designed to enhance the economic conditions of smallholder farmers by improving the traceability of global supply chains. Funded by the German Federal Ministry for Economic Cooperation and Development (BMZ) and implemented by GIZ, INATrace provides an efficient internal management system for cooperatives, digitally stores supply chain data, and supports compliance with regulations like the EU Deforestation Regulation (EUDR).*

</div>

---

## 📌 About This Repository

> **This is the INATrace meta repository** — the central hub for project-wide documentation, governance, technical specifications, and cross-repo coordination.

**Source code** lives in the four dedicated component repositories (listed below). **This repo** is the canonical home for everything that spans the full project:

| What lives here | Purpose |
|----------------|---------|
| 📋 **Project charter & governance** | Decision-making processes, roles, contribution policies |
| 📐 **Technical specs & proposals** | Architecture decisions, integration designs, enhancement proposals |
| 🔗 **Integration documentation** | Cross-system specs (e.g., Asset Registry, EUDR/Whisp, AgStack ecosystem) |
| 🗺️ **Roadmap & planning** | Project-wide priorities, phased roadmaps, task breakdowns |
| 📖 **Landing page & overview** | This README — the single entry point for understanding INATrace |
| 🤝 **Contributing guide** | How to get involved across all INATrace repos |

### Repository Structure

```
agstack/inatrace/                    ← You are here
│
├── README.md                        ← Project landing page (this file)
├── ASSET_REGISTRY_INTEGRATION.md    ← AgStack Asset Registry integration spec & roadmap
├── CONTRIBUTING.md                  ← (planned) Cross-repo contribution guide
├── CHARTER.md                       ← (planned) Project charter
├── GOVERNANCE.md                    ← (planned) Decision-making & roles
│
├── specs/                           ← (planned) Technical specs & enhancement proposals
│   ├── 001-asset-registry-v2.md
│   ├── 002-eudr-compliance.md
│   └── ...
│
├── decisions/                       ← (planned) Architecture Decision Records (ADRs)
│   ├── 001-meta-repo-structure.md
│   └── ...
│
└── .github/                         ← Issue/PR templates for cross-repo concerns
```

> **Design intent:** Any document that applies to INATrace as a whole — not just one component — belongs here. Code changes go in the component repos. Project-level decisions, specs, governance, and roadmaps go here.

---

## 🌍 What is INATrace?

**INATrace** is an end-to-end digital traceability platform for agricultural commodities (coffee, cocoa, and beyond). It provides:

- 🔗 **Full supply chain transparency** — trace every step from smallholder farm to final buyer
- ⛓️ **Blockchain-backed trust** — immutable records on Hyperledger Fabric
- 🏢 **Multi-tenant, multi-value-chain** — one system for multiple organizations and commodity types
- 📱 **Mobile-first field data** — GPS polygon mapping, offline-capable farmer registration
- 📊 **Quality & compliance** — assure quality standards and support EU Deforestation Regulation (EUDR) compliance
- 💰 **Fair pricing** — transparent pricing and payment tracking for smallholder farmers

> *INATrace enhances the economic conditions of smallholder farmers by improving traceability of global supply chains.*

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                         INATrace Platform                          │
├──────────────┬──────────────┬─────────────────┬────────────────────┤
│              │              │                 │                    │
│  📱 Mobile   │  🖥️ Frontend  │  ⚙️ Backend      │  ⛓️ Blockchain     │
│  App         │  (Angular)   │  (Java/Spring)  │  (Hyperledger)    │
│              │              │                 │                    │
│ React Native │ TypeScript   │ Java 17         │ Fabric Network    │
│ Expo         │ Angular 10   │ Spring Boot     │ Chaincode (Go)    │
│ MapBox       │              │ MySQL 8.4       │ CouchDB            │
│              │              │ REST API        │                    │
├──────────────┴──────────────┴─────────────────┴────────────────────┤
│                                                                     │
│  🗄️ MySQL Database    📧 Email (SMTP)    🗺️ MapBox    💱 Exchange API  │
│                                                                     │
│  🌐 AgStack Asset Registry (GeoID)    🛰️ Whisp/EUDR (Compliance)    │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 📦 Component Repositories

Source code lives in four dedicated repositories. Each has its own README with setup instructions, development guide, and component-specific docs.

### ⚙️ [inatrace-backend](https://github.com/agstack/inatrace-backend) — Java API Server

![Stars](https://img.shields.io/github/stars/agstack/inatrace-backend?style=flat-square)
![Forks](https://img.shields.io/github/forks/agstack/inatrace-backend?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/agstack/inatrace-backend?style=flat-square)
![Language](https://img.shields.io/github/languages/top/agstack/inatrace-backend?style=flat-square)

The core API server powering INATrace. Handles user management, product configuration, supply chain operations, processing actions, payments, and integrations.

| | |
|---|---|
| **Stack** | Java 17, Spring Boot, Maven, MySQL 8.4 |
| **License** | MPL-2.0 |
| **Top Maintainers** | [@pece-a](https://github.com/pece-a) (495 commits), [@RebernikNejc](https://github.com/RebernikNejc) (126), [@MusicDin](https://github.com/MusicDin) (96) |

**Quick Start:**
```bash
git clone https://github.com/agstack/inatrace-backend.git
# Set up MySQL via Docker:
docker run --name inatrace-mysql -e MYSQL_ROOT_PASSWORD=root \
  -e MYSQL_DATABASE=inatrace -e MYSQL_USER=inatrace \
  -e MYSQL_PASSWORD=inatrace -p 3306:3306 -d mysql:8.4.6
# Configure application.properties, then run INATraceBackendApplication.java
```

---

### 🖥️ [inatrace-frontend](https://github.com/agstack/inatrace-frontend) — Angular Web Application

![Stars](https://img.shields.io/github/stars/agstack/inatrace-frontend?style=flat-square)
![Forks](https://img.shields.io/github/forks/agstack/inatrace-frontend?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/agstack/inatrace-frontend?style=flat-square)
![Language](https://img.shields.io/github/languages/top/agstack/inatrace-frontend?style=flat-square)

The web-based user interface for managing products, companies, value chains, stakeholders, processing, orders, and payments.

| | |
|---|---|
| **Stack** | Angular 10, TypeScript, Node 14 |
| **License** | MPL-2.0 |
| **Top Maintainers** | [@pece-a](https://github.com/pece-a) (987 commits), [@RebernikNejc](https://github.com/RebernikNejc) (175), [@borce-paspalovski](https://github.com/borce-paspalovski) (145) |

**Quick Start:**
```bash
git clone https://github.com/agstack/inatrace-frontend.git
cd inatrace-frontend
npm install
# Configure environment, then:
ng serve
```

---

### 📱 [inatrace-mobile](https://github.com/agstack/inatrace-mobile) — React Native Mobile App

![Stars](https://img.shields.io/github/stars/agstack/inatrace-mobile?style=flat-square)
![Forks](https://img.shields.io/github/forks/agstack/inatrace-mobile?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/agstack/inatrace-mobile?style=flat-square)
![Language](https://img.shields.io/github/languages/top/agstack/inatrace-mobile?style=flat-square)

The field-level mobile app for cooperatives and farmers — GPS polygon mapping, farmer registration, offline data collection, and synchronization.

| | |
|---|---|
| **Stack** | React Native, Expo, TypeScript, MapBox |
| **Platforms** | Android ([Google Play](https://play.google.com/store/apps/details?hl=en-US&id=com.sunesis.inatrace)) · iOS ([App Store](https://apps.apple.com/us/app/inatrace/id6572305162)) |
| **License** | MPL-2.0 |
| **Top Maintainers** | [@pinokokol](https://github.com/pinokokol) (120 commits), [@pece-a](https://github.com/pece-a) (9) |

**Key Features:**
- 📍 **Polygon Mapping** — GPS-based field boundary capture
- 👨‍🌾 **Farmer Profiles** — Detailed cooperative member records
- 📴 **Offline Mode** — Full functionality without connectivity, auto-sync when online

**Quick Start:**
```bash
git clone https://github.com/agstack/inatrace-mobile.git
cd inatrace-mobile
npm install
# Configure .env (API URIs, MapBox tokens)
npx expo run:android   # or run:ios
```

---

### ⛓️ [inatrace-coffee-network](https://github.com/agstack/inatrace-coffee-network) — Hyperledger Fabric Blockchain

![Stars](https://img.shields.io/github/stars/agstack/inatrace-coffee-network?style=flat-square)
![Forks](https://img.shields.io/github/forks/agstack/inatrace-coffee-network?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/agstack/inatrace-coffee-network?style=flat-square)
![Language](https://img.shields.io/github/languages/top/agstack/inatrace-coffee-network?style=flat-square)

The blockchain layer — a Hyperledger Fabric network with smart contracts (chaincode) that provide immutable, auditable records for supply chain transactions.

| | |
|---|---|
| **Stack** | Hyperledger Fabric, Docker, CouchDB, Go chaincode |
| **Based On** | [BasicNetwork-2.0](https://github.com/adhavpavan/BasicNetwork-2.0.git), [Fabric Samples](https://github.com/hyperledger/fabric-samples) |
| **License** | MPL-2.0 |
| **Documentation** | [Hyperledger Fabric Docs](https://hyperledger-fabric.readthedocs.io/) |

---

## 📐 Specifications & Enhancement Docs

Cross-repo technical specifications, integration designs, and enhancement proposals live in this meta repository. These documents describe work that spans multiple INATrace components or connects INATrace to external systems.

| Document | Status | Summary |
|----------|--------|---------|
| **[Asset Registry Integration](ASSET_REGISTRY_INTEGRATION.md)** | 📋 Draft | Full spec for INATrace ↔ AgStack Asset Registry. Includes current state analysis, gap analysis, proposed architecture (async queue, ListIDs, EUDR pipeline), 5-phase roadmap, and task breakdown. |
| **EUDR Compliance Pipeline** | 🔜 Planned | Automated deforestation risk assessment via Whisp API, feeding compliance scores back into INATrace for batch reporting. |
| **Asset Registry v2.0 Migration** | 🔜 Planned | Hub+Node federation, WKT masking, ListIDs, shared identity — adapting INATrace for the next-gen registry. |

> **💡 Want to propose an enhancement?** Open an issue in this repo with the `enhancement` label, or submit a spec document as a PR.

---

## 🔗 AgStack Asset Registry Integration

> **⚠️ Partial Integration — Spec & Roadmap Available**

INATrace has an **existing but limited integration** with the [AgStack Asset Registry](https://github.com/agstack/asset-registry). When farmer plots are created with polygon coordinates, INATrace calls the Asset Registry's `/register-field-boundary` API to obtain a **GeoID** — a deterministic 64-character identifier for each geospatial boundary.

### Current State

| Feature | Status | Details |
|---------|--------|---------|
| Plot → GeoID registration | ✅ Implemented | `AgStackClientService.java` calls Asset Registry on plot create/update |
| GeoID stored in database | ✅ Implemented | `Plot.geoId` column persists the identifier |
| GeoID displayed in UI | ✅ Implemented | Web (Angular) + Mobile (React Native) show GeoID with copy button |
| "Open in Whisp" (EUDR analysis) | ✅ Implemented | Opens [whisp.earthmap.org](https://whisp.earthmap.org) with GeoID |
| Manual GeoID refresh | ✅ Implemented | `POST /userCustomers/{id}/plots/{plotId}/updateGeoID` |
| GeoID in Excel export | ✅ Implemented | Included in farmer data exports |

### Known Gaps

| Gap | Severity |
|-----|----------|
| 🔴 **Silent failure** — registration errors return null with no user notification | Critical |
| 🔴 **No batch registration** — Excel farmer import skips GeoID generation | Critical |
| 🔴 **Integration disabled by default** — config values are empty in template | Critical |
| 🟡 No reverse lookup (GeoID → boundary from registry) | Medium |
| 🟡 No GeoID history/versioning when boundaries change | Medium |
| 🟡 No overlap intelligence surfaced to users | Medium |
| 🟡 No automated EUDR compliance pipeline (Whisp is view-only) | Medium |
| 🟡 No preparation for Asset Registry v2.0 (federated Hub+Node, ListIDs) | Medium |

**👉 Full technical specification:** [ASSET_REGISTRY_INTEGRATION.md](ASSET_REGISTRY_INTEGRATION.md)

---

## 👥 Core Maintainers

<table>
<tr>
<td align="center">
<a href="https://github.com/pece-a"><img src="https://github.com/pece-a.png" width="70" height="70" style="border-radius:50%"/><br/><sub><b>@pece-a</b></sub></a><br/>
<sub>1,492 commits · Backend & Frontend lead</sub>
</td>
<td align="center">
<a href="https://github.com/RebernikNejc"><img src="https://github.com/RebernikNejc.png" width="70" height="70" style="border-radius:50%"/><br/><sub><b>@RebernikNejc</b></sub></a><br/>
<sub>301 commits · Backend & Frontend</sub>
</td>
<td align="center">
<a href="https://github.com/borce-paspalovski"><img src="https://github.com/borce-paspalovski.png" width="70" height="70" style="border-radius:50%"/><br/><sub><b>@borce-paspalovski</b></sub></a><br/>
<sub>223 commits · Frontend</sub>
</td>
<td align="center">
<a href="https://github.com/pinokokol"><img src="https://github.com/pinokokol.png" width="70" height="70" style="border-radius:50%"/><br/><sub><b>@pinokokol</b></sub></a><br/>
<sub>120 commits · Mobile lead</sub>
</td>
<td align="center">
<a href="https://github.com/MusicDin"><img src="https://github.com/MusicDin.png" width="70" height="70" style="border-radius:50%"/><br/><sub><b>@MusicDin</b></sub></a><br/>
<sub>148 commits · Backend</sub>
</td>
</tr>
<tr>
<td align="center">
<a href="https://github.com/MHA10"><img src="https://github.com/MHA10.png" width="70" height="70" style="border-radius:50%"/><br/><sub><b>@MHA10</b></sub></a><br/>
<sub>186 commits · Backend</sub>
</td>
<td align="center">
<a href="https://github.com/dockerymick"><img src="https://github.com/dockerymick.png" width="70" height="70" style="border-radius:50%"/><br/><sub><b>@dockerymick</b></sub></a><br/>
<sub>163 commits</sub>
</td>
<td align="center">
<a href="https://github.com/genovoxx"><img src="https://github.com/genovoxx.png" width="70" height="70" style="border-radius:50%"/><br/><sub><b>@genovoxx</b></sub></a><br/>
<sub>108 commits · Frontend</sub>
</td>
<td align="center">
<a href="https://github.com/sumerjohal"><img src="https://github.com/sumerjohal.png" width="70" height="70" style="border-radius:50%"/><br/><sub><b>@sumerjohal</b></sub></a><br/>
<sub>AgStack core team</sub>
</td>
<td align="center">
<a href="https://github.com/MBJuric"><img src="https://github.com/MBJuric.png" width="70" height="70" style="border-radius:50%"/><br/><sub><b>@MBJuric</b></sub></a><br/>
<sub>Mobile & Blockchain</sub>
</td>
</tr>
</table>

---

## ✨ Key Features (INATrace 2.x)

INATrace 2 is a major release that significantly expanded the platform:

### Value Chain Management
- ✅ **Generic value chain support** — configure different commodity chains with specific settings
- ✅ **Multi-tenant architecture** — multiple organizations in one deployment
- ✅ **Company profiles** — facilities, processing actions, farmers, and collectors per company
- ✅ **Product admin companies** — delegated product management within value chains

### Supply Chain Operations
- ✅ **Processing actions** — multiple types including bulk purchases for semi-products
- ✅ **Final products** — output of final processing, configurable by product admins
- ✅ **Customer orders** — linked to final products
- ✅ **Purchases, processing & payments** — comprehensive workflow management

### Data & Compliance
- ✅ **Farmer import** — bulk import from Excel files
- ✅ **Processing evidence fields** — configurable in system settings
- ✅ **Multi-language support** — translations for facilities, actions, semi-products, and evidence types
- ✅ **Multi-currency** — configurable currencies with daily exchange rate sync via [exchangeratesapi.io](https://exchangeratesapi.io/)
- ✅ **EUDR compliance** — EU Deforestation Regulation support through polygon mapping and traceability

### Mobile & Field
- ✅ **GPS polygon mapping** — field boundary capture on mobile devices
- ✅ **Offline-first** — full data collection without connectivity
- ✅ **Auto-sync** — seamless data synchronization when online
- ✅ **Available on** [Google Play](https://play.google.com/store/apps/details?hl=en-US&id=com.sunesis.inatrace) and [App Store](https://apps.apple.com/us/app/inatrace/id6572305162)

---

## 🚀 Getting Started

### Full Platform Deployment

To deploy the complete INATrace platform, you'll need to set up:

1. **Database** — MySQL 8.4+ (can use Docker)
2. **Backend** — Java 17 + Spring Boot API server
3. **Frontend** — Angular web application
4. **Mobile** *(optional)* — React Native app via Expo
5. **Blockchain** *(optional)* — Hyperledger Fabric network

```bash
# 1. Clone all repositories
git clone https://github.com/agstack/inatrace-backend.git
git clone https://github.com/agstack/inatrace-frontend.git
git clone https://github.com/agstack/inatrace-mobile.git
git clone https://github.com/agstack/inatrace-coffee-network.git

# 2. Start MySQL
docker run --name inatrace-mysql \
  -e MYSQL_ROOT_PASSWORD=root \
  -e MYSQL_DATABASE=inatrace \
  -e MYSQL_USER=inatrace \
  -e MYSQL_PASSWORD=inatrace \
  -p 3306:3306 -d mysql:8.4.6

# 3. Start Backend (see inatrace-backend README for full config)
cd inatrace-backend
# Configure application.properties
mvn spring-boot:run

# 4. Start Frontend
cd ../inatrace-frontend
npm install && ng serve

# 5. (Optional) Start Mobile
cd ../inatrace-mobile
npm install && npx expo run:android
```

For detailed setup instructions, see each repository's README.

---

## 🔗 Related Projects

INATrace is part of the broader **AgStack Foundation** ecosystem of open digital infrastructure for agriculture:

| Project | Description |
|---------|-------------|
| [TraceFoodChain](https://github.com/agstack/tracefoodchain) | Flutter app for tracing goods along food production chains |
| [TerraTrac](https://github.com/agstack/TerraTrac-field-app) | EUDR compliance mobile app by TechnoServe Labs |
| [Asset Registry](https://github.com/agstack/asset-registry) | Geospatial asset registration for agricultural land |
| [OpenAgri Platform](https://github.com/agstack/OpenAgri-Bootstrap-Deployment) | Modular digital agriculture microservices |

👉 **See all AgStack projects:** [github.com/agstack](https://github.com/agstack)

---

## 🏛️ Governance & Charter

> *Governance documents are being established for the INATrace project.*

This meta repository is the canonical location for:

- **Project Charter** — Mission, scope, and guiding principles
- **Governance Model** — Decision-making process, maintainer roles, voting procedures
- **Code of Conduct** — Community standards and enforcement
- **Release Process** — How releases are coordinated across the four component repos

These documents will be added as the governance framework is formalized. For now, INATrace operates under the broader [AgStack Foundation governance](https://github.com/agstack/governance).

| Document | Status |
|----------|--------|
| `CHARTER.md` | 🔜 Planned |
| `GOVERNANCE.md` | 🔜 Planned |
| `CODE_OF_CONDUCT.md` | 🔜 Planned |
| `RELEASE_PROCESS.md` | 🔜 Planned |

---

## 📜 License

All INATrace repositories are licensed under the **Mozilla Public License 2.0** (MPL-2.0).

---

## 🤝 Contributing

We welcome contributions of all kinds — code, documentation, specs, and ideas!

### Where to contribute

| Type of contribution | Where |
|---------------------|-------|
| **Bug fix or feature** in backend, frontend, mobile, or blockchain | The relevant [component repository](#-component-repositories) |
| **Cross-repo enhancement proposal** or technical spec | This meta repo — open an issue or submit a spec PR |
| **Governance, charter, or process** proposal | This meta repo |
| **Integration design** (Asset Registry, EUDR, etc.) | This meta repo — see [specs section](#-specifications--enhancement-docs) |
| **General question or discussion** | The [INATrace mailing list](https://lists.agstack.org/g/inatrace) |

### How to contribute

1. Browse [open issues across INATrace repos](https://github.com/issues?q=is%3Aopen+is%3Aissue+org%3Aagstack+inatrace)
2. Fork the relevant repository
3. Create a feature branch and submit a pull request
4. See individual repo READMEs for development setup details

---

<div align="center">

**[Backend](https://github.com/agstack/inatrace-backend)** · **[Frontend](https://github.com/agstack/inatrace-frontend)** · **[Mobile](https://github.com/agstack/inatrace-mobile)** · **[Blockchain](https://github.com/agstack/inatrace-coffee-network)**

Part of [The AgStack Foundation](https://github.com/agstack) · A [Linux Foundation](https://www.linuxfoundation.org/) Project

</div>
