# Naskah Video Tugas Praktik 1 – Aplikasi Restoran (Java)

Target durasi sekitar 13 menit 45 detik, di bawah batas 15 menit. Teks dalam tanda kutip adalah kalimat yang diucapkan. Bagian **[dalam kurung siku]** diganti dengan data Anda.

## Ringkasan durasi

| Bagian | Waktu | Durasi | Di layar | Wajib menurut soal |
| --- | --- | --- | --- | --- |
| 2. Pembukaan dan perkenalan | 00:00 – 01:00 | 1 menit | Wajah | Ya (nama, NIM, prodi, mata kuliah) |
| 3. Penjelasan singkat tugas | 01:00 – 02:00 | 1 menit | Soal / folder `src` | Ya |
| 4. Class Menu | 02:00 – 03:15 | 1,25 menit | `Menu.java` | Petunjuk poin 1 |
| 5. Class Konstanta dan DataMenu | 03:15 – 04:15 | 1 menit | `Konstanta.java`, `DataMenu.java` | Petunjuk poin 4 (array menu) |
| 6. Class Main | 04:15 – 07:15 | 3 menit | `Main.java` | Petunjuk poin 2–6 |
| 7. Demo 5 skenario | 07:15 – 12:15 | 5 menit | Terminal | Ya (demo langsung + skenario keputusan) |
| 8. Penjelasan hasil | 12:15 – 13:15 | 1 menit | Struk / wajah | Ya |
| 9. Penutup | 13:15 – 13:45 | 0,5 menit | Wajah | Ya |

Jika waktu kurang, persingkat bagian 6 (penjelasan class Main), bukan bagian demo.

---

## 1. Persiapan sebelum merekam

- [ ] Kamera/webcam menyala dan wajah terlihat jelas sepanjang video (wajib)
- [ ] Aplikasi perekam layar siap (OBS Studio, Xbox Game Bar `Win+G`, atau Zoom record) dengan webcam di pojok layar
- [ ] Mikrofon dites, ruangan tenang
- [ ] VS Code / Eclipse terbuka dengan file `Menu.java`, `Konstanta.java`, `DataMenu.java`, dan `Main.java`
- [ ] Terminal sudah di folder `src` dan program sudah pernah dikompilasi: `javac Menu.java Konstanta.java DataMenu.java Main.java`
- [ ] Ukuran font editor dan terminal diperbesar (zoom 125–150%) agar kode terbaca di video
- [ ] Naskah ini dibuka di monitor kedua atau di HP, bukan di layar yang direkam
- [ ] Input setiap skenario demo (bagian 6) disalin ke Notepad agar tinggal di-copy-paste saat demo
- [ ] Notifikasi laptop dimatikan (Focus Assist / Do Not Disturb)

---

## 2. Pembukaan dan perkenalan (00:00 – 01:00)

**Di layar:** wajah Anda (kamera penuh atau besar), belum perlu menampilkan kode.

**Ucapkan:**

> "Assalamualaikum warahmatullahi wabarakatuh / Selamat pagi, Bapak/Ibu Tutor. Perkenalkan:
>
> - Nama saya **[Nama Lengkap]**
> - NIM **[NIM]**
> - Program Studi **[Program Studi]**
> - Mata kuliah **[Nama dan Kode Mata Kuliah]**
>
> Pada video ini saya akan menjelaskan pengerjaan Tugas Praktik 1, yaitu program Java aplikasi pemesanan sederhana di sebuah restoran."

**Tips:** sebutkan identitas dengan pelan dan jelas. Bagian ini wajib ada di awal video.

---

## 3. Penjelasan singkat tugas (01:00 – 02:00)

**Di layar:** file soal atau laporan bagian Soal, lalu folder `src` yang berisi `Menu.java`, `Konstanta.java`, `DataMenu.java`, dan `Main.java`.

**Ucapkan:**

> "Tugas ini meminta kita membuat aplikasi restoran sederhana dengan empat fungsi: menyimpan data menu, menerima pesanan maksimal 4 menu, menghitung total biaya, dan mencetak struk.
>
> Aturan biayanya: total pesanan ditambah pajak 10% dan biaya pelayanan Rp 20.000. Ada dua promo. Diskon 10% jika total pesanan lebih dari Rp 100.000. Lalu promo beli 1 gratis 1 untuk minuman jika total pesanan lebih dari Rp 50.000.
>
> Program ini menunjukkan tiga indikator penilaian. Pertama, penggunaan tipe data, variabel, identifier, dan keyword di class, object, dan method. Kedua, penggunaan array dan String di dalam method. Ketiga, struktur keputusan: if, if-else, if-else if, nested if, dan switch case.
>
> Sesuai petunjuk, program ini sama sekali tidak memakai perulangan seperti for atau while. Programnya terdiri dari empat class. Class Menu untuk satu item menu, Konstanta untuk nilai tetap seperti pajak dan diskon, DataMenu untuk array data menu, dan Main untuk alur programnya. Pemisahan ini membuat setiap class punya satu tugas yang jelas."

---

## 4. Penjelasan class Menu (02:00 – 03:15)

**Di layar:** buka `Menu.java`. Sorot (blok) baris yang sedang dibahas.

**Ucapkan:**

> "Ini class `Menu`, yang mewakili satu item menu di restoran. Class ini punya tiga atribut: `nama` bertipe `String`, `harga` bertipe `int`, dan `kategori` bertipe `String`. Kategorinya diisi Makanan atau Minuman.
>
> Ketiga atribut memakai keyword `private`, sehingga hanya bisa diakses lewat method. Ini disebut enkapsulasi.
>
> Berikutnya ada constructor `Menu(String nama, int harga, String kategori)`. Constructor dipanggil ketika objek dibuat dengan keyword `new`. Keyword `this` dipakai untuk membedakan atribut dengan parameter yang namanya sama.
>
> Lalu ada method getter, yaitu `getNama()`, `getHarga()`, dan `getKategori()`, untuk mengambil nilai atribut. Terakhir, method `isMinuman()` mengembalikan `boolean`. Method ini memakai method String `equalsIgnoreCase` untuk mengecek apakah kategorinya Minuman. Method ini nanti dipakai untuk promo beli 1 gratis 1."

**Istilah yang perlu disebut:** identifier (nama class, atribut, method seperti `Menu`, `harga`, `getNama`) dan keyword (`public`, `private`, `class`, `this`, `return`, `new`).

---

## 5. Penjelasan class Konstanta dan DataMenu (03:15 – 04:15)

**Di layar:** buka `Konstanta.java`, lalu `DataMenu.java`.

### a. `Konstanta.java` (±30 detik)

> "Class `Konstanta` mengumpulkan semua nilai tetap di satu tempat. Isinya `PERSEN_PAJAK` 0.10 dan `PERSEN_DISKON` 0.10 bertipe `double`, lalu `BIAYA_PELAYANAN` 20000, `BATAS_DISKON` 100000, `BATAS_PROMO_MINUMAN` 50000, dan `MAKS_PESANAN` 4 bertipe `int`.
>
> Semuanya memakai keyword `static final`. `final` artinya nilainya tidak bisa diubah saat program berjalan. `static` artinya bisa dipanggil lewat nama class tanpa membuat objek, misalnya `Konstanta.BATAS_DISKON`. Kalau aturan restoran berubah, cukup class ini yang diubah."

### b. `DataMenu.java` (±30 detik)

> "Class `DataMenu` menyimpan array `daftarMenu` bertipe `Menu[]` dengan 8 elemen. Method `inisialisasiMenu` mengisi array itu dengan objek `Menu` memakai keyword `new`. Indeks 0 sampai 3 berisi makanan, dan indeks 4 sampai 7 berisi minuman. Class `Main` nanti mengambil data ini lewat `DataMenu.daftarMenu`."

---

## 6. Penjelasan class Main (04:15 – 07:15)

**Di layar:** buka `Main.java`. Scroll dari atas ke bawah mengikuti urutan di bawah.

### a. Array pesanan dan method `main` (±30 detik)

> "Di bagian atas `Main` ada dua array untuk data pesanan. `menuDipesan` menyimpan menu yang dipesan dan `jumlahDipesan` menyimpan jumlahnya. Ukuran keduanya diambil dari `Konstanta.MAKS_PESANAN`, yaitu 4. Array ini sengaja tetap di `Main` karena isinya pesanan pelanggan, bukan data restoran.
>
> Method `main` adalah titik awal program. Isinya memanggil empat langkah secara berurutan: `DataMenu.inisialisasiMenu`, `tampilkanDaftarMenu`, `terimaPesanan`, dan `cetakStruk`."

### b. `tampilkanDaftarMenu` (±20 detik)

> "Method `tampilkanDaftarMenu` menampilkan menu yang dikelompokkan per kategori, MAKANAN lalu MINUMAN. Karena tidak boleh memakai perulangan, setiap elemen array dipanggil langsung lewat indeksnya, dari `DataMenu.daftarMenu[0]` sampai `DataMenu.daftarMenu[7]`. Formatnya diatur dengan `printf`."

### c. `terimaPesanan` dan `prosesPesanan` (±1 menit)

> "`terimaPesanan` menanyakan berapa jenis menu yang ingin dipesan. Input dicek dengan method String `matches` agar berupa angka. Lalu ada **if – else if**: jika kurang dari 1 pesanan dibatalkan, dan jika lebih dari 4 dibatasi menjadi 4.
>
> Tanpa perulangan, setiap slot pesanan diisi dengan **if** terpisah: jika jumlah jenis ≥ 1 isi pesanan ke-1, jika ≥ 2 isi pesanan ke-2, dan seterusnya.
>
> Di `prosesPesanan`, input seperti `Nasi Padang = 2` dipecah dengan `split("=")` menjadi array String. Nama menu dan jumlahnya dirapikan dengan `trim()`. Di sini ada **nested if**, yaitu if di dalam if. Pertama dicek formatnya punya tanda sama dengan. Lalu dicek jumlahnya angka. Lalu dicek menunya ada dan jumlahnya tidak nol.
>
> Kalau semua valid, pesanan disimpan ke array dan program langsung menampilkan konfirmasi harga, misalnya `Ditambahkan: 2 x Nasi Padang @ Rp 35.000 = Rp 70.000`. Jadi pelanggan bisa langsung melihat harga satuan dan subtotalnya."

### d. `cariIndeksMenu` – switch case (±15 detik)

> "Method ini memakai **switch case**. Nama menu diubah ke huruf kecil dengan `toLowerCase()`, sehingga input tidak peka huruf besar-kecil. Setiap `case` mengembalikan indeks menu di array `DataMenu.daftarMenu`. Jika tidak cocok, `default` mengembalikan -1."

### e. Perhitungan biaya (±30 detik)

> "`hitungTotalItem` mengalikan harga dengan jumlah. Ada **if** untuk slot kosong yang nilainya 0. `hitungTotalPesanan` menjumlahkan keempat slot. `hitungDiskon` memakai **if-else**: jika total lebih dari `Konstanta.BATAS_DISKON`, yaitu Rp 100.000, diskonnya 10%; selain itu 0.
>
> Urutan hitungnya: total pesanan, dikurangi diskon, lalu pajak 10% dari total setelah diskon, ditambah biaya pelayanan Rp 20.000.
>
> `cariSlotMinumanPertama` memakai **if – else if** untuk mencari minuman pertama di pesanan. Minuman itulah yang mendapat promo beli 1 gratis 1."

### f. `cetakStruk` dan `cetakInfoPenawaran` (±25 detik)

> "`cetakStruk` mencetak item, qty, harga, total per item, total pesanan, pajak, biaya pelayanan, dan total bayar. Baris diskon dan total setelah diskon hanya muncul jika ada diskon, dengan **if**. Jika tidak ada pesanan valid, struk tidak dicetak.
>
> `cetakInfoPenawaran` memakai **nested if**. Jika total lebih dari Rp 50.000, program mencari minuman. Jika ada minuman, pelanggan mendapat bonus minuman gratis sejumlah yang dipesan. Jika tidak ada, muncul keterangan bahwa promo tidak dipakai. Terakhir, `formatRupiah` mengubah angka menjadi format seperti Rp 151.000."

---

## 7. Demo program langsung (07:15 – 12:15)

Jalankan program 5 kali, satu kali per skenario. Setiap skenario menunjukkan satu cabang struktur keputusan. Semua angka di bawah sudah dicek dari hasil program.

**Di layar:** terminal di folder `src`. Ketik:

```
javac Menu.java Konstanta.java DataMenu.java Main.java
java Main
```

> "Sekarang saya jalankan programnya. Pertama tampil daftar menu yang dikelompokkan berdasarkan kategori: 4 makanan dan 4 minuman."

| No | Skenario | Input yang diketik | Hasil di struk |
| --- | --- | --- | --- |
| 1 | Total ≤ Rp 50.000, tanpa promo | `2`, `Mie Ayam Bakso = 1`, `Es Teh Manis = 1` | Total pesanan Rp 30.000, pajak Rp 3.000, pelayanan Rp 20.000, **total bayar Rp 53.000**. Tidak ada diskon dan belum dapat promo minuman. |
| 2 | Total > Rp 50.000 dengan minuman | `2`, `Nasi Padang = 1`, `Es Jeruk = 2` | Total pesanan Rp 55.000, **total bayar Rp 80.500**. Bonus 2 x Es Jeruk gratis (senilai Rp 20.000). |
| 3 | Total > Rp 50.000 tanpa minuman | `1`, `Nasi Goreng Spesial = 2` | Total pesanan Rp 56.000, **total bayar Rp 81.600**. Promo minuman tidak dipakai karena tidak ada minuman. |
| 4 | Total > Rp 100.000, 4 menu | `4`, `Nasi Padang = 2`, `Sate Ayam = 1`, `Jus Alpukat = 2`, `Kopi Susu = 1` | Total pesanan Rp 151.000, diskon Rp 15.100, setelah diskon Rp 135.900, pajak Rp 13.590, **total bayar Rp 169.490**. Bonus 2 x Jus Alpukat gratis (senilai Rp 36.000). |
| 5 | Input tidak valid | `5`, `Nasi Uduk = 1`, `Es Teh Manis 2`, `Kopi Susu = dua`, `sate ayam = 3` | Pesan "Maksimal 4 menu", menu tidak ada, format salah, jumlah bukan angka. Hanya Sate Ayam 3 yang masuk struk, **total bayar Rp 119.000**. |

**Ucapkan saat skenario 1:**

> "Total pesanan Rp 30.000, belum lebih dari Rp 50.000. Jadi kondisi if untuk diskon dan promo minuman bernilai false, dan keduanya tidak didapat. Pajak 10% Rp 3.000 dan biaya pelayanan Rp 20.000, sehingga total bayar Rp 53.000."

**Ucapkan saat skenario 2:**

> "Total Rp 55.000, lebih dari Rp 50.000, dan ada minuman. Nested if-nya bernilai true di kedua tingkat, sehingga Es Jeruk mendapat promo beli 1 gratis 1. Karena dipesan 2, bonusnya 2 gelas gratis. Diskon 10% belum berlaku karena belum lebih dari Rp 100.000."

**Ucapkan saat skenario 3:**

> "Total Rp 56.000 sudah lebih dari Rp 50.000, tapi tidak ada minuman. Jadi if bagian luar true, tetapi if bagian dalam false, dan masuk ke else: promo tidak dipakai."

**Ucapkan saat skenario 4:**

> "Ini contoh pesanan maksimal 4 menu. Total Rp 151.000, lebih dari Rp 100.000, sehingga mendapat diskon 10% Rp 15.100. Pajak dihitung dari total setelah diskon: 10% x 135.900 = Rp 13.590. Ditambah pelayanan Rp 20.000, total bayar Rp 169.490. Promo minuman diberikan ke minuman pertama yang dipesan, yaitu Jus Alpukat."

**Ucapkan saat skenario 5:**

> "Sekarang saya tunjukkan validasi input. Saya mengetik 5, sehingga muncul pesan maksimal 4 menu dari if-else if. Nasi Uduk tidak ada di switch case, jadi default mengembalikan -1. Input tanpa tanda sama dengan dianggap format salah. Jumlah 'dua' ditolak karena bukan angka. Sate ayam dengan huruf kecil tetap diterima karena memakai toLowerCase."

**Opsional (jika waktu cukup):** ketik `0` pada pertanyaan jumlah jenis menu. Pesanan dibatalkan dan struk tidak dicetak.

---

## 8. Penjelasan hasil program (12:15 – 13:15)

**Di layar:** struk skenario 4 (yang paling lengkap) atau wajah Anda.

**Ucapkan:**

> "Dari demo tadi, program sudah memenuhi semua fungsi yang diminta. Menu disimpan di array dan ditampilkan per kategori. Pelanggan bisa memesan maksimal 4 menu dengan format Nama Menu = Jumlah. Total biaya dihitung lengkap dengan pajak 10% dan biaya pelayanan Rp 20.000. Struk menampilkan item, jumlah, harga per item, total per item, pajak, pelayanan, dan informasi diskon atau promo jika ada.
>
> Semua skenario struktur keputusan sudah ditunjukkan: tanpa promo, promo minuman, promo tanpa minuman, diskon 10% sekaligus promo, dan input yang tidak valid. Semua itu dikerjakan tanpa satu pun perulangan."

---

## 9. Penutup (13:15 – 13:45)

**Di layar:** wajah Anda (kamera besar).

**Ucapkan:**

> "Demikian penjelasan Tugas Praktik 1 dari saya, **[Nama]**, NIM **[NIM]**. Terima kasih kepada Bapak/Ibu Tutor yang telah menonton. Mohon maaf apabila ada kekurangan. Wassalamualaikum warahmatullahi wabarakatuh / Selamat pagi."

**Setelah merekam:**

- [ ] Unggah ke YouTube (Unlisted atau Public) atau Google Drive (akses "Siapa saja yang memiliki link")
- [ ] Buka link di jendela incognito untuk memastikan video bisa diputar tanpa login
- [ ] Tempel link di laporan bagian D
