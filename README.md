## Filtering Citra

Filtering citra merupakan salah satu bagian dari perbaikan kualitas citra, yaitu  menghaluskan dan menghilangkan noise  yang ada pada citra, baik secara linear maupun secara non-linear. Mean filter  merupakan salah satu filtering linear yang bekerja dengan menggantikan intensitas nilai pixel dengan rata-rata dari nilai pixel tersebut dengan nilai pixel-pixel tetangganya.  Sedangkan median filter merupakan salah satu  filtering non-linear yang mengurutkan nilai intensitas sekelompok pixel, kemudian mengganti nilai pixel yang diproses dengan nilai mediannya.

### Median Filtering
Median filtering mengambil area tertentu pada citra sesuai dengan ukuran mask yang telah ditentukan (umumnya 3x3), kemudian dilihat setiap nilai piksel pada area tersebut, dan nilai tengah pada area diganti dengan nilai median
                    F(x,y) = G(x,y) min, G(x,y) max
Keterangan:
F(x,y) = Citra Hasil Filter
G(x,y) = Nilai Piksel Minimum
G(x,y) = Nilai Piksel Maximum

Cara memperoleh nilai median adalah nilai keabuan dari titik-titik pada matriks diurutkan dari nilai terkecil hingga yang terbesar, kemudian ditentukan nilai yang berada di tengah dari deret piksel. Untuk tipe-tipe
noise tertentu, filter ini memberikan kemampuan reduksi noise yang sangat baik, dengan blurring yang lebih sedikit daripada linear smoothing filter untuk ukuran citra yang sama. Median filtering memberikan hasil yang sangat bagus untuk citra yang terkena noise impulse bipolar dan unipolar. 

Median filter memiliki beberapa kelebihan, seperti:
- Efektif dalam mengurangi noise salt and pepper
- Mudah diimplemetasikan
- Tidak memerlukan banyak komputasi

Namun, median filter juga memiliki beberapa kekurangan, seperti:

 - Tidak efektif dalam mengurangi noise Gaussian
 - Dapat menyebabkan kehilangan detail citra

### Mean Filtering
Menurut Usman (2005:61) salah satu filter linier adalah filter rata-rata (Filter Mean) dari intensitas pada beberapa pixel lokal dimana setiap pixel akan digantikan nilainya dengan rata-rata dari nilai intensitas pixel tersebut dengan pixel-pixel tetangganya, dan jumlah pixel tetangga yang dilibatkan tergantung pada filter yang dirancang. Mean Filter adalah mengganti nilai pixel pada posisi (x,y) dengan nilai rata-rata pixel yang berada tetangga disekitarnya. Luasan jumlah pixel tetangga ditentukan sebagai masking/kernel/window yang berukuran misalkan 2x2, 3x3, 4x4, dan seterusnya. Kemudian akan dilakukan mean filter untuk citra M dengan menggunakan matriks kernel (3x3). Pixel m(2,2) = 3, akan diubah menjadi selain mean filtering yang merupakan proses filter linier, terdapat pula pendekatan filter pembobotan (weighted filter).

Mean filter memiliki beberapa kelebihan, seperti:

- Efektif dalam mengurangi noise Gaussian
- Mudah diimplemetasikan
- Tidak memerlukan banyak komputasi

Namun, mean filter juga memiliki beberapa kekurangan, seperti:

- Tidak efektif dalam mengurangi noise salt and pepper
- Dapat menyebabkan kehilangan detail citra

Dalam project UAS ini, median filter digunakan untuk mengurangi noise pada citra RGB, sedangkan mean filter digunakan untuk mengurangi noise pada citra grayscale. Hasilnya menunjukkan bahwa median filter dapat mengurangi noise pada citra RGB dengan efektif, sedangkan mean filter dapat mengurangi noise pada citra grayscale dengan efektif.

## Tahap-tahap proses yang dilakukan
Langkah 1: Membaca dan Konversi Gambar 
Proyek dimulai dengan membaca file gambar bernama "pcduas.jpg" menggunakan fungsi Imread OpenCV. Gambar kemudian diubah dari ruang warna BGR ke ruang warna RGB menggunakan fungsi cvtColor.

Langkah 2: Konversi ke Grayscale 
Gambar asli diubah menjadi skala abu-abu menggunakan fungsi cvtColor. Ini merupakan langkah penting untuk beberapa teknik pemfilteran gambar.

Langkah 3: Penyaringan Median
Penyaringan median diterapkan pada gambar RGB menggunakan kernel berukuran 3x3. Hal ini dilakukan dengan menelusuri setiap saluran warna dan menerapkan fungsi medianBlur.

Langkah 4: Menampilkan gambar 
Gambar asli dan gambar median yang difilter ditampilkan berdampingan menggunakan fungsi subplot dan imshow Matplotlib.
 
Langkah 5: Penyaringan Rata-rata
Pemfilteran rata-rata diterapkan pada gambar skala abu-abu menggunakan kernel berukuran 5x5. Ini dilakukan dengan menggunakan fungsi blur.

Langkah 6: Tampilkan gambar (penyaringan rata-rata) 
Gunakan fungsi subplot dan imshow Matplotlib untuk menampilkan gambar skala abu-abu dan gambar rata-rata yang difilter secara berdampingan.
 
Langkah 7: Menampilkan gambar akhir 
Menggunakan fungsi subplot dan imshow Matplotlib, keempat gambar (gambar asli, filter median, skala abu-abu, dan filter rata-rata) ditampilkan dalam kotak 2x2. Ini memberikan gambaran komprehensif tentang gambar asli dan efektivitas teknik penyaringan median dan mean.

