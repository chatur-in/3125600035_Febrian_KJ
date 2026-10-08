# Latihan BAB 1 — Pengantar Jaringan Komputer dan Internet

> **Dokumen latihan — Pengantar Jaringan Komputer dan Internet**
>
> Berisi soal dan pembahasan dari level pemahaman hingga evaluasi, dilengkapi tabel, perhitungan, studi kasus, serta latihan sejarah dan teknologi jaringan.

## Daftar Isi

- [Level A — Ingatan dan Pemahaman](#level-a--ingatan-dan-pemahaman)
  - [Soal 1–10](#1-jelaskan-pengertian-jaringan-komputer-dengan-menyebutkan-empat-unsur-pokoknya)
- [Level B — Penerapan dan Analisis](#level-b--penerapan-dan-analisis)
  - [Soal 11–18](#11-sebuah-paket-berukuran-1000-byte-dikirim-melalui-tautan-10-mbps-hitung-transmission-delay-ideal-paket-tersebut-jelaskan-komponen-delay-yang-belum-tercakup)
- [Level C — Evaluasi dan Sintesis](#level-c--evaluasi-dan-sintesis)
  - [Soal 19–26](#19-rancang-klasifikasi-kebutuhan-jaringan-kampus-untuk-mahasiswa-staf-administrasi-tamu-kamera-pengawas-dan-laboratorium-riset-jelaskan-alasan-segmentasi-dan-aturan-komunikasi-utamanya)
- [Latihan Tabel dan Sejarah](#latihan-tabel-dan-sejarah)
  - [Perbandingan Kabel UTP Cat 1–Cat 9](#1-perbandingan-kabel-utp-cat-1--cat-9)
  - [Standar Protokol Wi-Fi](#2-standar-protokol-wi-fi-dari-generasi-ke-generasi)
  - [Sejarah dan Timeline Internet](#3-sejarah-dan-timeline-internet-global-dan-indonesia)
  - [Interpretasi Detail Internet pada Fast.com](#4-interpretasi-detail-internet-pada-fastcom)

---

---

## Level A — Ingatan dan Pemahaman

### 1. Jelaskan pengertian jaringan komputer dengan menyebutkan empat unsur pokoknya.
Jaringan komputer adalah kumpulan perangkat otonom yang saling terhubung untuk bertukar data dan sumber daya. Empat unsur pokoknya meliputi:
* **Perangkat (*Nodes*):** Komputer, server, atau peranti akhir yang mengirim/menerima data.
* **Media Transmisi:** Jalur komunikasi berupa kabel (UTP, *Fiber Optic*) atau nirkabel (Wi-Fi, Gelombang Radio).
* **Protokol:** Aturan dan standar yang mengatur cara komunikasi data (misal: TCP/IP).
* **Sumber Daya/Layanan (*Resources*):** Data, aplikasi, atau perangkat keras (seperti printer) yang dibagikan.

---

### 2. Apa yang dimaksud dengan perangkat otonom dalam definisi jaringan?
Perangkat otonom adalah perangkat yang memiliki pemrosesan (CPU), memori, dan sistem operasi sendiri, sehingga dapat berdiri sendiri tanpa bergantung penuh pada komputer lain untuk beroperasi. Perangkat ini tidak dikendalikan secara mutlak oleh perangkat lain di jaringan.

---

### 3. Bedakan data, sinyal, dan paket.
* **Data:** Informasi mentah atau konten digital dalam bentuk matematis/abstrak (teks, gambar, video) yang ingin disampaikan.
* **Sinyal:** Gelombang fisik (elektrik, optik, atau radio) yang merepresentasikan data agar bisa merambat melalui media transmisi.
* **Paket:** Unit atau blok data terstruktur yang dikemas bersama *header* (berisi alamat asal, alamat tujuan, dan kontrol) untuk dikirimkan melalui jaringan berbasis *switching*.

---

### 4. Jelaskan perbedaan PAN, LAN, MAN, dan WAN tanpa hanya menggunakan ukuran jarak.

| Jaringan | Skala & Cakupan | Kepemilikan & Administrasi | Operasional & Teknologi Utama |
| :--- | :--- | :--- | :--- |
| **PAN** | Area personal/pribadi (lingkup tubuh/ruangan) | Dikelola pengguna individu | Bluetooth, Zigbee, NFC |
| **LAN** | Satu gedung, kantor, atau rumah | Dikelola satu organisasi/lokal | Ethernet, Wi-Fi (802.11) |
| **MAN** | Lingkup satu kota atau kawasan metropolitan | Dikelola konsorsium atau penyedia jasa penyewaan | Fiber Optic, Metro Ethernet |
| **WAN** | Antarkota, antarnegara, hingga global | Melibatkan banyak ISP dan penyedia infrastruktur | Routing kompleks, MPLS, Satelit |

---

### 5. Apa perbedaan intranet, ekstranet, dan Internet publik?
* **Intranet:** Jaringan privat yang hanya bisa diakses oleh anggota internal suatu organisasi (misal: karyawan perusahaan).
* **Ekstranet:** Jaringan privat yang memberikan akses terbatas kepada pihak luar terpercaya (seperti pemasok, mitra bisnis, atau klien).
* **Internet Publik:** Jaringan global terbuka yang dapat diakses oleh siapa saja di seluruh dunia.

---

### 6. Mengapa Wi-Fi tidak dapat disamakan dengan Internet?
Wi-Fi adalah teknologi media transmisi nirkabel (LAN) untuk menghubungkan perangkat ke router lokal. Sedangkan Internet adalah jaringan global yang menghubungkan jutaan komputer di seluruh dunia. Terhubung ke Wi-Fi hanya berarti Anda terhubung ke router lokal, bukan jaminan terhubung ke jaringan Internet luar.

---

### 7. Jelaskan perbedaan client, server, dan peer.
* **Client:** Perangkat/aplikasi yang meminta layanan atau data (misal: browser web).
* **Server:** Perangkat/aplikasi berkapasitas tinggi yang menyediakan layanan atau data kepada *client* (misal: web server).
* **Peer:** Perangkat dalam jaringan yang bertindak setara, berfungsi sebagai *client* sekaligus *server* secara bersamaan.

---

### 8. Apa perbedaan bandwidth, throughput, dan goodput?
* **Bandwidth:** Kapasitas maksimum teoritis suatu media transmisi untuk mengirimkan data dalam satuan waktu tertentu, biasanya dinyatakan dalam bit per second (bps). Bandwidth adalah batas atas, bukan kecepatan aktual yang selalu tercapai.
* **Throughput:** Kecepatan transfer data yang sesungguhnya terjadi dalam praktik, yang biasanya lebih kecil dari bandwidth karena dipengaruhi oleh kondisi jaringan seperti kepadatan lalu lintas, jarak, dan gangguan sinyal.
* **Goodput:** Kecepatan transfer data yang benar-benar berguna (*payload* murni) sampai ke tujuan, tanpa menghitung data yang hilang, harus dikirim ulang, atau *overhead* protokol seperti *header* paket.

---

### 9. Sebutkan empat komponen nodal delay.
* **Processing Delay:** Waktu yang dibutuhkan node/router untuk memeriksa *header* paket dan menentukan rute.
* **Queuing Delay:** Waktu tunggu paket dalam antrean buffer router sebelum diproses.
* **Transmission Delay:** Waktu yang dibutuhkan untuk mendorong seluruh bit paket ke dalam media transmisi ($L/R$).
* **Propagation Delay:** Waktu yang dibutuhkan satu bit data untuk merambat dari sumber ke tujuan melalui media fisik ($d/s$).

---

### 10. Mengapa Web tidak sama dengan Internet?
Internet adalah infrastruktur jaringan fisik (kabel, router, IP) yang menghubungkan komputer di seluruh dunia, sedangkan Web (*World Wide Web*) adalah salah satu layanan yang berjalan di atas infrastruktur Internet menggunakan protokol HTTP/HTTPS untuk mengakses dokumen HTML dan media. Contoh layanan Internet selain Web adalah Email (SMTP), Transfer File (FTP), dan SSH.

---

---

## Level B — Penerapan dan Analisis

### 11. Sebuah paket berukuran 1.000 byte dikirim melalui tautan 10 Mbps. Hitung transmission delay ideal paket tersebut. Jelaskan komponen delay yang belum tercakup.

#### Rumus
$$\text{Transmission Delay} = \frac{\text{Ukuran data}}{\text{Bandwidth}}$$

* **Ukuran data:** $1.000\text{ byte} = 8.000\text{ bit}$
* **Bandwidth:** $10\text{ Mbps} = 10 \times 10^6\text{ bit/detik}$

#### Perhitungan
$$\text{Delay} = \frac{8.000}{10 \times 10^6} = 0,0008\text{ detik} = 0,8\text{ ms}$$

**Komponen delay yang belum tercakup:**
* *Propagation delay* (waktu tempuh sinyal di medium)
* *Queuing delay* (antrian di router/switch)
* *Processing delay* (waktu pemrosesan di perangkat jaringan)
* *Nodal delay* (total dari semua komponen di tiap node)

---

### 12. Sebuah kampus memiliki koneksi Internet 2 Gbps, tetapi pengguna di satu lantai hanya memperoleh throughput rendah. Susun sedikitnya lima hipotesis yang tidak langsung menyalahkan koneksi ISP.
* **Switch lantai mengalami *oversubscription*:** Kapasitas *uplink* switch tidak mencukupi untuk jumlah pengguna.
* **Kabel atau konektor fisik rusak/bermasalah:** Misalnya kabel UTP tertekuk, konektor longgar, atau terjadi interferensi.
* **Penggunaan Wi-Fi yang padat:** Banyak pengguna menggunakan Wi-Fi di kanal yang sama, menyebabkan *collision* dan *backoff*.
* **Ada serangan atau malware:** Misalnya *botnet* atau *broadcast storm* yang membanjiri jaringan lokal.
* **Konfigurasi QoS (*Quality of Service*) yang tidak sesuai:** Prioritas *bandwidth* diberikan ke layanan lain, bukan ke pengguna umum.

---

### 13. Bandingkan kebutuhan jaringan untuk transfer berkas cadangan dan panggilan video. Metrik apa yang paling penting bagi masing-masing aplikasi?

| Metrik | Transfer Berkas Cadangan | Panggilan Video |
| :--- | :--- | :--- |
| **Bandwidth** | Penting, tapi bisa ditoleransi jika lambat | Sangat penting, harus cukup untuk resolusi dan *frame rate* |
| **Latensi** | Tidak terlalu kritis (toleransi detik/menit) | Sangat kritis (< 150 ms untuk pengalaman baik) |
| **Jitter** | Tidak relevan | Sangat kritis (menyebabkan video tersendat) |
| **Packet Loss** | Bisa ditoleransi (retransmisi) | Sangat kritis (menyebabkan gambar pecah/putus) |
| **Keandalan** | Penting (integritas data) | Sedang (gangguan sesaat masih bisa diterima) |

#### Kesimpulan
* **Cadangan:** Prioritas *throughput* dan reliabilitas.
* **Video call:** Prioritas latensi, *jitter*, dan *packet loss* rendah.

---

### 14. Sebuah organisasi mempunyai dua koneksi Internet dari dua operator. Keduanya melewati tiang dan jalur ducting yang sama. Evaluasi kualitas redundansinya.

#### Kualitas redundansi Rendah (tidak ideal)

#### Alasan
* ***Single point of failure* fisik:** Jika tiang roboh, kebakaran, atau galian putus kabel, kedua koneksi akan terputus bersamaan.
* **Tidak ada diversitas jalur:** Redundansi seharusnya mencakup jalur fisik yang berbeda (rute berbeda, masuk dari sisi kampus berbeda).

#### Saran perbaikan
Gunakan operator dengan jalur masuk yang berbeda, atau tambahkan koneksi nirkabel (misal *microwave*) sebagai jalur alternatif.

---

### 15. Jelaskan mengapa penambahan bandwidth tidak selalu mengurangi waktu akses ke server yang sangat jauh.
Karena waktu akses total ditentukan oleh:
* ***Propagation delay*:** Kecepatan cahaya di serat optik tidak tergantung *bandwidth*, tetap $\sim 200.000\text{ km/s}$.
* **Latensi *round-trip* (RTT):** Untuk server jauh bisa mencapai 200–400 ms, tidak bisa dikurangi dengan *bandwidth*.
* ***Bandwidth* hanya memengaruhi *transmission delay*:** Yang biasanya kecil dibanding *propagation delay* pada jarak jauh.

**Jadi:** Untuk server jauh, *bottleneck* utama adalah jarak fisik dan jumlah *hop*, bukan *bandwidth*.

---

### 16. Sebuah layanan tersedia 99,9% selama satu tahun. Hitung perkiraan maksimum durasi ketidaktersediaannya. Bandingkan dengan target 99,99%.

$$1\text{ tahun} = 365 \times 24 \times 60 = 525.600\text{ menit}$$

* **Target 99,9%:**
  $$\text{Downtime} = 0,1\% = 0,001 \times 525.600 = 525,6\text{ menit} \approx 8,76\text{ jam}$$
* **Target 99,99%:**
  $$\text{Downtime} = 0,01\% = 0,0001 \times 525.600 = 52,56\text{ menit} \approx 0,876\text{ jam}$$

#### Perbandingan
Target 99,99% jauh lebih ketat, *downtime* hanya sekitar 1/10 dari 99,9%.

---

### 17. Analisis kelebihan dan kelemahan client-server serta P2P untuk distribusi berkas berukuran besar kepada ribuan pengguna.

| Aspek | Client-Server | P2P |
| :--- | :--- | :--- |
| **Keunggulan** | Mudah dikelola, keamanan terpusat, kontrol penuh | Skalabilitas tinggi, biaya server rendah, tahan terhadap lonjakan permintaan |
| **Kelemahan** | Server jadi *bottleneck*, biaya bandwidth besar, titik kegagalan tunggal | Keamanan lebih sulit, ketergantungan pada pengguna (*seed/leecher*), legalitas sering dipertanyakan |

#### Kesimpulan
* **Client-Server:** Cocok untuk internal/enterprise dengan kontrol ketat.
* **P2P:** Cocok untuk publik/open source (misal Linux ISO) karena beban terdistribusi.

---

### 18. Berikan contoh ketika topologi fisik dan topologi logis pada jaringan kampus berbeda.
* **Topologi fisik:** Semua gedung terhubung melalui kabel serat optik ke satu ruang server pusat (topologi *star* fisik).
* **Topologi logis:** Namun, lalu lintas antar gedung dilewatkan melalui VLAN dan *routing*, sehingga secara logis terlihat seperti *ring* atau *mesh* karena ada jalur redundan dan aturan *routing* tertentu.

**Contoh konkret:**
Kampus memiliki 4 gedung. Fisiknya semua kabel menuju ke satu *switch core* (*star*). Namun secara logis, gedung A dan C dibuat dalam satu VLAN, dan lalu lintas antar mereka diatur melalui router sehingga jalur logisnya tidak sama dengan jalur kabel fisik.

---

---

## Level C — Evaluasi dan Sintesis

### 19. Rancang klasifikasi kebutuhan jaringan kampus untuk mahasiswa, staf administrasi, tamu, kamera pengawas, dan laboratorium riset. Jelaskan alasan segmentasi dan aturan komunikasi utamanya.

#### Klasifikasi Kebutuhan & Segmentasi Jaringan Kampus

| Segmen / Profil | Kebutuhan Utama & Bandwidth | Prioritas QoS | Akses Sumber Daya Internal | Akses Internet |
| :--- | :--- | :--- | :--- | :--- |
| **Mahasiswa** | Akses media pembelajaran, browsing, streaming, portabel (Wi-Fi). Bandwidth dinamis/sedang. | *Best-Effort* | Terbatas (LMS, Portal Akademik, Perpustakaan Digital). | Bebas (dengan batas kuota/rate-limiting). |
| **Staf Administrasi** | Akses aplikasi ERP, Keuangan, Kepegawaian, Email enterprise, VoIP. Bandwidth terjamin & stabil. | Tinggi (SLA & Latensi Rendah) | Penuh ke server internal administrasi dan database. | Terbatas pada domain & layanan kerja resmi. |
| **Tamu (*Guest*)** | Akses web mendasar dan pesan instan (Wi-Fi publik). Bandwidth dibatasi (*rate limit*). | Sangat Rendah | **Tidak ada** (Isolasi total dari seluruh IP internal). | Hanya HTTP/HTTPS/DNS standar. |
| **Kamera Pengawas (CCTV)** | Streaming video kontinu 24/7, latensi stabil, throughput *upload* tinggi. | Menengah–Tinggi (Dedicated) | Terisolasi khusus ke Server NVR (*Network Video Recorder*). | **Tidak Ada** (Di-block total dari internet). |
| **Laboratorium Riset** | Transfer data masif (HPC, Datasets), pemrosesan cloud, latensi sangat rendah. | Sangat Tinggi (Jumbo Frames) | Akses ke Server Riset, Storage lokal, dan jaringan antar-lab. | Bebas tanpa batasan port (*unfiltered* untuk riset). |

#### Alasan Utama Segmentasi (VLAN / Subnetting):
* **Keamanan (*Security & Isolation*):** Mencegah potensi kebocoran data sensitif (misal: mahasiswa atau tamu tidak bisa meretas atau memindai jaringan administrasi dan server nilai/keuangan).
* **Kinerja dan Pengurangan Broadcast Domain:** Mengisolasi lalu lintas *broadcast* agar lalu lintas padat dari Wi-Fi Mahasiswa atau video CCTV tidak membebani segmen jaringan lainnya.
* **Pengelolaan QoS (*Quality of Service*):** Memudahkan pengalokasian *bandwidth* dan prioritas lalu lintas berdasarkan fungsi kritis tiap entitas.

#### Aturan Komunikasi Utama (*Firewall & Access Control List / ACL Rules*):
* **Aturan 1 (Isolasi Tamu):** *VLAN Tamu* hanya diizinkan lalu lintas `Outbound` ke Internet melalui port `80`, `443`, dan `53` (DNS). Semua akses ke subnet privat (`10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`) diblokir total (`Deny All`).
* **Aturan 2 (Restriksi CCTV):** *VLAN CCTV* hanya dapat berkomunikasi secara langsung ke IP Server NVR pada port spesifik (misal: RTSP `554`). Semua lalu lintas keluar ke Internet atau segmen kampus lain di-drop.
* **Aturan 3 (Proteksi Data Administrasi):** Hanya *VLAN Administrasi* dan perangkat terdaftar (MAC/IP terotentikasi) yang dapat mengakses server database akademik/keuangan.
* **Aturan 4 (Inter-VLAN Routing Terkontrol):** *VLAN Riset* dapat terhubung ke *VLAN Mahasiswa/Dosen* hanya jika melewati prosedur otentikasi VPN internal atau *firewall inspection*.

---

### 20. Evaluasi pernyataan: “Jaringan internal tidak memerlukan enkripsi karena sudah dilindungi firewall.” Gunakan prinsip kerahasiaan, integritas, dan ketersediaan.

**Evaluasi:** Pernyataan tersebut **TIDAK TEPAT / SALAH (Mitos Keamanan Klasik)**. Mengandalkan *firewall* perimeter tanpa enkripsi internal melanggar prinsip *Zero Trust Network Architecture* ("*Never Trust, Always Verify*").

**Analisis Berdasarkan Prinsip CIA Triad:**

* **Kerahasiaan (*Confidentiality*):**
  * *Ancaman:* Tanpa enkripsi internal (seperti HTTPS, TLS, SSH), siapapun yang berhasil menembus perimeter atau memasang alat *sniffing* (misal: pegawai nakal, penyusup di jaringan Wi-Fi lokal, atau perangkat IoT terinfeksi) dapat membaca data mentah (*plaintext*) yang melintas di jaringan internal (seperti kata sandi, token API, dan data keuangan).
  * *Evaluasi:* Firewall perimeter tidak dapat mencegah *packet sniffing* di dalam broadcast domain internal. Enkripsi (TLS/IPsec) mutlak diperlukan untuk menjaga kerahasiaan data.
* **Integritas (*Integrity*):**
  * *Ancaman:* Data *plaintext* di dalam jaringan internal rawan terkena serangan *Man-in-the-Middle* (MitM) seperti *ARP Spoofing* atau *DNS Poisoning*. Penyerang dapat merubah isi data yang ditransmisikan sebelum sampai ke server tujuan tanpa terdeteksi.
  * *Evaluasi:* Enkripsi modern yang dilengkapi *Message Authentication Code* (MAC/HMAC) memastikan data internal tidak diubah atau dimanipulasi di tengah jalan.
* **Ketersediaan (*Availability*):**
  * *Ancaman:* Jika perangkat perimeter (firewall) mengalami penyusupan (*breach*) atau dilewati melalui jalur belakang (*backdoor/insider threat*), seluruh sistem internal tanpa enkripsi langsung terkeskpos (*total compromise*), yang pada akhirnya dapat berujung pada penyebaran *ransomware* yang menghentikan ketersediaan layanan kampus.
  * *Evaluasi:* Enkripsi internal bertindak sebagai pertahanan berlapir (*Defense-in-Depth*) untuk membatasi pergerakan lateral (*lateral movement*) penyerang.

---

### 21. Diskusikan mengapa Internet dapat berkembang tanpa otoritas teknis pusat tunggal. Jelaskan manfaat serta risikonya.

#### Mengapa Internet Dapat Berkembang Tanpa Otoritas Pusat Tunggal?
Internet berkembang secara eksponensial karena dibangun di atas arsitektur **Terdesentralisasi** dan **Sistem Tata Kelola Multi-pemangku Kepentingan (*Multi-stakeholder Governance*)**. Standar teknis tidak ditentukan oleh satu pemerintah atau perusahaan, melainkan konsensus terbuka melalui lembaga seperti **IETF** (*Internet Engineering Task Force*), **ICANN** (pengelolaan domain/IP), **IEEE** (standar fisik/link), dan **RIR** (seperti APNIC) untuk alokasi IP. Selain itu, skema pengalamatan *Autonomous System* (AS) dan protokol **BGP** (*Border Gateway Protocol*) memungkinkan ribuan jaringan independen saling bernegosiasi dan bertukar lalu lintas secara sukarela (*peering/transit*).

#### Manfaat:
* **Skalabilitas dan Inovasi Cepat:** Siapapun dapat menciptakan aplikasi baru (misal: World Wide Web, streaming video, AI) tanpa perlu meminta izin dari otoritas pusat.
* **Ketahanan (*Resilience & Fault Tolerance*):** Tidak ada *single point of failure*. Jika satu jaringan atau jalur terputus, lalu lintas internet secara otomatis memutar rute melalui jalur lain.
* **Interoperabilitas Global:** Penggunaan standar terbuka (*Open Standards*) memastikan perangkat keras dari vendor manapun dapat saling berkomunikasi.

#### Risiko:
* **Kerentanan Keamanan Rute Global:** BGP awalnya didesain atas dasar rasa saling percaya (*trust*), sehingga rawan terhadap *BGP Hijacking* atau *Route Leaks* yang membelokkan lalu lintas global.
* **Kesulitan Penegakan Hukum & Penanganan Kejahatan Cyber:** Tidak adanya satu yurisdiksi tunggal menyulitkan penindakan terhadap pelaku kejahatan siber, penyebaran botnet, dan serangan DDoS lintas negara.
* **Fragmentasi Internet (*Splinternet*):** Adanya risiko beberapa negara membuat sensor ketat dan barikade nasional (seperti *Great Firewall*), yang mengancam keutuhan internet global.

---

### 22. Bandingkan circuit switching dan packet switching untuk layanan suara. Jelaskan mengapa suara modern tetap dapat berjalan pada jaringan paket.

#### Tabel Perbandingan untuk Layanan Suara

| Parameter | *Circuit Switching* (PSTN / Telepon Tradisional) | *Packet Switching* (VoIP / VoLTE / OTT) |
| :--- | :--- | :--- |
| **Prinsip Kerja** | Membuka sirkuit fisik/logis khusus yang terdedikasi sepanjang durasi panggilan. | Memotong suara menjadi paket-paket kecil dan dikirimkan secara independen melalui jaringan berbagi. |
| **Efisiensi Jalur** | Sangat Rendah (jalur tetap terpesan meskipun ada jeda hening/diam). | Sangat Tinggi (jalur digunakan bersama oleh banyak data/aplikasi lain). |
| **Jaminan Kualitas** | Terjamin secara konstan (*Bandwidth, Latency, Jitter* terisolasi). | Bergantung pada kondisi jaringan dan penerapan mekanisme QoS. |
| **Skalabilitas & Biaya** | Mahal dan sulit dikembangkan (membutuhkan infrastruktur sakelar fisik besar). | Sangat Murah dan Fleksibel (berjalan di atas infrastruktur IP yang sudah ada). |

#### Mengapa Suara Modern Tetap Dapat Berjalan Baik pada Jaringan Paket?
Meskipun jaringan paket bersifat *best-effort* (tidak menjamin urutan dan waktu sampai), suara modern dapat berjalan sangat jernih karena dukungan teknologi berikut:
1. **Penerapan QoS (*Quality of Service*):** Mekanisme seperti *DiffServ* (DSCP) mengidentifikasi dan memberi prioritas tertinggi pada paket data suara (RTP) di router/switch dibanding paket data biasa (web/download).
2. **Kapasitas Bandwidth Tinggi & Latensi Rendah:** Jaringan serat optik, 4G/5G, dan Wi-Fi modern menyediakan *bandwidth* berlimpah yang secara dramatis menekan *queuing delay*.
3. **Codec Suara Canggih (*Adaptive Codecs*):** Codec modern (seperti Opus atau AMR-WB) mampu melakukan kompresi tinggi, menggunakan *silence suppression* (hanya mengirim paket saat ada suara), dan menyesuaikan *bitrate* secara otomatis sesuai kondisi jaringan.
4. **Buffer Jitter & Kompensasi Hilang Paket (*PLC*):** Klien penerima menggunakan *jitter buffer* untuk menyusun kembali urutan paket suara dan teknik *Packet Loss Concealment* (PLC) untuk menutupi celah jika ada paket yang hilang.

---

### 23. Ambil satu keluhan nyata atau hipotetis berupa “Internet lambat”. Susun prosedur pengumpulan bukti, pengujian hipotesis, dan kriteria keberhasilan perbaikannya.

#### Studi Kasus Keluhan: "Akses Internet di Gedung Rektorat Lambat Saat Jam Kerja."

#### 1. Prosedur Pengumpulan Bukti (*Evidence Collection*):
* **Pengumpulan Metrik Klien:** Minta pengguna menjalankan uji kecepatan (*Speedtest / Fast.com*) dan catat metrik: *Throughput* (Download/Upload), *Latency (Unloaded vs Loaded)*, serta *Packet Loss*.
* **Pemeriksaan Statistik Alat Jaringan:** Tarik data utilisasi *bandwidth* pada *Core Router* dan *Access Point* (AP) lokal melalui SNMP/NMS (misal: MRTG/PRTG/Zabbix).
* **Capture Paket Data:** Lakukan perekaman paket (*packet capture*) dengan Wireshark pada titik antarmuka LAN untuk melihat persentase *TCP Retransmission* dan *DNS Response Time*.

#### 2. Pengujian Hipotesis (*Hypothesis Testing*):

| Hipotesis Masalah | Langkah Pengujian | Bukti / Indikator Konfirmasi |
| :--- | :--- | :--- |
| **H1: Bandwidth ISP Penuh** | Cek grafik lalu lintas pada interface Router WAN. | Utilisasi WAN mencapai 100% dari total alokasi jalur. |
| **H2: Interferensi / Kepadatan Wi-Fi** | Pindai spektrum radio Wi-Fi di area lokasi pengguna. | Utilisasi *Airtime* Wi-Fi > 80% atau *Frame Retry Rate* > 20% pada frekuensi 2.4 GHz. |
| **H3: Masalah Resolusi DNS** | Jalankan `nslookup` / `dig` ke server DNS internal vs Public DNS (`8.8.8.8`). | *DNS Latency* internal > 500ms atau sering *timeout*. |
| **H4: Monopoliser Bandwidth** | Analisis *Top Talkers* menggunakan protokol NetFlow/sFlow di router. | Ada beberapa host melakukan *download* berkas raksasa / torrent tanpa batasan rate limit. |

#### 3. Kriteria Keberhasilan Perbaikan (*Success Criteria*):
* **Kuantitatif:**
  * Throughput minimum tiap pengguna mencapai SLA lokal ($\ge 10\text{ Mbps}$).
  * Latensi *ping* internal gateway $< 5\text{ ms}$ dan latensi ke internet $< 50\text{ ms}$.
  * *Packet loss* di lingkungan LAN/Wi-Fi $\le 0.5\%$.
* **Kualitatif:** Pengguna dapat melakukan *video call* dan membuka portal aplikasi tanpa adanya *lag* atau keluhan ulang dalam rentang pengamatan 3 hari.

---

### 24. Kunjungi statistik IPv6 Google atau sumber pengukuran APNIC. Catat tanggal, definisi metrik, populasi yang diukur, dan nilai untuk Indonesia. Jelaskan mengapa angka dari dua sumber dapat berbeda.

#### Pencatatan Data Pengukuran Adopsi IPv6 Indonesia:

* **Sumber 1: Google IPv6 Adoption Statistics**
  * **Tanggal Akses/Data:** *Oktober 2026*
  * **Definisi Metrik:** Persentase pengguna yang mengakses situs-situs web Google menggunakan IPv6 (diukur berdasarkan kueri DNS dan koneksi TCP ke server Google).
  * **Populasi yang Diukur:** Seluruh lalu lintas pengguna Internet di Indonesia yang mengakses layanan Google (Search, YouTube, Gmail, dll.).
  * **Nilai Adopsi Indonesia:** $\approx 15,4\%$ *(estimasi tren)*.

* **Sumber 2: APNIC Labs (IPv6 Capable Rate)**
  * **Tanggal Akses/Data:** *Oktober 2026*
  * **Definisi Metrik:** Persentase populasi pengguna Internet yang mampu melakukan pengambilan sampel aset web (*fetch test*) via IPv6.
  * **Populasi yang Diukur:** Pengguna Internet di Indonesia yang memuat iklan web (*analytics script*) yang disiapkan oleh APNIC di berbagai situs web media.
  * **Nilai Adopsi Indonesia:** $\approx 18,2\%$ *(estimasi tren)*.

#### Mengapa Angka dari Kedua Sumber Dapat Berbeda?
1. **Perbedaan Metodologi Pengukuran:** Google mengukur koneksi **aktual** dari pengguna yang menggunakan layanan Google, sedangkan APNIC menguji **kemampuan (*capability*)** perangkat/jaringan melalui *script* iklan terdistribusi.
2. **Cakupan Sampel Populasi (*Sampling Bias*):** Google hanya mencakup pengguna yang membuka layanan Google. Jika pengguna mengakses internet melalui jaringan seluler yang mengaktifkan IPv6 secara *default* saat membuka YouTube, angka Google akan condong merefleksikan trafik tersebut. APNIC mengambil sampel dari penempatan iklan di ribuan situs web lokal dan global yang lebih heterogen.
3. **Perlakuan DNS & Happy Eyeballs:** Algoritma *Happy Eyeballs* pada sistem operasi dapat memilih IPv4 jika respons IPv6 dinilai sedikit lebih lambat, yang memengaruhi perhitungan koneksi aktual pada server Google.

---

### 25. Buat argumen mengenai penggunaan satelit orbit rendah sebagai koneksi utama atau cadangan bagi kampus di wilayah terpencil. Nilai kinerja, biaya, ketergantungan cuaca, pengelolaan, dan keamanan.

#### Argumen / Rekomendasi:
Satelit Orbit Rendah / LEO (*Low Earth Orbit*, seperti Starlink/OneWeb) **sangat direkomendasikan sebagai koneksi UTAMA** bagi kampus terpencil yang belum terjangkau serat optik (*Fiber Optic*), dan **sangat ideal sebagai koneksi CADANGAN (*Backup/Failover*)** bagi kampus terpencil yang hanya memiliki satu jalur transmisi terestrial (seperti *Radio Microwave* yang terbatas).

#### Matriks Evaluasi Komparatif

| Parameter Evaluasi | Analisis LEO Satellite (Starlink, dll.) | Implikasi Bagi Kampus Terpencil |
| :--- | :--- | :--- |
| **Kinerja (*Performance*)** | **Latensi Rendah ($20 - 40\text{ ms}$)** dibandingkan Satelit Geostasioner (GEO: $>500\text{ ms}$). *Throughput* tinggi ($100 - 220\text{ Mbps}$ per terminal). | Sangat memadai untuk aktivitas akademis, *video conference* (Zoom/GMeet), dan akses LMS kampus. |
| **Biaya (*Cost*)** | **Biaya Modal (CAPEX) Rendah-Sedang** (hanya perlu piringan/antena Dish). **Biaya Operasional (OPEX) Sedang**. | Jauh lebih murah daripada menggelar kabel Serat Optik mandiri sejauh puluhan kilometer. |
| **Ketergantungan Cuaca** | Redaman hujan (*Rain Fade*) jauh lebih kecil dibanding satelit GEO karena sinyal menembus atmosfer lebih pendek, namun hujan badai sangat lebat masih dapat menurunkan kualitas sinyal sesaat. | Perlu diantisipasi dengan penempatan posisi parabola bebas dari halangan visual (*Clear Sky View*). |
| **Pengelolaan (*Management*)** | **Sangat Mudah (*Plug and Play*).** Tidak memerlukan konfigurasi jaringan tingkat fisik yang rumit di sisi kampus. | Menghemat beban operasional tim IT kampus terpencil. |
| **Keamanan (*Security*)** | Jalur nirkabel ke angkasa rawan terhadap *jamming* spektrum frekuensi atau *interception* jika tidak dienkripsi. | Kampus **wajib** menerapkan enkripsi *IPsec VPN* atau *TLS* dari terminal kampus langsung ke *Datacenter* pusat. |

---

### 26. Jelaskan bagaimana otomatisasi jaringan dapat meningkatkan konsistensi sekaligus memperbesar dampak kesalahan. Usulkan kontrol teknis dan proses untuk mengurangi risiko tersebut.

#### Dua Sisi Otomatisasi Jaringan:
* **Meningkatkan Konsistensi:** Otomatisasi (menggunakan alat seperti Ansible, Terraform, Nornir, atau Python) menghilangkan *human error* (kesalahan ketik manual) saat mengonfigurasi puluhan hingga ratusan perangkat. Setiap perangkat menerima parameter konfigurasi yang identik sesuai standar.
* **Memperbesar Dampak Kesalahan (*Blast Radius*):** Jika terdapat kesalahan logika atau bug pada skrip/templat otomatisasi, kesalahan tersebut akan direplikasi secara instan ke seluruh jaringan (*blast radius* mencakup seluruh infrastruktur dalam hitungan detik), yang dapat menyebabkan *blackout/outage* massal.

#### Alur Kerja & Kontrol Mitigasi Risiko:
`[Kode Konfigurasi (Git)]` ➔ `[Linter & Dry-Run]` ➔ `[Validasi Lab/Staging]` ➔ `[Canary Deployment]` ➔ `[Automated Rollback]`

---

---

## Latihan Tabel dan Sejarah

### 1. Perbandingan Kabel UTP Cat 1 – Cat 9

| Kategori | Standar Umum | Frekuensi Maksimum | Kecepatan Data Maksimum | Aplikasi Utama | Catatan Tambahan |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Cat 1** | TIA/EIA-568 | 0,1 MHz | < 1 Mbps | Telepon analog (suara) | Tidak untuk data |
| **Cat 2** | TIA/EIA-568 | 1 MHz | 4 Mbps | Token Ring lama, ISDN | Sudah usang |
| **Cat 3** | TIA/EIA-568 | 16 MHz | 10 Mbps | 10BASE-T Ethernet, telepon | Umum di instalasi telepon lama |
| **Cat 4** | TIA/EIA-568 | 20 MHz | 16 Mbps | Token Ring | Jarang digunakan, hanya peningkatan kecil dari Cat 3 |
| **Cat 5** | TIA/EIA-568 | 100 MHz | 100 Mbps (Fast Ethernet) | 100BASE-TX, 10BASE-T | Standar lama, masih umum |
| **Cat 5e** | TIA/EIA-568-B.2 | 100 MHz | 1 Gbps (Gigabit Ethernet) | 1000BASE-T | Peningkatan dari Cat 5, mengurangi *crosstalk* |
| **Cat 6** | TIA/EIA-568-B.2-1 | 250 MHz | 1 Gbps (100m) / 10 Gbps (55m) | Gigabit Ethernet | Memiliki pemisah plastik (*spine*) untuk mengurangi interferensi |
| **Cat 6a** | TIA/EIA-568-B.2-10 | 500 MHz | 10 Gbps (100m) | 10GBASE-T | Peningkatan Cat 6, mendukung 10G hingga jarak penuh |
| **Cat 7** | ISO/IEC 11801 | 600 MHz | 10 Gbps | 10GBASE-T | Kabel *Shielded* (S/FTP), tidak diakui TIA/EIA |
| **Cat 7a** | ISO/IEC 11801 | 1000 MHz | 10 Gbps+ | 10GBASE-T, CATV | Peningkatan Cat 7, *shielded* |
| **Cat 8** | TIA-568-C.2-1 | 2000 MHz | 40 Gbps (30m) | Data Center, *switch-to-switch* | Kabel *Shielded* (S/FTP), jarak terbatas |
| **Cat 9** | Dalam pengembangan | > 2000 MHz | > 40 Gbps | Belum ditentukan | Belum menjadi standar resmi |

---

### 2. Standar Protokol Wi-Fi dari Generasi ke Generasi

| Standar | Nama Generasi | Tahun | Frekuensi | Kecepatan Maksimum | Fitur Kunci |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **802.11** | - | 1997 | 2.4 GHz | 2 Mbps | Standar awal, menggunakan FHSS atau DSSS |
| **802.11a** | - | 1999 | 5 GHz | 54 Mbps | Menggunakan OFDM, kecepatan lebih tinggi |
| **802.11b** | - | 1999 | 2.4 GHz | 11 Mbps | HR-DSSS, jangkauan lebih luas namun lebih lambat |
| **802.11g** | - | 2003 | 2.4 GHz | 54 Mbps | OFDM di 2.4 GHz, kompatibel dengan 802.11b |
| **802.11n** | Wi-Fi 4 | 2009 | 2.4 & 5 GHz | 600 Mbps | Memperkenalkan MIMO (*Multiple Input Multiple Output*) |
| **802.11ac** | Wi-Fi 5 | 2013 | 5 GHz | 6.93 Gbps | MU-MIMO, channel hingga 160 MHz |
| **802.11ax** | Wi-Fi 6 / 6E | 2019 | 2.4, 5, & 6 GHz | 9.6 Gbps | OFDMA, MU-MIMO, TWT untuk efisiensi daya |
| **802.11be** | Wi-Fi 7 | 2024 | 2.4, 5, & 6 GHz | 46 Gbps | 320 MHz channel, 4096-QAM, *Multi-Link Operation* (MLO) |

---

### 3. Sejarah dan Timeline Internet Global dan Indonesia

#### Timeline Internet Global
Perkembangan internet dimulai dari proyek penelitian militer hingga menjadi jaringan global.

| Tahun | Peristiwa Penting |
| :--- | :--- |
| **1957** | Uni Soviet meluncurkan Sputnik, memicu Amerika Serikat membentuk ARPA (*Advanced Research Projects Agency*). |
| **1969** | ARPANET diciptakan oleh Departemen Pertahanan AS, menghubungkan 4 universitas (UCLA, Stanford, UCSB, Univ. of Utah). |
| **1971** | Ray Tomlinson menciptakan sistem email pertama dan memilih simbol '@'. |
| **1973** | ARPANET mulai berkembang ke luar AS (Inggris dan Norwegia). |
| **1982/1983** | TCP/IP menjadi standar protokol internet. |
| **1983** | Domain Name System (DNS) diperkenalkan. |
| **1985** | Domain name pertama, `symbolics.com`, didaftarkan. |
| **1989/1990** | Tim Berners-Lee di CERN menciptakan World Wide Web (WWW). |
| **1991** | Situs web pertama dibuat oleh Tim Berners-Lee di CERN. |
| **1993** | Mosaic, browser web pertama yang *user-friendly*, diluncurkan. |
| **1994** | Perusahaan internet seperti Amazon dan Yahoo muncul; Netscape Navigator dirilis. |
| **1998** | Google didirikan, merevolusi pencarian informasi. |
| **2004** | Facebook diluncurkan, mengubah interaksi sosial online. |
| **2005** | YouTube muncul dan merevolusi video digital. |
| **2007** | Apple iPhone diperkenalkan, memicu adopsi internet mobile secara massal. |
| **2010-an** | Internet semakin cepat dengan 5G, *cloud computing*, dan AI; *Internet of Things* (IoT) berkembang. |
| **2020-an** | Peluncuran Starlink dan proyek satelit lain untuk cakupan internet global. |

#### Timeline Internet di Indonesia
Internet masuk ke Indonesia pada awal 1990-an melalui lingkungan akademis dan dikenal dengan semangat gotong royong.

| Tahun | Peristiwa Penting |
| :--- | :--- |
| **Awal 1990-an** | Internet mulai dikenal di kalangan akademisi dengan sebutan "Paguyuban Network". |
| **1992-1994** | Pembangunan jaringan internet dipelopori oleh M. Samik Ibrahim, Onno W. Purbo, dkk. |
| **1994** | IndoNet berdiri sebagai ISP komersial pertama di Indonesia. |
| **1995** | Pengguna internet di Indonesia mulai dapat mengakses internet luar negeri via *remote browser* Lynx. |
| **1996** | Bisnis warung internet (warnet) mulai tumbuh dan menjamur di kota-kota besar. |
| **1998** | APJII (Asosiasi Penyelenggara Jasa Internet Indonesia) didirikan. |
| **1998** | Internet berperan penting dalam aktivitas reformasi dan perubahan demokrasi. |
| **Awal 2000-an** | Era broadband dan internet seluler (3G, 4G) dimulai. |
| **2010-an** | Media sosial dan *e-commerce* berkembang pesat. |
| **2024** | Pengguna internet Indonesia mencapai 221,6 juta jiwa (penetrasi ~79,5%). |
| **Saat ini** | Pemerataan akses melalui Palapa Ring, Satria-1, dan satelit LEO seperti Starlink. |

---

### 4. Interpretasi Detail Internet pada Fast.com

Fast.com digunakan untuk mengukur kecepatan koneksi internet, terutama kecepatan *download*.

| Detail | Arti | Interpretasi |
| :--- | :--- | :--- |
| **Download** | Kecepatan menerima data dari internet | Semakin besar Mbps, semakin cepat mengunduh file dan *streaming* |
| **Upload** | Kecepatan mengirim data ke internet | Semakin besar Mbps, semakin cepat mengunggah file atau *video call* |
| **Latency / Unloaded** | Waktu respons saat jaringan tidak terbebani | Semakin kecil nilainya, semakin responsif koneksi |
| **Latency / Loaded** | Waktu respons saat koneksi digunakan penuh | Nilai tinggi menunjukkan koneksi dapat mengalami *delay* saat *bandwidth* digunakan |
| **Mbps** | Megabit per second | Satuan kecepatan transfer data |
| **Client** | Perangkat yang melakukan pengujian | Menunjukkan perangkat/lokasi yang digunakan untuk tes |
| **Server** | Server tumpuan untuk pengujian | Menunjukkan lokasi/server tujuan pengujian |

#### Analisis Hasil Pengujian Contoh (Fast.com)

| Parameter | Hasil | Interpretasi |
| :--- | :--- | :--- |
| **Download Speed** | 28 Mbps | Cukup untuk *browsing*, *streaming*, pembelajaran daring, dan unduh file sedang. |
| **Upload Speed** | 12 Mbps | Cukup untuk unggah file, *video conference*, dan kirim tugas. |
| **Latency - Unloaded** | 6 ms | Sangat rendah, koneksi memiliki responsibilitas cepat saat idle. |
| **Latency - Loaded** | 205 ms | Cukup tinggi, terjadi peningkatan *delay* signifikan saat jaringan terbebani penuh. |
| **Client** | Tulangan, ID | Perangkat klien terdeteksi di Tulangan, Indonesia. |
| **Server** | Kota Surabaya, ID / Singapore, SG | Server uji yang terhubung berada di Surabaya dan Singapura. |

**Kesimpulan Evaluasi:**
Secara keseluruhan, kecepatan *download* 28 Mbps dan *upload* 12 Mbps sangat mencukupi kebutuhan umum harian. Nilai *unloaded latency* 6 ms menunjukkan respons instan. Namun, lonjakan *loaded latency* hingga 205 ms mengindikasikan adanya potensi keterlambatan pada aplikasi sensitif waktu (*game online*, *real-time video*) saat *bandwidth* terpakai secara penuh.
