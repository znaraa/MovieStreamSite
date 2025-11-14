# Кино Сайт

**Төслийн тайлбар**

Кино Сайт нь React + TypeScript + Supabase ашиглан бүтээсэн бүрэн мэргэжлийн стрийминг платформ юм. Netflix-стайл дизайнтай, монгол интерфэйстэй, role-based access control (User / Member / Admin), Google OAuth (Gmail) болон Email/Password нэвтрэлт, MEGA.nz / YouTube / Google Drive видео дэмжлэгтэй.

---

## Шаардлагатай технологи

* React (TypeScript)
* Supabase (Auth, Database, Storage)
* MEGA.nz, YouTube, Google Drive embed/stream
* Material-UI, Iconify
* Tailwind (эсвэл өөр CSS систем) — интерфэйс тохиргооно

---

## Гол боломжууд (Highlights)

* 🎥 **Кино стрийм** — YouTube, MEGA.nz, Google Drive дэмжлэг
* 👤 **OAuth & Auth** — Email/Password болон Google (Gmail)
* 👑 **Member систем** — Үнэгүй (Free) болон Premium (Member) контентын ялгана
* 🔐 **Role-based access control** — User, Member, Admin
* ⚡ **Админ панел** — Кино удирдлага (CRUD), Хэрэглэгч удирдлага, Role тохиргоо
* ✅ **Supabase Storage** — Thumbnail болон зургийн upload (5MB max зөвлөмж)
* ✅ **Video URL auto-formatting** — YouTube/MEGA/Drive URL-уудыг автоматаар форматлана
* ✅ **Responsive Netflix-style дизайн** — Dark theme, Hero section, Grid with hover effects
* ✅ **Secure RLS policies** — Supabase дээрх RLS (Row Level Security)
* ✅ **Delete protection & Lock/Unlock toggle** — Алдаанаас сэргийлэх хамгаалалт

---

## Файлууд ба баримт бичиг

* `README.md` — Товч танилцуулга
* `INSTALLATION_GUIDE.md` — Database-ийн SQL командууд (админ үүсгэх, default roles, RLS гэх мэт)

---

## Суурилуулалт (Install)

**1. Репозиторыг clone хийх**

```bash
git clone <your-repo-url>
cd <project-folder>
```

**2. Шаардлагатай package-уудыг суулгах**

```bash
# npm
npm install
```

**3. .env файл тохируулах**

`./.env` файлд дараах тохиргоог оруулна (дараах нь жишээ):

```env
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
```

> **Анхаарах:** Service role key-г нууцалж, public репозиторт оруулж болохгүй.

---

## Хөгжүүлэлтийн сервер

```bash
# dev server
npm run dev
```

---

## Database setup

`DATABASE_SETUP.md` дотор SQL командууд байрлана. Жишээ: админ эрх өгөх SQL

```sql
-- Админыг үүсгэх (жишээ)
UPDATE users
SET role = 'admin'
WHERE email = 'admin@test.com';
```

**Тухайн файлыг ажиллуулж, RLS policy-уудыг тохируулна**.

---

## Authentication & OAuth

* Email/Password бүртгэл (Supabase Auth)
* Google OAuth (Gmail) тохиргоо — Google Cloud Console дээр Client ID/Secret үүсгээд `.env` руу оруулна.
* Тохиргоо хугацаанд Supabase дээр Redirect URL-ийг зөв оруулах

---

## Админ Панел (Admin Panel)

Админ нь дараахыг хийнэ:

* Кино нэмэх / засах / устгах (CRUD)
* Киног Lock/Unlock хийх (Member-д зориулсан контентыг хаах/нээх)
* Хэрэглэгчийн ролийг өөрчлөх (User/Member/Admin)
* Delete protection — устгах үед баталгаажуулалт

---

## Видео & Зураг upload

* Thumbnail upload — Supabase Storage, 5MB max (зөвлөмж)
* Video URL-уудыг автоматаар форматлах -> YouTube embed, MEGA.nz direct link эсвэл Google Drive embed
* Responsive video player (mobile friendly)

---

## Дизайн, UX

* Netflix-стайл dark theme
* Hero section-тон гол кино харуулах
* Grid layout with hover effects, smooth animations
* Material-UI компонентууд, Iconify (2000+ icons)
* Монгол хэл интерфэйс (бүх текст монголчилсон)

---

## Security & Policies

* Supabase RLS (Row Level Security) тохируулна
* Role-based access control — frontend болон backend дээр шалгана
* Service role key-ийг зөв хамгаална

---

## Түгээх / Deploy хийх

* Supabase-ийг backend болгон ашиглана
* Frontend-ийг Vercel / Netlify зэрэгт байршуулна
* Environment variables-ыг продакшн орчинд тохируулна

---

## Аюулгүй байдлын сануулга

* .env файлыг репозиторт commit хийхгүй явуулна (.gitignore-д нэмнэ)
* Service role key-г алдаж дэлгэхгүй (өрсөлдөгч, хакерын эсрэг хамгаал)

---

**Баярлалаа!**
