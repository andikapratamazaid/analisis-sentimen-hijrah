# Analisis Sentimen Hijrah & Manhaj Salaf di Media Sosial Indonesia

## Ringkasan Dataset Multi-Platform (Threads, Instagram, Facebook)

## Metode

Dataset ini disusun dari postingan publik yang diambil melalui pencarian media sosial (social search) pada **4 November 2026**, menggunakan banyak set kata kunci seputar testimoni hijrah, belajar manhaj salaf, ustadz sunnah dan salafi (mis. Khalid Basalamah, Yazid Jawas, Firanda Andirja, Syafiq Riza Basalamah), meninggalkan bid'ah, ittiba' kepada Sunnah, dan pemahaman salafus shalih di tiga platform: Threads, Instagram, dan Facebook.

Setiap postingan dicatat apa adanya dari hasil pencarian: platform, username penulis, tanggal (UTC), tipe konten, jumlah likes dan komentar, URL, serta teks ringkasan (Summary) sebagaimana diterima dari alat pencarian. Teks tidak diubah, diterjemahkan, atau ditambah. Pelabelan kategori topik dan sentimen dilakukan hanya berdasarkan teks ringkasan tersebut.

Inti tema proyek ini adalah hijrah yang meninggalkan (1) pekerjaan haram dan riba, serta (2) tradisi kuburiyyun dan praktik bid'ah dalam Islam Indonesia, seperti tawassul/tabarruk di kuburan, mencari karomah atau berkah dari habib atau gus, haul, dan tahlilan. Karena itu postingan yang menentang tradisi kuburiyyun atau praktik bid'ah dinilai relevan pada kategori "Meninggalkan bid'ah" (atau "Polemik & kritik" bila bernada menyerang), dan postingan tentang meninggalkan pekerjaan haram atau riba dinilai relevan pada kategori "Testimoni hijrah".

Dataset memiliki kolom tambahan **klaster_tema** yang mencatat asal putaran pengumpulan setiap baris: "Umum (pengumpulan utama)" untuk baris dari pengumpulan kata kunci utama dan penambahan akun spesifik, serta tiga klaster tematik dari putaran tematik 4 November 2026: "Riba & pekerjaan haram", "Kuburiyyun & berkah kubur/habib", dan "Tradisi bid'ah Indonesia" (rincian pada bagian "Putaran tematik").

**Catatan keterwakilan:** ini adalah sampel kemudahan (convenience sample) dari postingan yang muncul pada hasil pencarian kata kunci, **bukan** gambaran yang mewakili seluruh Muslim Indonesia di media sosial. Hasil pencarian cenderung menonjolkan postingan berinteraksi tinggi dan akun dakwah yang aktif, sehingga distribusi sentimen di sini tidak dapat digeneralisasikan ke populasi umum.

## Alur Penyaringan Data

- Entri mentah ter-parse dari 22 file hasil pencarian pengumpulan utama: **725** (Facebook 311, Threads 210, Instagram 204)
- Duplikat (URL yang sama muncul di beberapa set kata kunci) dibuang: **50**
- Entri unik setelah deduplikasi: **675**
- Dibuang karena di luar topik (konten Islami generik tanpa sudut hijrah/manhaj salaf/kajian ustadz sunnah, promosi umrah, iklan, dsb.): **149**
- Baris dari pengumpulan kata kunci: **526**
- Penambahan akun spesifik atas permintaan pengguna (4 Nov 2026): **+19** baris (rincian pada bagian berikutnya)
- Subtotal sebelum putaran tematik: **545**
- Putaran tematik (4 Nov 2026): 383 entri mentah dari 9 file pencarian, 2 duplikat di dalam putaran, 13 duplikat terhadap dataset yang sudah ada, 75 dibuang di luar topik: **+293** baris (rincian pada bagian "Putaran tematik")
- **Baris final dataset: 838**

## Penambahan akun spesifik (4 Nov 2026)

Atas permintaan pengguna, dataset ditambah dengan postingan dari tiga akun spesifik yang diambil melalui pencarian per penulis (author search) pada 4 November 2026: **@andikzaa_** (Threads), **@mufy.thalib** (Instagram), dan **@farhancaesario** (Threads). Filter relevansi yang sama dengan pengumpulan utama diterapkan tanpa pelonggaran: hanya postingan yang benar-benar bertema testimoni/perjalanan hijrah (termasuk meninggalkan pekerjaan haram dan riba), belajar manhaj salaf, ustadz sunnah/salafi dan kajiannya, meninggalkan bid'ah dan tradisi kuburiyyun, ittiba' kepada Sunnah, pemahaman salafus shalih, atau tren gaya hidup hijrah yang lolos.

| Akun | Ter-parse | Sudah ada (duplikat) | Dibuang (di luar topik) | Ditambahkan |
| --- | ---: | ---: | ---: | ---: |
| @andikzaa_ (Threads) | 30 | 0 | 28 | 2 |
| @mufy.thalib (Instagram/Threads) | 48 | 0 | 31 | 17 |
| @farhancaesario (Threads) | 24 | 0 | 24 | 0 |
| **Total** | **102** | **0** | **83** | **19** |

Catatan penambahan:

- **@andikzaa_**: sebagian besar postingannya adalah konten pribadi, bisnis, dan gaya hidup, sehingga hanya 2 yang lolos filter: peringatan keras terhadap praktik pertukaran uang baru yang dinilai riba (dikategorikan "Testimoni hijrah" sesuai penajaman tema riba) dan pembelaan terhadap pengikut Sunnah yang distigma kaku ("Polemik & kritik", Positif). Satu postingan tidak memiliki teks ringkasan pada data pencarian ("No data"), sehingga relevansinya tidak dapat diverifikasi dari ringkasan dan tidak dimasukkan. Sebagian URL postingan akun ini memakai handle lama **@andika.zaid**, tetapi identitas penulis pada data adalah @andikzaa_ (akun yang sama), dan di dataset dicatat sebagai @andikzaa_.
- **@mufy.thalib**: akun Ustadz Abu Eirbadh Mufy Thalib. Dari 48 postingan, 17 lolos: rekaman dan pengumuman kajiannya serta kabar wafatnya Syaikh Rabi' bin Hadi Al-Madkhali ("Ustadz sunnah & kajian"), anekdot taubat seorang mantan pekerja riba ("Testimoni hijrah"), keputusan MPU Simeulue terkait tahlilan dan koreksi praktik tadarus bersuara keras ("Meninggalkan bid'ah"), kutipan Imam Al-Awza'i tentang berpegang pada amalan Salaf ("Belajar manhaj salaf"), kritik terhadap kajian berbayar ala konser dan polemik ghuluw terhadap ulama ("Polemik & kritik"), serta konten ta'aruf dan komitmen di atas Sunnah meski dilabeli Wahabi ("Tren hijrah & gaya hidup sunnah"). Postingan beliau muncul di Instagram maupun Threads sesuai URL masing-masing. Sisanya berupa pengingat Islami generik (hasad, doa, tips Ramadan, dsb.) dan konten lain di luar tema, sehingga tidak dimasukkan.
- **@farhancaesario**: tidak ada postingannya yang lolos filter. Kontennya berupa komentar umum seputar agama dan masyarakat, hubungan, dan gaya hidup, tanpa sudut hijrah, manhaj salaf, ustadz sunnah, atau penolakan bid'ah/kuburiyyun secara spesifik.

## Putaran tematik (4 Nov 2026)

Putaran pengumpulan tambahan dengan tiga klaster kata kunci tematik, mencakup tiga platform (Threads, Instagram, Facebook). Setiap baris hasil putaran ini ditandai pada kolom **klaster_tema** sesuai klaster asal pencariannya. Filter relevansi yang sama diterapkan, dengan penegasan khusus: untuk klaster kuburiyyun dan tradisi bid'ah, postingan yang **membela** praktik tersebut dari kritik salafi juga relevan dan dicatat pada kategori "Polemik & kritik" dengan sentimen Negatif (atau Netral bila hanya deskriptif/diskusi seimbang).

| Klaster tema | Ter-parse | Duplikat dalam putaran | Duplikat vs dataset lama | Dibuang (di luar topik) | Ditambahkan |
| --- | ---: | ---: | ---: | ---: | ---: |
| Riba & pekerjaan haram | 150 | 0 | 4 | 51 | 95 |
| Kuburiyyun & berkah kubur/habib | 83 | 0 | 0 | 6 | 77 |
| Tradisi bid'ah Indonesia | 150 | 2 | 9 | 18 | 121 |
| **Total** | **383** | **2** | **13** | **75** | **293** |

Pembagian sentimen baris yang ditambahkan per klaster:

| Klaster tema | Positif | Netral | Negatif |
| --- | ---: | ---: | ---: |
| Riba & pekerjaan haram (95) | 37 | 58 | 0 |
| Kuburiyyun & berkah kubur/habib (77) | 26 | 48 | 3 |
| Tradisi bid'ah Indonesia (121) | 33 | 61 | 27 |

Catatan putaran tematik:

- **Riba & pekerjaan haram** (95 baris): isinya testimoni resign dari bank/lembaga ribawi dan pekerjaan haram (33), edukasi hukum pekerjaan haram dan riba (42), serta potongan kajian ustadz tentang tema ini (18). Sebanyak 51 entri dibuang, terbanyak berupa postingan resign atau refleksi karier generik tanpa sudut haram/riba yang dapat diverifikasi dari ringkasannya, pengingat Islami umum, dan konten hak pekerja.
- **Kuburiyyun & berkah kubur/habib** (77 baris): isinya bantahan terhadap tawassul/tabarruk di kuburan dan pencarian berkah dari orang yang sudah wafat, dalam bentuk poster dakwah, potongan kajian, dan video kritik; 3 baris Negatif adalah postingan yang membela tawassul sebagai persoalan fikih yang diperselisihkan. Hanya 6 yang dibuang, antara lain dokumentasi praktik berkah (mis. pembaca doa memberkati air minum) tanpa pendirian atau perdebatan yang dapat dinilai, dan konten yang melenceng dari tema kuburan.
- **Tradisi bid'ah Indonesia** (121 baris): klaster dengan sisi pembela paling besar. Dari 121 baris, 27 berlabel Negatif, yaitu postingan yang membela tahlilan, maulid, yasinan, dan praktik terkait dari kritik salafi (antara lain konten GP Ansor, KH. Luthfi Bashori, KH. Marzuqi Mustamar, Buya Yahya, dan posisi resmi Muhammadiyah soal tahlilan yang tercatat Netral sebagai paparan institusional). Sebanyak 18 dibuang, antara lain dokumentasi acara haul tanpa sudut perdebatan (konsisten dengan perlakuan pada putaran utama), satu hasil positif-palsu kata kunci "haul" yang ternyata membahas haul zakat (masa satu tahun kepemilikan harta), dan satu postingan tanpa teks ringkasan.
- Username Facebook pada putaran ini diambil dari nama penulis (entity) sebagaimana tercatat pada data pencarian; tidak ada nama yang dikarang.

## Pengguna Unik (User)

Jumlah penulis unik di dataset final, diidentifikasi dari identitas penulis pada data (handle untuk Threads/Instagram, nama akun untuk Facebook) dan dihitung ulang dari file CSV final: **586 user**.

| Platform | Baris | User unik |
| --- | ---: | ---: |
| Facebook | 325 | 230 |
| Instagram | 273 | 165 |
| Threads | 240 | 191 |
| **Total** | **838** | **586** |

## Distribusi Sentimen

Sentimen dinilai terhadap hijrah dan manhaj salaf: Positif = mendukung/membagikan perjalanan hijrah atau pembelajaran; Netral = informatif/pengumuman/diskusi netral termasuk peringatan doktrinal tanpa nada permusuhan; Negatif = menolak, mengejek, atau menyerang hijrah/manhaj salaf, termasuk polemik internal yang bernada menyerang.

| Sentimen | Jumlah | Persentase |
| --- | ---: | ---: |
| Positif | 348 | 41,5% |
| Netral | 428 | 51,1% |
| Negatif | 62 | 7,4% |

## Distribusi Kategori Topik

| Kategori | Jumlah | Persentase |
| --- | ---: | ---: |
| Ustadz sunnah & kajian | 273 | 32,6% |
| Polemik & kritik | 159 | 19,0% |
| Belajar manhaj salaf | 135 | 16,1% |
| Testimoni hijrah | 105 | 12,5% |
| Meninggalkan bid'ah | 104 | 12,4% |
| Tren hijrah & gaya hidup sunnah | 62 | 7,4% |

## 15 Kata Paling Sering Muncul

Dihitung ulang dari seluruh teks ringkasan dataset final (838 baris) setelah membuang stopword bahasa Indonesia dan Inggris serta kata-kata teknis deskripsi visual dan kata kerja pelaporan ringkasan (video, gambar, latar, penulis, menjelaskan, dsb.). Ringkasan diterima dalam bahasa Inggris sebagaimana dikeluarkan alat pencarian, sehingga kata yang terhitung adalah kata bahasa Inggris dan istilah dakwah yang dipertahankan apa adanya.

| Kata | Frekuensi |
| --- | ---: |
| indonesian | 553 |
| ustadz | 356 |
| islamic | 303 |
| religious | 299 |
| sunnah | 283 |
| lecture | 180 |
| allah | 167 |
| hijrah | 150 |
| salaf | 148 |
| against | 128 |
| bid'ah | 126 |
| tahlilan | 121 |
| study | 113 |
| basalamah | 106 |
| prophet | 106 |

## Contoh Baris Dataset

| ID | Platform | Username | Kategori | Sentimen | Cuplikan ringkasan |
| ---: | --- | --- | --- | --- | --- |
| 645 | Threads | @moose.579710 | Testimoni hijrah | Netral | The author shares a personal confession about regretting their decision to resign from a bank job. They e... |
| 500 | Instagram | @gyyodm | Testimoni hijrah | Positif | This 10-slide Instagram carousel from HIJRAHACADEMY.ID tells a personal story: the creator's father died... |
| 584 | Instagram | @khalidbasalamahofficial | Ustadz sunnah & kajian | Netral | The Instagram post, created by Khalid Z.A Basalamah, features a high‑quality video of the speaker deliver... |
| 701 | Threads | @ahmadlukmansaad | Polemik & kritik | Negatif | The author critiques a lengthy explanation by Ustadz Firanda Andirja that declares the practice of Tahlil... |
| 737 | Threads | @febriegyst | Meninggalkan bid'ah | Positif | The author posts a short prayer in Indonesian expressing the hope that several traditional Muslim commemo... |
| 814 | Threads | @gp.ansor | Polemik & kritik | Negatif | This four-slide Instagram carousel is an educational and reverent tribute to tahlilan, the Indonesian Mus... |

URL lengkap setiap contoh dan seluruh baris tersedia di file CSV `dataset_sentimen_hijrah_4platform.csv`.

## Catatan Kejujuran Data

### X (Twitter) belum termasuk

Platform X (Twitter) **tidak** masuk dataset ini karena postingan X tidak dapat diambil melalui alat pencarian yang tersedia: X memblokir pengindeksan eksternal, dan dua pencarian web yang dicoba tidak menghasilkan postingan x.com yang sebenarnya. Karena itu dataset saat ini mencakup tiga platform: **Threads, Instagram, dan Facebook**. Menambahkan X memerlukan akses API resmi X atau pengambilan manual per postingan.

### Target 1000+ user

Target yang diminta adalah **1000 user atau lebih**. Angka terverifikasi yang berhasil dicapai saat ini adalah **586 user unik** (838 baris postingan relevan), sehingga masih ada kekurangan sekitar **414 user** dari target. Angka ini tidak ditutup-tutupi dan tidak dilengkapi dengan data karangan. Ada dua jalan jujur untuk menutup kekurangan tersebut:

1. **Pengumpulan lanjutan bertahap**: menjalankan lebih banyak putaran pencarian dengan set kata kunci dan rentang waktu yang lebih luas secara berkala, lalu menggabungkan hasilnya dengan deduplikasi URL yang sama seperti pada dataset ini.
2. **Tambahan data sintetis berlabel SIMULASI**: bila dataset 1000 baris dibutuhkan untuk keperluan latihan/pengujian model, baris tambahan dapat dibuat sebagai data simulasi yang **wajib diberi label jelas 'SIMULASI'** pada kolom tersendiri dan tidak dicampuradukkan sebagai postingan asli, agar tidak pernah terbaca sebagai data nyata.
