# CreativeTech

Next.js 14 (App Router) + Supabase + Tailwind + komponen gaya shadcn/ui.

## Menjalankan
1. `npm install`
2. Buat proyek di Supabase, lalu jalankan isi `supabase/schema.sql` di **SQL Editor**.
3. Salin `.env.example` menjadi `.env.local`, isi URL, anon key, dan service role key (Project Settings → API).
4. `npm run dev` lalu buka http://localhost:3000
5. Daftar lewat `/register`, lalu jadikan akun itu admin di SQL Editor:
   `update profiles set role = 'admin' where email = 'emailanda@contoh.com';`
   Setelah itu admin bisa menambah desainer dan user lain lewat menu **User Management**.

## Peran
- Semua akun baru berperan `user`. Hanya admin yang bisa mengubah peran (menu User Management).
- Hak akses dijaga di database lewat Row Level Security, bukan hanya di tampilan.

## Deploy ke Vercel
Import repo, isi tiga environment variable di atas (service role key tanpa awalan `NEXT_PUBLIC_`), lalu deploy.
Di Supabase → Authentication → URL Configuration, tambahkan domain Vercel Anda.
Jika ingin pendaftaran langsung masuk tanpa konfirmasi email, matikan "Confirm email" di Authentication → Providers → Email.
