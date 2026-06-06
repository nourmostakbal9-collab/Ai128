# Blog Platform Backend - API Documentation

## 🚀 تشغيل الخادم

### المتطلبات
- Node.js 18+
- PostgreSQL 16
- npm أو yarn

### خطوات التثبيت

```bash
# تثبيت الاعتماديات
npm install

# نسخ ملف البيئة
cp .env.example .env.local

# تشغيل الخادم
npm run dev
```

الخادم سيعمل على: **http://localhost:3000**

---

## 📚 API Endpoints

### 🔐 المصادقة (Auth)

#### تسجيل حساب جديد
```http
POST /api/auth/register
Content-Type: application/json

{
  "email": "user@example.com",
  "username": "username",
  "password": "password123"
}
```

**الرد:**
```json
{
  "user": {
    "id": 1,
    "email": "user@example.com",
    "username": "username",
    "createdAt": "2026-06-06T21:00:00Z"
  },
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

#### تسجيل الدخول
```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "password123"
}
```

---

### 👤 المستخدمون (Users)

#### الحصول على ملف المستخدم
```http
GET /api/users/profile
Authorization: Bearer {token}
```

**الرد:**
```json
{
  "id": 1,
  "email": "user@example.com",
  "username": "username",
  "avatar": null,
  "bio": null,
  "createdAt": "2026-06-06T21:00:00Z"
}
```

---

### 📝 المقالات (Posts)

#### الحصول على جميع المقالات المنشورة
```http
GET /api/posts
```

**الرد:**
```json
[
  {
    "id": 1,
    "title": "عنوان المقالة",
    "slug": "article-slug",
    "content": "محتوى المقالة...",
    "excerpt": "ملخص المقالة",
    "status": "published",
    "viewCount": 150,
    "publishedAt": "2026-06-06T21:00:00Z",
    "author": {
      "id": 1,
      "username": "author_name",
      "avatar": null
    },
    "category": {
      "id": 1,
      "name": "التقنية"
    }
  }
]
```

#### الحصول على مقالة واحدة
```http
GET /api/posts/:id
```

#### إنشاء مقالة جديدة
```http
POST /api/posts
Authorization: Bearer {token}
Content-Type: application/json

{
  "title": "عنوان المقالة",
  "content": "محتوى المقالة...",
  "excerpt": "ملخص المقالة",
  "slug": "article-slug",
  "categoryId": 1
}
```

#### تحديث مقالة
```http
PUT /api/posts/:id
Authorization: Bearer {token}
Content-Type: application/json

{
  "title": "عنوان جديد",
  "content": "محتوى جديد",
  "status": "published"
}
```

#### حذف مقالة
```http
DELETE /api/posts/:id
Authorization: Bearer {token}
```

---

### 📂 الفئات (Categories)

#### الحصول على جميع الفئات
```http
GET /api/categories
```

**الرد:**
```json
[
  {
    "id": 1,
    "name": "التقنية",
    "slug": "technology",
    "description": "مقالات عن التقنية والبرمجة",
    "color": "#FF5733",
    "createdAt": "2026-06-06T21:00:00Z"
  }
]
```

#### إنشاء فئة جديدة
```http
POST /api/categories
Content-Type: application/json

{
  "name": "التقنية",
  "slug": "technology",
  "description": "مقالات عن التقنية",
  "color": "#FF5733"
}
```

---

### 💬 التعليقات (Comments)

#### الحصول على تعليقات المقالة
```http
GET /api/comments/post/:postId
```

**الرد:**
```json
[
  {
    "id": 1,
    "content": "تعليق رائع!",
    "status": "approved",
    "likes": 5,
    "createdAt": "2026-06-06T21:00:00Z",
    "author": {
      "id": 2,
      "username": "commenter",
      "avatar": null
    }
  }
]
```

#### إضافة تعليق
```http
POST /api/comments
Authorization: Bearer {token}
Content-Type: application/json

{
  "content": "تعليق رائع!",
  "postId": 1
}
```

---

## 🔒 الأمان

جميع الـ Endpoints المحمية تتطلب رمز JWT في رأس الطلب:

```
Authorization: Bearer <token>
```

---

## ❌ رموز الأخطاء

| الرمز | المعنى |
|------|--------|
| 200 | نجح ✅ |
| 400 | طلب غير صحيح |
| 401 | غير مصرح (تحتاج للدخول) |
| 403 | مرفوع (ليس لديك صلاحية) |
| 404 | غير موجود |
| 500 | خطأ في الخادم |

---

## 📖 أمثلة استخدام

### مثال: إنشاء مقالة

```bash
curl -X POST http://localhost:3000/api/posts \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "مقالتي الأولى",
    "content": "محتوى رائع هنا...",
    "excerpt": "ملخص قصير",
    "slug": "my-first-post",
    "categoryId": 1
  }'
```

### مثال: التسجيل

```bash
curl -X POST http://localhost:3000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{
    "email": "user@example.com",
    "username": "myusername",
    "password": "securepass123"
  }'
```

---

## 🛠️ متغيرات البيئة

انسخ `.env.example` إلى `.env.local` وعدّل القيم:

```env
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=your_password
DB_NAME=blog_db
JWT_SECRET=your-secret-key
PORT=3000
```

---

**جاهز للبدء! 🚀**
