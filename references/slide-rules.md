# slide-rules.md — Aturan Slide ITICM (canon)

Jika bertentangan dengan dokumen lain (SKILL.md, mk-iticm, history), **file ini yang menang**.
Semua deck ITICM (kuliah, praktikum, ujian) mengikuti file ini. Nomor seksi dirujuk oleh
`scripts/check_deck.py` dan dokumen lain — **jangan mengubah nomor, tambahkan di akhir**.

---

## §0 — Sebelum mulai (Define-before-Produce)

1. **Cerita dulu, bentuk belakangan.** Sebelum menulis draft, buat *storyline*: satu baris
   pesan per slide (kelak jadi judul). Baris ini isi kohesif (definisi → mekanisme → contoh
   angka → studi kasus → implementasi → output → latihan). Jumlah slide dan bentuk diputuskan
   SETELAH storyline disepakati.
2. **Tuju 1 slide 1 pesan.** Dua pesan → pecah dua slide. Dilarang menjejalkan untuk kurangi jumlah.
3. **Isi > tampilan.** Kalau materi belum punya data/angka/contoh, katakan miskin — jangan ditutupi
   lekukan atau kartu hias.
4. **Konteks dikonfirmasi dulu.** Siapa pembacanya (mahasiswa/penilai), dokumen apa, level draft
   atau final — ditulis singkat sebelum produksi. Tanpa kepastian konteks, jangan produksi penuh.
5. **Angka tidak boleh dikarang.** Bobot, tanggal, skor, tolok ukur datang dari RPS/knowledge —
   kalau belum ada, pakai nilai relatif + "dapat disesuaikan". (Anti-fabrikasi, turunan mk-iticm.)

## §1 — Kanvas & merek

| Item | Nilai |
|---|---|
| Rasio | Selalu 16:9. `python-pptx`: 12192000 × 6858000 EMU |
| Warna | `DARK_BG #1a1a2e` · `ACCENT #e86c00` · `LIGHT_GRAY #f5f5f5` · `DARK_TEXT #1a1a2e` · `WHITE #ffffff` · `MUTED #6b7080` · `CODE_BG #2d2d3a` · `CODE_LIGHT #c0c5d0` · `TASK_BG #25253a` |
| Font | Calibri (semua) · Consolas (kode) |
| Logo | 1.0×1.0", kanan atas, **HANYA title + closing**. Slide lain hanya label `iticm.ac.id` |
| Kartu | `ROUNDED_RECTANGLE`, adjust 0.167, border `#e0e0e0` 1pt. **Ini pengecualian §5.1 (brand ITICM memakai rounded)** |
| Aksesori | Diagram PIL: oval navy, proses putih, diamond oranye, panah navy + label Ya/Tidak |

Aturan warna tidak boleh diubah per-deck. Kalau ada kebutuhan baru, ubah di sini — bukan di draft.

## §2 — Judul (message line)

1. **Kesimpulan ditulis di judul.** Satu baris; bila panjang → 2 baris di batas makna.
   **Dilarang mengecilkan font untuk memaksa 1 baris.**
2. **Gaya formal.** Hindari format percakapan ("kita akan membahas…", "mari kita…").
   Kalimat berpredikat: "A* menjamin jalur terpendek bila heuristik admissible."
3. **Judul terbaca tanpa melihat slide lain.** Uji: judul dipotong sendiri, pembaca baru
   paham topiknya. Referensi silang ("seperti tadi", "ini") di judul = tolak.
4. **Jangan basiskan judul pada jumlah.** "5 jenis agen", "3 langkah", "memahami X dalam 4
   poin" **bukan klaim** — ganti dengan nama konkret atau strukturnya. Angka hanya boleh bila
   angka itu sendiri pesannya: "62% dataset salah label", "A* hemat 40% node vs Greedy".
5. **Judul tidak diwarnai/aksen.** Tanpa pemecahan run berwarna di judul.
6. **Judul dibaca urut = satu cerita.** Sebelum kirim, keluarkan daftar judul dan baca beruntun.
7. **Dilarang tag "Step 1" di dalam judul.** Langkah/nomor urut ditangani dengan kartu bernomor
   atau badge di isi slide, bukan di teks judul.
8. **Judul dari storyline, bukan template.** Meniru bentuk template tidak dilarang, tapi kalimat
   judul JANGAN menjadi "tiruan pola" (mis. semua dimulai "Perbedaan…"). Kalau ≥60% judul
   berpola sama → WARN "menyalin template".
9. **Angka di judul wajib cocok dengan isi.** "Algoritma dalam 3 fase" tapi ada 4 kartu alur = FAIL.
   Catatan: angka "bobot" dari RPS bisa milik **rubrik suatu tugas**, bukan bobot nilai MK
   (lihat `mk-iticm` Pitfalls §A) — jangan dipakai sebagai bobot komponen di deck.
10. **Slide topik kaya wajib memuat data kejudulan** (bobot 5%, ukuran 8×8, dsb.) — belum tentu
    di judul, tapi judul tidak boleh menjanjikan apa yang isi tidak beri.
11. **Tidak berlebihan vs bukti.** Klaim "paling akurat", "dijamin" hanya bila isi menyediakan
    data pendukung (akurasi terukur, kondisi pengukuran).

## §3 — Sub-judul / baris label (dilarang)

- **TIDAK ada baris penjelasan di bawah judul.** Informasi "apa slide ini" ditanggung judul +
  badge/daftar isi.
- TIDAK ada caption "Gambar 1: …" di atas/bawah diagram — keterangan diagram masuk kartu kode
  atau panel teks.
- Pengecualian satu: label sumbu data (mis. "Presisi, kondisi 10-fold CV") boleh satu baris
  tipis di atas tabel/diagram.

## §4 — Layout

1. **Maks 3 kartu per slide.** Materi 6 item → pecah dua slide (1/2, 2/2).
2. **Jangan menumpuk isi yang tidak berhubungan ke atas-bawah.** Seksi dipisah kiri-kanan,
   masing-masing berjudul.
3. **Ringkasan "tentang halaman ini" dilarang di dasar slide (band GOAL/KEY/POINT).** So-what
   ditaruh kolom kanan atau slide ringkasan tersendiri.
4. **Proses/alur = kartu bernomor atau chevron.** Jangan baris kotak rapat tanpa penanda urutan.
5. **Kolom kanan untuk So-what/implikasi**, kolom kiri fakta/prasyarat/definisi.
6. **Setiap kolom ada judul yang terlihat hubungannya** (kiri "Gambaran sistem" / kanan "Alasan
   desain ini").
7. **Gunakan tabel ber-poros daripada kartu rebutan bila yang dibandingkan >3 dimensi.**
   Baris = item, kolom = aspek. (Better: tabel dengan header tebal + border untuk perbandingan.)
8. **Slide kosong sisa → vertical center**, bukan merenggangkan kartu/baris.
9. **Elemen mengambang dilarang.** Setiap label/badge masuk struktur (kartu, tabel, kolom).
10. **Pecah slide padat dengan "build-up".** Kalau 1 slide berisi 2 tahap, pisah menjadi 2–3
    slide dengan layout yang TIDAK BERUBAH 1mm — hanya elemen yang bertambah.

## §5 — Warna, garis, kartu

1. ITICM memakai kartu rounded (lihat §1) — **pengecualian kelas brand**. Hinakan rounded hanya
   bila beralih brand resmi.
2. **Kartu berisi warna/bg TIDAK boleh diberi outline.** Outline dipakai hanya untuk kartu putih.
3. **Garis pemisah hanya di tempat yang sungguh memisahkan.** Tidak ada border pada kartu
   paling bawah, tidak ada garis di dasar slide.
4. **Setiap penggunaan warna yang bermakna wajib ada keterangannya** (badge/legend di slide yang
   sama). Warna hanya aksen (oranye) untuk penekanan, bukan pemetaan kategori.
5. **Palet wajib memuat netral** (abu-abu `#6b7080`) untuk non-emphasis — jangan semua kategori
   diwarnai.
6. **Diagram: navy = judul/entitas, putih = proses, oranye = keputusan** (konsisten antar slide).
7. **Fill-rate: isi ≥55% area badan slide.** Bila kosong → tambah data/angka/contoh, bukan
   memperlebar box.

## §6 — Tabel

1. Header tabel: **≥ +2pt di atas body, tebal, warna dark teks** (bukan abu tipis). Sumbu lewat
   border tebal di bawah head, bukan fill.
2. Body tabel ≥ 11.5pt; diproyeksikan di kelas 16:9 wajib terbaca. Header ≥ 13.5pt.
3. **No zebra.** Pisah baris dengan garis tipis abu; **TANPA garis di bawah baris terakhir**.
4. Judul kolom: nama alami, tidak ambigu, apakah isi selnya jelas (bukan "Data"/"Informasi").
5. Sel penjelas (contoh, bukti, langkah): **2–3 bullet pendek**, bukan paragraf panjang.
6. **Sumber/statistik: di kiri bawah footer area** (label `sumber:`), bukan di judul tabel.
7. Sel tidak berlaku → **"—" dengan warna abu** (dikecilkan secara visual), bukan kosong.
8. **Baris = anggota dari sumbu definisi kolom kiri saja.** Jangan campur fakta makro/kesimpulan
   ke dalam baris; itu pindah ke kolom kanan atau slide lain.
9. **Kolom yang tidak membantu pesan dibuang.** Kolom "skor" di tabel peran membuat pembaca
   membandingkan skor, bukan peran.

## §7 — Bahasa & AI-smell

**3 tanda "buatan AI" (wajib cek manual per slide):**
  1. elemen melayang tanpa struktur,
  2. paragraf panjang tanpa bullet (pecah jadi baris "•", satu baris satu klaim),
  3. pemendekan tanpa subjek+predikat ("pengoptimalan", "peningkatan efisiensi" saja).

1. Kurung `()` dibatasi: prefer `／` atau kalimat utuh.
2. Singkatan/kata serapan tanpa definisi = tolak. Istilah asing disebut lengkap di slide pertama
   kali dipakai (mis. "A* (A-star)").
3. **Konsistensi istilah: 1 dokumen, 1 istilah.** memory vs memori, masukan vs input — pilih satu
   dan jaga konsisten di seluruh deck. Periksa dengan cari kata.
4. Akhiran bullet dalam satu level harus seragam (semua predikat atau semua frasa).
5. **Bullet berisi subjek + predikat** ("Algoritma menghitung jarak Euclidean…") jangan hanya
   objek-objek kering.
6. **Buang kalimat template/penutup kosong** ("sebagai kesimpulan dapat kita lihat", "demikian
   penjelasan", "sangat", "luar biasa", "perlu diingat bahwa"). Ingat Student-AI-smell: kata-kata
   hebat tanpa data = ciri AI.
7. **Setiap bullet beda sudut pandang.** Dilarang 3 bullet = parafrase ulang satu klaim.
8. **Angka wajib berunit & berkonteks**: bukan hanya "85%", tapi "85% (presisi, 10-fold CV, dataset
   iris, k=5)". Sumber wajib ada di §6.6.
9. **Narasi speaker-notes = "cer mengalir, siap dibacakan"** (diperbarui 2026-09-26). Label di
   draft: `> **Narasi:**`. Isinya **5–8 kalimat (±90–160 kata)**, plain text (tanpa markdown),
   supaya dosen bisa membacanya langsung di depan kelas.
   Empat bagian, tanpa perlu label:
   1. **Pembuka (1 kalimat)** — konteks/analogi/hook.
   2. **Isi (2–4 kalimat)** — apa itu, bagaimana kerjanya, kenapa penting.
   3. **Data (1–2 kalimat)** — sebut angka konkret + interpretasinya, bukan mencicil seluruh tabel.
   4. **Penutup (1 kalimat)** — jahit ke slide berikutnya, atau pertanyaan pemantik.

   **DILARANG** meta-pembuka & template: "Slide ini menjelaskan tentang…", "Pada slide ini
   kita akan…", "Coba perhatikan…", "Terlihat bahwa…", "Jadi jelas bahwa…", penutup kosong.

   Per tipe slide:
   - **Kode** → apa yang dikerjakan kode, baris mana yang menentukan, output yang harus muncul, jebakan umum.
   - **Tabel/angka** → trend + 1–2 angka kunci, bukan dibaca baris per baris.
   - **Diagram** → alur kiri-ke-kanan + titik keputusan.
   - **Konsep** → definisi + analogi + batasnya (kapan tidak berlaku).

   ✅ Lolos: "Bayangkan Anda memesan kopi. Pesan Anda masuk ke kasir sebagai satu utuh, lalu kasir
   memecahnya jadi setiap bahan satu per satu. Forward chaining bekerja persis seperti itu: fakta
   awal dipecah, dicocokkan ke aturan, lalu kesimpulan baru ditambahkan sebagai fakta berikutnya.
   Kunci loop while di sini bukan sekadar syntactic sugar — dialah yang menghentikan proses begitu
   tidak ada fakta baru lagi, yang disebut fixed point. Di slide berikutnya kita lihat kapan loop itu
   benar-benar berhenti."
   ❌ Tolak: "Slide ini menjelaskan tentang algoritma A*." (meta, tidak informatif, tak bisa langsung dibaca)

## §8 — Pemeriksaan & review

Alur wajib sebelum serah terima (semua deck materi):
1. `python3 scripts/check_deck.py pptx/Pxx-*.pptx` → **FAIL 0** (struktur) dan baca laporan WARN.
2. Daftar judul diekstrak dan **dibaca berurutan = harus jadi cerita** (§2.6).
3. **Fresh-eyes review**: agent/sesi TANPA konteks build dikasih deck (file pptx) + prompt dari
   `references/content-review-prompt.md`. Temuan dijadikan **tabel terima/tolak**; yang diterima
   diperbaiki; yang ditolak dicatat alasan 1 baris.
4. **Perbaikan dimasukkan kembali ke slide-rules ini** (loop pertumbuhan kualitas).
5. **Hitung 1 rally = check → QA visual → fresh-eyes → perbaiki → check ulang.** Setelah 1 rally,
   TAMPILKAN hasil + tabel terima/tolak ke user, lalu TANYA "lanjut rally berikutnya?" — jangan
   auto-loop.

## §9 — Kedalaman & Data (kedalaman di atas jumlah)

> Ini aturan inti. Deck tidak ditegakkan ke jumlah tertentu; kedalaman ditentukan isi, dan isi
> wajib berbasis data yang jelas.

1. **TIDAK ada batas atas slide.** Deck materi biasanya ≥20 slide; boleh 25–35+ bila materi kaya
   data. Yang dilarang adalah *menambah slide untuk menipiskan*.
2. **Kedalaman diukur per slide, bukan per hitungan.** Setiap slide konten WAJIB memuat minimal
   SATU dari: tabel data, angka konkret, dataset, contoh perhitungan bertahap, kode + output,
   kasus nyata, atau perbandingan multi-dimensi dengan angka.
3. **Slide "tipis" = pelanggaran** (turunan §7): bilamana slide hanya 1–2 bullet singkat tanpa
   data/angka/contoh → tulis ulang atau gabung. Kurang dari ±60 karakter isi pada slide konten
   ⇒ curiga tipis (check_deck memberi WARN).
4. **Perluas dengan membuka dimensi, bukan memperbanyak bullet.** Satu topik dibagi ke beberapa
   slide yang masing-masing punya datanya: definisi → mekanisme/arsitektur → contoh angka →
   studi kasus perhitungan manual → implementasi kode + output dijalankan → analisis hasil →
   latihan. Setiap slide diisi bahan nyata.
5. **Slide "Studi Kasus: Perhitungan Manual" wajib di deck algoritma** (trace angka langkah-demi-langkah:
   tabel, jarak, voting, SSE, cost) — ditaruh SEBELUM kode.
6. **Angka harus dibuktikan**: dipakai contoh perhitungan manual (cost A* = 4, akurasi = 93.3%,
   SSE = 0.76) dengan langkah yang bisa diikuti mahasiswa dari nol.
7. **Bukan hanya satu angka**: beri rentang, perbandingan (KNN vs K-Means, Greedy vs A*, k=3 vs k=5)
   dan kondisi (dataset, k, jarak, iterasi).
8. **Deck ujian (UTS/UAS) bebas ramping (±8–12 slide, tanpa tugas baru)** — aturan kedalaman
   tidak berlaku untuk slide ujian, tapi judul & struktur tetap ikut §2–§7.

## §10 — Ujian (UTS/UAS)

1. Deck ujian ramping: identitas ujian, jadwal/lingkup, petunjuk, kisi-kisi bobot, contoh soal,
   peta Sub-CPMK. TANPA slide tugas baru.
2. Kisi-kisi & kunci berada di `bank-soal/` / internal — tidak dipublikasikan di deck ujian.

## §11 — Referensi

- Russell & Norvig (2021), Kusumadewi (2003) untuk AI; sumber topik per deck disalin dari
  knowledge/ (KNOWLEDGE.md). Setiap referensi dicantumkan di slide Referensi deck terima.

## §12 — Kedalaman minimum deck (ditambahkan 2026-09-26, dari rebuild IF022)

> Diturunkan dari satu rebuild penuh (Kecerdasan Buatan, 17 deck) + hasil fresh-eyes review.
> §9 sudah bicara tentang "tanpa batas atas"; §12 ini menetapkan **ambang bawah** supaya
> "boleh banyak slide" tidak berubah jadi "boleh tipis".

1. **Deck materi = 24–30 slide.** Deck kontrak (P00) boleh 20–22. Deck ujian 10–12 (§10).
   Total ±400 slide untuk 16 pertemuan — bukan target, hanya konsekuensi dari kepadatan isi.
2. **Perbesar topik, bukan perbesar slide.** Yang memperbesar slide: menambah **dimensi** baru
   (Definisi → Mekanisme → Contoh angka → Studi kasus trace → Kode+output → Analisis →
   Latihan), bukan menambah bullet pada slide yang sudah ada.
3. **Wajib ada di deck algoritma:** satu slide **"Studi Kasus: Perhitungan Manual"**
   (trace angka langkah demi langkah) sebelum slide kode — sudah di §9.5; di sini ditegaskan
   bahwa slide ini **tidak boleh dihapus** demi slide yang lebih ringkas.
4. **Angka dari sumber terverifikasi**, bukan dikarang. Kalau sumber tidak ada, pakai nilai
   relatif + "dapat disesuaikan" (§0.5). Angka di judul wajib cocok dengan isi (§2.9).
5. **Narasi** mengikuti §7.9 (cer mengalir) — bukan ringkasan judul, bukan meta-pembuka.