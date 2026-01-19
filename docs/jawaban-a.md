### Jawaban Bagian A

#### 1. Analisis Kondisi
thisneptunegirl@gmail.com

#### 2. Source Control Management
a. Menurut [Git (n.d.)](https://git-scm.com/docs/git#_git_commands), berikut ini 4 _commands_ dalam Git.  
 * **branch**: digunakan untuk menge-_list_, membuat, dan menghapus _branch_ 'cabang' dari sebuah repositori.   
  Contoh penggunaan: Menghapus _branch_ dengan nama "nama_branch". 

```shell
  git branch -d nama_branch
  ```  
 * **add**: digunakan untuk menambahkan konten dari fail ke dalam indeks. Indeks atau disebut juga _staging area_ merupakan tempat yang digunakan untuk mempersiapkan konten yang akan di-_commit_ berikutnya.  
  Contoh penggunaan: Menambahkan (_add_) konten yang diubah dari file nama_file_dan_jalurnya.
```shell
  git add nama_file_dan_jalurnya
  ```  
 * **commit**: digunakan untuk me-_record_ segala perubahan yang telah ditambahkan sebelumnya (menggunakan git-add).  
  Contoh penggunaan: Mencatat (_record_) seluruh (ditandai dengan .) perubahan konten.
```shell
  git commit .
  ```
 * **switch**: digunakan untuk mengubah _current branch_ 'cabang yang sedang ditempati'.  
  Contoh penggunaan: Mengubah _current branch_ dari _branch_ lain menjadi _branch_ dengan nama nama_branch
```shell
  git switch nama_branch
  ```

b. Tangkapan layar _source code_ Visual Studio Code
 ![tangkapan layar source code Visual Studio Code](../lampiran/tangkapan-layar-source-code-vsc.png)

c. Tangkapan layar learn git branching
 ![tangkapan layar stage 4 main pertama](../lampiran/tangkapan-layar-akhir-main-pertama.png)
 ![tangkapan layar select a level main](../lampiran/tangkapan-layar-select-a-level-main.png)
 ![tangkapan layar stage 6 remote pertama](../lampiran/tangkapan-layar-akhir-6-remote.png)
 ![tangkapan layar select a level remote](../lampiran/tangkapan-layar-select-a-level-remote.png)

d. Tangkapan layar bukti menyelesaikan _exercise_ Git SSH Security
 ![tangkapan layar bukti menyelesaikan exercise Git SSH Security](../lampiran/tangkapan-layar-exercise-git-ssh.png)

e. **SOON**

#### 3. Pengenalan Ground Control System
a. Tangkapan layar halaman utama Mission Planner
![tangkapan layar halaman utama Mission Planner](../lampiran/tangkapan-layar-instalasi-mission-planner.png)

b. Merujuk pada dokumentasi [Ardupilot (2024)](https://ardupilot.org/planner/docs/mission-planner-features.html), berikut adalah fitur-fitur utama Mission Planner beserta kegunaannya dalam operasi UAV.
 * **Data**: Memberikan informasi terkait hal-hal yang dapat dilihat dan dilakukan pada Flight Data Screens. Dalam Flight Data Screen, terdapat HUD (Heads Up Area) yang berisi informasi terkait kecepatan udara, arah yang sedang dituju, seberapa jauh kesalahan arah pesawat, koneksi telemetri, sudut pembelokan, dan lainnya. Selain itu, terdapat pula Control dan Status yang memberikan informasi (seperti Status) atau kontrol terhadap kendaraan yang digunakan--dalam hal ini UAV (seperti Action). Ada pula Map Area yang memberikan visualisasi pergerakan UAV.
 * **Plan**: Dalam seksi ini, pengguna dapat merencanakan dan mengeksekusi rencana penerbangan. Rencana ini disebut dengan _Mission_ 'misi'. Di sini, terdapat Mission Planning yang dapat meng-_auto-generate_ survei dan misi berbasis grid. Kebanyakan survei dan misi didasarkan pada poligon yang digambar pada peta. Pengguna dapat menggambar poligon untuk membuat area penerbangan. Area penerbangan ini membuat batas selama penerbangan UAV berlangsung.
 * **Setup**: _Section_ ini memperbolehkan pengguna mempersiapkan dan mengonfigurasi autopilot untuk kendaraan spesifik. Kebanyakan _subsections_ memberikan informasi terkait hal-hal yang perlu dilakukan sebelum penerbangan pertama. Di sini, terdapat instalasi Firmware, perangkat keras yang diperlukan, perangkat keras yang opsional, dan tahapan yang harus dilakukan sebelum menerbangkan UAV.
 * **Simulation**: Simulation menyediakan simulasi SITL (Software in the Loop) yang memperbolehkan pengguna menjalankan UAV tanpa perangkat keras. Dalam _section_ ini, pengguna dapat melihat bagaimana UAV akan diterbangkan sebelum penerbangan dilakukan sehingga meminimalisasi kerusakan riil fisik UAV.

 c. Misi pemetaan sederhana persegi panjang 80x100  
  [misi-pemetaan-sederhana-80x100.waypoints](../lampiran/misi-pemetaan-sederhana-80x100.waypoints)
  ![Tangkapan layar misi sederhana (untuk error prevention)](../lampiran/tangkapan-layar-misi-pemetaan-sederhana.png)

#### 4. Development Environment


#### 5. Dasar-Dasar UAV
a. [Menurut P S dan Jeyan (2022)](https://www.researchgate.net/publication/359081357_Comparative_Analysis_of_Fixed-Wing_Rotary-Wing_and_Hybrid_Mini_Unmanned_Aircraft_Systems_UAS_from_the_Applications_Perspective), berikut ini perbedaan tiga klasifikasi UAV berdasarkan cara terbang.
 * **_Fixed-Wing_ (HTOL).** _Fixed-Wing UAV_ memiliki daya tahan penerbangan yang sangat baik sehingga dapat meliputi area yang luas dalam sekali operasi penerbangan. Beberapa keunggulan _Fixed-Wing UAV_ atau HTOL adalah desain yang sederhana, kapabilitas muatan yang lebih besar, dan kebutuhan pemeliharaan yang minim. Untuk UAV tipe ini, gaya angkat yang menyebabkan penerbangan akan terbentuk ketika daya tolak dan kecepatan lepas landas dengan pertimbangan-berat-dan-besar-pesawat yang-dibutuhkan terpenuhi. Dengan demikian, dibutuhkan lajur yang mendatar dan panjang. Kekurangan UAV tipe ini adalah lepas landas dan pendaratan karena lajur panjang yang dibutuhkan lebih sering tidak tersedia. Selain itu, sulit bagi UAV tipe ini untuk berdiam di udara. Kemudian, dibutuhkan roda yang yang tepat untuk memastikan perlambatan ketika mendarat dalam waktu tertentu terpenuhi [(Lee, Kim, & Chu, 2021)](https://doi.org/10.1007/s12541-021-00489-y).
 ![Gambar Penerbangan HTOL](../lampiran/gambar-penerbangan-htol.png)
 * **_Rotary-Wing_ (VTOL).** _Rotary-Wing_ UAV, UAV yang membentuk gaya angkat melawan gravitasi dengan memutar angin. UAV jenis ini memiliki keunggulan untuk lepas landas dan mendarat secara vektikal. Fitur ini memungkinkan operasi penerbangan dalam area yang lebih sempit. Selain itu, VTOL juga dapat melakukan "pelayangan" di udara yang memungkinkan UAV jenis ini untuk mempertahankan ketinggian di udara. Kekurangan VTOL atau _Rotary-Wing_ UAV adalah penggunaan bahan bakar yang tinggi karena seluruh rotor harus bergerak terus-menerus untuk membentuk gaya angkat yang kontinu [(Lee, Kim, & Chu, 2021)](https://doi.org/10.1007/s12541-021-00489-y). 
 ![Gambar Penerbangan VTOL](../lampiran/gambar-penerbangan-vtol.png)
 * **_Hybrid-Wing Based UAV_.** UAV jenis ini membentuk gaya angkat dengan mengombinasikan _fixed wing_ dan _rotating wing_. _Hybrid-wing_ mengombinasikan keunggulan dua jenis penerbangan. Contohnya, UAV jenis ini dapat melakukan lepas landas dan mendarat secara vertikal (VTOL) dan mempertahankan ketinggian di udara dengan rotor sekaligus terbang dengan kecepatan tinggi dan menempuh perjalanan jarak jauh dengan membentuk gaya angkat dengan _fixed wing_ [(Lee, Kim, & Chu, 2021)](https://doi.org/10.1007/s12541-021-00489-y).
 ![Gambar Penerbangan Hybrid](../lampiran/gambar-penerbangan-hybrid.png)

b. Menurut [Desa (2014)](https://www.academia.edu/21293217/Yaw_Pitch_and_Roll_controller_design_for_fixed_wing_UAV_under_uncertainty_and_perturbed_condition), _pitch angle_ ($\theta$) adalah sumbu yang melewati pesawat dari ujung sayap sampai ujung sayap lainnya. Pergerakan yang memanjang di sekitar sumbu tersebut disebut _pitch_. _Pitch angle_ digunakan untuk mengubah arah vertikal UAV _fixed-wing_ yang dapat dikontrol dengan pergerakan elevator (dalam kata lain, apakah kerucut hidung pesawat sedang menghadap ke atas atau bawah). Sementara itu, _roll angle_ adalah sumbu yang melewati pesawat dari ujung kerucut hidung pesawat hingga ekor pesawat. Pergerakan yang melintang sepanjang sumbu tersebut disebut dengan pergerakan _roll_. Gerakan memutar tersebut disebabkan oleh pembelokan aileron pesawat. Terakhir, _yaw angle_ adalah sumbu yang menembus ruang antara pesawat dari atas sampai bawah. Pergerakan vertikal sepanjang sumbu tersebut disebut dengan _yaw_.

![Ilustrasi Sumbu Pitch, Roll, dan Yaw](../lampiran/UAV-attributes-Roll-Pitch-Yaw-with-coordinate-description.png)  
Sumber gambar: https://www.researchgate.net/publication/357930432_Deep_Reinforcement_Learning_Based_Unmanned_Aerial_Vehicle_UAV_Control_Using_3D_Hand_Gestures

Menurut [NASA (2021)](https://www.grc.nasa.gov/www/k-12/airplane/move.html), _ground speed_ 'kecepatan di tanah' adalah kecepatan relatif suatu kendaraan terbang dengan sudut pandang referensi dari tanah. Sementara itu, _airspeed_ 'kecepatan di udara' merupakan kecepatan relatif suatu kendaraan terbang dengan sudut pandang referensi dari tanah. _Airspeed_ tidak dapat dihitung dari posisi tanah, tetapi harus dengan _ground speed_ dan _wind speed_ 'kecepatan angin'. _Airspeed_ adalah selisih antara vektor _ground speed_ dan _wind speed_.

_Airspeed_ = _Ground speed_ - _Windspeed_

Dalam keadaan ideal ketika angin tidak bertiup (_windspeed_ = 0), besar _airspeed_ dan _ground speed_ sama. Apabila angin bertiup searah dengan arah gerak kendaraan terbang (seperti UAV), besar _airspeed_ akan lebih kecil daripada _ground speed_.

Menurut [Lerus Training (2024)](https://www.lerus.com/articles/hdop-horizontal-dilution-of-precision-in-gps-and-dgps-systems.html), HDOP adalah indikator utama pengukuran keberhasilan yang digunakan untuk menilai akurasi sistem GPS atau DGPS. HDOP akan merefleksikan dampak geometris satelit terhadap akurasi posisi horizontal GPS _receiver_. Makin kecil HDOP, makin baik pula akurasinya. HDOP yang rendah terjadi ketika satelit terdistribusi dengan rata di langit sehingga kekuatan triangulasi (pengukuran) lebih kuat, sementara HDOP yang tinggi terjadi ketika satelit berkumpul di satu area sehingga akurasi posisi menjadi lebih lemah. HDOP 1-2 menunjukkan akurasi yang sangat baik sehingga cocok untuk operasi kritis, 2-5 menunjukkan akurasi yang cukup baik sehingga cukup untuk kebanyakan tugas di sekitar pantai, angka di atas 5 menunjukkan akurasi yang buruk sehingga membutuhkan sistem alternatif. Akurasi GPS akan berguna untuk menentukan apakah tempat tersebut cukup layak untuk menerbangkan UAV atau tidak.

Sementara itu, berdasarkan jurnal dari [Khan et al. (2021)](https://scispace.com/pdf/rssi-controlled-long-range-communication-in-secured-iot-2kn3bqmmzw.pdf), RSSI (_Received Signal Strength Identifier_) atau biasa juga dikenal sebagai pengukuran kekuatan sinyal yang diterima adalah teknik untuk mengalkulasi jarak antara dua UAV atau _node_ nirkabel. Kekuatan sinyal akan bervariasi bergantung pada perubahan jarak _node_. RSSI dapat digunakan untuk proses lokalisasi (menghitung jarak antar-_node_).

c. 

d. Publikasi ilmiah: https://doi.org/10.3390/en15010217
 Publikasi ilmiah ini terbagi menjadi enam bagian, yakni pengenalan, agrikultur presisi, tipe-tipe UAV, peran UAV dalam manajemen hama presisi, manfaat ekonomi dari teknologi UAV, serta kesimpulan.

#### 6. Algoritma
a. 

Sementara itu, menurut [Stentz (1994)](https://web.mit.edu/16.412j/www/html/papers/original_dstar_icra94.pdf), nama algoritma D* dipilih karena mirip dengan A*, tetapi D* cenderung dinamis; _arc cost parameters_ (hambatan) dapat berubah selama proses penyelesaian masalah. Apabila pergerakan robot terhubung dengan benar dengan algoritma, D* menghasilkan lintasan yang optimal. Tujuan _path planner_ adalah mencapai lokasi yang dituju dengan menghindari alangan serta meminimalisasi "pengeluaran" metrik (misalnya panjang lajur). D* menggunakan _backpointer_ untuk merepresentasikan lajur-lajur yang memungkinkan untuk mencapai tujuan. D* membuat _list_ OPEN yang digunakan untuk menyebarkan informasi terkait perubahan hambatan lajur dan menghitung hambatan setiap lajur di tahap tertentu. Setiap kemungkinan lajur akan disebut NEW jika belum pernah ditaruh di _list_ OPEN, OPEN jika berada di _list_ OPEN, dan CLOSED jika sudah tidak berada di _list_ OPEN. Setiap kali terdapat perubahan, D* mendeteksinya dan membagi setiap anggotanya menjadi dua tipe: RAISE dan LOWER. RAISE untuk anggota yang mengalami kenaikan "pengeluaran", serta LOWER untuk anggota yang mengalami penurunan "pengeluaran". Ini memungkinkan D* untuk terus memperbarui anggota dalam _list_ OPEN. Setelah diperbarui, perubahan tersebut akan dilanjutkan (untuk diperiksa) ke lajur terdekat dan seterusnya.

Berikut ini contoh penggunaan algoritma D*
* Mengoptimalisasi navigasi swatantra UAV [(Suanpang & Jamjuntr, 2024)](https://doi.org/10.3390/su16177867) 
* Mengoptimalisasi pemilihan lajur UAV dalam lingkungan yang berbeda-beda [(Wang, Wang, & Yang, 2024)](https://doi.org/10.1117/12.3027181)
* _Path planning_ robot dengan dua sambungan lengan dalam lingkungan dinamis [(Raheem & Hameed, 2019)](https://doi.org/10.22153/kej.2019.01.004)

b. Menurut [Chen (2024)](https://doi.org/10.54097/6q4xxg69), PID (_proportional-integral-derivatives_) adalah mekanisme kontrol timbal balik yang didasarkan pada tiga komponen esensial tersebut (proporsional, integral, derivatif). Teknik kontrol ini esensial untuk menyelesaikan permasalahan dinamis dalam konteks sistem _engineering_ karena simplisitas, fleksibilitas, dan efektivitasnya. Kontrol PID merupakan teknik automasi industrial yang lumrah digunakan dalam proses manufaktur, produksi, dan aplikasi industri lainnya. Teknik kontrol PID paling sesuai digunakan ketika terdapat kekurangan pemahaman komprehensif tentang sistem dan objek yang akan digunakan atau ketika parameterisasi akurat tidak dapat diperolah dengan cara yang sistematis. Pengontrol PID merupakan pengontrol bertipe linear yang menghasilkan keluaran kontrol berupa defleksi dasar antara himpunan nilai dan hasil praktis. Hal yang membentuk sistem kontrol PID adalah kombinasi linear antara komponen proporsional, integral, dan derivatif. Representasi matematis pengontrol PID adalah sebagai berikut.

$$
  u_{(t)} = K_p \times e_{(t)} + K_i \times \int_{0}^{t} e_{(t)} dt + K_d \times \frac{de_{(t)}}{dt}
$$

dengan $u(t)$ sebagai keluaran pengontrol, $e(t)$ sebagai kesalahan saat ini, dan $K_p$, $K_i$, dan $K_d$ secara berurutan adalah setelan parameter proporsional, integral, dan derivatif. 

Aplikasi kontrol PID dalam berbagai bidang adalah sebagai berikut.
* Industri manufaktur: Aplikasi dalam suhu, aliran, tekanan, kelajuan, tingkat cairan, kualitas, pencampuran gas, dan posisi mekanikal.
* Industri kimia: Secara tepat meregulasi suhu, tekanan, dan aliran. Optimisasi ini dapat meningkatkan efisiensi reaksi, meningkatkan kualitas produk, serta menjaga sistem tetap stabil dan berfungsi.
* Sistem listrik: Menjaga stabilitas keluaran voltase, meregulasi frekuensi untuk menjaga frekuensi sistem tetap berada dalam rentang yang benar, meningkatkan efisiensi sistem, serta menjaga stabilitas sistem dalam berbagai variasi beban [(Chen, 2024)](https://doi.org/10.54097/6q4xxg69).

c. Berdasarkan tulisan [Welch dan Bishop (2002)](https://www.mit.edu/course/16/16.070/www/project/PF_kalman_intro.pdf), Filter Kalman adalah himpunan persamaan matematika yang menyediakan solusi komputasional (rekursif) yang efisien dari metode kuadrat terkecil. Filter ini sangat berguna dalam beberapa aspek karena dapat mengestimasi keadaan pada masa lalu, kini, dan masa depan. Bahkan, filter Kaman dapat digunakan meskipun aspek alamiah sebuah sistem tidak diketahui secara pasti. 

###
---

### Referensi
* [Git Documentation](https://git-scm.com/docs/git#_git_commands)
* [Ardupilot Documentation](https://ardupilot.org/planner/docs/mission-planner-features.html)

### Daftar Pustaka

