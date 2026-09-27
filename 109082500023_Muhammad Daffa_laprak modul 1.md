# <h1 align="center">Laporan Praktikum Modul 1 - Codeblocks IDE & Pengenalan Bahas C++ (Bagian Pertama)</h1>
<p align="center">Muhammad Daffa Sha'ib Nandana - 109082500023</p>

## Dasar Teori
Visual Studio Code (VS Code) merupakan source-code editor yang
bersifat ringan, open-source, dan cross-platform, yang mendukung
berbagai bahasa pemrograman termasuk C++ melalui ekstensi
tambahan. Editor ini digunakan pada praktikum Struktur Data untuk
menulis kode program, kemudian meng-compile dan menjalankannya
melalui terminal terintegrasi menggunakan compiler g++ (GNU
Compiler Collection untuk C++).
Bahasa C++ merupakan pengembangan dari bahasa C yang
diciptakan oleh Bjarne Stroustrup di AT&T Bell Laboratories pada
awal tahun 1980-an, yang pada mulanya disebut “C with class”
sebelum akhirnya disempurnakan dengan fasilitas pembebanlebihan
operator dan fungsi[2]. Struktur dasar program C++ terdiri dari
header file (misalnya #include <iostream>), deklarasi variabel dan
konstanta, serta fungsi utama main() sebagai titik masuk eksekusi
program.
Untuk berinteraksi dengan pengguna, C++ menyediakan fungsi cout
untuk mencetak (output) data ke layar dan cin untuk menerima
(input) data dari keyboard[2]. Selain itu, C++ juga menyediakan
berbagai jenis operator seperti operator aritmatika, operator
pengerjaan (assignment), operator logika, dan operator kondisional,
serta struktur kendali seperti if, if-else, dan switch untuk
pengambilan keputusan dalam program.



## Unguided 

### 1. Program menerima input dua buah bilangan bertipe float, kemudian memberikan output hasil penjumlahan, pengurangan, perkalian dan pembagian dari dua bilangan tersebut.

#include <iostream>

using namespace std;

int main() {
    float a, b;

    cout << "Masukan bilangan pertama: ";
    cin >> a;
    cout << "masukkan bilangan kedua: ";
    cin >> b;

    cout << "Penjumlahan : " << a + b << endl;
    cout << "Pengurangan : " << a - b << endl;
    cout << "Perkalian   : " << a * b << endl;
    
    if (b != 0) {
        cout << "Pembagian  : " << a / b << endl;
    } else {
        cout << "Pembagian  : Error (tidak bisa dibagi 0)" << endl;
    }

    return 0;
}

##### Output 1
![Screenshot Output Unguided 1_1] (https://github.com/daffaeca-a11y/Struktur-Data/blob/main/input%20soal%201.png)

Program di atas menerima dua buah masukan bilangan bertipe float, kemudian melakukan kalkulasi aritmatika dasar yang meliputi penjumlahan (+), pengurangan (-), perkalian (*), dan pembagian (/). Khusus pada operasi pembagian, program menerapkan struktur kondisi if (b != 0) untuk memvalidasi nilai pembagi agar terhindar dari galat pembagian dengan nol.


### 2. Program menerima masukan angka dan pengeluaran output nilai angka tersebut dalam bentuk tulisan (bilangan bulat positif 0 s.d 100)

#include <iostream>
#include <string>

using namespace std;

int main() {
    int angka;
    string kata[] = {"nol", "satu", "dua", "tiga", "empat", "lima", 
                     "enam", "tujuh", "delapan", "sembilan", "sepuluh", "sebelas"};

    cout << "Input angka: ";
    cin >> angka;

    cout << angka << " : ";

    if (angka < 12) {
        cout << kata[angka];
    } else if (angka < 20) {
        cout << kata[angka - 10] << " belas";
    } else if (angka < 100) {
        cout << kata[angka / 10] << " puluh";
        if (angka % 10 != 0) {
            cout << " " << kata[angka % 10];
        }
    } else if (angka == 100) {
        cout << "seratus";
    } else {
        cout << "Di luar jangkauan";
    }

    cout << endl;
    return 0;
}

##### Output 2
![Screenshot Output Unguided 2_1] (https://github.com/daffaeca-a11y/Struktur-Data/blob/main/input%20soal%202.jpeg)

Program di atas menerima sebuah bilangan bulat antara 0 sampai 100, kemudian mengonversinya ke dalam bentuk tulisan teks menggunakan bantuan larik (array) string bernama kata sebagai basis data angka 0 sampai 11. Struktur percabangan if-else digunakan untuk memetakan rentang nilai, mencetak langsung dari larik untuk angka < 12, menambahkan akhiran "belas" untuk rentang belasan, serta memanfaatkan operasi pembagian bulat (/ 10) dan modulus (% 10) untuk memisahkan sebutan puluhan dan satuan pada bilangan 20 sampai 99

### 3. (Program dapat memberikan input dan output pola mirror)

#include <iostream>

using namespace std;

int main() {
    int n;

    cout << "input: ";
    cin >> n;

    cout << "output:" << endl;
    for (int i = n; i >= 0; i--) {
        for (int s = 0; s < (n - i); s++) {
            cout << "  ";
        }

        for (int j = i; j >= 1; j--) {
            cout << j << " ";
        }

        cout << "*";

        for (int j = 1; j <= i; j++) {
            cout << " " << j;
        }

        cout << endl;
    }

    return 0;
}

##### Output 3
![Screenshot Output Unguided 3_1](https://github.com/daffaeca-a11y/Struktur-Data/blob/main/input%20soal%203.jpeg)

Program di atas menerima masukan nilai n, kemudian membentuk pola simetris (mirror) terbalik menggunakan perulangan bersarang (nested loop) for yang berjalan mundur dari n hingga 0. Pada setiap iterasi baris, program mengeksekusi tiga sub-loop: mencetak spasi di awal untuk indentasi piramida, mencetak deret angka menurun dari i ke 1, menaruh karakter * tepat di tengah sebagai poros cermin, lalu diakhiri dengan mencetak deret angka menaik dari 1 ke i.

## Kesimpulan
Kesimpulan dari modul kali ini adalah program itu tidak asal jalan tetapi juga membutuhkan logika yang rapi dan aman dari error, pentingnya memberi validasi seperti pengecekan pembagi nol agar program tidak crash saat di run, lalu konversi angka ke teks menunjukan bahwa pemanfaatan array yang digabung dengan operasi modulus dan pembagian bulat jauh lebih ringkas dan enak dibaca daripada harus menuliskan puluhan kondisi if-else.

## Referensi
[1] Triase. (2020). Diktat Edisi Revisi : STRUKTUR DATA. Medan: UNIVERSTAS ISLAM NEGERI SUMATERA UTARA MEDAN. 
<br>[2] Indahyati, Uce., Rahmawati Yunianita. (2020). "BUKU AJAR ALGORITMA DAN PEMROGRAMAN DALAM BAHASA C++". Sidoarjo: Umsida Press. Diakses pada 10 Maret 2024 melalui https://doi.org/10.21070/2020/978-623-6833-67-4.

