# RDPX - Free Ubuntu & Windows GUI Access via GitHub Actions

RDPX adalah proyek otomatisasi GitHub Actions yang memungkinkan Anda menjalankan sistem operasi **Ubuntu Desktop** atau **Windows dengan RDP** secara gratis di cloud selama maksimal **6 hingga 9 jam**, menggunakan Tailscale untuk konektivitas aman.

## ✨ Fitur

- 🖥️ Ubuntu Desktop dengan XFCE + VNC
- 🪟 Windows Remote Desktop (RDP) dengan autentikasi bawaan
- 🔒 Terhubung secara aman melalui [Tailscale](https://tailscale.com/)
- 🕒 Runtime hingga 6–9 jam per sesi
- 🚀 Mudah dijalankan dengan satu klik melalui GitHub Actions

---

## 📦 Struktur Workflow

### 1. Ubuntu GUI Access (`.github/workflows/Ubuntu.yml`)

- Menginstal:
  - XFCE4 Desktop
  - TightVNCServer
  - Firefox
- Mengatur password root & VNC (`admin123`)
- Mengaktifkan koneksi Tailscale untuk remote access
- Menjaga runner aktif selama **6 jam** (21600 detik)

### 2. Windows RDP Access (`.github/workflows/Windows.yml`)

- Mengaktifkan fitur Remote Desktop (RDP)
- Mengatur user password: `p@ssw0rd!` untuk `runneradmin`
- Mengaktifkan firewall RDP
- Menginstal dan mengautentikasi Tailscale
- Menjaga sesi aktif selama **6 jam**

---

## 🛠️ Cara Menggunakan

### Prasyarat

1. Akun GitHub
2. [Tailscale Auth Key](https://tailscale.com/kb/1085/auth-keys/) – disimpan di `Settings > Secrets and variables > Actions` sebagai `TS_AUTHKEY`

### Langkah Menjalankan

1. Fork repositori ini ke akun GitHub Anda.
2. Buka tab **Actions** di repositori Anda.
3. Pilih workflow `RDPX Ubuntu` atau `RDPX Windows`.
4. Klik **Run workflow** → Jalankan.
5. Setelah beberapa menit, sistem siap digunakan.

---

## 🔗 Akses Desktop

Setelah workflow berjalan:
- Login ke akun **Tailscale** yang sama dengan auth key Anda.
- Lihat node `ubuntu-gui` atau `github-runner` di daftar perangkat.
- Hubungkan melalui:
  - **Ubuntu**: VNC client ke `hostname:1` (password: `admin123`)
  - **Windows**: Remote Desktop (RDP) ke IP hostname tersebut (user: `runneradmin`, password: `p@ssw0rd!`)

---

## ⚠️ Peringatan

- Jangan gunakan ini untuk aktivitas ilegal.
- RDP/VNC akan **berakhir otomatis setelah ~6 jam**.
- Jangan ubah password default jika tidak memperbarui dokumentasi.

---

## 🧑‍💻 Kontribusi

Kontribusi sangat terbuka! Silakan buat issue atau pull request untuk peningkatan keamanan, performa, atau fitur.

---

## 📄 Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE).
