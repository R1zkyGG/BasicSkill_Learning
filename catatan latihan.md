# 🛡️ Dashboard Latihan

> **Tujuan:** Dashboard ini digunakan sebagai catatan latihan, progres belajar, dan rencana lanjutan selama libur akhir tahun 2025.

---

## 📅 Periode Latihan

**Durasi:** 2 Minggu (Libur Akhir Tahun 2025)

---

## 🎯 Fokus Pembelajaran

### 1️⃣ Model Jaringan

* [ ] Memahami **cara kerja OSI Model (7 Layer)**
* [ ] Memahami **cara kerja TCP/IP Model (4 Layer)**
* [ ] Mengetahui **perbedaan OSI vs TCP/IP**

---

### 2️⃣ Protokol Jaringan & Keamanan

Protokol yang dipelajari:

* **HTTP / HTTPS**
* **DNS**
* **SSH**
* **FTP**
* **SMB**

Yang dipelajari dari tiap protokol:

* Fungsi dasar protokol
* Cara kerja komunikasi
* Jenis serangan yang sering terjadi
* Cara mendeteksi serangan
* Cara mitigasi / penanganan

---

## 🔍 Detail Pembelajaran Protokol

### 🌐 HTTP / HTTPS

**Target Pemahaman:**

* Status Code dasar dan indikasi keamanan

| Status Code     | Arti               | Indikasi Keamanan                |
| --------------- | ------------------ | -------------------------------- |
| `200 OK`        | Request berhasil   | Normal                           |
| `403 Forbidden` | Akses ditolak      | Bisa indikasi probing            |
| `404 Not Found` | Resource tidak ada | Bisa indikasi directory scanning |

**Serangan Umum:**

* Directory Scanning
* SQL Injection
* XSS

---

### 📡 DNS

**Target Pemahaman:**

* Cara kerja DNS (Query & Response)

**Serangan Umum:**

* DNS Spoofing
* DNS Amplification
* **DNS Tunneling** (mengirim data lewat DNS untuk melewati firewall)

---

### 🔐 SSH / RDP

**Target Pemahaman:**

* Proses autentikasi SSH/RDP

**Serangan Umum:**

* Brute Force Attack
* Credential Stuffing

**Ciri Brute Force:**

* Ribuan login gagal
* Sumber IP sama
* Waktu singkat

---

### 📁 FTP

**Target Pemahaman:**

* Perbedaan FTP vs FTPS

**Serangan Umum:**

* Anonymous Login Abuse
* Clear-text Credential Sniffing

---

### 🖥️ SMB

**Target Pemahaman:**

* Fungsi SMB dalam file sharing

**Serangan Umum:**

* SMB Enumeration
* Exploit SMB lama (contoh: EternalBlue)

---

## 🧪 Tools yang Digunakan

### 🦈 Wireshark

* [ ] Capture traffic
* [ ] Filter protocol (http, dns, ssh)
* [ ] Analisis paket mencurigakan

### 📊 SIEM – Splunk

* [ ] Membaca log
* [ ] Mendeteksi pola serangan
* [ ] Membuat alert sederhana

---

## 📈 Progress Tracking

* [ ] Hari 1–2 : OSI & TCP/IP
* [ ] Hari 3–5 : HTTP / HTTPS
* [ ] Hari 6–7 : DNS
* [ ] Hari 8–9 : SSH / RDP
* [ ] Hari 10 : FTP & SMB
* [ ] Hari 11–13 : Wireshark
* [ ] Hari 14 : Splunk & Review

---

## 📝 Catatan & Rencana Selanjutnya

> Gunakan bagian ini untuk mencatat hasil latihan, kendala, dan topik lanjutan yang ingin dipelajari.

---

🚀 **Target Akhir:**
Mampu mengenali traffic normal vs berbahaya, memahami pola serangan jaringan, dan membaca log security dengan percaya diri.
