# 🚀 AI Tools Directory SaaS Platform

Enterprise-grade AI Tools Directory platform inspired by Toolify, Futurepedia, There's An AI For That, and TopAI.tools.

## 🎯 Features

### Core Platform
- ✅ Public AI tools directory with 1000+ tools capacity
- ✅ Advanced AI-powered semantic search
- ✅ Dynamic categorization and tagging system
- ✅ Smart filtering and discovery
- ✅ Tool comparison system
- ✅ Reviews and ratings system
- ✅ Bookmark and collections management
- ✅ AI-powered recommendations

### Monetization
- ✅ Stripe, PayPal, Paddle, and LemonSqueezy integration
- ✅ Multiple pricing tiers
- ✅ Sponsored listings and featured placements
- ✅ API access monetization
- ✅ Banner ads system
- ✅ Affiliate system
- ✅ Analytics and revenue tracking

### Admin & Moderation
- ✅ Comprehensive admin dashboard
- ✅ Tool moderation and approval workflow
- ✅ Pending edits management
- ✅ Duplicate detection
- ✅ Claim ownership system
- ✅ Report tools workflow
- ✅ Audit logs

### International
- ✅ Multilingual (EN, AR, ES, ZH, HI)
- ✅ Full RTL support for Arabic
- ✅ Locale-based routing
- ✅ hreflang SEO optimization
- ✅ Localized metadata

### Developer Features
- ✅ REST API with full documentation
- ✅ Developer portal
- ✅ API keys management
- ✅ Rate limiting and quotas
- ✅ Webhook system
- ✅ SDK documentation

### Security
- ✅ JWT authentication
- ✅ CSRF protection
- ✅ XSS sanitization
- ✅ SQL injection prevention
- ✅ Rate limiting
- ✅ 2FA support
- ✅ Device tracking
- ✅ GDPR compliance

### SEO & Performance
- ✅ Structured data (JSON-LD, Schema.org)
- ✅ Dynamic metadata
- ✅ Sitemap generation
- ✅ SEO-friendly URLs
- ✅ Image optimization & CDN
- ✅ Redis caching
- ✅ Lighthouse score > 90

## 🏗️ Architecture

### Monorepo Structure
```
.
├── apps/
│   ├── web/                 # Next.js 15 Frontend
│   │   ├── src/
│   │   │   ├── app/         # App router
│   │   │   ├── components/  # React components
│   │   │   ├── pages/       # Legacy pages
│   │   │   ├── hooks/       # Custom hooks
│   │   │   ├── utils/       # Utilities
│   │   │   ├── styles/      # Global styles
│   │   │   └── lib/         # Libraries
│   │   ├── public/          # Static files
│   │   ├── next.config.js
│   │   ├── tsconfig.json
│   │   └── package.json
│   │
│   └── api/                 # NestJS Backend
│       ├── src/
│       │   ├── modules/     # Feature modules
│       │   ├── common/      # Common utilities
│       │   ├── config/      # Configuration
│       │   ├── guards/      # Auth guards
│       │   ├── interceptors/# Request interceptors
│       │   ├── filters/     # Exception filters
│       │   ├── decorators/  # Custom decorators
│       │   └── main.ts      # Entry point
│       ├── test/            # Tests
│       ├── .env.example
│       ├── docker.env
│       ├── nest-cli.json
│       ├── tsconfig.json
│       └── package.json
│
├── packages/
│   ├── shared/              # Shared types & utils
│   │   ├── src/
│   │   │   ├── types/
│   │   │   ├── utils/
│   │   │   └── constants/
│   │   └── package.json
│   │
│   ├── ui/                  # Shared UI components
│   │   ├── src/
│   │   │   ├── components/
│   │   │   ├── hooks/
│   │   │   └── styles/
│   │   └── package.json
│   │
│   └── db/                  # Prisma schema & migrations
│       ├── prisma/
│       │   ├── schema.prisma
│       │   ├── seed.ts
│       │   └── migrations/
│       ├── src/
│       │   └── index.ts
│       └── package.json
│
├── docker-compose.yml
├── turbo.json
├── package.json
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- Docker & Docker Compose
- PostgreSQL 16
- Redis 7

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/ai-tools-directory.git
cd ai-tools-directory
```

2. **Install dependencies**
```bash
npm install
```

3. **Setup environment variables**
```bash
cp .env.example .env.local
```

4. **Start Docker services**
```bash
npm run docker:up
```

5. **Setup database**
```bash
npm run db:push
npm run db:seed
```

6. **Start development servers**
```bash
npm run dev
```

Access the application:
- Frontend: http://localhost:3001
- Backend: http://localhost:3000
- API Docs: http://localhost:3000/api/docs
- Database Studio: `npm run db:studio`

## 📊 Database Schema

### Core Tables
- `users` - User accounts and profiles
- `tools` - AI tools directory
- `categories` - Tool categories
- `tags` - Tool tags
- `reviews` - User reviews
- `ratings` - Tool ratings
- `bookmarks` - User bookmarks
- `collections` - Custom collections
- `comparisons` - Tool comparisons
- `analytics` - Usage analytics

### Monetization
- `subscriptions` - User subscriptions
- `pricing_plans` - Pricing configurations
- `sponsored_listings` - Sponsored tools
- `featured_placements` - Featured slots
- `invoices` - Billing invoices
- `transactions` - Payment transactions
- `affiliate_links` - Affiliate system

### Admin & Moderation
- `pending_edits` - Edit approvals
- `reports` - Tool reports
- `audit_logs` - System audit logs
- `moderations` - Moderation actions
- `api_keys` - API access keys
- `webhooks` - Webhook subscriptions

## 🔑 Key Technologies

### Frontend
- Next.js 15 with App Router
- React 19
- TypeScript
- Tailwind CSS
- ShadCN UI
- Framer Motion
- React Query
- Zustand
- Zod Validation
- React Hook Form

### Backend
- NestJS 10
- TypeScript
- PostgreSQL 16
- Prisma ORM
- Redis 7
- BullMQ
- JWT Authentication
- Swagger/OpenAPI

### DevOps
- Docker & Docker Compose
- GitHub Actions (CI/CD)
- Environment management
- Database migrations

## 📚 API Documentation

Comprehensive API documentation available at `/api/docs` when running locally.

## 🛡️ Security

- CSRF Protection
- XSS Sanitization
- SQL Injection Prevention
- Rate Limiting
- JWT with Refresh Tokens
- GDPR Compliance
- Device Tracking
- Optional 2FA

## 🌍 Internationalization

Supported languages:
- 🇺🇸 English
- 🇸🇦 Arabic (RTL)
- 🇪🇸 Spanish
- 🇨🇳 Chinese (Simplified)
- 🇮🇳 Hindi

## 📈 Analytics

- Click tracking
- Impression tracking
- Traffic sources
- Geo-analytics
- User growth metrics
- MRR/ARR tracking
- Conversion tracking
- Custom dashboards

## 💳 Payment Integration

- Stripe
- PayPal
- Paddle
- LemonSqueezy

## 📄 License

MIT License - see LICENSE file for details

## 👥 Contributing

Contributions are welcome! Please read CONTRIBUTING.md for guidelines.

## 📞 Support

For support, email support@aitoolsdirectory.com or open an issue on GitHub.
