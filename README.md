# Simulasi Distribusi Air Gedung 11 Lantai

Simulasi interaktif 3D sistem distribusi air bersih pada gedung apartemen 11 lantai dengan sistem tangki atap (*down-feed*). Air dipompa dari tangki bawah (GWT) melalui pipa PVC ke tangki atas, lalu turun ke unit hunian secara gravitasi.

Dibuat oleh **Kelompok 4** untuk **Mini Project Mekanika Fluida Dasar I**, Program Studi Teknik Mesin, UIN Maulana Malik Ibrahim Malang. Angka pada simulasi dihitung dengan rumus yang sama dengan laporan teknis kelompok.

**Demo:** https://muflikulhakim.github.io/simulasi-distribusi-air/

## Fitur

- Model 3D gedung, tangki bawah, pompa, fitting, pipa tegak, dan tangki atas. Geser untuk memutar, scroll atau cubit untuk zoom.
- Pilihan sudut pandang: seluruh gedung, ruang pompa, kaki pipa tegak, dan tangki atas.
- Pengaturan: diameter pipa PVC AW (2", 2½", 3", 4") dan debit pompa 10–30 m³/jam.
- Opsi tampilan: pompa hidup/mati, aliran air, dinding gedung, serta isi unit dan pipa distribusi.
- Tampilan per lantai (lantai 1–11) dengan kebutuhan air dan tekanan di keran.
- Klik nomor fitting atau titik penting (titik 1, titik 2, manometer, pompa) untuk melihat nilai K, rugi head, dan penjelasannya.
- Hasil perhitungan langsung: kecepatan, v²/2g, bilangan Reynolds, faktor gesekan, rugi mayor dan minor, head pompa, daya hidrolik, daya input, tekanan keluar pompa, NPSH tersedia, waktu isi tangki atas, dan energi listrik per hari.
- Tabel perbandingan keempat diameter pipa pada debit yang dipilih, lengkap dengan status kecepatan (ideal, lolos, atau ditolak).

Nilai bawaan adalah desain akhir laporan: pipa PVC AW 3 inci dan debit 20 m³/jam, dengan head pompa 42,83 m dan daya input 3,33 kW.

## Cara Menggunakan

1. Buka halaman demo di browser (desktop atau ponsel).
2. Pilih diameter pipa dan atur debit pompa.
3. Baca ringkasan head pompa, hasil perhitungan, dan tabel perbandingan diameter.
4. Klik nomor fitting pada gambar atau daftar untuk melihat hitungannya, atau pilih lantai untuk melihat kebutuhan air dan tekanan keran.

Untuk menjalankan secara lokal, unduh `index.html` lalu buka di browser. Tidak ada proses instalasi atau build.

## Data dan Rumus

| Besaran | Persamaan atau nilai |
| --- | --- |
| Kontinuitas | v = Q/A, A = πD²/4 |
| Bilangan Reynolds | Re = vD/ν, ν = 8,91 × 10⁻⁷ m²/s (air 25 °C) |
| Faktor gesekan | Persamaan Colebrook, pipa PVC dianggap halus |
| Rugi mayor | h_f = f (L/D)(v²/2g), L = 55,5 m |
| Rugi minor | h_m = ΣK (v²/2g), ΣK = 5,6 |
| Head pompa | H = 41,5 + v²/2g + h_L (Bernoulli dari muka air tangki bawah ke ujung pipa di tangki atas) |
| Daya | P_h = ρ g Q H, P_in = P_h / 0,70 |

Diameter dalam pipa PVC kelas AW: 2" 51,8 mm; 2½" 67,8 mm; 3" 78,0 mm; 4" 100,8 mm.

**Asumsi perancangan**

- Pompa berada di z = −1,0 m (isap tergenang). Pipa isap 3 m, ruang pompa 4 m, pipa tegak 42,5 m, pipa atap 6 m.
- Lantai 1 untuk lobi dan pengelola. Lantai 2–11 masing-masing 8 unit × 4 orang = 320 penghuni.
- Kebutuhan air harian 96 m³ (320 orang × 250 L + 20%). Volume tangki atas 20 m³.
- Batas kecepatan aliran 0,6–2,0 m/s, dengan rentang ideal 0,9–1,2 m/s.

**Asumsi tambahan (di luar perhitungan head pompa pada laporan)**

- NPSH tersedia dihitung dengan tekanan atmosfer standar permukaan laut (101,325 kPa), tekanan uap air 25 °C sebesar 3,169 kPa, dan ΣK sisi isap = 0,7 (lubang masuk dan satu gate valve).
- Tekanan di keran tiap lantai dihitung sebagai tekanan statik, P = ρ g h, dengan h diukur dari dasar tangki atas (38,6 m, tangki hampir kosong), air diam, dan rugi pipa distribusi diabaikan.
- Pipa, fitting, dan pipa distribusi digambar lebih besar dari skala aslinya supaya terlihat.

## Catatan

Simulasi ini adalah alat bantu visual dan belajar. Pemilihan pompa sebenarnya tetap memerlukan kurva dan data NPSH yang dibutuhkan dari katalog produsen, serta analisis pukulan air.

## Teknologi

HTML, CSS, dan JavaScript dalam satu berkas `index.html`, dengan [Three.js](https://threejs.org/) r128 (lisensi MIT) untuk tampilan 3D.

## Referensi

- Çengel, Y. A., & Cimbala, J. M. (2018). *Fluid Mechanics: Fundamentals and Applications* (4th ed.). McGraw-Hill Education.
- Colebrook, C. F. (1939). Turbulent flow in pipes, with particular reference to the transition region between the smooth and rough pipe laws. *Journal of the Institution of Civil Engineers, 11*(4), 133–156.
- Noerbambang, S. M., & Morimura, T. (2005). *Perancangan dan Pemeliharaan Sistem Plambing*. Pradnya Paramita.
- Sularso, & Tahara, H. (2000). *Pompa dan Kompresor: Pemilihan, Pemakaian, dan Pemeliharaan*. Pradnya Paramita.

## Penyusun

Kelompok 4, Mini Project Mekanika Fluida Dasar I, Program Studi Teknik Mesin, UIN Maulana Malik Ibrahim Malang, 2026.
