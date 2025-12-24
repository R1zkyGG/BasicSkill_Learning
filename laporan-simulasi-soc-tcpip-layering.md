# LAPORAN LENGKAP SIMULASI PRAKTIK SOC ANALYST
## TCP/IP LAYERING & INCIDENT RESPONSE

---

**Analyst**     : Septian Rizky Izza Ramadhan  
**Tanggal**     : -  
**Environment** :
- Kali Linux (Attacker)
- Ubuntu Server (Victim)
- Ubuntu Desktop (Monitoring)

---

## LAYER 1: NETWORK ACCESS
### (Physical & Data Link Layer)

**Fokus:** MAC Address & ARP Protocol

### Konsep Dasar
Komunikasi pada jaringan lokal (LAN) menggunakan **MAC Address**.
Protokol **ARP (Address Resolution Protocol)** berfungsi untuk memetakan
**IP Address** ke **MAC Address**.

### Simulasi Serangan: ARP Spoofing
Penyerang mengirim paket ARP palsu yang mengklaim IP Gateway memiliki MAC Address
milik penyerang sehingga trafik korban dialihkan (**Man-in-the-Middle**).

### Detection (SOC)
- Perubahan MAC Address Gateway
- ARP Reply ganda
- Alert IDS: ARP Cache Poisoning

### Response
```bash
sudo arp -d [IP-GATEWAY]
sudo iptables -A INPUT -m mac --mac-source [MAC-PENYERANG] -j DROP
```

### Prevention
```bash
sudo arp -s [IP-GATEWAY] [MAC-GATEWAY]
```
- Dynamic ARP Inspection
- Segmentasi VLAN
- HTTPS

---

## LAYER 2: INTERNET LAYER

**Fokus:** IP Address, ICMP, Reconnaissance

### Simulasi Serangan: Ping Sweep
Penyerang memindai host aktif menggunakan ICMP Echo Request.

### Detection
- ICMP Type 8 ke banyak host
- Alert IDS: ICMP Sweep

### Response
```bash
sudo iptables -A INPUT -p icmp --icmp-type echo-request -s [IP] -j DROP
```

### Prevention
```bash
sudo iptables -A INPUT -p icmp --icmp-type echo-request -m limit --limit 1/s -j ACCEPT
sudo sysctl -w net.ipv4.icmp_echo_ignore_all=1
```

---

## LAYER 3: TRANSPORT LAYER

**Fokus:** TCP/UDP & Connection Control

### TCP Three-Way Handshake
1. SYN
2. SYN-ACK
3. ACK

### Simulasi Serangan
- Port Scanning
- SYN Flood (DoS)

### Detection
- Banyak koneksi half-open
- Lonjakan SYN tanpa ACK

### Response
```bash
sudo sysctl -w net.ipv4.tcp_syncookies=1
sudo iptables -A INPUT -p tcp --syn -m limit --limit 10/s -j ACCEPT
sudo iptables -A INPUT -p tcp --syn -j DROP
```

### Prevention
- Stateful Firewall
- IDS/IPS
- Load Balancer

---

## LAYER 4: APPLICATION LAYER

**Fokus:** Protokol Layanan & Interaksi User

### Port Penting
| Port | Layanan | Risiko |
|----|----|----|
| 22 | SSH | Brute Force |
| 53 | DNS | Tunneling |
| 80/443 | HTTP/S | SQLi, XSS |
| 21 | FTP | Plaintext |

### Simulasi Serangan: SSH Brute Force

### Detection
- Failed login berulang
- Akses di luar jam normal

### Response
```bash
sudo iptables -A INPUT -s [IP-PENYERANG] -j DROP
sudo passwd -l username
```

### Prevention
- Fail2Ban
- SSH Key
- Disable root login
- MFA

---

## KESIMPULAN SOC ANALYST

| Layer | Ancaman | Fokus |
|----|----|----|
| L1 | MITM | ARP Monitoring |
| L2 | Recon | ICMP Analysis |
| L3 | DoS | TCP Flags |
| L4 | Account Attack | Log Analysis |

**SOC Analyst bertanggung jawab untuk:**
- Mendeteksi ancaman sedini mungkin
- Melakukan respons cepat terhadap insiden
- Melakukan pencegahan agar serangan tidak terulang

---
