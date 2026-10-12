<p align="center">
  <img src="https://raw.githubusercontent.com/Team-25-Second-Hand-Vehicle-Marketplace/AutoVaultLK/main/web-frontend/public/favicon.svg" width="88" alt="AutoVault LK" />
</p>

<h1 align="center">AutoVault&nbsp;LK</h1>

<p align="center">
  <b>Sri Lanka's second-hand vehicle marketplace — search it the way you'd say it.</b><br/>
  <sub>"family friendly vehicle under 8 million" is a valid search. No dropdowns required.</sub>
</p>

<p align="center">
  <a href="https://d35ak0s3rd3633.cloudfront.net"><img src="https://img.shields.io/badge/▶_Live_Demo-1b5fff?style=for-the-badge" alt="Live demo" /></a>
  <a href="https://youtu.be/U6pDi2PnsIo"><img src="https://img.shields.io/badge/Watch_Demo-ff0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch the demo on YouTube" /></a>
  <a href="https://github.com/Team-25-Second-Hand-Vehicle-Marketplace/AutoVaultLK"><img src="https://img.shields.io/badge/Source_Code-181717?style=for-the-badge&logo=github" alt="Source code" /></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/release-1.0.0-1b5fff" alt="Release 1.0.0" />
  <img src="https://img.shields.io/badge/NestJS-e0234e?logo=nestjs&logoColor=white" alt="NestJS" />
  <img src="https://img.shields.io/badge/React-20232a?logo=react&logoColor=61dafb" alt="React" />
  <img src="https://img.shields.io/badge/TypeScript-3178c6?logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/PostgreSQL_17_+_pgvector-336791?logo=postgresql&logoColor=white" alt="PostgreSQL 17 with pgvector" />
  <img src="https://img.shields.io/badge/AWS_Serverless-232f3e?logo=amazonaws&logoColor=white" alt="AWS serverless" />
  <img src="https://img.shields.io/badge/Terraform-7b42bc?logo=terraform&logoColor=white" alt="Terraform" />
</p>

---

### See it in action

<p align="center">
  <a href="https://youtu.be/U6pDi2PnsIo">
    <img src="https://img.youtube.com/vi/U6pDi2PnsIo/maxresdefault.jpg" width="640" alt="Watch the AutoVault LK walkthrough on YouTube" />
  </a>
</p>

<p align="center">
  <a href="https://youtu.be/U6pDi2PnsIo"><b>▶&nbsp; Watch the walkthrough</b></a><br/>
  <sub><i>AutoVaultLK — A Smarter Way to Buy and Sell Vehicles in Sri Lanka</i></sub>
</p>

### The problem

Buying a used vehicle in Sri Lanka means scrolling endless Facebook groups, guessing
the right keywords on classifieds sites, and hoping the seller is real.

### What we built

| | |
|---|---|
| 🗣️ **Natural-language search** | Ask in plain English. An LLM-backed parser maps intent to filters, then *relaxes* constraints instead of returning nothing. |
| 🎚️ **Classic filters too** | Make, model, year, price, mileage, fuel, transmission — for buyers who prefer dropdowns. |
| ✅ **Verified dealers only** | Every dealer submits documents and is approved by an admin before listing. |
| 📦 **Bulk inventory upload** | Dealers drop a CSV + a ZIP of photos; a Step Functions ETL pipeline validates, enriches and publishes the whole batch. |
| ❤️ **Favourites & recommendations** | Personalised suggestions driven by pgvector similarity. |
| 📧 **Transactional email** | Verification, password reset and upload outcomes, with retries. |

### How it's built

Seven independently deployable pieces, one PostgreSQL database with a schema per service.

| Service | Responsibility |
|---|---|
| `web-frontend` | React + Vite single-page app |
| `auth-user-service` | Sign-up, sign-in, Google OAuth, tokens, dealer profiles |
| `marketplace-service` | Listings, search, favourites, recommendations |
| `ingestion-service` | Bulk upload API, job status, ETL worker |
| `admin-service` | Dealer approval, users, uploads, reports, audit logs |
| `notification-service` | Email delivery with retries |
| `api-gateway` | Routing and OpenAPI specs |

In production every NestJS service ships as an **AWS Lambda container** behind API
Gateway, with **S3** for files, **SQS + Step Functions** for the upload pipeline,
**SES** for email, and **CloudFront** in front of the frontend — all provisioned by
Terraform. Pushing to `main` tests and deploys only the services that changed.

### Repositories

| Repository | What's inside |
|---|---|
| **[AutoVaultLK](https://github.com/Team-25-Second-Hand-Vehicle-Marketplace/AutoVaultLK)** | The monorepo: all services, frontend, database, infrastructure. Start here — setup instructions are in its README. |
| **[Project-Documents](https://github.com/Team-25-Second-Hand-Vehicle-Marketplace/Project-Documents)** | SRS, architecture and design documentation, reports. |

### Team 25

<p align="center">
  <a href="https://github.com/rash200319"><img src="https://github.com/rash200319.png?size=72" width="72" alt="rash200319" /></a>&nbsp;&nbsp;
  <a href="https://github.com/BhanukaRC"><img src="https://github.com/BhanukaRC.png?size=72" width="72" alt="BhanukaRC" /></a>&nbsp;&nbsp;
  <a href="https://github.com/JanithVishula"><img src="https://github.com/JanithVishula.png?size=72" width="72" alt="JanithVishula" /></a>&nbsp;&nbsp;
  <a href="https://github.com/virusan-T"><img src="https://github.com/virusan-T.png?size=72" width="72" alt="virusan-T" /></a>
</p>

<p align="center">
  <sub>Built as a cloud-native software engineering project · Department of Computer Science &amp; Engineering, University of Moratuwa</sub>
</p>
