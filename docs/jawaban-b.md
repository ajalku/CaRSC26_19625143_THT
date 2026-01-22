### Jawaban Bagian B

#### Dasar Pemrograman

1. OOP

i. Menurut [GeeksforGeeks (2025)](https://www.geeksforgeeks.org/cpp/object-oriented-programming-in-cpp/) dan [W3School (n.d.)](https://www.w3schools.com/cpp/cpp_classes.asp), berikut ini konsep-konsep dasar dalam OOP pada C++
* **_Class_**: _Blue-print_ (semacam _template_) yang menjadi acuan penciptaan suatu objek. _Class_ merepresentasikan set properti yang berlaku bagi semua objek bertipe sama. Dengan _class_, kita dapat membuat objek bertipe sama berulang kali tanpa harus menulis kode yang sama lagi dan lagi. Class memiliki komponen _Access Specifier_ (mengontrol aksesibilitas), _Class Name_ (nama kelas), dan _Body_ (berisi data anggotanya). Berikut contohnya dalam C++ (membuat kelas Nilai).

```shell
class Nilai {
    public:
        int Matematika;
        int Sejarah;
        int BahasaPrancis;
};
```

* **_Object_**: Bagian dasar OOP yang merepresentasikan sesuatu yang nyata. Dalam C++, program biasanya mengandung banyak _object_ yang saling berinteraksi. _Object_ adalah hal yang ditampilkan dan terlihat oleh pengguna. _Object_ terdiri atas _States_ (direpresentasikan oleh atribut dan properti sebuah objek), _Member Function_ (kumpulan _statements_ yang menampilkan tugas-tugas tertentu dan dapat mengembalikan hasil), _Behavior_ (direpresentasikan oleh _member function_; bagaimana sebuah objek merespons objek lainnya), dan _Identity_ (nama unik atau referensi agar ia dapat berinteraksi dengan objek lain). Contoh objek adalah sebagai berikut (dengan nama Anton).

```shell
#include <iostream>
#include <string>
using namespace std;

class Nilai{
    public:
        int Matematika;
        int Sejarah;
        int BahasaPrancis;
};

int main() {
    Nilai Anton;
    
    Anton.Matematika = 95;
    Anton.Sejarah = 98;
    Anton.BahasaPrancis = 85;
    
    cout << Anton.Matematika << "\n";
    cout << Anton.Sejarah << "\n";
    cout << Anton.BahasaPrancis;
    
    return 0;
}
```
* **_Abstraction_**: Proses menyembunyikan detail implementasi dan hanya menunjukkan bagian dan fitur penting kepada pengguna. Dalam C++, contohnya adalah _abstract class_ (memiliki fungsi virtual dan tidak bisa digunakan langsung membuat objek; harus dibuat kelas turunan dulu).

```shell
#include <iostream>
using namespace std;

class Peliharaan { // abstract class
public:
    virtual void peluk() = 0;
    virtual void pukpuk() = 0;
    void bermain() {
        cout << "Peliharaan suka bermain!" << endl;
    }
};

class Kucing : public Peliharaan {
    void peluk() override{
        cout << "Kucing tidak suka dipeluk!" << endl;
    }
    
    void pukpuk() override {
        cout << "Kucing suka dipukpuk!" << endl;
    }
};

int main()
{
    Peliharaan* Catty = new Kucing;
    Catty->bermain();
    Catty->peluk();
    Catty->pukpuk();
    
    delete Catty;
    return 0;
}
```

* **_Encapsulation_**: Proses "mengemas" data dan metode menjadi satu unit, biasanya sebuah _class_. Dapat melindungi data dari pengaksesan kode di luar kelas tersebut. _Encapsulation_ dapat dilakukan dengan mendeklarasikan seluruh variabel dalam kelas menjadi _private_, kemudian membuat metode publik untuk mengeset dan mendapatkan (_set and get_) nilai variabel tersebut. Berikut ini contohnya dalam C++

```shell
#include <iostream>
#include <string>
using namespace std;

class Makanan {
    
private:
    int harga;
    string nama;

public:

    // metode setter
    void setHarga(int harga) {
        this->harga = harga;
    }

    void setNama(string nama) {
        this->nama = nama;
    }

    // metode getter
    int getHarga() {
        return harga;
    }
    string getNama() {
        return nama;
    }
};

int main() {
    Makanan rendang;

    rendang.setHarga(100000);
    rendang.setNama("Rendang");

    cout << "Nama makanan: " << rendang.getNama() << endl;
    cout << "Harga makanan: Rp" << rendang.getHarga() << endl;

    return 0;
}
```

* **_Inherintance_**: Mekanisme yang memungkinkan sebuah kelas "mewarisi" fitur kelas lain. Diketahui sebagai hubungan "adalah", misal "Rendang adalah makanan". Berikut ini contohnya dalam C++.

```shell
#include <iostream>
using namespace std;

class Makanan { // pewaris (ngasih warisan)
public:
    void fungsi() {
        cout << "Fungsi makanan adalah memberi energi." << endl;
    }
    void caraDapat() {
        cout << "Cara mendapatkan makanan adalah memasak atau membeli." << endl;
    }
};

class Rendang : public Makanan { // ahli waris
public:
    void nama() {
        cout << "Salah satu nama makanan adalah rendang." << endl;
    }
};
int main() {
    Rendang rendangWarungSaya;

    // yang diwarisi dari kelas Makanan
    rendangWarungSaya.fungsi();
    rendangWarungSaya.caraDapat();

    // yang dari kelas Rendang
    rendangWarungSaya.nama();

    return 0;
}
```

* **_Polymorphism_**: _Poly_ (banyak) dan _morph_ (bentuk), maknanya sebuah entitas bisa memiliki banyak bentuk. Dalam C++, _polymorphism_ memungkinkan metode atau objek yang sama berperilaku berbeda sesuai konteks. Terdapat dua jenis, yakni _overloading_ (_compile-time_, dua atau lebih fungsi dalam kelas yang sama memiliki nama yang sama, tetapi memiliki _list_ parameter yang berbeda; _return_-nya bisa sama atau berbeda) dan overriding (_run-time_, terjadi ketika fungsi dalam kelas ahli waris memiliki nama, _return type_, dan parameter yang sama sebagai fungsi di kelas pewaris; didapatkan dengan fungsi _virtual_). Contoh dalam C++ adalah sebagai berikut.

```shell
#include <iostream>
using namespace std;

class Peliharaan { // pewaris
public:

    // metode overloaded
    void harga() {
        cout << "Peliharaan memiliki harga." << endl;
    }

    // metode overloaded 
    virtual void harga(int jumlah) {   
        cout << "Harga pasar peliharaan di toko: Rp" << jumlah << endl;
    }
};

class Kucing : public Peliharaan { // ahli waris
public:

    // override harga(int jumlah)
    void harga(int jumlah) override {
        cout << "Harga kucing di toko: Rp" << jumlah << endl;
    }
};

int main() {
    Peliharaan peliharaanSaya;
    Kucing kucingSaya;
    Peliharaan* kucingTeman = new Kucing();  

    // overloading
    peliharaanSaya.harga();        
    peliharaanSaya.harga(1000000);     

    // overriding
    kucingSaya.harga(2000000);      

    // polymorphism
    kucingTeman->harga(2500000);  

    delete kucingTeman;  
    return 0;
}
```

2. Bahasa C++

i. Menurut [Lafore (2002)](https://docs.google.com/file/d/0B21HoBq6u9TsUHhqS3JIUmFuamc/view?resourcekey=0-MYlet9RIjEukd6CvLEHUbw) perbedaan <code>include <file_name></code> dan <code>#include "file_name"</code>
adalah <code>#include <file_name></code> mengandung tanda kurung bersudut < dan >, mengindikasikan bahwa _compiler_ harus mencari _file_ tersebut di _standard_ <code>#include</code> _directory_. _Directory_ ini menyediakan _file-file header_ yang memang sudah ada dari manufaktur _compiler_ untuk sistem (dipakai untuk mengakses _file_ yang sudah disediakan). Sementara itu, <code>#include "file_name"</code> yang mengandung tanda kutip dua ("...") mengindikasikan instruksi kepada _compiler_ untuk mencari _header file_ dalam _directory_ yang sedang ditempati, biasanya _directory_ yang mengandung _file_ asal. Biasanya, <code>#include <file_name></code> digunakan untuk _header file_ yang dibuat oleh kita sendiri. Kedua cara akan bekerja dalam keadaan mana saja, tetapi menggunakan cara yang sesuai akan mempercepat proses _compilation_ karena memberi _"hint"_ kepada _compiler_ tentang di mana harus menemukan _header file_ tersebut.

ii. Dalam [GeeksforGeeks (2025)](https://www.geeksforgeeks.org/cpp/cpp-preprocessor-directives-set-2/), <code>ifdef</code> "if defined" digunakan untuk memastikan apakah sebuah _macro_ sudah ada/sudah dibuat (_macro_ dibuat dengan <code>define</code>); "jika ada, jalankan tugas ini". Sementara itu, <code>ifndef</code> digunakan untuk memastikan apakah sebuah _macro_ tidak ada/tidak dibuat; "jika tidak ada, jalankan tugas ini". <code>endif</code> digunakan untuk mengakhiri "tugas" yang diberikan dalam <code>ifdef</code> dan <code>ifndef</code>. Terakhir, <code>pragma once</code> digunakan untuk memastikan _header files_ hanya di-_include_ sekali.

iii. Dalam [GeeksforGeeks (2025)](https://www.geeksforgeeks.org/cpp/namespace-in-c/), _namespace_ adalah sebuah wadah yang menyimpan grup nama-nama--seperti variabel, fungsi, atau _class_--untuk menghindari _error_ apabila terdapat nama sama yang digunakan dalam bagian berbeda dalam sebuah program. Jika ada _namespace_ bernama <code>ruang1</code> dan <code>ruang2</code> dan keduanya memiliki fungsi <code>greet()</code>, cara memanggil fungsi tersebut tanpa tertukar adalah dengan menggunakan _scope resolution operator_ (<code>::</code>). Jadi, cara pemanggilannya adalah <code>ruang1::greet()</code> atau <code>ruang2::greet()</code>.

iv. Dalam [GeeksforGeeks (2025)](https://www.geeksforgeeks.org/c/c-define-preprocessor/), <code>#define</code> adalah _preprocessor directive_ yang digunakan untuk mendefinisikan _macro_. _Macro_ adalah _identifier_ yang didefinisikan oleh #define yang diganti dengan nilai di dalamnya sebelum melakukan _compilation_. Kita dapat mendefinisikan kontanta dan fungsi seperti _macro_ menggunakan #define. Cara menulis sintaksnya adalah <code>#define NAMA_MACRO nilai</code> atau <code>#define NAMA_MACRO (ekspresi dalam tanda kurung)</code> atau <code>#define NAMA_MACRO (argumen1, argumen2) (ekspresi dalam tanda kurung)</code>. Sementara itu, menurut [GeeksforGeeks (2025)](https://www.geeksforgeeks.org/cpp/using-keyword-in-cpp-stl/), <code>using</code> digunakan untuk menspesifikasikan penggunaan _namespace_ tertentu. Contoh penggunaannya adalah <code>using namespace std</code>; biasanya, untuk menggunakan <code>cout</code>, perlu menulisnya dengan cara <code>std::cout</code>. Namun, dengan <code>using namespace std</code> di bawah header, bagian <code>std::</code> dapat dilewati karena kita sudah memberi tahu pada program bahwa kita ingin menggunakan <code>cout</code> pada _namespace_ <code>std</code>.

v. Menurut [GeeksforGeeks (2025)](https://www.geeksforgeeks.org/c/c-pointers/), _pointer_ adalah variabel yang menyimpan _memory address_ variabel lain. Untuk mendeklarasikan _pointer_, digunakan <code>data_type *ptr</code> (ganti data_type dengan tipe data, misal <code>int</code>). Terdapat dua tujuan penggunaan asteris/tanda bintang, yakni (1) untuk mendeklarasikan variabel _pointer_ dan (2) untuk mendapatkan nilai yang disimpan. Misal, sudah dibuat variabel dengan <code>int vari = 5</code>, lalu dibuat pointer dengan cara <code>int *ptr = &vari</code>. Perhatikan bahwa cara mendapatkan _memory address_ adalah dengan menggunakan "&" sebelum nama variabel. Maka, _print_ <code>ptr</code> akan mengeluarkan _memory address_ <code>vari</code>, sementara _print_ <code> *ptr</code> akan mengeluarkan nilai vari, yakni 5. _Print_ dengan * disebut juga dereferensi (mengembalikan nilai variabel, bukan _memory address_).

vi. Dari [Sanfoundry (n.d.)](https://www.sanfoundry.com/pass-by-value-and-pass-by-reference-in-cpp/), terdapat dua cara mengoper data, yakni _pass by value_ dan _pass by reference_. Dalam _pass by value_, data yang dioper ke sebuah fungsi akan dikopi dalam variabel lain. Perubahan data dalam fungsi tersebut tidak memengaruhi data asli. Sementara itu, _pass by reference_ mengoper data dengan cara mengirimkan _address_ yang menyimpan data tersebut ke fungsi sehingga perubahan data dalam fungsi tersebut akan memengaruhi data asli.

Contoh _pass by value_ adalah

```shell
void sebuahFungsi(int variabel){
    variabel = 20;
}

int main(){
    int variabel = 5;
    sebuahFungsi(variabel);
    cout << variabel;
}
```

keluaran yang dihasilkan adalah 5 karena <code>sebuahFungsi()</code> tidak mengubah variabel asli.

Contoh _pass by reference_ adalah

```shell
void sebuahFungsi(int &variabel){
    variabel = 20;
}

int main(){
    int variabel = 5;
    sebuahFungsi(variabel);
    cout << variabel;
}
```

keluaran yang dihasilkan adalah 20 karena <code>sebuahFungsi()</code> mengubah variabel asli.

v. Menurut [GeeksforGeeks (2026)](https://www.geeksforgeeks.org/cpp/auto_ptr-unique_ptr-shared_ptr-weak_ptr-in-cpp/), <code>std::unique_ptr</code> dan <code>std::shared_pointer</code> adalah jenis dari _smart pointer_ yang merupakan objek yang _stack-allocated_ yang dapat meningkatkan performa _pointer_ biasa dan secara otomatis mengatur masa pakai memori yang secara dinamis dialokasikan. <code>unique_ptr</code> adalah sebuah _pointer_ yang memiliki karakteristik kepemilikan eksklusif, tidak bisa disalin, kepemilikan dapat dipindahkan menggunakan <code>std::move()</code>, efisien dan ringan, serta mendukung _custom deleters_ dan _arrays_. Misal kita membuat sintaks

```shell

std::unique_ptr<sebuahFungsi> pointerA(new sebuahFungsi);
std::unique_ptr<sebuahFungsi> pointerB = pointerA;   // ERROR

```

Error tersebut terjadi karena <code>pointerA</code> dipaksa berbagi kepemilikan dengan <code>pointerB</code>. Yang dapat dilakukan apabila tetap ingin mendeklarasikan <code>pointerB</code> adalah memindahkan kepemilikannya, bukan membaginya.

```shell
std::unique_ptr<sebuahFungsi> pointerA(new sebuahFungsi);
std::unique_ptr<sebuahFungsi> pointerB = move(pointerA);
```

Dengan demikian, kepemilikan berpindah, bukan bertambah. Gunakan <code>std::unique_ptr</code> apabila ingin membuat _pointer_ kepada suatu objek yang kepemilikannya akan diambil jika _pointer_ tersebut dihapus.

Sementara itu, <code>shared_ptr</code> mengimplementasikan kepemilikan bersama sambil menghitung berapa _pointer_ yang memilikinya (_reference counting_). Karakteristiknya adalah lebih dari satu _pointer_ dapat memiliki objek bersama, objek akan dihancurkan apabila tidak ada yang memilikinya (_reference counting_ = 0), serta mungkin memakan lebih banyak _resource_ karena menggunakan _reference counting_. _Reference counting_ akan bertambah jika _pointer_ disalin dan berkurang jika _pointer_ dihancurkan. Gunakan <code>std::shared_ptr</code> apabila beberapa pemilik (_pointer_) harus berbagi objek yang sama.






###
---

### Referensi
* [Object Oriented Programming in C++](https://www.geeksforgeeks.org/cpp/object-oriented-programming-in-cpp/)
* [C++ Classes and Objects](https://www.w3schools.com/cpp/cpp_classes.asp)
* [Object-Oriented Programming in C++ (4th Edition)](https://docs.google.com/file/d/0B21HoBq6u9TsUHhqS3JIUmFuamc/view?resourcekey=0-MYlet9RIjEukd6CvLEHUbw)
* [C Preprocessor Directives](https://www.geeksforgeeks.org/cpp/cpp-preprocessor-directives-set-2/)
* [Namespace in C++](https://www.geeksforgeeks.org/cpp/namespace-in-c/)
* [#define in C](https://www.geeksforgeeks.org/c/c-define-preprocessor/)
* [Using Keywords in C++ STL](https://www.geeksforgeeks.org/cpp/using-keyword-in-cpp-stl/)
* [Pointers in C](https://www.geeksforgeeks.org/c/c-pointers/)
* [Pass by Value and Pass by Reference in C++](https://www.sanfoundry.com/pass-by-value-and-pass-by-reference-in-cpp/)
* [auto_ptr vs unique_ptr vs shared_ptr vs weak_ptr in C++](https://www.geeksforgeeks.org/cpp/auto_ptr-unique_ptr-shared_ptr-weak_ptr-in-cpp/)