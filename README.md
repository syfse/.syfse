# Syfse

**Empowering local farm shops with digital commerce solutions.**

---

## 🌾 About Syfse

Syfse is a multi-tenant SaaS platform that enables local farm shop owners (Hofläden) to launch their own professional e-commerce stores through a simple subscription model. We believe in supporting local agriculture by providing the digital tools farmers need to reach customers online.

### Our Mission

To bridge the gap between traditional farm shops and modern e-commerce, making it effortless for local producers to sell their products online while maintaining complete control and data isolation.

---

## ✨ What We Offer

- 🛒 **Subscription-based shop rental** - Pay monthly, no setup fees
- 🔒 **Complete isolation** - Each shop runs in its own secure Docker container
- 💳 **Integrated payments** - Seamless Stripe integration for hassle-free transactions
- 🚀 **Instant deployment** - Shops go live automatically upon subscription
- 🎨 **Customizable storefronts** - Tailor each shop to match your farm's unique brand
- 📊 **Built-in analytics** - Track sales, customers, and inventory
- 📱 **Mobile-responsive** - Beautiful shopping experience on any device

---

## 🏗️ Platform Architecture

### Core Services

| Service | Description | Technology |
|---------|-------------|------------|
| **syfse-web** | Marketing website and customer portal | Next.js, React, Tailwind CSS |
| **syfse-api** | Central API and tenant management | Node.js, Express, PostgreSQL |
| **syfse-shop** | Customer-facing shop template | Next.js, React, Stripe |
| **syfse-orchestrator** | Container lifecycle management | Node.js, Docker |
| **syfse-admin** | Internal operations dashboard | React, Next.js |

### Shared Libraries

| Package | Purpose |
|---------|---------|
| **syfse-types** | Shared TypeScript definitions |
| **syfse-ui** | Reusable React components |
| **syfse-stripe** | Stripe integration wrapper |

---

## 🚀 Tech Stack

**Frontend**
- React 18
- Next.js 14
- TypeScript
- Tailwind CSS

**Backend**
- Node.js
- Express
- PostgreSQL
- Prisma ORM

**Infrastructure**
- Docker
- GitHub Container Registry (GHCR)
- Stripe API
- Let's Encrypt (SSL)

**DevOps**
- GitHub Actions
- Docker Compose
- Kubernetes (optional)

---

## 🔄 How It Works

```
1. Farm shop owner subscribes on syfse.com
        ↓
2. Stripe processes payment and triggers webhook
        ↓
3. syfse-api creates tenant account in database
        ↓
4. syfse-orchestrator provisions isolated Docker container
        ↓
5. Subdomain configured (e.g., bauernhof-mueller.syfse.shop)
        ↓
6. SSL certificate automatically issued
        ↓
7. Shop owner receives login credentials
        ↓
8. Shop is live and ready for customers! 🎉
```

---

## 📦 Container Architecture

Each customer's shop runs in complete isolation:

```
┌─────────────────────────────────────┐
│  syfse-web (Marketing Site)         │
│  ghcr.io/syfse/web:latest           │
└────────────┬────────────────────────┘
             │
             ↓
┌─────────────────────────────────────┐
│  syfse-api (Core API)                │
│  ghcr.io/syfse/api:latest           │
└────────────┬────────────────────────┘
             │
             ↓
┌─────────────────────────────────────┐
│  syfse-orchestrator                  │
│  Container Management                │
└────────────┬────────────────────────┘
             │
    ┌────────┴────────┬────────┐
    ↓                 ↓         ↓
┌─────────┐    ┌─────────┐    ┌─────────┐
│ Shop A  │    │ Shop B  │    │ Shop C  │
│ Tenant 1│    │ Tenant 2│    │ Tenant 3│
└─────────┘    └─────────┘    └─────────┘
```

---

## 🔐 Security & Privacy

- ✅ **Complete tenant isolation** - Each shop in separate container
- ✅ **End-to-end encryption** - SSL/TLS for all connections
- ✅ **GDPR compliant** - Data protection by design
- ✅ **Regular security audits** - Continuous monitoring
- ✅ **Secure payment processing** - PCI DSS compliant via Stripe
- ✅ **Database row-level security** - Automatic data segregation

---

## 🛠️ Development

### Prerequisites

- Node.js 20+
- Docker & Docker Compose
- PostgreSQL 15+
- Stripe account (for payments)

### Quick Start

```bash
# Clone repositories
git clone https://github.com/syfse/syfse-web
git clone https://github.com/syfse/syfse-api
git clone https://github.com/syfse/syfse-shop

# Setup environment
cp .env.example .env

# Start database
docker-compose up -d postgres redis

# Install dependencies
npm install

# Run migrations
npm run db:migrate

# Start development server
npm run dev
```

### Repository Structure

```
syfse/
├── syfse-web/              # Marketing & subscription site
├── syfse-api/              # Core API & webhooks
├── syfse-shop/             # Shop template (containerized)
├── syfse-orchestrator/     # Container management
├── syfse-admin/            # Internal admin dashboard
├── syfse-types/            # Shared TypeScript types
├── syfse-ui/               # Component library
└── syfse-stripe/           # Stripe integration SDK
```

---

## 📊 Status

🚧 **Currently in Development**

- ✅ Core architecture designed
- ✅ Repository structure established
- 🔄 MVP development in progress
- ⏳ Beta launch planned for Q2 2025

---

## 🤝 Contributing

Syfse is currently a proprietary platform. We are not accepting external contributions at this time.

If you're interested in partnership opportunities or have questions, please reach out to us.

---

## 📄 License

Copyright © 2025 Syfse. All rights reserved.

This software is proprietary and confidential. Unauthorized copying, distribution, or modification is strictly prohibited. See [LICENSE](./LICENSE) for details.

---

## 📞 Contact

- **Website**: [syfse.com](https://syfse.com) *(coming soon)*
- **Email**: hello@syfse.com
- **Support**: support@syfse.com
- **Twitter**: [@syfse](https://twitter.com/syfse) *(coming soon)*

---

## 🌟 Our Vision

We envision a future where every local farm shop has access to world-class e-commerce technology, enabling them to compete with large retailers while maintaining their unique character and direct relationship with customers.

**Built with ❤️ for local farmers and food producers.**

---

*Syfse - Simplifying farm shop e-commerce, one subscription at a time.*
