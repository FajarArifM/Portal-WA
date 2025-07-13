WhatsAppBot Webportal Pelanggan Saja
Versi ringan dari whatsappbot Genieacs API dan Mikrotik API yang hanya menggunakan fitur WhatsApp webportal pelanggan saja

Persyaratan
Node.js v18+ (direkomendasikan v20+)
npm atau yarn
Akses ke GenieACS API
Akses ke Mikrotik API (opsional)
Cara Instalasi
apt install git curl -y
git clone https://github.com/FajarArifM/Portal-WA
cd Portal-WA
1. Install Dependensi
apt install npm
2. Konfigurasi Environment Variables
Edit file .env dengan pengaturan yang sesuai:

# Konfigurasi Server
PORT=4555 (jika sudah dipake ganti)
HOST=localhost

# Konfigurasi Admin
ADMIN_USERNAME=admin
ADMIN_PASSWORD=password

# Konfigurasi GenieACS
GENIEACS_URL=http://192.166.20.xx:7557
GENIEACS_USERNAME=username
GENIEACS_PASSWORD=password

# Konfigurasi Mikrotik (opsional)
MIKROTIK_HOST=192.166.20.1
MIKROTIK_PORT=8728
MIKROTIK_USER=admin
MIKROTIK_PASSWORD=password

# Konfigurasi WhatsApp
ADMIN_NUMBER=6282140501327
TECHNICIAN_NUMBERS=628xxxxxxxx
WHATSAPP_SESSION_PATH=./whatsapp-session
WHATSAPP_KEEP_ALIVE=true
WHATSAPP_RESTART_ON_ERROR=true
setting juga file settings.json
samakan dengan env

3. Menjalankan Aplikasi
npm start
siapkan dua nomer whatsapp 1 buat bot 1 buat admin
Scan QR code yang muncul di terminal untuk login WhatsApp.
setelah di scan tinggal jalankan dengan PM2

pm2 start app-whatsapp-only.js
webportal pelanggan : ipserver:4555
Perintah WhatsApp
Perintah untuk Pelanggan
menu - Menampilkan menu bantuan
status - Cek status perangkat
refresh - Refresh data perangkat
gantiwifi [nama] - Ganti nama WiFi
gantipass [password] - Ganti password WiFi
Perintah untuk Admin
Semua perintah pelanggan
admin - Menampilkan menu admin
cek [nomor] - Cek status ONU pelanggan
list - Daftar semua ONU
cekall - Cek status semua ONU
editssid [nomor] [ssid] - Edit SSID pelanggan
editpass [nomor] [password] - Edit password WiFi pelanggan
addhotspot [user] [pass] [profile] - Tambah user hotspot
delhotspot [user] - Hapus user hotspot
hotspot - Lihat user hotspot aktif
addpppoe [user] [pass] [profile] [ip] - Tambah secret PPPoE
delpppoe [user] - Hapus secret PPPoE
setprofile [user] [profile] - Ubah profile PPPoE
pppoe - Lihat koneksi PPPoE aktif
offline - Lihat user PPPoE offline
resource - Info resource router
addwan [nomor] [tipe] [mode] - Tambah konfigurasi WAN
addtag [device_id] [nomor] - Tambahkan nomor pelanggan ke perangkat
addpppoe_tag [pppoe_username] [nomor] - Tambahkan nomor pelanggan berdasarkan PPPoE
`Otp On untuk mengaktifkan OTP
`Otp off untuk nonaktifkan OTP
Otp status untuk melihat status OTP
Jangan lupa untuk mengkonfigurasi file .env terlebih dahulu!