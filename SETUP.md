# AI Tools Directory - Complete Setup Guide

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- Docker & Docker Compose
- PostgreSQL 16 (or use Docker)
- Redis 7 (or use Docker)

### Local Development

1. **Install dependencies**
```bash
npm install
```

2. **Setup environment**
```bash
cp .env.example .env.local
```

3. **Start services**
```bash
npm run docker:up
```

4. **Initialize database**
```bash
npm run db:push
npm run db:seed
```

5. **Start dev servers**
```bash
npm run dev
```

Access:
- Frontend: http://localhost:3001
- Backend API: http://localhost:3000
- API Docs: http://localhost:3000/api/docs
- Database Studio: `npm run db:studio`

## 📁 Project Structure

```
ai-tools-directory/
├── apps/
│   ├── api/              # NestJS Backend
│   │   ├── src/
│   │   │   ├── modules/  # Feature modules
│   │   │   ├── config/   # Configuration
│   │   │   └── main.ts   # Entry point
│   │   ├── Dockerfile
│   │   └── package.json
│   │
│   └── web/              # Next.js Frontend
│       ├── src/
│       │   ├── app/      # App Router
│       │   ├── components/
│       │   ├── hooks/
│       │   └── lib/
│       ├── Dockerfile
│       └── package.json
│
├── packages/
│   ├── db/               # Prisma Database
│   │   └── prisma/
│   │       ├── schema.prisma
│   │       └── seed.ts
│   ├── shared/           # Shared types
│   └── ui/               # Shared components
│
├── docker-compose.yml
├── turbo.json
└── package.json
```

## 🗄️ Database Schema

**Core Tables:**
- `users` - User accounts with roles (ADMIN, MODERATOR, USER, DEVELOPER, AFFILIATE)
- `tools` - AI tools directory with full content
- `categories` - Tool categorization
- `tags` - Tool tagging system
- `reviews` - User reviews and ratings
- `bookmarks` - User bookmarks
- `collections` - Custom tool collections

**Monetization:**
- `subscriptions` - User subscriptions
- `pricing_plans` - Subscription tiers
- `invoices` - Billing records
- `sponsored_listings` - Sponsored placements
- `affiliate_links` - Affiliate tracking

**Admin & Moderation:**
- `pending_edits` - Pending tool edits
- `tool_reports` - Tool reports
- `tool_claims` - Tool ownership claims
- `audit_logs` - System audit logs

**Developer:**
- `api_keys` - API access keys
- `webhooks` - Webhook subscriptions

## 🔗 API Endpoints

### Authentication
- `POST /auth/register` - Register new account
- `POST /auth/login` - Login with email/password
- `GET /auth/me` - Get current user profile

### Tools
- `GET /tools` - List all tools (paginated)
- `GET /tools/featured` - Get featured tools
- `GET /tools/search?q=query` - Search tools
- `GET /tools/:id` - Get tool details
- `GET /tools/category/:categoryId` - Get tools by category

### Categories
- `GET /categories` - List all categories
- `GET /categories/:id` - Get category details
- `GET /categories/slug/:slug` - Get by slug

### Reviews
- `GET /reviews/tool/:toolId` - Get tool reviews
- `POST /reviews` - Create review (requires auth)
- `PATCH /reviews/:id` - Update review

### Subscriptions
- `GET /subscriptions/plans` - Get pricing plans
- `GET /subscriptions/me` - Get user subscription (auth)
- `POST /subscriptions` - Create subscription (auth)
- `POST /subscriptions/:id/cancel` - Cancel subscription (auth)

### Analytics
- `GET /analytics/tools/:toolId` - Get tool analytics
- `GET /analytics/top-tools` - Get top tools
- `POST /analytics/track/:toolId` - Track view

### Admin (requires ADMIN role)
- `GET /admin/tools/pending` - Get pending tools
- `POST /admin/tools/:id/approve` - Approve tool
- `POST /admin/tools/:id/reject` - Reject tool
- `GET /admin/edits/pending` - Get pending edits
- `POST /admin/edits/:id/approve` - Approve edit
- `GET /admin/reports` - Get tool reports
- `POST /admin/reports/:id/resolve` - Resolve report

## 🔐 Security Features

✅ JWT Authentication with refresh tokens
✅ CSRF Protection
✅ XSS Sanitization
✅ SQL Injection Prevention (via Prisma)
✅ Rate Limiting (configurable per endpoint)
✅ CORS Configuration
✅ Secure Headers (X-Content-Type-Options, X-Frame-Options, etc.)
✅ GDPR Compliance Ready
✅ Optional 2FA Support
✅ Device Tracking & Session Management
✅ Audit Logging for all admin actions

## 🌍 Internationalization

Supported languages:
- 🇺🇸 English (en)
- 🇸🇦 Arabic (ar) - Full RTL Support
- 🇪🇸 Spanish (es)
- 🇨🇳 Chinese (zh)
- 🇮🇳 Hindi (hi)

Features:
- Locale-based routing
- hreflang SEO optimization
- Localized metadata
- RTL layout support for Arabic

## 💳 Payment Integration

Supported payment providers:
- Stripe (subscriptions, invoices)
- PayPal (recurring billing)
- Paddle (digital products)
- LemonSqueezy (affiliate support)

## 📊 Analytics & Monitoring

Tracked metrics:
- Click tracking per tool
- View impressions
- CTR (Click Through Rate)
- Traffic sources
- User growth
- MRR/ARR (Monthly/Annual Recurring Revenue)
- Conversion tracking
- Geo-analytics

## 🧪 Testing

```bash
# Run all tests
npm run test

# Watch mode
npm run test -- --watch

# Coverage report
npm run test -- --coverage
```

## 🐳 Docker Deployment

Build and run with Docker Compose:

```bash
# Build images
npm run docker:build

# Start services
npm run docker:up

# Stop services
npm run docker:down

# View logs
docker compose logs -f

# Access containers
docker compose exec api sh
docker compose exec web sh
```

## 🚀 Production Deployment

### Environment Variables

Create `.env.production`:
```
DATABASE_URL=postgresql://user:password@prod-db:5432/ai_tools
REDIS_URL=redis://prod-redis:6379
JWT_SECRET=your-production-secret-key
NODE_ENV=production
API_PORT=3000
NEXT_PUBLIC_API_URL=https://api.aitoolsdirectory.com
NEXT_PUBLIC_APP_URL=https://aitoolsdirectory.com
STRIPE_SECRET_KEY=sk_live_...
```

### CI/CD Pipeline

See `.github/workflows/` for GitHub Actions setup:
- Automated testing on push
- Build and lint
- Docker image building
- Deployment to production

## 📚 Additional Resources

- [NestJS Documentation](https://docs.nestjs.com)
- [Next.js Documentation](https://nextjs.org/docs)
- [Prisma Documentation](https://www.prisma.io/docs)
- [Tailwind CSS](https://tailwindcss.com/docs)

## 🤝 Contributing

Contributions welcome! Please read CONTRIBUTING.md

## 📄 License

MIT License - see LICENSE file

## 💬 Support

- Email: support@aitoolsdirectory.com
- GitHub Issues: [Report a bug](https://github.com/yourusername/ai-tools-directory/issues)
- Documentation: [https://docs.aitoolsdirectory.com](https://docs.aitoolsdirectory.com)
