# ☠️ ESCNOR Academy — دليل الإعداد الكامل

**Code In Silence • Run The System ⚡**

---

## 📁 هيكل الملفات

```
escnor-academy/
├── landing.html    ← الصفحة التعريفية (الأولى)
├── dashboard.html  ← لوحة التعلم (بعد الدخول)
├── vercel.json     ← إعدادات Vercel
├── sitemap.xml     ← خريطة الموقع لـ Google
├── robots.txt      ← إعدادات محركات البحث
└── README.md       ← هذا الملف
```

---

## 🔄 كيف يعمل الموقع

```
المستخدم ← landing.html ← يوافق الشروط ← Google Login
                 ↓
           dashboard.html ← يتعلم الدروس
                 ↓
     لو moreand458@gmail.com ← لوحة التحكم
```

---

## 🚀 النشر على Vercel

1. ارفع الملفات على GitHub
2. روح vercel.com ← Import Project
3. اختار الـ Repo ← Deploy ✅

---

## 🔥 إعداد Firebase

### تفعيل Google Sign-In:
Authentication → Sign-in method → Google → Enable

### Firestore Rules:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /lessons/{lessonId} {
      allow read: if true;
      allow write: if request.auth != null && request.auth.token.email == "moreand458@gmail.com";
    }
    match /tracks/{trackId} {
      allow read: if true;
      allow write: if request.auth != null && request.auth.token.email == "moreand458@gmail.com";
    }
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
```

### إضافة Domain:
Authentication → Settings → Authorized domains → أضف رابط Vercel

---

## ⚙️ لوحة التحكم

- سجّل دخول بـ Google بإيميل: moreand458@gmail.com
- اضغط ⚙️ لوحة التحكم
- إضافة درس ← اختار المسار ← اكتب المحتوى ← نشر

### تنسيق المحتوى:
```html
<h2>عنوان</h2>
<p>نص</p>
<pre><code>كود</code></pre>
<div class="note">ملاحظة</div>
<div class="warning">تحذير</div>
<div class="tip">نصيحة</div>
```

---

## 🔍 Google Search Console

1. search.google.com/search-console
2. Add Property ← رابط موقعك
3. Sitemaps ← أضف sitemap.xml
4. URL Inspection ← Request Indexing

---

**☠️ ESCNOR — CYBER DEV 💻**
𝐂𝐨𝐝𝐞 𝐈𝐧 𝐒𝐢𝐥𝐞𝐧𝐜𝐞 • 𝐑𝐮𝐧 𝐓𝐡𝐞 𝐒𝐲𝐬𝐭𝐞𝐦 ⚡ — © ESCNOR 2025
