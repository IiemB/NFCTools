# NFCTools untuk iOS 📱⚡

<p align="center">
  <b>Rangkaian diagnostik NFC nirsentuh, emulasi kartu virtual, dan pendamping Pusat Kontrol lengkap untuk iOS.</b>
</p>

<p align="center">
  <a href="README.md">English</a> | <b>Bahasa Indonesia</b>
</p>

---

> [!NOTE]
> Beberapa rilis merupakan **versi beta** yang digunakan untuk menguji fitur baru serta mengumpulkan masukan. Versi ini ditandai dengan label *beta* pada halaman Rilis, nama berkas, dan di dalam aplikasi. Versi beta dari aplikasi dan tweak **berfungsi selama 14 hari sejak dibuat**. Setelah itu, aplikasi akan menampilkan layar pembaruan dan fitur emulasi pada tweak/CLI akan dinonaktifkan. Unduh versi terbaru dari **[Rilis](https://github.com/IiemB/NFCTools/releases/latest)** untuk melanjutkan. Rilis reguler (non-beta) tidak memiliki masa kedaluwarsa.

---

## 🌟 Ringkasan

**NFCTools** adalah toolkit diagnostik NFC serbaguna, emulasi kartu virtual, dan manajemen kartu yang dirancang khusus untuk iOS. Aplikasi ini memadukan antarmuka native SwiftUI dengan tweak jailbreak opsional untuk membaca tag tingkat rendah, diagnostik kartu mendalam, pengelolaan kartu yang fleksibel, emulasi kartu virtual, serta integrasi langsung ke sistem iOS.

---

## 📥 Unduh

Dapatkan versi terbaru di **[Halaman Rilis](https://github.com/IiemB/NFCTools/releases/latest)**. Berkas versi beta menyertakan kata `beta` pada nama filenya (`NFCTools_<version>-beta+<build>.ipa`, `NFCTools_Plus_<version>~beta+<build>_…deb`).

---

## 📱 Aplikasi NFCTools (Aplikasi Utama)

Aplikasi utama dikemas sebagai berkas `.ipa` mandiri (dipasang via TrollStore) yang memberikan akses langsung ke hardware, analisis mendalam terhadap tag, serta emulasi kartu virtual langsung dari aplikasi.

### 📡 Diagnostik & Pemindaian Tag
- **Deteksi Teknologi Universal**: Memeriksa kartu ISO 14443 Tipe A, ISO 14443 Tipe B, ISO 15693 (Vicinity), FeliCa, dan MIFARE.
- **Pemeriksaan Hardware Mendalam**: Melihat UID / PUPI (panjang 4, 7, 8, 10, dan 12 bita), ATQA, SAK, struktur memori, informasi pabrikan, dan parameter protokol. Tekan dan tahan properti mana pun untuk menyalin nilainya.
- **Pembacaan NDEF & Penguraian Payload**: Otomatis mendekode teks NDEF, URI/URL, serta rekaman payload mentah.
- **Pemeriksaan Status Tulis NDEF**: Mendeteksi status proteksi/kunci fisik tag dan kesiapan tulis langsung saat dipindai.

### ⚡ Emulasi Kartu Virtual
- **Pancarkan Kartu Virtual Tersimpan**: Emulasikan kartu NFC yang telah disimpan langsung dari iPhone sebagai kartu nirsentuh virtual.
- **Pengiriman Identitas Khusus (Custom UID)**: Memancarkan UID kustom dan parameter protokol ke pembaca kartu eksternal maupun ponsel lain.
- **Umpan Balik Haptik Interaktif**: Getaran haptik responsif akan memicu saat pembaca kartu eksternal melakukan kontak RF dengan kartu virtual Anda.
- **Applet Virtual NDEF Tipe 4**: Merespons perintah standar APDU SELECT dan READ BINARY sehingga payload NDEF dapat dibaca dengan lancar oleh perangkat lain.
- **Emulasi dengan NFCTools Plus**: Jika tweak terpasang, aplikasi dapat menyerahkan tugas emulasi ke tweak sehingga Anda mendapatkan overlay melayang kecil dengan tombol Stop alih-alih layar emulasi penuh.

### 🗃️ Brankas Kartu & Pengelolaan
- **Penyimpanan Lokal Terenkripsi**: Simpan tag hasil pindaian dengan nama panggilan kustom, lebih dari 50+ ikon SF Symbols, dan pilihan warna aksen.
- **Editor Data**: Buat dan ubah rekaman NDEF Teks (multi-baris) dan URL.
- **Atur Urutan dengan Geser & Lepas**: Rapikan urutan daftar kartu tersimpan Anda sesuai kebutuhan.
- **Cadangan Portabel (`.nftag`)**: Ekspor dan impor berkas tag individual dilengkapi layar verifikasi keamanan untuk berbagi atau memulihkan koleksi kartu.

### 🏷️ Kloning Tag Magic & Penulisan UID
- **Dukungan Kartu Magic**: Mengirim perintah langsung (transceive) untuk menulis dan mengkloning UID kustom ke kartu fisik yang mendukung penulisan ulang.
- **Protokol yang Didukung**: Gen3 APDU, Magic Tipe 2 (NTAG21x / MIFARE Ultralight dengan kalkulasi checksum BCC otomatis dan perlindungan bita pabrikan), serta tag Gen4 UMC.

### 🩺 Diagnostik & Laporan Masalah
- **Halaman Diagnostik**: Pemeriksaan status dalam bahasa yang mudah dipahami mencakup versi iOS, model iPhone, instalasi, pembacaan tag, emulasi, chip NFC, layanan sistem nfc, penyimpanan, tag tersimpan, dan status NFCTools Plus. Ditampilkan saat peluncuran pertama atau kapan saja melalui **Pengaturan › Diagnostik**.
- **Kirim Laporan ke Pengembang**: Dari Pengaturan › Diagnostik, kirimkan hasil pengujian, model perangkat, versi iOS, catatan tambahan (opsional), serta log aplikasi langsung ke pengembang. Log dienkripsi di perangkat Anda sehingga hanya pengembang yang dapat membukanya. Anda akan menerima ID laporan untuk dilampirkan jika berdiskusi di GitHub.

### 🎨 Pengalaman Pengguna Native
- **100% Native SwiftUI**: Antarmuka modern dengan transisi halus, mendukung tema gelap/terang, dan animasi radar kustom.
- **Widget Layar Utama & Layar Kunci**: Widget Layar Utama 8-slot dan 4 widget melingkar di Layar Kunci (iOS 16+) untuk memulai emulasi dalam sekali ketuk. Pengaturan menyediakan pratinjau langsung sesuai tampilan widget aslinya.

---

## ⚙️ NFCTools Plus (Tweak Jailbreak)

Tweak ini didistribusikan sebagai paket `.deb` mandiri untuk jailbreak rootless dan RootHide (Dopamine, RootHide), menghadirkan akses cepat emulasi kartu virtual langsung dari antarmuka sistem iOS.

### 🎛️ Emulasi Cepat dari Pusat Kontrol (Control Center)
- **Tombol Pintas Khusus**: Empat tombol Pusat Kontrol ("NFC Tag 1–4") untuk memulai emulasi kartu dari mana saja di perangkat Anda, bahkan saat layar terkunci (dengan auto-stop aktif).
- **Pengaturan Tombol di Aplikasi**: Tautkan kartu tersimpan ke masing-masing slot di **NFCTools › Pengaturan**, dilengkapi pratinjau tampilan tombol. Selanjutnya, tambahkan tombol tersebut melalui **Pengaturan iOS › Pusat Kontrol**.
- **HUD Melayang Interaktif**: Status overlay di layar menampilkan nama kartu virtual yang sedang aktif, UID, animasi gelombang transmisi, dan tombol penghenti cepat (Stop).
- **Penghenti Otomatis (Auto-Stop)**: Emulasi akan selalu berhenti secara otomatis setelah 5–30 detik (standar: 10 detik).

### 💻 Antarmuka Baris Perintah / CLI (`nfctools`)
Perangkat baris perintah dengan hak akses root yang dapat diakses melalui Terminal atau SSH:
```sh
nfctools emulate <slot 1-4 | uuid | uid | nama>  # Mulai emulasi tag (tanpa perlu slot)
nfctools stop                                    # Hentikan emulasi yang sedang berjalan
nfctools list [-v]                               # Tampilkan kartu tersimpan dan penugasan slot
nfctools assign <slot 1-4> <nama|uid|uuid|none>  # Tetapkan kartu ke slot Pusat Kontrol
nfctools autostop [5-30]                         # Lihat atau ubah batas waktu auto-stop (detik)
nfctools config                                  # Tampilkan konfigurasi slot dan auto-stop
nfctools status                                  # Tampilkan status emulasi saat ini
nfctools help                                    # Bantuan (dan tanggal kedaluwarsa pada versi beta)
```

---

## 📲 Kompatibilitas & Pemasangan

### Kebutuhan Perangkat
- iPhone dengan kontroler NFC yang mendukung akses langsung hardware (misal: iPhone 12 / 13). Perangkat uji utama: **iPhone 12 mini, iOS 16.1.2**.
- Halaman Diagnostik di aplikasi akan memberi tahu apakah iPhone dan jenis instalasi Anda dapat menggunakan masing-masing fitur.

### Aplikasi Utama (`.ipa`)
- **Kompatibilitas**: iOS 15.0 ke atas (iOS 18 ke atas masih dalam tahap pengujian)
- **Pemasangan**: Pasang berkas `NFCTools_<version>+<build>.ipa` menggunakan **TrollStore**.

### Tweak Pendamping (`.deb`)
- **Kompatibilitas**: iOS 15.0 – 16.5.1+ (Rootless / RootHide)
- **Pemasangan**: Pasang paket `.deb` yang sesuai via Sileo, Zebra, atau `dpkg -i`, lalu lakukan respring:
  - **Dopamine (Rootless)**: `NFCTools_Plus_<version>+<build>_iphoneos-arm64.deb`
  - **RootHide**: `NFCTools_Plus_<version>+<build>_iphoneos-arm64e.deb`
- Tweak ini mengemulasikan kartu yang telah Anda simpan di aplikasi, jadi pastikan aplikasi utama juga terpasang.

---

## 💬 Masukan & Laporan Masalah

Masukan dan laporan pengujian sangat membantu pengembangan proyek ini.

1. **Menemukan kendala/kerusakan?** Buka **Pengaturan › Diagnostik** di aplikasi, ketuk **Kirim Laporan ke Pengembang**, jelaskan apa yang terjadi di catatan, lalu kirim. Simpan ID laporan yang muncul di layar.
2. **Ingin berdiskusi atau mengusulkan fitur?** [Buka issue di GitHub](https://github.com/IiemB/NFCTools/issues) dan cantumkan ID laporan jika sebelumnya sudah mengirimkannya.
3. **Versi beta kedaluwarsa?** Unduh rilis terbaru dari [Halaman Rilis](https://github.com/IiemB/NFCTools/releases/latest).

---

## 📄 Ketentuan & Privasi

Ketentuan Penggunaan dan Kebijakan Privasi dapat dilihat langsung di aplikasi pada menu **Pengaturan › Ketentuan & Privasi**, dan teks sumbernya tersedia di [`content/legal.json`](content/legal.json). Singkatnya: aplikasi ini tidak menggunakan akun, tidak ada iklan maupun analitik/pelacakan, dan tidak mengirim data apa pun ke pengembang kecuali Anda secara sukarela memilih untuk mengirim laporan masalah.

---

## ⚖️ Penafian (Disclaimer)

- **Penggunaan Resmi**: NFCTools dikembangkan untuk keperluan pribadi, edukasi, dan diagnostik pada tag serta perangkat keras milik Anda sendiri. Selalu pastikan Anda memiliki izin resmi sebelum membaca, menulis, atau mengemulasikan kartu nirsentuh apa pun.
- **Proyek Berbantuan AI**: Proyek ini awalnya dimulai sebagai alat pribadi untuk memenuhi kebutuhan dan alur kerja saya sendiri karena alat yang ada belum sesuai dengan preferensi saya. Proyek ini dibagikan apa adanya bagi siapa saja yang membutuhkannya—masukan dan laporan perbaikan bug selalu diterima dengan senang hati!
