# Laporan: Subnetting IP & Visualisasi Sinyal Harmonik

## Daftar Isi

1. [Soal 1: Perhitungan Subnet IP](#soal-1-perhitungan-subnet-ip)
2. [Soal 2: Visualisasi Sinyal Harmonik](#soal-2-visualisasi-sinyal-harmonik)

---

## Soal 1: Perhitungan Subnet IP

### Yang dicari

- IP Gateway
- Host pertama
- Host terakhir
- Broadcast
- IP Network

### Daftar IP

| No | IP |
|----|----|
| 1 | 21.26.8.5 |
| 2 | 212.6.8.3 |
| 3 | 103.24.56.32 |
| 4 | 1.1.1.1 |
| 5 | 172.31.16.8 |

### Asumsi

Soal tidak menyertakan prefix/CIDR, sehingga digunakan **subnet default menurut kelas IP (classful)**:

| Kelas | Rentang Oktet Pertama | Default Mask |
|-------|-----------------------|--------------|
| A | 1 – 126 | 255.0.0.0 (/8) |
| B | 128 – 191 | 255.255.0.0 (/16) |
| C | 192 – 223 | 255.255.255.0 (/24) |

### Hasil

| No | IP | Kelas | Mask | IP Network | Host Pertama | Host Terakhir | Broadcast | IP Gateway* |
|----|----|:----:|:----:|------------|--------------|---------------|-----------|-------------|
| 1 | 21.26.8.5 | A | /8 | 21.0.0.0 | 21.0.0.1 | 21.255.255.254 | 21.255.255.255 | 21.0.0.1 |
| 2 | 212.6.8.3 | C | /24 | 212.6.8.0 | 212.6.8.1 | 212.6.8.254 | 212.6.8.255 | 212.6.8.1 |
| 3 | 103.24.56.32 | A | /8 | 103.0.0.0 | 103.0.0.1 | 103.255.255.254 | 103.255.255.255 | 103.0.0.1 |
| 4 | 1.1.1.1 | A | /8 | 1.0.0.0 | 1.0.0.1 | 1.255.255.254 | 1.255.255.255 | 1.0.0.1 |
| 5 | 172.31.16.8 | B | /16 | 172.31.0.0 | 172.31.0.1 | 172.31.255.254 | 172.31.255.255 | 172.31.0.1 |

> \* Gateway diambil dari **host pertama** (konvensi umum). Pada jaringan nyata, gateway bisa berbeda sesuai konfigurasi.

### Rumus yang dipakai

| Komponen | Cara menghitung |
|----------|-----------------|
| IP Network | IP di-AND dengan netmask (bit host = 0) |
| Broadcast | Semua bit host diubah menjadi 1 |
| Host pertama | IP Network + 1 |
| Host terakhir | Broadcast − 1 |

---

## Soal 2: Visualisasi Sinyal Harmonik

### Deskripsi

Sinyal dibentuk dari penjumlahan gelombang sinus pada **harmonik ke-1, 3, 5, 7, 9, dan 10**.

| Parameter | Nilai |
|-----------|-------|
| Orde harmonik | 1, 3, 5, 7, 9, 10 |
| Frekuensi dasar (f0) | 1 Hz |
| Amplitudo harmonik ke-n | 1/n |
| Durasi | 2 periode |

Rumus sinyal gabungan:

$$x(t) = \sum_{n \in \{1,3,5,7,9,10\}} \frac{1}{n}\sin(2\pi n f_0 t)$$

### Kode Python

```python
import numpy as np
import matplotlib
matplotlib.use("Agg")   # hapus 2 baris ini kalau ingin tampil di layar
import matplotlib.pyplot as plt

harmonik = [1, 3, 5, 7, 9, 10]   # orde harmonik
f0 = 1.0                          # frekuensi dasar (Hz)
t = np.linspace(0, 2, 2000)       # 2 periode

# Amplitudo tiap harmonik = 1/n (seperti deret Fourier gelombang persegi)
sinyal = {n: (1 / n) * np.sin(2 * np.pi * n * f0 * t) for n in harmonik}
total = sum(sinyal.values())

fig = plt.figure(figsize=(13, 10))
gs = fig.add_gridspec(3, 2)

# 1) Tiap komponen harmonik
ax1 = fig.add_subplot(gs[0, :])
for n, y in sinyal.items():
    ax1.plot(t, y, label=f"Harmonik ke-{n}  (A=1/{n})")
ax1.set_title("Komponen sinyal tiap harmonik", weight="bold")
ax1.set_ylabel("Amplitudo"); ax1.legend(ncol=3, fontsize=8); ax1.grid(alpha=.3)

# 2) Sinyal gabungan
ax2 = fig.add_subplot(gs[1, :])
ax2.plot(t, total, color="#d93025", lw=2)
ax2.set_title("Sinyal gabungan (jumlah semua harmonik)", weight="bold")
ax2.set_xlabel("Waktu (detik)"); ax2.set_ylabel("Amplitudo"); ax2.grid(alpha=.3)

# 3) Spektrum frekuensi (dari FFT)
ax3 = fig.add_subplot(gs[2, 0])
fs = len(t) / (t[-1] - t[0])
fft = np.abs(np.fft.rfft(total)) * 2 / len(t)
freq = np.fft.rfftfreq(len(t), 1 / fs)
ax3.plot(freq, fft, color="#1a56b0")
ax3.set_xlim(0, 12)
ax3.set_title("Spektrum frekuensi (FFT)", weight="bold")
ax3.set_xlabel("Frekuensi (Hz)"); ax3.set_ylabel("Magnitudo"); ax3.grid(alpha=.3)

# 4) Batang amplitudo per harmonik
ax4 = fig.add_subplot(gs[2, 1])
ax4.bar([str(n) for n in harmonik], [1 / n for n in harmonik],
        color="#fcc934", edgecolor="#a06a00")
ax4.set_title("Amplitudo tiap harmonik", weight="bold")
ax4.set_xlabel("Orde harmonik"); ax4.set_ylabel("Amplitudo"); ax4.grid(alpha=.3, axis="y")

fig.suptitle("Visualisasi Sinyal Harmonik: 1, 3, 5, 7, 9, 10", fontsize=15, weight="bold")
plt.tight_layout()
plt.savefig("sinyal_harmonik.png", dpi=150)
print("Tersimpan: sinyal_harmonik.png")
```

### Hasil Visualisasi

![Visualisasi sinyal harmonik](.assets/sinyal_harmonik.png)

| Panel | Isi |
|-------|-----|
| 1 | Komponen sinus tiap harmonik |
| 2 | Sinyal gabungan semua harmonik |
| 3 | Spektrum FFT dengan puncak di 1, 3, 5, 7, 9, 10 Hz |
| 4 | Batang amplitudo per harmonik |

### Catatan

- Harmonik **1, 3, 5, 7, 9** (ganjil) membentuk pendekatan **gelombang persegi**.
- Harmonik **ke-10** (genap) membuat sinyal tidak lagi simetris.

### Cara menjalankan

```bash
pip install numpy matplotlib
python sinyal_harmonik.py
```
