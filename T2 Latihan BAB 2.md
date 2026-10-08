# Latihan BAB 2 — Komunikasi Jaringan dan Model Berlapis

> **Dokumen latihan — Komunikasi Jaringan dan Model Berlapis**
>
> Pembahasan mencakup model OSI, TCP/IP, enkapsulasi, protokol jaringan, troubleshooting, keamanan, hingga prinsip desain jaringan.

## Daftar Isi

- [Level A — Ingatan dan Pemahaman](#level-a--ingatan-dan-pemahaman)
  - [Soal 1–10](#1-jelaskan-alasan-komunikasi-jaringan-disusun-berlapis)
- [Level B — Penerapan dan Analisis](#level-b--penerapan-dan-analisis)
  - [Soal 11–20](#11-petakan-http-tls-tcp-udp-quic-ipv6-icmp-ethernet-wi-fi-dan-dns-ke-model-tcpip-tandai-protokol-yang-pemetaannya-memerlukan-penjelasan)
- [Level C — Evaluasi dan Sintesis](#level-c--evaluasi-dan-sintesis)
  - [Soal 21–30](#21-evaluasi-pernyataan-model-osi-tidak-lagi-relevan-karena-internet-menggunakan-tcpip-susun-argumen-akademik-yang-membedakan-model-protokol-dan-kegunaan-pedagogis)

---

---

## Level A — Ingatan dan Pemahaman

### 1. Jelaskan alasan komunikasi jaringan disusun berlapis.

Komunikasi jaringan disusun berlapis (*layered architecture*) untuk beberapa alasan utama:

- **Dekomposisi Masalah (Kompleksitas):** Memecah masalah komunikasi jaringan yang sangat kompleks menjadi bagian-bagian yang lebih kecil dan mudah dikelola.

- **Abstraksi dan Modularitas:** Setiap lapisan fokus pada tugas/fungsi spesifik tanpa harus tahu bagaimana lapisan lain diimplementasikan.

- **Independensi dan Interoperabilitas:** Perubahan atau pembaruan teknologi di satu lapisan (misalnya mengganti kabel Ethernet dengan Wi-Fi di Physical/Data Link) tidak memengaruhi lapisan di atasnya (IP, TCP, atau HTTP).

- **Standardisasi:** Memudahkan vendor perangkat lunak dan perangkat keras mengikuti standar yang sama sehingga produk dari vendor berbeda dapat saling berkomunikasi.

### 2. Bedakan layanan, antarmuka, dan protokol.

- **Layanan (*Service*):** Menjelaskan *apa* yang disediakan oleh suatu lapisan kepada lapisan di atasnya melalui seperangkat operasi/fungsi (tidak mendefinisikan bagaimana operasi tersebut diimplementasikan).

- **Antarmuka (*Interface*):** Menjelaskan *bagaimana* lapisan di atas mengakses layanan dari lapisan di bawahnya (seperti panggilan API, fungsi, atau batas antar-lapisan pada node yang sama).

- **Protokol (*Protocol*):** Seperangkat aturan dan format pesan yang mengatur *bagaimana* entitas sejajar (*peer entities*) pada dua mesin yang berbeda berkomunikasi untuk menyediakan suatu layanan.

### 3. Sebutkan tujuh lapisan OSI dari bawah ke atas beserta fungsi utamanya.

1. **Physical (Layer 1):** Mentransmisikan bit mentah (*raw bits*) melalui media fisik (kabel, gelombang radio, optik).

2. **Data Link (Layer 2):** Menyediakan transfer data bebas kesalahan antar-node yang terhubung langsung (*hop-to-hop*), mengatur enkapsulasi *frame*, kontrol akses media (MAC), dan deteksi/koreksi kesalahan fisik.

3. **Network (Layer 3):** Mengatur pengalamatan logis (IP address), *routing*, dan pengiriman paket dari node asal ke node tujuan melewati banyak jaringan (*host-to-host*).

4. **Transport (Layer 4):** Menyediakan komunikasi ujung-ke-ujung (*end-to-end*), kendali aliran (*flow control*), kendali kongesti (*congestion control*), serta pemulihan kesalahan (*multiplexing* via port/TCP/UDP).

5. **Session (Layer 5):** Mengelola, membuka, memelihara, dan menutup sesi atau dialog antar-aplikasi (*dialog control* & *synchronization*).

6. **Presentation (Layer 6):** Mengatur sintaksis dan format data, termasuk translasi karakter (ASCII/Unicode), kompresi data, dan enkripsi/dekripsi.

7. **Application (Layer 7):** Menyediakan antarmuka langsung bagi aplikasi pengguna (HTTP, FTP, SMTP, DNS) untuk mengakses layanan jaringan.

### 4. Sebutkan empat lapisan model TCP/IP.

1. **Application Layer** (Menggabungkan Application, Presentation, dan Session pada OSI)

2. **Transport Layer** (Host-to-Host)

3. **Internet Layer** (Sama dengan Network layer pada OSI)

4. **Network Access / Link Layer** (Menggabungkan Data Link dan Physical pada OSI)

### 5. Mengapa model TCP/IP kadang disajikan sebagai lima lapisan?

Model TCP/IP sering disajikan sebagai model **5 Lapisan** (*Hybrid / Updated Internet Model*) untuk kepentingan pengajaran/pedagogis. Lapisan paling bawah (*Network Access*) dipecah kembali menjadi **Data Link Layer** (Lapisan 2) dan **Physical Layer** (Lapisan 1) agar penjelasan aspek perangkat keras/media komunikasi dan kontrol akses media (seperti Ethernet, Wi-Fi, pengkodean bit) dapat dijelaskan dengan lebih jelas dan terstruktur sesuai kenyataan arsitektur jaringan modern.

### 6. Apa perbedaan frame, IP packet, TCP segment, dan UDP datagram?

- **Frame:** Unit Data Protokol (PDU) di **Data Link Layer (Layer 2)**, berisi header/trailer MAC address dan payload paket L3.

- **IP Packet:** PDU di **Network Layer (Layer 3)**, berisi IP header (alamat asal & tujuan) serta payload segmen/datagram L4.

- **TCP Segment:** PDU di **Transport Layer (Layer 4)** yang berorientasi koneksi (*connection-oriented*), andal, menggunakan header TCP (nomor urut, ack, port).

- **UDP Datagram:** PDU di **Transport Layer (Layer 4)** yang tanpa koneksi (*connectionless*), tidak andal, menggunakan header UDP yang simpel dan berbobot ringan (*low overhead*).

### 7. Definisikan header, trailer, dan payload.

- **Header:** Informasi kontrol yang ditambahkan di *awal* unit data oleh suatu protokol (berisi alamat asal/tujuan, port, nomor urut, flag, dll.).

- **Payload:** Data aktual atau beban data yang dibawa oleh protokol tersebut (biasanya merupakan PDU utuh dari lapisan di atasnya).

- **Trailer:** Informasi kontrol tambahan yang ditambahkan di *akhir* unit data (umumnya pada Layer 2/Data Link, seperti nilai FCS/CRC untuk pengecekan kesalahan).

### 8. Jelaskan enkapsulasi dan dekapsulasi.

- **Enkapsulasi:** Proses membungkus data dari lapisan atas dengan menambahkan header (dan/atau trailer) milik lapisan saat ini selagi data bergerak **turun** dari lapisan Aplikasi ke lapisan Fisik pada sisi pengirim.

- **Dekapsulasi:** Proses sebaliknya, yaitu melepas/membuka header (dan trailer) dari data selagi data bergerak **naik** dari lapisan Fisik ke lapisan Aplikasi pada sisi penerima.

### 9. Apa fungsi multiplexing dan demultiplexing?

- **Multiplexing:** Menggabungkan aliran data dari banyak aplikasi/sumber yang berbeda di sisi pengirim agar dapat ditransmisikan bersama-sama melalui satu media/jalur komunikasi tunggal (misal: menggunakan nomor port L4 untuk membedakan HTTP, SSH, dan DNS).

- **Demultiplexing:** Menerima aliran data tunggal di sisi penerima lalu mengarahkannya/membaginya kembali ke proses/aplikasi tujuan yang sesuai berdasarkan informasi header (misal: port tujuan).

### 10. Mengapa OSI tidak boleh dianggap sebagai spesifikasi implementasi?

Model OSI diciptakan sebagai **model referensi konseptual/teoretis** untuk mendefinisikan fungsi-fungsi komunikasi jaringan secara terstruktur. OSI tidak mendefinisikan implementasi kode program aktual, struktur data, atau protokol spesifik yang harus digunakan dalam perangkat lunak/keras. Implementasi dunia nyata (seperti protokol TCP/IP) sering kali menggabungkan atau melewati beberapa lapisan OSI demi efisiensi performa.

---

## Level B — Penerapan dan Analisis

### 11. Petakan HTTP, TLS, TCP, UDP, QUIC, IPv6, ICMP, Ethernet, Wi-Fi, dan DNS ke model TCP/IP. Tandai protokol yang pemetaannya memerlukan penjelasan.

| Protokol | Lapisan TCP/IP | Catatan / Pemetaan yang Memerlukan Penjelasan | 
| ----- | ----- | ----- | 
| **HTTP** | Application | Protokol aplikasi tingkat tinggi. | 
| **DNS** | Application | Protokol aplikasi untuk pemetaan nama host ke IP. | 
| **TLS** | Application / Transport | Terletak di antara Transport dan Application. Di OSI masuk Presentation (Layer 6), namun pada TCP/IP dianggap bagian dari skema enkripsi Application atau sub-layer di atas Transport. | 
| **QUIC** | Transport / Application | Dirancang di atas UDP (Transport), namun mengimplementasikan fungsi TLS 1.3, multiplexing, dan kendali aliran bawaan di ruang pengguna (*user-space*). | 
| **TCP** | Transport | Protokol transport andal berorientasi koneksi. | 
| **UDP** | Transport | Protokol transport tanpa koneksi/ringan. | 
| **IPv6** | Internet | Protokol pengalamatan dan routing jaringan. | 
| **ICMP** | Internet | Digunakan untuk kontrol/pelaporan kesalahan IP. Berada di Network layer, meskipun secara teknis pesannya di-enkapsulasi di dalam paket IP. | 
| **Ethernet** | Network Access | Spesifikasi LAN kabel (Data Link & Physical). | 
| **Wi-Fi (802.11)** | Network Access | Spesifikasi LAN nirkabel (Data Link & Physical). | 

### 12. Gambarkan enkapsulasi permintaan DNS melalui UDP, IPv4, dan Ethernet. Sebutkan pengenal yang digunakan pada setiap batas.

#### Alur Enkapsulasi

`[Data DNS]` ➔ `[UDP Header + DNS Data]` ➔ `[IPv4 Header + UDP + DNS]` ➔ `[Ethernet Header + IPv4 + UDP + DNS + Ethernet Trailer]`

#### Pengenal (*Identifiers*) pada setiap batas

1. **Aplikasi ke Transport (DNS ke UDP):** Nomor Port Tujuan = `53`.

2. **Transport ke Internet (UDP ke IPv4):** Nilai `Protocol ID` pada header IPv4 = `17` (menandakan UDP).

3. **Internet ke Data Link (IPv4 ke Ethernet):** Nilai `EtherType` pada header Ethernet = `0x0800` (menandakan IPv4).

4. **Batas Fisik/Data Link:** Alamat MAC Asal (*Source MAC*) dan Alamat MAC Tujuan (*Destination MAC*).

### 13. Ulangi soal sebelumnya untuk HTTP/3 melalui QUIC. Jelaskan mengapa QUIC tetap dapat dianggap transport meskipun menggunakan UDP.

**Alur Enkapsulasi HTTP/3:**

`[Data HTTP/3]` ➔ `[QUIC Header (termasuk TLS 1.3) + Data]` ➔ `[UDP Header + QUIC]` ➔ `[IP Header + UDP]` ➔ `[Ethernet Header + IP...]`

#### Mengapa QUIC tetap dianggap sebagai protokol Transport?
Meskipun QUIC berjalan di atas UDP (agar dapat menembus middlebox/firewall internet tanpa perubahan kernel OS), QUIC **menyediakan layanan transport tingkat lanjut** sendiri, yaitu:

- Pemulihan kesalahan (*error recovery*) dan transfer data andal.

- Kendali aliran (*flow control*) dan kendali kongesti (*congestion control*).

- *Multiplexing* banyak aliran tanpa masalah *Head-of-Line (HoL) blocking*.

Oleh karena itu, dari sudut pandang fungsionalitas, QUIC adalah protokol Transport, sedangkan UDP hanya digunakan sebagai pembungkus/substrat *datagram framing*.

### 14. Dua host berada pada subnet berbeda. Jelaskan header mana yang berubah dan tetap ketika paket melewati satu router, dengan mengabaikan NAT.

- **Header yang TETAP:**

  - **Header Transport (TCP/UDP):** Port asal dan tujuan tidak berubah.

  - **Header IP (Network):** Alamat IP Asal (*Source IP*) dan Alamat IP Tujuan (*Destination IP*) tetap sama.

- **Header yang BERUBAH:**

  - **Header IP:** Nilai **TTL (Time to Live)** berkurang 1, dan nilai **Header Checksum** dihitung ulang.

  - **Header Ethernet (Data Link):** Header Ethernet **sepenuhnya diganti** pada setiap hop/router. Source MAC berubah menjadi MAC interface router keluar, dan Destination MAC berubah menjadi MAC interface host tujuan (atau router berikutnya).

### 15. Jelaskan perubahan analisis apabila router tersebut juga melakukan NAT/PAT.

Jika router melakukan **NAT/PAT (Port Address Translation)**:

1. **Header IP Berubah:**

   - **Source IP** (untuk paket keluar) diubah dari IP privat host menjadi IP publik milik router.

   - **IP Header Checksum** dihitung ulang.

2. **Header Transport (TCP/UDP) Berubah:**

   - **Source Port** diubah menjadi nomor port publik bebas yang dialokasikan oleh router NAT.

   - **TCP/UDP Checksum** harus dihitung ulang karena IP pseudo-header berubah.

3. **Penyimpanan Status (*Stateful*):** Router menyimpan tabel pemetaan (*NAT Translation Table*) untuk mengarahkan kembali paket balasan ke IP dan port privat asal.

### 16. Sebuah capture menunjukkan checksum TCP salah pada paket keluar, tetapi tidak ada gangguan komunikasi. Ajukan hipotesis yang berkaitan dengan NIC offload.

#### Hipotesis Kasus ini terjadi akibat fitur **TCP Checksum Offload** (bagian dari *Large Send Offload* / LSO pada Kartu Jaringan/NIC).

#### Penjelasan Saat perangkat lunak *packet capture* (seperti Wireshark) menangkap paket *sebelum* dikirim ke fisik NIC, kernel sistem operasi belum menghitung checksum paket (nilai checksum masih diisi dummy/0). Kalkulasi checksum TCP diserahkan kepada prosesor hardware NIC (*hardware offloading*). NIC memproses kalkulasi checksum secara fisik tepat saat paket dikirim keluar ke media, sehingga penerima mendapatkan paket dengan checksum yang benar meskipun capture lokal mencatat checksum "invalid/salah".

### 17. Pengguna dapat membuka portal dengan alamat IP, tetapi tidak dengan nama. Gunakan model lapisan untuk menyusun diagnosis.

- **Lapis 1–4 (Physical, Link, Network, Transport): Bekerja Normal.**
  Pengguna berhasil terhubung menggunakan alamat IP, menandakan konektivitas fisik, rute IP, enkapsulasi, dan koneksi transport (TCP port 80/443) berfungsi baik.

- **Lapis 7 (Application - Resolusi DNS) / Layer Transport (UDP Port 53): Bermasalah.**
  #### Diagnosis/Penyebab
  1. **DNS Server Down/Unreachable:** Server DNS yang dikonfigurasi di perangkat klien tidak merespon.
  2. **Konfigurasi IP/DNS Klien Salah:** IP DNS server pada settingan jaringan salah.
  3. **Domain Name Resolution Error:** Rekaman A/AAAA untuk nama domain tidak terdaftar atau bermasalah di DNS.
  4. **Blokir Port 53:** Firewall lokal/jaringan memblokir lalu lintas UDP/TCP port 53.

### 18. Ping ke server berhasil, tetapi HTTPS gagal. Susun sedikitnya enam hipotesis pada lapisan Transport hingga Application.

1. **[Transport Layer] Port 443 Diblokir:** Firewall (lokal/network) memblokir port TCP 443, sementara paket ICMP (Ping) diizinkan.

2. **[Transport Layer] Web Server Down:** Layanan web server (Nginx/Apache) pada host tujuan mati/tidak mendengarkan (*listen*) di port 443.

3. **[Presentation / TLS Layer] HTTPS Handshake Failure:** Terjadi kegagalan negosiasi SSL/TLS (misal: *cipher suite* tidak cocok atau versi TLS tidak didukung).

4. **[Presentation / Application Layer] Sertifikat TLS Tidak Valid / Expired:** Sertifikat SSL kadaluarsa atau tidak dipercayai (*untrusted CA*), menyebabkan klien memutus koneksi.

5. **[Application Layer] Masalah SNI / Virtual Hosting:** Server memerlukan *Server Name Indication* (SNI) yang benar untuk mengarahkan ke virtual host HTTPS.

6. **[Transport / Network Layer] Masalah MTU / PMTUD (Black Hole Router):** Paket ICMP kecil berhasil lewat, tetapi paket HTTPS yang besar terfragmentasi dan di-drop karena MTU terlalu kecil dan flag *Don't Fragment (DF)* aktif.

### 19. Bandingkan sesi aplikasi dengan koneksi TCP. Berikan contoh ketika sesi bertahan setelah koneksi berubah.

- **Koneksi TCP:** Berada di **Transport Layer**, didefinisikan oleh 4-tuple (*Source IP, Source Port, Dest IP, Dest Port*). Jika IP atau jaringan terputus, koneksi TCP gugur dan harus dibuat ulang (*3-way handshake*).

- **Sesi Aplikasi:** Berada di **Session / Application Layer**, melacak status identitas dan aktivitas pengguna (menggunakan Session ID, JWT Token, atau Cookie).

- #### Contoh Sesi Bertahan saat Koneksi Berubah

  - **Mobile App / E-commerce pada Smartphone:** Pengguna melakukan streaming atau belanja saat berpindah dari koneksi Wi-Fi rumah ke Jaringan Seluler 4G/5G. Alamat IP berubah total dan koneksi TCP lama putus, namun pengguna **tetap ter-login** pada aplikasi karena token sesi (*session token*) dikirimkan kembali melalui koneksi TCP baru.

  - **QUIC / HTTP/3 (Connection ID):** QUIC menggunakan *Connection ID* di tingkat aplikasi/transport sehingga sesi tetap terhubung tanpa terputus meskipun IP perangkat berubah (*connection migration*).

### 20. Jelaskan mengapa enkripsi tidak dapat selalu ditempatkan secara mutlak pada Presentation layer.

Enkripsi tidak selalu dapat ditempatkan di Presentation Layer karena **tujuan keamanan dan batas kepercayaan (trust boundary) berbeda-beda**:

- **Enkripsi Lapisan Jaringan (IPsec):** Dibutuhkan untuk mengamankan seluruh lalu lintas antar-site (*VPN/Site-to-Site*) tanpa memedulikan jenis aplikasinya.

- **Enkripsi Lapisan Transport (TLS/QUIC):** Mengamankan saluran komunikasi antar-proses, namun header transport tetap terlihat oleh jaringan.

- **Enkripsi Lapisan Aplikasi (End-to-End Encryption / E2EE):** Diperlukan jika server perantara (seperti database atau cloud provider) tidak boleh membaca isi pesan sama sekali (contoh: WhatsApp/Signal, di mana data dienkripsi sebelum masuk ke rantai protokol jaringan bawah).

Oleh karena itu, penempatan enkripsi disesuaikan dengan ancaman (*threat model*) yang ingin dicegah.

---

## Level C — Evaluasi dan Sintesis

### 21. Evaluasi pernyataan: “Model OSI tidak lagi relevan karena Internet menggunakan TCP/IP.” Susun argumen akademik yang membedakan model, protokol, dan kegunaan pedagogis.

**Evaluasi:** Pernyataan tersebut **TIDAK TEPAT / SALAH**.

**Argumen Akademik:**

1. **Pembedaan Model vs Protokol:**

   - **OSI adalah Model Referensi Konseptual**, sedangkan **TCP/IP adalah Arsitektur Protokol Praktis**.

   - Kegagalan OSI sebagai suite protokol komersial tidak menghilangkan nilainya sebagai kerangka kerja teoretis untuk memahami struktur komunikasi.

2. **Kegunaan Pedagogis (Pendidikan):**

   - Model OSI 7-layer memberikan pemisahan tugas (*separation of concerns*) yang sangat terperinci dan bersih. Pemisahan antara *Application, Presentation*, dan *Session* sangat krusial untuk mengajarkan konsep format data, enkripsi, dan manajemen dialog secara akademis.

3. **Penyelarasan Industri:**

   - Dalam praktik industri modern, bahasa standar diagnosis (seperti "Masalah Layer 2 vs Layer 3", "L4 Load Balancer", atau "L7 Firewall") seluruhnya menggunakan terminologi dari Model OSI. Oleh karena itu, OSI tetap sangat relevan.

### 22. Analisis keuntungan dan kerugian strict layering. Kapan cross-layer information dapat membantu dan kapan ia merusak modularitas?

- **Keuntungan Strict Layering:**
  Modularitas tinggi, pemeliharaan kode mudah, kemudahan pembagian kerja vendor, serta transparansi penggantian teknologi di satu lapisan tanpa merusak lapisan lain.

- **Kerugian Strict Layering:**
  Duplikasi fungsi (misal: kontrol kesalahan di L2, L3, dan L4), *performance overhead* akibat enkapsulasi/parsing berulang, serta hilangnya efisiensi karena ketidakmampuan membaca kondisi media bawah.

- #### Kapan Cross-Layer Information Membantu?
  **Jaringan Nirkabel/Seluler (Wi-Fi/5G):** Lapisan Transport (TCP) dapat merespon kondisi kehilangan paket (*packet loss*) akibat kendala sinyal (L1/L2) tanpa menyimpulkannya secara salah sebagai kongesti jaringan (*congestion*).

- #### Kapan Mengganggu Modularitas?
  Ketika aplikasi bergantung pada detail spesifik lapisan fisik/link dasar. Hal ini membuat aplikasi menjadi kaku (*rigid*), sulit diporting ke teknologi jaringan baru, dan menciptakan ketergantungan tersembunyi (*spaghetti architecture*).

### 23. Buat prosedur penelusuran gangguan untuk kasus video konferensi yang tersendat hanya pada Wi-Fi kampus saat jam sibuk. Hubungkan bukti pada sedikitnya empat lapisan.

**Prosedur Penelusuran Gangguan (Troubleshooting Procedure):**

1. **Physical Layer (Layer 1):**

   - *Aksi:* Cek tingkat kekuatan sinyal (RSSI), *Signal-to-Noise Ratio* (SNR), dan interferensi frekuensi 2.4GHz vs 5GHz pada Access Point.

   - *Bukti:* SNR buruk / kekuatan sinyal drop saat jam sibuk akibat tingginya jumlah perangkat aktif.

2. **Data Link Layer (Layer 2):**

   - *Aksi:* Analisis persentase *Frame Retries*, *Collisions*, dan utilisasi *Airtime* pada Wi-Fi (802.11).

   - *Bukti:* Tingginya angka *frame retry* dan tingginya pembacaan *contention window* menunjukkan kepenuhan media nirkabel (*wireless congestion*).

3. **Network Layer (Layer 3):**

   - *Aksi:* Jalankan `ping` kontinu dan `traceroute` ke server video konferensi untuk mengukur *Latency* dan *Packet Loss*.

   - *Bukti:* Latensi melonjak tinggi (*high jitter*) dan terdapat *packet loss* berulang pada gateway Wi-Fi lokal.

4. **Application Layer (Layer 7):**

   - *Aksi:* Periksa statistik internal aplikasi (misal: Zoom/Teams Media Stats) terkait *bitrate*, *frame rate (FPS)*, dan penggunaan *codecs* audio/video adaptif.

   - *Bukti:* Aplikasi secara otomatis menurunkan resolusi dari 1080p ke 240p dan terjadi keterlambatan *buffer audio/video*.

### 24. Rancang skenario laboratorium perekaman paket yang menunjukkan Ethernet, IP, TCP atau UDP, TLS, dan protokol aplikasi tanpa mengumpulkan data sensitif.

**Skenario Laboratorium:**

1. **Tujuan:** Merekam lalu lintas web HTTPS (HTTP/2 melalui TLS) tanpa membocorkan kredensial asli.

2. **Setup:**

   - Klien menggunakan browser yang terisolasi dalam VM atau kontainer.

   - Jalankan alat penganalisis paket: `Wireshark` atau `tcpdump`.

3. **Langkah Eksekusi:**

   - Minta siswa mengakses situs publik statically-hosted non-login (misal: `https://example.com` atau `https://httpbin.org/get`).

   - Lakukan *filter capture* di Wireshark: `host example.com and (tcp port 443)`.

4. **Pengamatan Struktur Lapisan Paket:**

   - **Ethernet II:** Menunjukkan Alamat MAC Asal & Tujuan, EtherType (`0x0800`).

   - **IPv4 / IPv6:** Menunjukkan Alamat IP, TTL, Protocol ID (`6` untuk TCP).

   - **TCP:** Menunjukkan Port Asal, Port Tujuan (`443`), Sequence Number, Flag SYN/ACK.

   - **TLS (Transport Layer Security):** Menunjukkan pesan *Client Hello*, *Server Hello*, dan sertifikat publik (Handshake) tanpa perlu mendekripsi payload key.

   - **Application (HTTP/2):** Ditampilkan dalam bentuk terenkripsi (*Encrypted Application Data*) untuk mendemonstrasikan aspek kerahasiaan (*confidentiality*).

### 25. Sebuah organisasi menggunakan VXLAN di atas UDP dan IPsec tunnel. Gambarkan kemungkinan urutan header dan jelaskan risiko MTU.

**Urutan Header (Enkapsulasi Luar ke Dalam):**

`[Outer Ethernet Header]` ➔ `[Outer IP Header]` ➔ `[IPsec ESP Header]` ➔ `[Outer UDP Header (Port 4789)]` ➔ `[VXLAN Header]` ➔ `[Inner Ethernet Header]` ➔ `[Inner IP Header]` ➔ `[Inner Payload (TCP/UDP Data)]`

**Risiko MTU (Maximum Transmission Unit):**

- **Masalah Overhead:** Penambahan header ganda (Outer IP + IPsec ESP + UDP + VXLAN + Inner Ethernet) menambahkan beban ekstra sekitar 80–100+ byte pada setiap paket.

- **Risiko Fragmentasi / Packet Drop:** Jika MTU jaringan standar adalah 1500 byte, paket data inner berkuran 1500 byte akan melampaui MTU fisik ($\approx 1580-1600$ byte).

- **Solusi:**
  1. Konfigurasi **Jumbo Frames** (MTU 9000 byte) pada jaringan backbone underlay.
  2. Turunkan nilai **MSS (Maximum Segment Size)** pada TCP MSS Clamping atau sesuaikan MTU interface overlay menjadi lebih kecil (misal: 1350–1400 byte).

### 26. Bandingkan perlindungan MACsec, IPsec, TLS, dan enkripsi end-to-end aplikasi dari sisi cakupan kepercayaan dan titik terminasi.

| Teknologi Enkripsi | Lapisan OSI | Titik Terminasi (*Termination Point*) | Cakupan Kepercayaan (*Trust Scope*) | 
| ----- | ----- | ----- | ----- | 
| **MACsec (802.1AE)** | Layer 2 (Data Link) | Antara dua perangkat fisik yang terhubung langsung (Switch to Switch / Switch to Host). | Sangat terbatas (*Hop-by-Hop* fisik saja). | 
| **IPsec (Tunnel Mode)** | Layer 3 (Network) | Antara dua Gateway VPN / Router / Firewall. | Mengamankan seluruh subnet/jaringan antar gateway. | 
| **TLS** | Layer 4/7 (Transport/App) | Antara Aplikasi Klien (Browser) dan Server Web (atau Proxy/CDN Termination point). | Mengamankan jalur proses-ke-proses (*Process-to-Process*). | 
| **App End-to-End (E2EE)** | Layer 7 (Application) | Langsung pada Perangkat Klien Pengirim dan Perangkat Klien Penerima. | Sangat Luas (*True End-to-End*), server perantara/cloud tidak dipercayai. | 

### 27. Jelaskan bagaimana firewall, proxy, dan load balancer menantang anggapan bahwa setiap perangkat hanya membaca header lapisannya.

Anggapan dasar model berlapis adalah bahwa perangkat perantara (*intermediate node* seperti router/switch) hanya membaca dan memproses header hingga lapisannya saja (misal: Router hanya sampai Layer 3). Namun perangkat modern melanggar abstraksi ini:

- **Stateful Firewall:** Membaca header Layer 3 (IP) dan Layer 4 (TCP/UDP flags & state tracking) sekaligus untuk memantau status sesi koneksi.

- **Layer 7 Firewall / WAF / Reverse Proxy:** Membongkar header L2, L3, L4, hingga membaca/mendekripsi **Payload Layer 7 (Aplikasi)** untuk mendeteksi serangan seperti *SQL Injection*, mengecek Cookie, atau URL path.

- **L7 Load Balancer:** Membaca header HTTP (L7) untuk mengarahkan lalu lintas (*traffic routing*) berdasarkan HTTP Request Headers atau URL target.

Pelanggaran (*layer violation*) ini dilakukan demi keamanan, efisiensi lalu lintas, dan kecerdasan navigasi data.

### 28. Gunakan prinsip end-to-end untuk mengevaluasi penempatan fungsi pemeriksaan integritas berkas pada router, transport, atau aplikasi.

#### Prinsip End-to-End (*End-to-End Principle*)
Menyatakan bahwa fungsi tertentu harus diimplementasikan pada titik ujung sistem (*end hosts/application*), kecuali jika penempatan di jaringan bawah memberikan optimasi kinerja yang signifikan.

- **Pemeriksaan Integritas di Router (Network Layer):**
  - *Evaluasi:* Tidak efektif. Router hanya mengecek integritas hop-by-hop. Router tidak dapat menjamin data tidak rusak di dalam memori router itu sendiri atau saat diproses oleh aplikasi.

- **Pemeriksaan Integritas di Transport Layer (TCP Checksum):**
  - *Evaluasi:* Baik untuk mendeteksi kesalahan bit saat transmisi jaringan, namun checksum TCP sangat lemah (hanya 16-bit) dan tidak menjamin integritas file tingkat lanjut dari manipulasi sengaja.

- **Pemeriksaan Integritas di Application Layer (misal: SHA-256 Hashing):**
  - *Evaluasi:* **Sangat Tepat dan Mutlak Diperlukan.** Hanya lapisan aplikasi di titik ujung yang memiliki pemahaman utuh terhadap konteks file lengkap. Memeriksa hash SHA-256 pada aplikasi penerima menjamin integritas file secara keseluruhan dari ujung ke ujung.

### 29. Analisis potensi retry storm ketika aplikasi, service mesh, dan client sama-sama melakukan pengulangan. Jelaskan mengapa masalah ini bersifat lintas lapisan.

- #### Analisis Potensi *Retry Storm*
  Jika terjadi gangguan jaringan sesaat (*transient failure*), setiap lapisan melakukan percobaan ulang secara independen secara eksponensial. Misal: Jika Client melipatgandakan percobaan $3\times$, Service Mesh (Envoy/Istio) $3\times$, dan Aplikasi internal $3\times$, maka 1 permintaan gagal dapat memicu $3 \times 3 \times 3 = 27$ permintaan ulangan beruntun ke backend. Ini menyebabkan beban lonjakan ekstrim (*amplification attack*) yang merubuhkan sistem backend (*Cascading Failure*).

- #### Mengapa Masalah Ini Bersifat Lintas Lapisan (*Cross-Layer*)?
  Karena mekanisme pemulihan kesalahan (*retry*) ada dan beroperasi di berbagai tingkatan tanpa adanya koordinasi:
  - *Transport Layer:* Retransmisi TCP.
  - *Infrastructure/Mesh Layer:* Retry pada level sidecar proxy (L7 infrastructure).
  - *Application Layer:* Logika percoba ulang (*retry logic*) pada kode aplikasi pengguna.
  Tanpa adanya strategi batas waktu (*timeouts*), *circuit breakers*, dan *backoff with jitter* yang terkoordinasi secara lintas lapisan, sistem akan runtuh akibat retri tak terkendali.

### 30. Susun argumen apakah materi jaringan pemula sebaiknya memakai model OSI tujuh lapisan, TCP/IP empat lapisan, atau model lima lapisan. Nyatakan tujuan pembelajaran, manfaat, dan keterbatasan pilihan Anda.

#### Rekomendasi Argumen
Materi jaringan untuk pemula sebaiknya menggunakan **Model 5 Lapisan (*Hybrid Model*)**.

- **Tujuan Pembelajaran:**
  Memahami cara kerja komunikasi jaringan secara menyeluruh dari aspek fisik hardware hingga aplikasi perangkat lunak tanpa membingungkan siswa dengan arsitektur teoretis yang sudah tidak dipakai secara langsung.

- **Manfaat Model 5 Lapisan:**
  1. **Memisahkan Physical & Data Link:** Memisahkan media fisik (L1) dan alamat MAC/Switching (L2) memudahkan penjelasan perangkat keras seperti kabel, switch, dan Wi-Fi.
  2. **Relevan dengan Industri Praktis:** Lapisan Network (L3), Transport (L4), dan Application (L5) mencerminkan tumpukan protokol TCP/IP nyata di lapangan.
  3. **Menghindari Kebingungan OSI:** OSI 7-layer sering membingungkan pemula saat menjelaskan di mana tepatnya posisi fungsi *Session* dan *Presentation* dalam aplikasi web modern.

- **Keterbatasan Pilihan:**
  1. Siswa tetap perlu dijelaskan istilah histori OSI (seperti istilah *Layer 2 Switch*, *Layer 3 Router*, *Layer 7 Firewall*) yang masih banyak digunakan dalam standar industri dan sertifikasi profesional (seperti Cisco CCNA).
