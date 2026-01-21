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

    // polymorphism (beda cara pendefinisian objek dengan kucingSaya)
    kucingTeman->harga(2500000);  

    delete kucingTeman;  
    return 0;
}
```





###
---

### Referensi
* [Object Oriented Programming in C++](https://www.geeksforgeeks.org/cpp/object-oriented-programming-in-cpp/)
* [C++ Classes and Objects](https://www.w3schools.com/cpp/cpp_classes.asp)