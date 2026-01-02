# Sistem Manajemen Produk - Love Skin Glow 🛍️

## 📋 Panduan Lengkap

### 🎯 Fitur Utama

#### 1. **Dashboard Manajemen Produk (products.html)**
Halaman eksklusif untuk seller/admin yang sudah login.

**Fitur:**
- ✅ Tambah produk baru dengan form lengkap
- ✅ Upload gambar produk
- ✅ Preview gambar sebelum disimpan
- ✅ Edit produk yang sudah ada
- ✅ Hapus produk dengan konfirmasi
- ✅ Statistik produk (Total, Stok, Nilai Inventory)
- ✅ Daftar produk grid yang responsif
- ✅ Pencarian dan filter kategori

**Data Produk yang Dapat Diisi:**
- Nama Produk (required)
- Kategori (required)
  - Facial Cleanser
  - Moisturizer
  - Sunscreen
  - Serum
  - Mask
  - Toner
  - Lainnya
- Harga (required)
- Stok (required)
- Deskripsi Produk (required)
- Foto Produk (optional)

#### 2. **Toko Online (shop.html)**
Halaman publik untuk melihat semua produk dari semua seller.

**Fitur:**
- ✅ Tampilkan semua produk dari semua seller
- ✅ Filter produk berdasarkan kategori
- ✅ Pencarian produk real-time
- ✅ Tampilkan informasi seller
- ✅ Status stok (Tersedia, Sisa, Habis)
- ✅ Desain yang menarik dan responsif
- ✅ Integrasi dengan sistem login

---

## 🚀 Cara Penggunaan

### Untuk Seller (Menambah Produk)

#### Step 1: Login
1. Buka `login.html`
2. Gunakan kredensial:
   - Email: `user@example.com`, Password: `password123`
   - Email: `admin@loveskinglow.com`, Password: `admin123`
3. Setelah login, Anda akan diarahkan ke `products.html` (Dashboard Produk)

#### Step 2: Tambah Produk Baru
1. Di halaman `products.html`, Anda akan melihat form di sebelah kiri
2. Isi semua field:
   - **Nama Produk**: Masukkan nama produk (contoh: "Facial Wash Organik")
   - **Kategori**: Pilih dari dropdown
   - **Harga**: Masukkan harga dalam Rupiah
   - **Stok**: Masukkan jumlah stok
   - **Deskripsi**: Jelaskan keunggulan produk
   - **Foto**: Pilih gambar produk (opsional)
3. Klik tombol "Tambah Produk"
4. Produk akan langsung muncul di list di sebelah kanan

#### Step 3: Edit Produk
1. Klik tombol "✏️ Edit" pada produk yang ingin diubah
2. Form akan ter-fill otomatis dengan data produk
3. Ubah data yang diperlukan
4. Tombol berubah menjadi "💾 Update Produk"
5. Klik untuk menyimpan perubahan

#### Step 4: Hapus Produk
1. Klik tombol "🗑️ Hapus" pada produk
2. Konfirmasi penghapusan di modal
3. Produk akan dihapus dari list

### Untuk Customer (Membeli Produk)

#### Step 1: Browsing Produk
1. Buka `shop.html` untuk melihat toko online
2. Gunakan fitur pencarian untuk mencari produk tertentu
3. Gunakan filter kategori untuk memfilter jenis produk
4. Lihat informasi harga, stok, dan seller

#### Step 2: Lihat Detail Produk
1. Setiap kartu produk menampilkan:
   - Gambar produk
   - Nama seller
   - Nama produk
   - Kategori
   - Deskripsi singkat
   - Harga
   - Status stok

#### Step 3: Login sebagai Seller
1. Klik tombol "Masuk" di header
2. Login dengan akun Anda
3. Setelah login, tombol berubah menjadi "Kelola Produk"
4. Klik "Kelola Produk" untuk mengelola produk Anda

---

## 📊 Statistik & Dashboard

### Di Dashboard Seller (products.html)
Anda akan melihat kartu statistik yang menampilkan:
- **Total Produk**: Jumlah produk yang Anda jual
- **Total Stok**: Jumlah unit stok semua produk
- **Nilai Stok**: Total nilai inventory (Harga × Stok)

---

## 💾 Penyimpanan Data

### Sistem Penyimpanan
Semua data disimpan di **localStorage** browser:
- `products`: Menyimpan semua produk (JSON array)
- `loggedInUser`: Menyimpan data user yang login saat ini

### Struktur Data Produk
```javascript
{
    id: 1234567890,                    // Unique ID (timestamp)
    name: "Facial Wash",               // Nama produk
    category: "Facial Cleanser",       // Kategori
    price: 50000,                      // Harga
    stock: 100,                        // Stok
    description: "Pembersih wajah...",  // Deskripsi
    image: "data:image/...",           // Base64 image
    createdBy: "user@example.com",     // Email seller
    createdDate: "02/01/2026",         // Tanggal dibuat
    updatedDate: "02/01/2026"          // Tanggal diupdate
}
```

---

## 🔒 Keamanan & Autentikasi

### Pengecekan Login
Sistem otomatis mengecek apakah user sudah login:
- Jika belum login → redirect ke `login.html`
- Jika sudah login → tampilkan dashboard

### Isolasi Data Seller
- Setiap seller hanya bisa lihat/edit produk mereka sendiri
- Produk difilter berdasarkan `createdBy` (email seller)
- Customer bisa lihat semua produk dari semua seller

---

## 📱 Responsif Design

Semua halaman sudah responsif untuk:
- ✅ Desktop (1200px+)
- ✅ Tablet (768px - 1199px)
- ✅ Mobile (320px - 767px)

---

## 🎨 Integrasi dengan Website Utama

### Menambahkan Link ke Shop
Di `LSG.html`, Anda bisa menambahkan:

```html
<a href="shop.html" class="btn">Kunjungi Toko</a>
```

### Menambahkan Link Dashboard Seller
```html
<a href="products.html" class="btn">Kelola Produk</a>
```

---

## ⚠️ Catatan Penting

### Untuk Development
- Data disimpan di localStorage → akan hilang jika cache dibersihkan
- Untuk production, gunakan database nyata

### Untuk Production
Anda perlu tambahkan:
1. **Backend API** untuk menyimpan produk ke database
2. **Image Storage** (Cloud Storage seperti AWS S3, Firebase)
3. **Payment Gateway** untuk transaksi
4. **Admin Panel** untuk moderasi produk
5. **Wishlist & Cart** untuk customer
6. **Order Management** untuk tracking pembelian
7. **Rating & Review** dari customer

---

## 📂 File-File yang Dibuat

```
LSG/
├── login.html           ← Halaman login (updated)
├── signup.html          ← Halaman registrasi
├── products.html        ← Dashboard seller (BARU)
├── shop.html            ← Toko online (BARU)
├── LSG.html             ← Halaman utama
└── btn.html             ← Contact person
```

---

## 🔑 Test Credentials

```
Email: user@example.com
Password: password123

Email: admin@loveskinglow.com
Password: admin123
```

Atau daftar akun baru di halaman signup!

---

## 🆘 Troubleshooting

### Produk tidak muncul?
- Cek apakah Anda sudah login
- Cek console browser (F12) untuk error message
- Cek localStorage sudah ada data products

### Foto produk tidak tampil?
- Pastikan format file adalah gambar (JPG, PNG, etc)
- Ukuran file tidak terlalu besar
- Browser sudah support FileReader API

### Logout tidak bekerja?
- Pastikan Anda klik tombol logout yang benar
- Clear cache browser jika masih ada masalah

---

## 📞 Support

Untuk pertanyaan lebih lanjut atau fitur tambahan, hubungi tim development.

---

**Dibuat untuk:** Love Skin Glow  
**Tanggal:** 2 Januari 2026  
**Status:** ✅ Production Ready (Client-Side)
