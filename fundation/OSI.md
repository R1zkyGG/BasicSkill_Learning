## OSI layer 


---

### 7 lapisan OSI layer

Layer 7 application

* Pengertian: Lapisan di mana pengguna berinteraksi langsung dengan aplikasi.
* Fungsi: Menyediakan layanan jaringan untuk aplikasi (browser, email).
* Contoh: HTTP (Web), SMTP (Email), FTP (Transfer File).

Layer 6 presentation 

* Pengertian: Lapisan yang menerjemahkan format data.
* Fungsi: Enkripsi (keamanan), kompresi, dan format data (penerjemah).
* Contoh: SSL/TLS (Enkripsi), JPEG, ASCII, MP4. 

Layer 5 session 

* Pengertian: Lapisan yang mengelola "percakapan" antar komputer.
* Fungsi: Membuka, menjaga, dan menutup koneksi (sesi).
* Contoh: NetBIOS, RPC.

Layer 4 trassport 

* Pengertian: Lapisan pengiriman data antar perangkat.
* Fungsi: Memecah data jadi potongan kecil (segment) dan memastikan data sampai dengan benar.
* Contoh: TCP (Pasti sampai) dan UDP (Cepat tapi tak menjamin sampai).

Layer 3 network

* Pengertian: Lapisan alamat logika dan rute.
* Fungsi: Menentukan jalur terbaik (routing) dan menggunakan alamat IP. 
* Contoh: IP Address (IPv4, IPv6), Router, ICMP (Ping).

Layer 2 data link 

* Pengertian: Lapisan koneksi fisik antar perangkat dalam satu jaringan lokal.
* Fungsi: Mengubah data jadi frame dan menggunakan alamat fisik (MAC Address).
* Contoh: Ethernet, Switch, MAC Address.

Layer 1 physical 

* Pengertian: Lapisan fisik perangkat keras.
* Fungsi: Mengirimkan data mentah (bit 0 dan 1) melalui media fisik.
* Contoh: Kabel LAN (UTP), Serat Optik, Hub, Wi-Fi.


---

Dari ke 7 layer itu ada 3 layer yang paling penting SOC analyst yaitu 

* layer 7 (Application)
* layer 4 (Trassport)
* layer 3 (Network)


---

Karena di layer 7 (Application) kita memantau protokol yang digunakan applikasi. Ini adalah layer paling sibuk karena serangan modern banyak menyerang disini. Ancamannya sering kali dengan phising, SQL injection, cross-site scripting (XSS), dan serangan API. **Di layer 7 ini penting untuk tahu "apa" yang diserang (application/data).**

Dilayer 4 (Trassport) kita akan Analisis port dan protokol komunikasi (TCP/UDP). Sangat penting untuk mendeteksi scanning atau koneksi ilegal. Ancamannya sering kali dengan Port Scanning, SYN Flood (DDoS), eksploitasi protokol transmisi. **Di layer 4 ini penting untuk tau "bagaimana" cara mereka masuk (port/protokol).**

Dan dilayer 3 (network) kita akan Analisis alamat IP asal dan tujuan. Digunakan untuk memblokir IP penyerang atau mendeteksi lateral movement. Ancamannya sering kali dengan IP Spoofing, pelacakan sumber serangan, komunikasi C2 (Command and Control). **Di layer 4 ini penting untuk tau "siapa/dari mana" asal serangan (IP-Address).**


---

