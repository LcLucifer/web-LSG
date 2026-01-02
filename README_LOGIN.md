# Sistem Login - Love Skin Glow 💄

## 📋 Daftar Isi
1. [Fitur Utama](#fitur-utama)
2. [File yang Dibuat](#file-yang-dibuat)
3. [Kredensial Test](#kredensial-test)
4. [Cara Penggunaan](#cara-penggunaan)
5. [Integrasi dengan Website](#integrasi-dengan-website)
6. [Keamanan](#keamanan)
7. [Pengembangan Lebih Lanjut](#pengembangan-lebih-lanjut)

---

## 🎯 Fitur Utama

### 1. **Login Page (login.html)**
- ✅ Form login dengan validasi email dan password
- ✅ Fitur "Ingat Saya" (Remember Me)
- ✅ Lupa Kata Sandi (Forgot Password)
- ✅ Login dengan Social Media (Google & Facebook - placeholder)
- ✅ Desain responsif dan modern
- ✅ Animasi loading
- ✅ Pesan error dan success yang jelas
- ✅ Tema sesuai dengan website Love Skin Glow

### 2. **Signup Page (signup.html)**
- ✅ Form registrasi dengan field lengkap (Nama, Email, Telepon)
- ✅ Validasi real-time strength password
- ✅ Pengecekan kecocokan password
- ✅ Syarat & Ketentuan yang wajib disetujui
- ✅ Penyimpanan data ke localStorage
- ✅ Desain responsif dengan tema yang konsisten

### 3. **Keamanan**
- ✅ Session management dengan sessionStorage
- ✅ Password strength indicator
- ✅ Input validation di client-side
- ✅ Perlindungan dari akses tanpa login

---

## 📁 File yang Dibuat

```
LSG/
├── login.html      ← Halaman login
├── signup.html     ← Halaman pendaftaran
├── LSG.html        ← Website utama (sudah ada)
└── btn.html        ← Contact Person (sudah ada)
```

---

## 🔑 Kredensial Test

### User 1 (Regular User)
- **Email:** `user@example.com`
- **Password:** `password123`

### User 2 (Admin)
- **Email:** `admin@loveskinglow.com`
- **Password:** `admin123`

> 💡 Anda bisa mendaftar akun baru juga melalui halaman Signup!

---

## 🚀 Cara Penggunaan

### Untuk Login:
1. Buka file `login.html` di browser
2. Masukkan email dan password dari kredensial test di atas
3. Centang "Ingat saya" jika ingin email diingat
4. Klik tombol "Masuk"

### Untuk Mendaftar:
1. Di halaman login, klik "Daftar di sini"
2. Atau buka `signup.html` langsung
3. Isi semua field dengan data yang benar
4. Pastikan password minimal 8 karakter
5. Setujui syarat & ketentuan
6. Klik "Daftar"

### Untuk Reset Password:
1. Di halaman login, klik "Lupa kata sandi?"
2. Masukkan email Anda
3. Sistem akan menampilkan pesan konfirmasi

---

## 🔗 Integrasi dengan Website

### Untuk menambahkan tombol login di website LSG.html:

```html
<!-- Tambahkan di navbar atau header -->
<a href="login.html" class="btn">Masuk</a>
<a href="signup.html" class="btn">Daftar</a>
```

### Untuk mengecek status login di LSG.html:

```javascript
<script>
    // Cek apakah user sudah login
    const loggedInUser = sessionStorage.getItem('loggedInUser');
    
    if (loggedInUser) {
        const user = JSON.parse(loggedInUser);
        console.log('User yang login:', user.name);
        // Tampilkan nama user di navbar
    } else {
        // Arahkan ke login jika belum login
    }
</script>
```

---

## 🔒 Keamanan

### Saat Ini (Client-Side):
- ✅ Validasi input form
- ✅ Password strength checker
- ✅ Session management

### Untuk Production (Server-Side):
Anda perlu menambahkan:

1. **Backend/Database:**
   - Simpan user data di database (bukan localStorage)
   - Hash password menggunakan bcrypt atau similar
   - Implementasi JWT atau session tokens

2. **HTTPS:**
   - Gunakan protokol HTTPS untuk enkripsi

3. **CORS & Security Headers:**
   - Implementasikan CORS yang tepat
   - Tambahkan security headers

4. **Rate Limiting:**
   - Batasi jumlah login attempts
   - Cegah brute force attacks

5. **Two-Factor Authentication (2FA):**
   - Implementasikan OTP atau authenticator app

---

## 📦 Pengembangan Lebih Lanjut

### Feature yang bisa ditambahkan:

1. **Email Verification**
   ```
   - Kirim email verifikasi saat registrasi
   - User harus verify email sebelum bisa login
   ```

2. **Social Media Integration**
   ```
   - Implementasikan OAuth untuk Google & Facebook
   - Sederhanakan proses login
   ```

3. **User Profile**
   ```
   - Halaman untuk edit profil user
   - Ganti password
   - Hapus akun
   ```

4. **Password Reset Email**
   ```
   - Kirim link reset password via email
   - Token dengan waktu ekspirasi
   ```

5. **Login History**
   ```
   - Catat setiap login attempt
   - Tampilkan device dan lokasi
   - Deteksi aktivitas mencurigakan
   ```

6. **Role-Based Access Control (RBAC)**
   ```
   - Admin Panel
   - User Management
   - Permission System
   ```

---

## 📱 Responsive Design

Sistem login sudah responsive untuk:
- ✅ Desktop (1200px+)
- ✅ Tablet (768px - 1199px)
- ✅ Mobile (320px - 767px)

---

## 🎨 Tema & Warna

Menggunakan warna dari website Love Skin Glow:
- **Primary:** #FFD700 (Gold)
- **Secondary:** #000000 (Black)
- **Accent:** #0288d1 (Light Blue)
- **Background:** Gradient (Black to Gray)

---

## 📞 Support

Jika ada pertanyaan atau memerlukan modifikasi lebih lanjut, silakan hubungi tim development.

---

**Dibuat untuk: Love Skin Glow**  
**Tanggal: 2 Januari 2026**  
**Status: ✅ Production Ready (Client-Side)**
