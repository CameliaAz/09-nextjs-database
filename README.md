This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

Judul Project: 09-nextjs-database
Hasil Deploy: ![image](https://github.com/user-attachments/assets/876f2222-caaf-4f58-ac9e-628b6b157529)

Pembelajaran:
Langkah-langkah utama dalam proses deploy.
Pemahaman baru atau best practice yang diperoleh dari jobsheet ini.

# Konfigurasi Basis Data dengan Vercel Postgres

## Hasil Basis Data
![Hasil Basis Data] ![image](https://github.com/user-attachments/assets/efe0b1f6-d44f-4cfb-bcfc-828048fa2a9e)

## Pembelajaran
Selama proses konfigurasi basis data ini, saya mempelajari beberapa hal penting:
- **Pemilihan Region Basis Data**: Memahami bahwa region harus dipilih sebelum proses inisialisasi agar tidak perlu konfigurasi ulang.
- **Keamanan Konfigurasi Rahasia**: Menggunakan file `.env` dan memastikan `.env` tercantum di `.gitignore` agar informasi rahasia tidak terekspos ke publik.
- **Instalasi SDK**: Mempelajari cara menginstal dan menggunakan Vercel Postgres SDK untuk berinteraksi dengan basis data.

## Melakukan Seed ke Basis Data
![Hasil Seed ke Basis Data] ![WhatsApp Image 2024-11-10 at 00 46 01_cee90922](https://github.com/user-attachments/assets/4fd564ef-d4bf-40e6-aa75-f59e409d3620)

## Pembelajaran
Setelah menjalankan perintah `npm run seed`, data berhasil disisipkan ke dalam tabel `users`, `customers`, `invoices`, dan `revenue`. Berikut adalah beberapa hal yang saya pelajari:
- Skrip `seed.js` menggunakan data dari file `data.js` dan menyisipkan data tersebut ke dalam basis data PostgreSQL.
- Saya harus memastikan bahwa modul `dotenv` dan `bcrypt` terinstal dengan benar agar skrip dapat dijalankan tanpa error.
- Setelah seed berhasil dijalankan, saya memverifikasi data di **Vercel Data** dan memastikan bahwa data yang dimasukkan sudah sesuai.

## Menjelajah Basis Data dan Menjalankan Query SQL
![Hasil menjelajah basis data dan menjalankan query] ![image](https://github.com/user-attachments/assets/fa97ed4d-66a6-48fd-95c8-899dc55b22ea)
![image](https://github.com/user-attachments/assets/26334b2e-e700-4769-99a1-8a35c066d9ac)


Setelah data disisipkan, saya menjelajahi basis data melalui Vercel dan menjalankan beberapa query SQL. Berikut adalah hasil query yang saya jalankan:

1. **Query untuk mencari invoice dengan amount 666:**
   ```sql
   SELECT invoices.amount, customers.name
   FROM invoices
   JOIN customers ON invoices.customer_id = customers.id
   WHERE invoices.amount = 666;
Hasilnya menunjukkan pelanggan yang memiliki invoice dengan jumlah 666, yaitu:
Pelanggan: Evil Rabbit
Jumlah: 666

## W09: Jawaban soal 5
![image](https://github.com/user-attachments/assets/ae7ac137-bd40-4b54-85ff-6e1e301a70e3)

link vercel : nextjs-database-alpha.vercel.app

# Laporan Jawaban Soal 6
![image](https://github.com/user-attachments/assets/40aa0366-7e3d-4a45-bde0-692ea484469a)


## Deskripsi
Pada soal ini, saya diminta untuk menghapus komentar pada komponen `RevenueChart` yang terdapat di file `src/app/page.tsx`, kemudian melakukan push ke GitHub dan melakukan deploy aplikasi ke Vercel. Setelah itu, saya mengambil screenshot tampilan aplikasi untuk melengkapi laporan ini.


## Apa yang Dipelajari
- **Penggunaan komponen di Next.js**: Saya belajar bagaimana cara memodifikasi tampilan dengan mengaktifkan atau menonaktifkan komponen tertentu dengan menghapus komentar pada komponen.
- **Proses Deployment**: Saya juga belajar tentang bagaimana perubahan di GitHub akan otomatis dideteksi dan dideploy oleh Vercel tanpa memerlukan konfigurasi manual lebih lanjut.
- **Debugging dan Verifikasi Tampilan**: Selama proses ini, saya memverifikasi apakah komponen ditampilkan dengan baik dan bagaimana cara memeriksa konsol browser untuk mencari potensi masalah.
