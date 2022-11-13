# SIG-Teori-Modul6-Basic-RasterStylingandAnalysis-

##data

Silahkan download data berikut :

[gpw-v4-population-count-rev11_2000_2pt5_min_tif.zip](https://www.qgistutorials.com/downloads/gpw-v4-population-count-rev11_2000_2pt5_min_tif.zip)

[gpw-v4-population-count-rev11_2010_2pt5_min_tif.zip](https://www.qgistutorials.com/downloads/gpw-v4-population-count-rev11_2010_2pt5_min_tif.zip)

## Prosedure

1. Buka QGIS dan temukan file yang diunduh di panel Browser . Perluas gpw-v4-population-count-rev11_2000_2pt5_min_tif.zipfile dan seret gpw-v4-population-count-rev11_2000_2pt5_min.tiffile ke kanvas.
2. Layer baru gpw-v4-population-count-rev11_2000_2pt5_minakan ditambahkan ke panel Layers . Demikian pula, cari gpw-v4-population-count-rev11_2010_2pt5_min_tif.zipfile dan seret gpw-v4-population-count-rev11_2010_2pt5_min.tiffile ke kanvas.
3. Mari jelajahi lapisan ini. Klik tombol Identifikasi pada Bilah Alat Atribut . Setelah alat dipilih, klik titik mana pun di kanvas.
4. Nilai yang terkait dengan piksel itu akan ditampilkan di panel Identifikasi Hasil baru. Di panel Identifikasi Hasil , ubah Mode menjadi . Ini akan menampilkan nilai piksel dari semua raster, bukan hanya lapisan paling atas. Bandingkan nilai dari kedua lapisan. Karena resolusi raster kira-kira 5km x 5km, nilai piksel mewakili total populasi di area (25 km persegi) yang diwakili oleh piksel.Top down
5. Tutup panel Identifikasi Hasil . Mari kita buat visualisasi layer yang lebih baik. Klik tombol Open the layer Styling panel di panel Layers .
6. Di panel Layer Styling , klik dropdown Render type dan pilih renderer.Singleband pseudocolor
7. Renderer ini akan memberi style pada layer menggunakan color ramp. Ramp warna default adalah putih-merah di mana nilai minimum akan diberi warna putih dan nilai maksimum di lapisan akan diberi warna merah. Nilai tengah akan diberi warna interpolasi linier merah. Perluas Pengaturan Nilai Min / Maks dan pilih opsi. Anda akan melihat bahwa visualisasi peta sekarang jauh lebih baik. Rentang data standar ditetapkan dari 2% hingga 98% dari nilai data, artinya outlier tidak akan digunakan untuk menetapkan nilai minimum dan maksimum, sehingga menghasilkan visualisasi yang jauh lebih representatif.Cumulative count cut
8. Close the Layer Styling panel. We can apply the similar styling to the other layer as well. But there is an easier way to transfer the styles from one layer to the other. Right-click the gpw-v4-population-count-rev11_2010_2pt5_min layer and select Styles ‣ Copy Style.
9. Sekarang klik kanan gpw-v4-population-count-rev11_2000_2pt5_minlayer un-style dan pilih Styles Paste Style.
10. Parameter gaya yang sama akan diterapkan ke lapisan lainnya. Fitur ini sangat berguna ketika Anda ingin membandingkan lapisan yang berbeda menggunakan kategorisasi yang sama. Saat Anda mengaktifkan visibilitas lapisan atas, Anda dapat melihat perubahan populasi secara visual.
11. Tugas kita adalah membuat peta tematik dari perubahan populasi. Mari hitung selisih antara 2 layer dan buat raster lain di mana setiap piksel mewakili perubahan dalam populasi. Pergi ke Raster ‣ Kalkulator raster .
12. Di bagian Raster bands , Anda dapat memilih layer dengan mengklik dua kali pada layer tersebut. Band diberi nama setelah nama raster diikuti dengan @dan nomor band. Karena setiap raster kami hanya memiliki 1 band, Anda akan diberi nama dengan @1ditambahkan ke nama layer. Kalkulator raster dapat menerapkan operasi matematika pada piksel raster. Dalam hal ini kita ingin memasukkan rumus sederhana untuk mengurangkan populasi tahun 2010 dari tahun 2000. Masukkan ekspresi berikut. Selanjutnya, klik tombol … di sebelah Output layer .

------------------

"gpw-v4-population-count-rev11_2010_2pt5_min@1" - "gpw-v4-population-count-rev11_2000_2pt5_min@1"

------------------

13. Masukkan population_change_2010_2000.tifsebagai file Keluaran . Klik OK untuk memulai perhitungan.
14. Setelah selesai layer baru population_change_2010_2000akan ditambahkan ke panel Layers . Mari kita ubah gayanya agar perubahan populasi negatif dan positif lebih divisualisasikan. Klik tombol Open the layer Styling panel di panel Layers .
15. Salah satu pilihannya adalah menggunakan teknik penataan yang sama seperti sebelumnya dan memilih jalur warna yang berbeda. Klik drop-down Color ramp dan pilih Spectralramp. Klik tarik-turun lagi dan pilih untuk menetapkan warna biru ke nilai rendah dan merah ke nilai tinggi.Invert Color Ramp.
16. Ini adalah visualisasi yang bagus, tetapi tidak mudah untuk ditafsirkan. Mari kita buat peta yang lebih baik dengan 4 kategori diskrit, Decline, Neutral, Growthdan . Gulir ke bawah ke tabel dengan kelas. Tahan tombol dan pilih semua baris. Klik tombol Hapus baris yang dipilih .High GrowthShift
17.  Ubah mode InterpolasiDiscrete ke . Sekarang kita akan membuat peta warna secara manual. Klik tombol Tambahkan nilai secara manual . Masukkan -100sebagai Nilai dan Declinesebagai Label . Tetapkan warna biru untuk kategori ini. Cara kerja peta warna adalah semua nilai yang lebih rendah dari nilai yang dimasukkan akan diberi warna entri tersebut. Anda akan melihat bahwa kanvas hanya akan menampilkan area dengan perubahan populasi negatif.
18. Lengkapi peta warna dengan nilai yang sesuai. Saya memilih 100, 1000dan 100000sebagai batas atas untuk Neutral, Growthdan kategori masing-masing. Tetapkan warna untuk setiap kategori yang dibuat, misalnya krem, oranye, dan merah.High Growth.
19. Setelah Anda puas dengan visualisasi, tutup panel Layer Styling . Anda sekarang memiliki peta tematik global tentang perubahan populasi.
20. selesai.
