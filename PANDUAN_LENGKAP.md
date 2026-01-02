# 📚 PANDUAN LENGKAP SISTEM LOGIN & MANAJEMEN PRODUK
## Love Skin Glow - Integrated E-Commerce System

---

## 🎯 Ringkasan Fitur

Sistem ini menyediakan:
1. ✅ **Sistem Login & Registrasi** (login.html, signup.html)
2. ✅ **Dashboard Manajemen Produk** untuk seller (products.html)
3. ✅ **Toko Online** untuk customer (shop.html)
4. ✅ **Integrasi penuh** dengan website utama (LSG.html)

---

## 📁 STRUKTUR FILE

```
LSG/
├── index.html               (atau LSG.html - halaman utama)
├── login.html               ← Halaman login
├── signup.html              ← Halaman registrasi
├── products.html            ← Dashboard seller (HANYA untuk yang sudah login)
├── shop.html                ← Toko online (public, semua orang bisa lihat)
├── btn.html                 ← Contact Person
├── README_LOGIN.md          ← Dokumentasi login
├── README_PRODUCTS.md       ← Dokumentasi produk
└── PANDUAN_LENGKAP.md       ← File ini
```

---

## 🚀 ALUR PENGGUNAAN

### UNTUK CUSTOMER (Pembeli)

```
Buka LSG.html
    ↓
Klik tombol "🛍️ Toko" di navbar
    ↓
Halaman shop.html terbuka → bisa lihat semua produk dari semua seller
    ↓
Cari/filter produk yang diinginkan
    ↓
Untuk menjadi seller → klik "Masuk" atau "Daftar"
```

### UNTUK SELLER (Penjual)

```
1. LOGIN/DAFTAR
   ├─ Buka login.html
   ├─ Jika belum punya akun → klik "Daftar di sini" → isi form signup.html
   └─ Jika sudah → masukkan email & password

2. SETELAH LOGIN
   ├─ Otomatis diarahkan ke products.html (Dashboard Seller)
   ├─ Di navbar akan muncul nama Anda dan tombol "Kelola Produk"
   └─ Nama dan email disimpan di sessionStorage

3. MENGELOLA PRODUK
   ├─ Form di sebelah kiri → input data produk
   ├─ Sebelah kanan → daftar produk Anda
   ├─ Setiap produk bisa di-edit atau dihapus
   └─ Statistik otomatis terupdate

4. MELIHAT TOKO ONLINE
   ├─ Buka shop.html atau klik "🛍️ Toko" di navbar
   ├─ Bisa lihat semua produk dari semua seller
   └─ Data terhubung langsung dengan produk yang Anda upload
```

---

## 🔐 SISTEM LOGIN

### Akun Test yang Sudah Ada

```
Akun 1:
  Email: user@example.com
  Password: password123
  Nama: John Doe

Akun 2:
  Email: admin@loveskinglow.com
  Password: admin123
  Nama: Administrator
```

### Membuat Akun Baru

1. Buka `login.html`
2. Klik **"Daftar di sini"** atau buka `signup.html` langsung
3. Isi semua field:
   - Nama Depan
   - Nama Belakang
   - Email
   - Nomor Telepon
   - Kata Sandi (minimal 8 karakter)
   - Konfirmasi Kata Sandi
   - Setujui Syarat & Ketentuan
4. Klik **"Daftar"**
5. Akun Anda akan tersimpan di localStorage
6. Anda bisa langsung login dengan akun baru

---

## 📦 MENAMBAH PRODUK

### Fitur Produk yang Dapat Diisi

| Field | Tipe | Wajib | Keterangan |
|-------|------|-------|-----------|
| Nama Produk | Text | ✅ | Contoh: "Facial Wash Organik" |
| Kategori | Select | ✅ | 7 kategori tersedia |
| Harga | Number | ✅ | Dalam Rupiah |
| Stok | Number | ✅ | Jumlah unit |
| Deskripsi | Textarea | ✅ | Keunggulan produk |
| Foto | File | ❌ | JPG/PNG, auto-resize |

### Kategori Produk yang Tersedia

1. Facial Cleanser
2. Moisturizer
3. Sunscreen
4. Serum
5. Mask
6. Toner
7. Lainnya

### Langkah Menambah Produk

1. Login → Masuk ke `products.html`
2. Di sebelah kiri, ada form **"Tambah Produk Baru"**
3. Isi semua field (lihat tabel di atas)
4. Pilih gambar (opsional) → akan muncul preview
5. Klik **"+ Tambah Produk"**
6. Produk langsung muncul di list sebelah kanan
7. Pesan sukses akan ditampilkan

### Langkah Edit Produk

1. Di list produk, klik tombol **"✏️ Edit"**
2. Form akan ter-fill otomatis dengan data produk
3. Ubah data yang ingin diubah
4. Tombol berubah jadi **"💾 Update Produk"**
5. Klik untuk menyimpan
6. Produk akan terupdate di list

### Langkah Hapus Produk

1. Di list produk, klik tombol **"🗑️ Hapus"**
2. Modal konfirmasi akan muncul
3. Klik **"Hapus"** untuk konfirmasi
4. Produk akan dihapus dari list
5. Statistik akan terupdate otomatis

---

## 🛍️ TOKO ONLINE (shop.html)

### Fitur untuk Customer

1. **Tampilkan Semua Produk**
   - Dari semua seller
   - Grid layout responsif
   - Real-time loading

2. **Pencarian Produk**
   - Search box untuk cari nama/deskripsi
   - Real-time search (langsung update saat mengetik)

3. **Filter Kategori**
   - Tombol filter kategori
   - Bisa kombinasi dengan search
   - Menampilkan "Semua" atau kategori spesifik

4. **Informasi Produk**
   - Foto produk
   - Nama produk
   - Nama seller
   - Kategori
   - Deskripsi singkat
   - Harga
   - Status stok (Tersedia/Sisa X/Habis)

5. **Integrasi Login**
   - Jika belum login → tombol "Masuk"
   - Jika sudah login → tombol "Kelola Produk" + "Logout"

---

## 💾 PENYIMPANAN DATA

### Menggunakan localStorage Browser

Semua data disimpan di **localStorage**:

```javascript
// Data Produk
localStorage.getItem('products')    // Array JSON produk

// Data Registrasi Baru
localStorage.getItem('registeredUsers')  // Array JSON user baru

// Data Login Saat Ini (Session)
sessionStorage.getItem('loggedInUser')   // Object JSON user yang login
```

### Struktur Data Produk

```javascript
{
    id: 1704196800000,                     // Unique ID (timestamp)
    name: "Facial Wash",                   // Nama produk
    category: "Facial Cleanser",           // Kategori
    price: 50000,                          // Harga dalam Rp
    stock: 100,                            // Jumlah stok
    description: "Pembersih wajah...",     // Deskripsi lengkap
    image: "data:image/png;base64,...",    // Base64 encoded image
    createdBy: "user@example.com",         // Email seller
    createdDate: "02/01/2026",             // Tanggal dibuat
    updatedDate: "02/01/2026"              // Tanggal diupdate
}
```

### Struktur Data User Terdaftar

```javascript
{
    firstName: "John",
    lastName: "Doe",
    email: "john@example.com",
    phone: "+62 812 3456 7890",
    password: "password123",               // (tidak di-hash di client-side)
    registeredDate: "02/01/2026"
}
```

---

## 🔒 KEAMANAN

### Fitur Keamanan Saat Ini

✅ **Password Strength Indicator**
- Indikator kekuatan password saat registrasi
- Warna (Lemah/Sedang/Kuat)

✅ **Validasi Input**
- Email format validation
- Password minimum 8 karakter
- Konfirmasi password harus sama

✅ **Autentikasi Sederhana**
- Cek login status sebelum buka halaman terbatas
- Session management dengan sessionStorage

✅ **Isolasi Data Seller**
- Setiap seller hanya bisa lihat produk mereka sendiri
- Customer bisa lihat semua produk

### ⚠️ PERHATIAN: Untuk Production

Ini adalah **prototype** client-side. Untuk production, Anda HARUS:

1. **Hash Password** (jangan simpan plain text)
   - Gunakan bcrypt atau argon2
   - Hash di backend, bukan frontend

2. **Backend/Database** 
   - Pindahkan data ke server
   - Gunakan SQL atau NoSQL database
   - Jangan simpan data sensitif di client

3. **HTTPS/SSL**
   - Enkripsi komunikasi client-server
   - Wajib untuk production

4. **Authentication Tokens**
   - Gunakan JWT atau session tokens
   - Set token expiration
   - Refresh token mechanism

5. **Security Headers**
   - Content-Security-Policy
   - X-Frame-Options
   - X-Content-Type-Options
   - Dll

6. **Rate Limiting**
   - Batasi login attempts
   - Prevent brute force attacks

7. **Input Sanitization**
   - Bersihkan input dari XSS
   - Validasi di backend juga

8. **Image Upload Security**
   - Validasi file type
   - Scan virus
   - Resize/compress image
   - Simpan di cloud storage (S3, GCS, dll)

---

## 📱 RESPONSIF DESIGN

Semua halaman sudah responsif untuk:

✅ **Desktop** (1200px ke atas)
- Navbar horizontal
- Grid 3-4 kolom

✅ **Tablet** (768px - 1199px)
- Navbar adaptif
- Grid 2-3 kolom

✅ **Mobile** (320px - 767px)
- Navbar mobile-friendly
- Grid single/double column
- Button ukuran optimal

---

## 🎨 INTEGRASI DI LSG.html

### Navbar Update
- Tombol "🛍️ Toko" untuk ke halaman shop
- Tombol "Masuk" / "Daftar" jika belum login
- Jika sudah login → tampilkan nama + "Kelola Produk" + "Logout"

### Script untuk Check Login Status

```javascript
window.addEventListener('load', () => {
    const loggedInUser = sessionStorage.getItem('loggedInUser');
    const authNav = document.getElementById('authNav');

    if (loggedInUser) {
        const user = JSON.parse(loggedInUser);
        // Tampilkan nama user dan tombol logout
        // Update navbar sesuai status login
    }
});
```

---

## 🧪 TESTING CHECKLIST

### Test Login
- [ ] Login dengan akun test
- [ ] Lihat pesan error untuk email/password salah
- [ ] Fitur "Ingat Saya" (Remember Me)
- [ ] Fitur "Lupa Password"
- [ ] Logout dan kembali ke login

### Test Registrasi
- [ ] Daftar akun baru
- [ ] Validasi form (required fields)
- [ ] Password strength indicator
- [ ] Cek konfirmasi password
- [ ] Cek syarat & ketentuan wajib disetujui
- [ ] Cek duplicate email detection

### Test Dashboard Produk
- [ ] Login → otomatis ke products.html
- [ ] Tambah produk baru
- [ ] Upload gambar → preview tampil
- [ ] Edit produk → form ter-fill
- [ ] Hapus produk → konfirmasi modal
- [ ] Statistik terupdate

### Test Toko Online
- [ ] Buka shop.html tanpa login
- [ ] Lihat semua produk semua seller
- [ ] Search produk by name
- [ ] Filter by kategori
- [ ] Kombinasi search + filter
- [ ] Status stok tampil benar (Tersedia/Sisa/Habis)

### Test Responsif
- [ ] Desktop (1920px)
- [ ] Tablet (768px)
- [ ] Mobile (375px)
- [ ] Semua tombol clickable di mobile

### Test Data Persistence
- [ ] Refresh halaman → data tetap
- [ ] Close browser → data tetap
- [ ] Buka di tab baru → data sama
- [ ] Clear localStorage → data hilang (expected)

---

## 🐛 TROUBLESHOOTING

### Masalah: "Halaman redirect ke login"
**Solusi:**
- Pastikan Anda sudah login
- Cek sessionStorage apakah ada data 'loggedInUser'
- Clear cache dan login ulang

### Masalah: "Produk tidak muncul di shop"
**Solusi:**
- Pastikan produk sudah ditambahkan di products.html
- Refresh halaman shop
- Cek console browser (F12) untuk error
- Cek localStorage ada data 'products'

### Masalah: "Foto produk tidak tampil"
**Solusi:**
- Pastikan format file adalah image (JPG, PNG, GIF)
- Ukuran file tidak terlalu besar
- Browser support FileReader API

### Masalah: "Data hilang setelah clear cache"
**Solusi:**
- Ini expected behavior karena data di localStorage
- Untuk production, gunakan database
- Export data sebelum clear cache

### Masalah: "Tombol logout tidak bekerja"
**Solusi:**
- Pastikan Anda klik tombol logout yang benar
- Cek browser support onclick function
- Gunakan F12 untuk debug

---

## 📈 FITUR TAMBAHAN (Future)

Ini adalah saran fitur yang bisa ditambahkan:

1. **Wishlist** - Pelanggan bisa save produk favorit
2. **Shopping Cart** - Keranjang belanja
3. **Order Management** - Tracking pesanan
4. **Payment Gateway** - Pembayaran online
5. **Rating & Review** - Rating produk dari customer
6. **Message System** - Chat antara seller-buyer
7. **Admin Panel** - Moderasi produk
8. **Analytics Dashboard** - Statistik penjualan
9. **Inventory Alert** - Notif stok habis
10. **Email Notification** - Kirim email ke customer

---

## 📞 SUPPORT

Jika ada pertanyaan atau menemukan bug:
1. Cek dokumentasi di file README
2. Cek console browser untuk error message
3. Hubungi tim development

---

## 📝 CHANGELOG

### v1.0 (2 Januari 2026)
- ✅ Sistem login & registrasi
- ✅ Dashboard manajemen produk
- ✅ Toko online publik
- ✅ Integrasi dengan website utama
- ✅ Responsif design

---

**Created for:** Love Skin Glow  
**Date:** January 2, 2026  
**Status:** ✅ Production Ready (Client-Side)

**Note:** Ini adalah aplikasi client-side prototype. Untuk production, implementasikan backend dan database yang proper.

---

**Happy Selling! 💄✨**
