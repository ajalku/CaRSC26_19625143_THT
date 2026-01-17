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
 * **Setup**: _Section_ ini memperbolehkan pengguna mempersiapkan dan mengonfigurasi autopilot untuk kendaraan spesifik. Kebanyakan _subsections_ memberikan informasi terkait hal-hal yang perlu dilakukan sebelum penerbangan pertama. Di sini, terdapat instalasi Firmware, perangkat keras yang diperlukan, perangkat keras yang opsional, dan tahapan yang harus dilakukan sebelum menerbangkan UAV.\
 * **Simulation**: Simulation menyediakan simulasi SITL (Software in the Loop) yang memperbolehkan pengguna menjalankan UAV tanpa perangkat keras. Dalam _section_ ini, pengguna dapat melihat bagaimana UAV akan diterbangkan sebelum penerbangan dilakukan sehingga meminimalisasi kerusakan riil fisik UAV.

 c. Misi pemetaan sederhana persegi panjang 80x100
  [Fail misi sederhana](../lampiran/misi-pemetaan-sederhana-80x100.waypoints)
  ![Tangkapan layar misi sederhana (untuk _error prevention_)](../lampiran/tangkapan-layar-misi-pemetaan-sederhana.png)