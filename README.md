# Pengembangan Aplikasi Buku Pada Saat Pandemi Virus Corona
# Pendahuluan <a id='intro'></a>

Dampak dari merebaknya virus corona telah mengubah cara masyarakat berinteraksi secara global. Saat ini, kita melihat pergeseran ke arah lebih banyak waktu dihabiskan di dalam rumah, menggantikan aktivitas sosial di tempat-tempat umum seperti kafe atau mal. Sebagai tanggapan terhadap transformasi ini, banyak startup telah memulai pengembangan aplikasi-inovatif yang diarahkan untuk memenuhi kebutuhan baru masyarakat. Sebagai bagian dari inisiatif ini, kita diberikan akses ke sebuah basis data yang mencakup informasi terkait buku, penerbit, penulis, serta penilaian dan ulasan dari pengguna. Data ini menjadi landasan kritis dalam perancangan strategi penawaran harga untuk produk-produk inovatif yang sedang kita garap.


# Tujuan <a id='GoalSet'></a>

Tujuan dari proyek ini adalah untuk melakukan analisis data menggunakan SQL terhadap database buku guna mendapatkan wawasan yang berharga terkait dengan industri buku dalam konteks pandemi yaitu:

1. Menjelaskan tujuan dari studi lakukan.󠀲󠀡󠀠󠀦󠀥󠀩󠀡󠀥󠀳
2. Mempelajari tabelnya (tampilkan baris-baris pertamanya).󠀲󠀡󠀠󠀦󠀥󠀩󠀡󠀦󠀳
3. Membuat kueri SQL untuk setiap tugas.󠀲󠀡󠀠󠀦󠀥󠀩󠀡󠀧󠀳
4. Menampilkan hasil dari setiap queri tersebut pada notebook.󠀲󠀡󠀠󠀦󠀥󠀩󠀡󠀨󠀳
5. Menjelaskan kesimpulan untuk setiap tugas.


# Tahapan <a id='Stages'></a>

Berikut beberapa tahapan yang akan kita lakukan yaitu:

1. Menghitung jumlah buku yang dirilis setelah tanggal 1 Januari 2000.󠀲󠀡󠀠󠀦󠀥󠀩󠀠󠀩󠀳
2. Menghitung jumlah ulasan pengguna dan rating rata-rata untuk setiap buku.󠀲󠀡󠀠󠀦󠀥󠀩󠀡󠀠󠀳
3. Mengidentifikasi Penerbit yang Telah Menerbitkan Jumlah Buku Terbanyak dengan Jumlah Halaman Lebih dari 50󠀡 (hal ini akan membantu kita dalam mengecualikan brosur dan publikasi serupa dari hasil analisis).󠀲󠀡󠀠󠀦󠀥󠀩󠀡󠀡󠀳
4. Mengidentifikasi Penulis dengan Rating Rata-Rata Buku Tertinggi: temukan buku dengan rating minimal 5.0.󠀲󠀡󠀠󠀦󠀥󠀩󠀡󠀢󠀳
5. Menghitung Jumlah Rata-Rata Teks Ulasan di Antara Pengguna yang Memberi Rating Terhadap Lebih dari 50 buku


# Deskripsi Data <a id='description'></a>

**`books`**:

* Berisi data tentang buku:
    * `book_id` — ID buku (**Primary Key** -- int)
    * `author_id` — ID penulis (**Foreign Key** -- int)
    * `title` — judul buku (varchar)
    * `num_pages` — jumlah halaman (int)
    * `publication_date` — tanggal penerbitan (datetime)
    * `publisher_id` — ID penerbit (**Foreign Key** -- int)
    
**`authors`**:

* Berisi data tentang penulis:
    * `author_id` — ID penulis (**Primary Key** -- int)
    * `author` — nama penulis (varchar)

**`publishers`**:

* Berisi data tentang penerbit:
    * `publisher_id` — ID penerbit (**Primary Key** -- int)
    * `publisher` — nama penerbit (varchar)

**`ratings**`:

* Berisi data tentang rating pengguna:
    * `rating_id` — ID rating (**Primary Key** -- int)
    * `book_id` — ID buku (**Foreign Key** -- int)
    * `username` — nama pengguna yang memberi rating buku (varchar)
    * `rating` (int)

**`reviews`**:

* Berisi data tentang ulasan pelanggan:
    * `review_id` — ID ulasan (int)
    * `book_id` — ID buku (**Foreign Key** -- int)
    * `username` — nama pengguna yang mengulas buku (varchar)
    * `text` — teks ulasan (varchar)
