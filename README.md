# LYLA Food — متجر حبوب الكفير الحية

موقع المتجر (صفحة واحدة، عربي/دارجة، RTL) مستضاف على GitHub Pages.

## تشغيل محلي
```bash
python3 -m http.server 8080
# ثم افتح http://localhost:8080
```

## الملفات
```
index.html          كل شي: التصميم + السكريبت (HTML/CSS/JS بلا أي مكتبة خارجية)
images/             الصور (صور أشخاص حقيقيين + صور الكفير)
functions/          (فقط فالمستودع الأساسي) دالة تسجيل الطلبات
```

## الطلبيات
استمارة الطلب كتصيفط الطلبية لهاد الـ endpoint:
```
https://base44.app/api/apps/6ae231e376f8435c23a48922/functions/createKefirOrder
```
وكتتسجل فقاعدة البيانات (جدول `KefirOrder`) بحقول: الاسم، الهاتف، المدينة، العنوان،
العرض، الثمن، ملاحظة، الحالة (`new` / `confirmed` / `shipped` / `delivered` / `cancelled`).

## شنو تبدل قبل ما تنشر
1. **رقم الواتساب** — فآخر `index.html`، فـ `CONFIG`:
   ```js
   const CONFIG = { whatsapp: "2126XXXXXXXX", instagram: "https://instagram.com/..." };
   ```
2. **الأثمنة** — كاينة فجوج بلايص: كروت المنتجات (HTML) وفـ `<input data-price>` داخل الاستمارة،
   وزيادة فدالة `createKefirOrder` (جدول `PACKS`). خاصهم يكونو متطابقين.
3. **صور الزبناء** — بدّل الملفات هادو بصور حقيقية ديال زبنائك (نفس الأسماء، نفس القياس):
   `images/person-woman-hijab.jpg`, `images/person-man-smiling.jpg`,
   `images/person-woman-hijab-joy.jpg`, `images/person-man-portrait.jpg`.

> ملاحظة: صور الأشخاص اللي كاينة دابا هي صور فوتوغرافية حقيقية من مكتبة Pexels
> (رخصة مجانية للاستعمال التجاري)، ولكن ماشي زبناء حقيقيين ديال المتجر.
> من الأفضل تبديلها بصور ديال زبنائك ملّي تجمعهم.

## النشر (GitHub Pages)
الموقع كيتنشر أوتوماتيكيًا من الفرع `main`. أي تعديل: بدّل الملف و `git push`،
و GitHub كيعاود يبني الصفحة فـ 30-60 ثانية.
