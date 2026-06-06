# 📝 منصة المدونة الاحترافية - Blog Platform

منصة مدونة حديثة وقابلة للتوسع مع ميزات احترافية للنشر والإدارة.

## 🎯 الميزات الرئيسية

### 📚 إدارة المحتوى
- ✅ كتابة وتحرير المقالات
- ✅ نظام التصنيفات والوسوم
- ✅ حفظ المسودات التلقائي
- ✅ جدولة نشر المقالات
- ✅ دعم الصور والملفات المرفقة

### 💬 التفاعل والمجتمع
- ✅ نظام التعليقات المتقدم
- ✅ الإعجابات والمشاركة الاجتماعية
- ✅ نظام المتابعين
- ✅ الإشعارات الفورية
- ✅ المحادثات والردود

### 🔍 البحث والاكتشاف
- ✅ بحث متقدم بالمقالات
- ✅ تصفية حسب التاريخ والفئة
- ✅ أرشيف المقالات
- ✅ قائمة المقالات الشهيرة
- ✅ المقالات ذات الصلة

### 📊 التحليلات والإحصائيات
- ✅ عدد المشاهدات والقراء
- ✅ تحليل الأداء
- ✅ مصادر الحركة
- ✅ التفاعل والمشاركة
- ✅ تقارير شاملة

### 🎨 التصميم والتخصيص
- ✅ واجهة مستخدم حديثة
- ✅ دعم الوضع المظلم والفاتح
- ✅ تصميم متجاوب (Responsive)
- ✅ ثيمات قابلة للتخصيص
- ✅ دعم RTL للعربية

### 🔐 الأمان والحماية
- ✅ مصادقة آمنة (JWT)
- ✅ التحكم بالأذونات
- ✅ حماية من الهجمات (CSRF, XSS)
- ✅ النسخ الاحتياطية التلقائية
- ✅ التشفير

### 🌐 SEO والأداء
- ✅ تحسين محركات البحث
- ✅ Sitemap وRobots.txt
- ✅ Structured Data (JSON-LD)
- ✅ سرعة التحميل العالية
- ✅ CDN Integration

## 🏗️ بنية المشروع

```
Blog_Platform/
├── backend/                    # NestJS Backend
│   ├── src/
│   │   ├── modules/
│   │   │   ├── posts/         # إدارة المقالات
│   │   │   ├── categories/    # الفئات والتصنيفات
│   │   │   ├── comments/      # التعليقات
│   │   │   ├── users/         # المستخدمون
│   │   │   ├── auth/          # المصادقة
│   │   │   ├── tags/          # الوسوم
│   │   │   ├── analytics/     # التحليلات
│   │   │   └── notifications/ # الإشعارات
│   │   ├── common/
│   │   ├── config/
│   │   └── main.ts
│   ├── test/
│   ├── package.json
│   └── tsconfig.json
│
├── frontend/                   # Next.js Frontend
│   ├── src/
│   │   ├── app/              # App Router
│   │   ├── components/       # مكونات React
│   │   │   ├── Header/
│   │   │   ├── Navigation/
│   │   │   ├── PostCard/
│   │   │   ├── Sidebar/
│   │   │   └── Comments/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── utils/
│   │   ├── styles/
│   │   └── lib/
│   ├── public/
│   ├── next.config.js
│   └── package.json
│
├── database/                   # Prisma Schema
│   ├── schema.prisma
│   ├── seed.ts
│   └── migrations/
│
└── docker-compose.yml

```

## 🛠️ التقنيات المستخدمة

### Backend
- **NestJS 10** - Framework قوي للـ Backend
- **TypeScript** - لسلامة النوع
- **PostgreSQL** - قاعدة البيانات
- **Prisma ORM** - للتعامل مع قاعدة البيانات
- **Redis** - للـ Caching والجلسات
- **JWT** - المصادقة
- **Swagger** - توثيق API

### Frontend
- **Next.js 15** - React Framework
- **React 19** - مكتبة الواجهات
- **TypeScript** - السلامة النوعية
- **Tailwind CSS** - تصميم متقدم
- **ShadCN UI** - مكونات جاهزة
- **React Query** - إدارة البيانات
- **Zod** - التحقق من البيانات
- **Framer Motion** - الرسوميات

### DevOps
- **Docker** - Container
- **Docker Compose** - تنسيق الخدمات
- **GitHub Actions** - CI/CD

## 📊 نموذج قاعدة البيانات

### الجداول الأساسية

#### Users (المستخدمون)
```
- id
- email
- username
- password (hashed)
- avatar
- bio
- createdAt
- updatedAt
```

#### Posts (المقالات)
```
- id
- title
- slug
- content
- excerpt
- authorId
- categoryId
- status (draft/published/archived)
- viewCount
- publishedAt
- createdAt
- updatedAt
```

#### Categories (الفئات)
```
- id
- name
- slug
- description
- image
- color
- createdAt
```

#### Tags (الوسوم)
```
- id
- name
- slug
- postCount
- createdAt
```

#### Comments (التعليقات)
```
- id
- content
- postId
- authorId
- parentId (للردود)
- status (pending/approved)
- likes
- createdAt
- updatedAt
```

#### PostTags (علاقة المقالات والوسوم)
```
- postId
- tagId
```

#### Analytics (التحليلات)
```
- id
- postId
- viewCount
- uniqueVisitors
- clicksCount
- shareCount
- date
```

#### Notifications (الإشعارات)
```
- id
- userId
- content
- link
- read
- createdAt
```

## 🚀 البدء السريع

### المتطلبات
- Node.js 18+
- Docker & Docker Compose
- PostgreSQL 16
- Redis 7

### الخطوات

1. **استنساخ المستودع**
```bash
git clone https://github.com/yourusername/blog-platform.git
cd blog-platform
```

2. **تثبيت الاعتماديات**
```bash
npm install
```

3. **إعداد متغيرات البيئة**
```bash
cp .env.example .env.local
```

4. **تشغيل Docker**
```bash
docker-compose up -d
```

5. **إعداد قاعدة البيانات**
```bash
npm run db:migrate
npm run db:seed
```

6. **تشغيل الخادم**
```bash
npm run dev
```

### الوصول
- 🌐 Frontend: http://localhost:3001
- 🔌 Backend: http://localhost:3000
- 📚 API Docs: http://localhost:3000/api/docs

## 🎨 صفحات الموقع الرئيسية

### الصفحات العامة
- **الصفحة الرئيسية** - عرض أحدث المقالات
- **صفحة المقالة** - عرض المقالة كاملة
- **الفئات** - عرض مقالات الفئة
- **الأرشيف** - عرض المقالات القديمة
- **البحث** - صفحة البحث المتقدم
- **عن المدونة** - معلومات عن المدونة
- **اتصل بنا** - نموذج التواصل

### صفحات المستخدم
- **تسجيل الدخول** - صفحة Login
- **التسجيل** - صفحة Sign Up
- **الملف الشخصي** - معلومات المستخدم
- **مقالاتي** - المقالات المحفوظة
- **الإعدادات** - إعدادات الحساب

### صفحات الإدارة
- **لوحة التحكم** - الإحصائيات الرئيسية
- **إدارة المقالات** - إنشاء وتحرير المقالات
- **إدارة الفئات** - إدارة التصنيفات
- **إدارة الوسوم** - إدارة الوسوم
- **التعليقات** - إدارة التعليقات
- **المستخدمون** - إدارة المستخدمين
- **التحليلات** - التقارير والإحصائيات

## 🔑 API الرئيسية

### Posts API
- `GET /api/posts` - الحصول على المقالات
- `GET /api/posts/:id` - الحصول على مقالة
- `POST /api/posts` - إنشاء مقالة
- `PUT /api/posts/:id` - تحديث مقالة
- `DELETE /api/posts/:id` - حذف مقالة

### Comments API
- `GET /api/posts/:id/comments` - التعليقات
- `POST /api/comments` - إضافة تعليق
- `PUT /api/comments/:id` - تحديث تعليق
- `DELETE /api/comments/:id` - حذف تعليق

### Categories API
- `GET /api/categories` - الحصول على الفئات
- `POST /api/categories` - إنشاء فئة
- `PUT /api/categories/:id` - تحديث فئة
- `DELETE /api/categories/:id` - حذف فئة

### Analytics API
- `GET /api/analytics/posts/:id` - إحصائيات المقالة
- `GET /api/analytics/dashboard` - إحصائيات لوحة التحكم

## 🔐 الأمان

- JWT Authentication
- CSRF Protection
- XSS Prevention
- SQL Injection Protection
- Rate Limiting
- GDPR Compliance

## 📱 المميزات المتقدمة

- 🌙 Dark Mode
- 📱 Responsive Design
- ⚡ Performance Optimization
- 🔍 SEO Friendly
- 🌍 Multilingual Support (EN, AR)
- 📊 Advanced Analytics
- 🔔 Real-time Notifications
- 💾 Auto-save Drafts

## 📄 الترخيص

MIT License

## 👥 المساهمة

المساهمات مرحب بها! يرجى قراءة CONTRIBUTING.md للمزيد من التفاصيل.

## 📞 التواصل

- 📧 Email: support@blogplatform.com
- 🐛 Bug Reports: GitHub Issues
- 💬 Discussions: GitHub Discussions

---

**جاهز للبدء؟ ابدأ الآن مع Blog Platform! 🚀**
