# Kumpulan Soal & Jawaban — Jaringan Komputer & Sinyal

---

## Daftar Isi

* [1. Analisis Alamat IP](#1-analisis-alamat-ip)
* [2. Subnetting](#2-subnetting)
* [3. Analisis Traceroute & Mekanisme TTL](#3-analisis-traceroute--mekanisme-ttl)
* [4. Subnetting VLSM (Variable Length Subnet Mask)](#4-subnetting-vlsm-variable-length-subnet-mask)

---

## 1. Analisis Alamat IP

### Soal
Diketahui beberapa alamat IP berikut:
1. `21.26.8.5`
2. `212.6.8.3`
3. `103.24.56.32`
4. `1.1.1.1`
5. `172.31.16.8`

Tentukan untuk masing-masing IP:
* IP Gateway
* Host Pertama
* Host Terakhir
* Broadcast
* IP Network

---

### Jawaban
Berdasarkan kelas standar alamat IP (*Classful Addressing*):

#### 1.1. Alamat IP: `21.26.8.5` (Kelas A)
* **Subnet Mask Standar:** `255.0.0.0` (`/8`)
* **IP Network:** `21.0.0.0`
* **Host Pertama:** `21.0.0.1`
* **Host Terakhir:** `21.255.255.254`
* **Broadcast:** `21.255.255.255`
* **IP Gateway (Default Usability):** `21.0.0.1`

#### 1.2. Alamat IP: `212.6.8.3` (Kelas C)
* **Subnet Mask Standar:** `255.255.255.0` (`/24`)
* **IP Network:** `212.6.8.0`
* **Host Pertama:** `212.6.8.1`
* **Host Terakhir:** `212.6.8.254`
* **Broadcast:** `212.6.8.255`
* **IP Gateway:** `212.6.8.1`

#### 1.3. Alamat IP: `103.24.56.32` (Kelas A)
* **Subnet Mask Standar:** `255.0.0.0` (`/8`)
* **IP Network:** `103.0.0.0`
* **Host Pertama:** `103.0.0.1`
* **Host Terakhir:** `103.255.255.254`
* **Broadcast:** `103.255.255.255`
* **IP Gateway:** `103.0.0.1`

#### 1.4. Alamat IP: `1.1.1.1` (Kelas A)
* **Subnet Mask Standar:** `255.0.0.0` (`/8`)
* **IP Network:** `1.0.0.0`
* **Host Pertama:** `1.0.0.1`
* **Host Terakhir:** `1.255.255.254`
* **Broadcast:** `1.255.255.255`
* **IP Gateway:** `1.0.0.1`

#### 1.5. Alamat IP: `172.31.16.8` (Kelas B)
* **Subnet Mask Standar:** `255.255.0.0` (`/16`)
* **IP Network:** `172.31.0.0`
* **Host Pertama:** `172.31.0.1`
* **Host Terakhir:** `172.31.255.254`
* **Broadcast:** `172.31.255.255`
* **IP Gateway:** `172.31.0.1`

---

## 2. Subnetting

### Soal
Lakukan pembagian subnet (*subnetting*) untuk setiap jaringan berikut:
1. `192.168.1.0/24` dibagi menjadi 4 subnet
2. `132.10.0.0/16` dibagi menjadi 10 subnet
3. `17.8.0.0/16` dibagi menjadi 4 subnet
4. `8.32.0.0/12` dibagi menjadi 6 subnet

Tentukan untuk setiap subnet:
* IP Network
* Subnet Mask (prefix baru)
* Host Pertama
* Host Terakhir
* Broadcast
* Jumlah host per subnet

---

### Jawaban

#### 2.1. `192.168.1.0/24` dibagi menjadi 4 subnet
* **Aturan Bit Subnet:** Membutuhkan 4 subnet $\rightarrow 2^2 = 4$ subnet (meminjam 2 bit).
* **Prefix Baru:** `/24 + 2 = /26` (`255.255.255.192`)
* **Jumlah Host Valid per Subnet:** $2^6 - 2 = 62$ host.

| Subnet | IP Network | Subnet Mask (Prefix Baru) | Host Pertama | Host Terakhir | Broadcast | Jumlah Host |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Subnet 1 | `192.168.1.0` | `255.255.255.192` (`/26`) | `192.168.1.1` | `192.168.1.62` | `192.168.1.63` | 62 |
| Subnet 2 | `192.168.1.64` | `255.255.255.192` (`/26`) | `192.168.1.65` | `192.168.1.126` | `192.168.1.127` | 62 |
| Subnet 3 | `192.168.1.128` | `255.255.255.192` (`/26`) | `192.168.1.129` | `192.168.1.190` | `192.168.1.191` | 62 |
| Subnet 4 | `192.168.1.192` | `255.255.255.192` (`/26`) | `192.168.1.193` | `192.168.1.254` | `192.168.1.255` | 62 |

#### 2.2. `132.10.0.0/16` dibagi menjadi 10 subnet
* **Aturan Bit Subnet:** Membutuhkan minimal 10 subnet $\rightarrow 2^4 = 16$ subnet (meminjam 4 bit).
* **Prefix Baru:** `/16 + 4 = /20` (`255.255.240.0`)
* **Jumlah Host Valid per Subnet:** $2^{12} - 2 = 4.094$ host.

| Subnet | IP Network | Subnet Mask (Prefix Baru) | Host Pertama | Host Terakhir | Broadcast | Jumlah Host |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Subnet 1 | `132.10.0.0` | `255.255.240.0` (`/20`) | `132.10.0.1` | `132.10.15.254` | `132.10.15.255` | 4.094 |
| Subnet 2 | `132.10.16.0` | `255.255.240.0` (`/20`) | `132.10.16.1` | `132.10.31.254` | `132.10.31.255` | 4.094 |
| Subnet 3 | `132.10.32.0` | `255.255.240.0` (`/20`) | `132.10.32.1` | `132.10.47.254` | `132.10.47.255` | 4.094 |
| Subnet 4 | `132.10.48.0` | `255.255.240.0` (`/20`) | `132.10.48.1` | `132.10.63.254` | `132.10.63.255` | 4.094 |
| Subnet 5 | `132.10.64.0` | `255.255.240.0` (`/20`) | `132.10.64.1` | `132.10.79.254` | `132.10.79.255` | 4.094 |
| Subnet 6 | `132.10.80.0` | `255.255.240.0` (`/20`) | `132.10.80.1` | `132.10.95.254` | `132.10.95.255` | 4.094 |
| Subnet 7 | `132.10.96.0` | `255.255.240.0` (`/20`) | `132.10.96.1` | `132.10.111.254` | `132.10.111.255` | 4.094 |
| Subnet 8 | `132.10.112.0` | `255.255.240.0` (`/20`) | `132.10.112.1` | `132.10.127.254` | `132.10.127.255` | 4.094 |
| Subnet 9 | `132.10.128.0` | `255.255.240.0` (`/20`) | `132.10.128.1` | `132.10.143.254` | `132.10.143.255` | 4.094 |
| Subnet 10 | `132.10.144.0` | `255.255.240.0` (`/20`) | `132.10.144.1` | `132.10.159.254` | `132.10.159.255` | 4.094 |

#### 2.3. `17.8.0.0/16` dibagi menjadi 4 subnet
* **Aturan Bit Subnet:** Membutuhkan 4 subnet $\rightarrow 2^2 = 4$ subnet (meminjam 2 bit).
* **Prefix Baru:** `/16 + 2 = /18` (`255.255.192.0`)
* **Jumlah Host Valid per Subnet:** $2^{14} - 2 = 16.382$ host.

| Subnet | IP Network | Subnet Mask (Prefix Baru) | Host Pertama | Host Terakhir | Broadcast | Jumlah Host |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Subnet 1 | `17.8.0.0` | `255.255.192.0` (`/18`) | `17.8.0.1` | `17.8.63.254` | `17.8.63.255` | 16.382 |
| Subnet 2 | `17.8.64.0` | `255.255.192.0` (`/18`) | `17.8.64.1` | `17.8.127.254` | `17.8.127.255` | 16.382 |
| Subnet 3 | `17.8.128.0` | `255.255.192.0` (`/18`) | `17.8.128.1` | `17.8.191.254` | `17.8.191.255` | 16.382 |
| Subnet 4 | `17.8.192.0` | `255.255.192.0` (`/18`) | `17.8.192.1` | `17.8.255.254` | `17.8.255.255` | 16.382 |

#### 2.4. `8.32.0.0/12` dibagi menjadi 6 subnet
* **Aturan Bit Subnet:** Membutuhkan minimal 6 subnet $\rightarrow 2^3 = 8$ subnet (meminjam 3 bit).
* **Prefix Baru:** `/12 + 3 = /15` (`255.254.0.0`)
* **Jumlah Host Valid per Subnet:** $2^{17} - 2 = 131.070$ host.

| Subnet | IP Network | Subnet Mask (Prefix Baru) | Host Pertama | Host Terakhir | Broadcast | Jumlah Host |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Subnet 1 | `8.32.0.0` | `255.254.0.0` (`/15`) | `8.32.0.1` | `8.33.255.254` | `8.33.255.255` | 131.070 |
| Subnet 2 | `8.34.0.0` | `255.254.0.0` (`/15`) | `8.34.0.1` | `8.35.255.254` | `8.35.255.255` | 131.070 |
| Subnet 3 | `8.36.0.0` | `255.254.0.0` (`/15`) | `8.36.0.1` | `8.37.255.254` | `8.37.255.255` | 131.070 |
| Subnet 4 | `8.38.0.0` | `255.254.0.0` (`/15`) | `8.38.0.1` | `8.39.255.254` | `8.39.255.255` | 131.070 |
| Subnet 5 | `8.40.0.0` | `255.254.0.0` (`/15`) | `8.40.0.1` | `8.41.255.254` | `8.41.255.255` | 131.070 |
| Subnet 6 | `8.42.0.0` | `255.254.0.0` (`/15`) | `8.42.0.1` | `8.43.255.254` | `8.43.255.255` | 131.070 |

---

## 3. Analisis Traceroute & Mekanisme TTL

### Soal
Lakukan analisis terhadap cara kerja **Traceroute** serta mekanisme **TTL (Time To Live)** pada jaringan komputer.

Poin yang harus dibahas:
* Pengertian dan fungsi Traceroute
* Pengertian dan fungsi TTL (Time To Live)
* Bagaimana Traceroute memanfaatkan TTL untuk memetakan jalur paket
* Peran ICMP (Internet Control Message Protocol) dalam proses Traceroute
* Contoh alur/langkah kerja Traceroute dari sumber ke tujuan

---

### Jawaban

#### 3.1. Pengertian dan Fungsi Traceroute
Traceroute (atau `tracert` pada Windows) adalah utilitas diagnostik jaringan untuk melacak jalur fisik yang dilewati paket data dari komputer sumber ke komputer tujuan di jaringan IP.

* **Fungsi Utama:**
  * Memetakan daftar router (*hop*) yang dilewati paket.
  * Mengukur waktu tempuh bolak-balik (*Round Trip Time / RTT*) ke setiap router.
  * Mendeteksi lokasi kemacetan (*bottleneck*) atau kegagalan rute (*routing loop*).

#### 3.2. Pengertian dan Fungsi TTL (Time To Live)
TTL adalah field 8-bit pada *header* IPv4 (atau *Hop Limit* pada IPv6) yang menentukan batas usia hidup suatu paket data.

* **Fungsi Utama:**
  * Mencegah paket berputar tanpa henti (*infinite loop*) akibat kesalahan tabel *routing*.
  * Nilai TTL berkurang $1$ setiap melewati satu router (*hop*). Jika TTL mencapai $0$, router akan membuang paket (*drop*) dan mengirimkan pesan kesalahan kembali.

#### 3.3. Cara Traceroute Memanfaatkan TTL untuk Memetakan Jalur
Traceroute bekerja dengan menaikkan nilai TTL secara bertahap:
1. Mengirim paket awal dengan $\text{TTL} = 1$.
2. Router pertama menerima paket, mengurangkan TTL menjadi $0$, membuang paket, dan mengirim pesan peringatan ICMP balik ke pengirim.
3. Pengirim mencatat IP router pertama dan RTT-nya.
4. Pengirim mengirim paket baru dengan $\text{TTL} = 2$. Paket melewati router pertama (TTL menjadi $1$) lalu berhenti di router kedua (TTL menjadi $0$), yang kemudian mengirim pesan ICMP.
5. Proses diulang ($\text{TTL} = 3, 4, 5, \dots$) sampai paket mencapai tujuan akhir.

#### 3.4. Peran ICMP (Internet Control Message Protocol) dalam Traceroute
ICMP berfungsi sebagai protokol umpan balik (*feedback*):
* **Pesan `ICMP Time Exceeded` (Type 11, Code 0):** Dikirim oleh router perantara ketika paket dibuang karena TTL habis ($0$).
* **Pesan `ICMP Echo Reply` / `Destination Unreachable`:** Dikirim oleh host tujuan saat paket akhirnya tiba untuk menandai proses pelacakan selesai.

#### 3.5. Alur Kerja Traceroute (Komputer A ke Server B)

```
[Komputer A] ---> (Router 1) ---> (Router 2) ---> [Server B]
```

1. **Langkah 1 ($\text{TTL} = 1$):**
   * Komputer A mengirim paket ($\text{TTL} = 1$) ke Server B.
   * Router 1 mengurangkan TTL menjadi $0$, membuang paket, dan mengirim `ICMP Time Exceeded`.
   * Komputer A mencatat Router 1 sebagai **Hop 1**.

2. **Langkah 2 ($\text{TTL} = 2$):**
   * Komputer A mengirim paket ($\text{TTL} = 2$).
   * Router 1 meneruskan paket (TTL menjadi $1$). Router 2 mengurangkan TTL menjadi $0$, membuang paket, dan mengirim `ICMP Time Exceeded`.
   * Komputer A mencatat Router 2 sebagai **Hop 2**.

3. **Langkah 3 ($\text{TTL} = 3$):**
   * Komputer A mengirim paket ($\text{TTL} = 3$).
   * Paket melewati Router 1 (TTL = $2$), Router 2 (TTL = $1$), dan tiba di Server B.
   * Server B merespon dengan `ICMP Echo Reply`.
   * Komputer A mencatat Server B sebagai tujuan akhir dan menyelesaikan proses.

---

## 4. Subnetting VLSM (Variable Length Subnet Mask)

### Soal
Sebuah kampus memiliki alokasi jaringan **10.252.108.0/24** yang akan dibagi untuk empat segmen dengan kebutuhan host sebagai berikut:

| Segmen | Kebutuhan Host |
| :--- | :--- |
| Laboratorium A | 90 host |
| Laboratorium B | 60 host |
| Administrasi | 14 host |
| Tautan Point-to-Point | 4 endpoint |

Tentukan untuk setiap segmen:
* IP Network
* Subnet Mask (prefix baru)
* Host Pertama
* Host Terakhir
* Broadcast
* Jumlah host yang tersedia
* Sisa alokasi IP yang belum terpakai (jika ada)

---

### Jawaban

**Alokasi Jaringan Induk:** `10.252.108.0/24` ($256$ IP total)

Alokasi diurutkan dari kebutuhan host terbesar hingga terkecil:
1. **Laboratorium A:** 90 host $\rightarrow$ Butuh $90 + 2 = 92$ IP $\rightarrow$ Blok terdekat $2^7 = 128$ IP (`/25`).
2. **Laboratorium B:** 60 host $\rightarrow$ Butuh $60 + 2 = 62$ IP $\rightarrow$ Blok terdekat $2^6 = 64$ IP (`/26`).
3. **Administrasi:** 14 host $\rightarrow$ Butuh $14 + 2 = 16$ IP $\rightarrow$ Blok terdekat $2^4 = 16$ IP (`/28`).
4. **Tautan Point-to-Point:** 4 endpoint $\rightarrow$ Butuh $4 + 2 = 6$ IP $\rightarrow$ Blok terdekat $2^3 = 8$ IP (`/29`).

#### 4.1. Tabel Pembagian VLSM

| Segmen | Kebutuhan Host | IP Network | Subnet Mask (Prefix Baru) | Host Pertama | Host Terakhir | Broadcast | Jumlah Host Tersedia |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Laboratorium A | 90 host | `10.252.108.0` | `255.255.255.128` (`/25`) | `10.252.108.1` | `10.252.108.126` | `10.252.108.127` | 126 host |
| Laboratorium B | 60 host | `10.252.108.128` | `255.255.255.192` (`/26`) | `10.252.108.129` | `10.252.108.190` | `10.252.108.191` | 62 host |
| Administrasi | 14 host | `10.252.108.192` | `255.255.255.240` (`/28`) | `10.252.108.193` | `10.252.108.206` | `10.252.108.207` | 14 host |
| Point-to-Point | 4 endpoint | `10.252.108.208` | `255.255.255.248` (`/29`) | `10.252.108.209` | `10.252.108.214` | `10.252.108.215` | 6 host |

#### 4.2. Analisis Sisa Alokasi IP
* **Total IP Terpakai:** $128 + 64 + 16 + 8 = 216$ IP.
* **Rentang Sisa IP yang Belum Terpakai:** `10.252.108.216` s/d `10.252.108.255`
* **Jumlah Sisa IP Tersedia:** $256 - 216 = 40$ IP (dapat digunakan sebagai blok *Reserved*).