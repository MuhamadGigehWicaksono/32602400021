# 📘 Tugas 1 Pemrograman Berorientasi Object
### Meliputi materi :
1. **Class dan Object (Pertemuan 2)**
2. **Encapsulation (Pertemuan 3)**
3. **Constructor (Pertemuan 4)**


---

## 💻 Analisa Kode Berikut

### Kode `MakhlukHidup.java` dan `TestAccess.java` versi `ERROR`
><div style="color: blue">
><strong>Tugas:<br/>
>1. Temukan, jelaskan, dan perbaiki setiap error berkaitan dengan materi pada MakhlukHidup.java dan TestAccess.java. Ada 10+ kesalahan. Setiap kesalahan memiliki skor (lihat pada tabel skor). Skor minimal LULUS = 60.
><br/>
>2. Tuliskan output dari TestAccess jika kode sudah diperbaiki
></strong>
</div>

```java

public class MakhlukHidup {

    private string nama;       
    private String jenis;
    public double berat = -1.0;  
    private int umur;


    public MakhlukHidup() {
        this.nama = "Unknown";
        this.jenis = "Unknown";
        this.umur = 15;
        this.berat = 10.0;
    }

    public void MakhlukHidup(String nama) { 
        this.nama = nama;
        this.jenis = "Salah";
        this.umur = 12;
        this.berat = 170.0;
    }

    public makhlukHidup(String nama, String jenis, int umur, double berat) { 
        this.nama = jenis;  
        this.jenis = nama; 
        this.umur = umur;
        this.berat = berat;
    }

    public MakhlukHidup(MakhlukHidup other) {
        this.nama = nama; 
        this.jenis = other.jenis; 
        this.umur = this.umur; 
        this.berat = other.berat;
    }


    public void setUmur(String umur) { 
        this.umur = umur;
    }

    public void setNama(String nama) {
        nama = this.nama; 
    }

    public int getInfo() { 
        return "Nama=" + nama + ", Jenis=" + jenis 
        + ", Umur=" + umur + ", Berat=" + berat;
    }
}

```

```java
class TestAccess {
    public static void main(String[] args) {
        MakhlukHidup m = new MakhlukHidup();
        
        m.nama = "Kucing";  
        
        MakhlukHidup m2 = new MakhlukHidup("Harimau", "Hewan", 3, 120.0);
        
        MakhlukHidup m3 = new MakhlukHidup(m2);
 
        System.out.println(m.getInfo());
        
        System.out.println(m2.getInfo());
        
        m2.MakhlukHidup("Kuda"); 
                
        System.out.println(m2.getInfo());
        
        m3.setUmur(-10); 
        
        System.out.println(m3.getInfo());

        
    }
}
```


## Table Score
| No | Error | Materi terkait            | Skor |
|----|-------|---------------------------|------|
| 1  | ERR1  | Class & Object (syntax)   | 10   |
| 2  | ERR2  | Class & Object (type)     | 10   |
| 3  | ERR3  | Constructor/init          | 10   |
| 4  | ERR4  | Encapsulation / Setter    | 10   |
| 5  | ERR5  | Constructor (copy)        | 10   |
| 6  | ERR6  | Constructor (copy)        | 10   |
| 7  | ERR7  | Encapsulation / Setter    | 10   |
| 8  | ERR8  | Class & Object (type)     | 10   |
| 9  | ERR9  | Class & Object (type)     | 10   |
| 10 | ERR10 | Encapsulation / Validation| 10   |
**Total skor : 100**

## Petunjuk Pengerjaan

Temukan semua ERR#, jelaskan kenapa salah dalam bentuk table dengan kolom berikut, selanjutnya tulis kode perbaikannya.

| No | Class        | Kesalahan | Perbaikan |
|----|--------------|-----------|-----------|
| 1 | MakhlukHidup | [contoh] variable `jumlah` salah penulisan akses `publik` | seharusnya `public jumlah = 10`|

2. Kompilasi dan jalankan setelah diperbaiki.
3. Upload kode pada **Github** repository anda dan **upload link nya ke dalam sinau** di topik **Tugas 1 PBO** disertai **file penjelasannya** dalam format word atau markdown

> Peringatan : Penggunaan AI tidak menjamin jawaban anda semuanya benar



##   JAWABAN
## 📋TABEL CLASS MAKHLUKHIDUP DARI SOURCE CODE MakhlukHidup.java

| No  | Class        | Kode Error | Penyebab Salah                                                      | Perbaikan Benar                                    |
|-----|--------------|------------|---------------------------------------------------------------------|----------------------------------------------------|
| 1   | MakhlukHidup | ERR6       | Di copy constructor: this.umur = this.umur; (ngambil dirinya sendiri) | Harusnya this.umur = other.umur;                 |
| 2   | MakhlukHidup | ERR1       | string huruf kecil (Java peka huruf besar-kecil)                   | Ganti pakai String (S besar)                     |
| 3  | MakhlukHidup | ERR7       | Setter nama kebalik: nama = this.nama;                            | Harusnya this.nama = nama;                       |
| 4   | MakhlukHidup | ERR3       | Constructor ditulis public void MakhlukHidup(...) ada void       | Constructor nggak boleh pakai void               |
| 5  | MakhlukHidup | ERR10      | Getter info return type int, padahal balikin teks (String)         | Ubah ke public String getInfo()                  |
| 6   | MakhlukHidup | ERR8       | Constructor ditulis public makhlukHidup(...) huruf M kecil         | Harus sama persis dengan nama class → MakhlukHidup|
| 7  | MakhlukHidup | ERR9       | Setter umur: tipe parameter beda (String vs int)                    | Ganti jadi setUmur(int umur) dan assign ke this.umur |
| 8  | MakhlukHidup | ERR10      | Getter info balikin String tapi dideklarasi int                   | Harus deklarasi return String                    |
| 9   | MakhlukHidup | ERR2       | public double berat = -1.0; default negatif (kurang masuk akal)   | Lebih aman pakai 0.0                             |
| 10   | MakhlukHidup | ERR4       | Di constructor ke-2: this.nama = jenis; kebalik                   | Harusnya this.nama = nama;                       |
| 11   | MakhlukHidup | ERR7       | Di constructor ke-2: this.jenis = nama; kebalik                   | Harusnya this.jenis = jenis;                     |
| 12   | MakhlukHidup | ERR9       | Setter umur pakai String umur padahal harus angka                 | Harusnya setUmur(int umur)                       |
| 13   | MakhlukHidup | ERR5       | Copy constructor: this.nama = nama; salah ambil                   | Harusnya this.nama = other.nama;                 |


###  💻SOURCE CODE MakhlukHidup.java YANG SUDAH DIPERBAIKI

java
public class MakhlukHidup {

    // Atribut
    private String nama;
    private String jenis;
    private int umur;
    private double berat;

    // 1. Default Constructor
    public MakhlukHidup() {
        this.nama = "kucing";
        this.jenis = "persia";
        this.umur = 0;
        this.berat = 0.0;
        System.out.println("[Default Constructor] Objek MakhlukHidup dibuat.");
    }

    // 2. Parameterized Constructor
    public MakhlukHidup(String nama, String jenis, int umur, double berat) {
        this.nama = nama;
        this.jenis = jenis;
        this.umur = umur;
        this.berat = berat;
        System.out.println("[Parameterized Constructor] Objek MakhlukHidup dibuat.");
    }

    // 3. Copy Constructor
    public MakhlukHidup(MakhlukHidup other) {
        this.nama = other.nama;
        this.jenis = other.jenis;
        this.umur = other.umur;
        this.berat = other.berat;
        System.out.println("[Copy Constructor] Objek MakhlukHidup disalin.");
    }

    // Setter
    public void setNama(String nama) {
        this.nama = nama;
    }

    public void setJenis(String jenis) {
        this.jenis = jenis;
    }

    public void setUmur(int umur) {
        this.umur = umur;
    }

    public void setBerat(double berat) {
        this.berat = berat;
    }

    // Getter
    public String getNama() {
        return nama;
    }

    public String getJenis() {
        return jenis;
    }

    public int getUmur() {
        return umur;
    }

    public double getBerat() {
        return berat;
    }

    public String getInfo() {
        return "Nama: " + nama + ", Jenis: " + jenis + ", Umur: " + umur + ", Berat: " + berat;
    }

    // Method 
    public void makan() {
        System.out.println(nama + " sedang makan.");
    }

    public void bergerak() {
        System.out.println(nama + " sedang bergerak.");
    }

    @Override
    public String toString() {
        return "MakhlukHidup {nama='" + nama + "', jenis='" + jenis + "', umur=" + umur + ", berat=" + berat + "}";
    }

}


class Main {
    public static void main(String[] args) {

        // Default constructor
        MakhlukHidup m1 = new MakhlukHidup();
        System.out.println(m1);

        // Parameterized constructor
        MakhlukHidup m2 = new MakhlukHidup("Anjing", "Bulldog", 3, 12.5);
        System.out.println(m2);

        // Copy constructor
        MakhlukHidup m3 = new MakhlukHidup(m2);
        System.out.println(m3);

        // Coba setter & getter
        m1.setNama("Kelinci");
        m1.setJenis("kelinci polandia");
        m1.setUmur(2);
        m1.setBerat(3.4);

        System.out.println("Nama: " + m1.getNama());
        System.out.println("Jenis: " + m1.getJenis());
        System.out.println("Umur: " + m1.getUmur());
        System.out.println("Berat: " + m1.getBerat());
        System.out.println("Info: " + m1.getInfo());

        // Tes method lain
        m1.makan();
        m1.bergerak();
    }
}



### 📋OUTPUT CODE MakhlukHidup.java

```
[Default Constructor] Objek MakhlukHidup dibuat.
MakhlukHidup {nama='kucing', jenis='persia', umur=0, berat=0.0}
[Parameterized Constructor] Objek MakhlukHidup dibuat.
MakhlukHidup {nama='Anjing', jenis='Bulldog', umur=3, berat=12.5}
[Copy Constructor] Objek MakhlukHidup disalin.
MakhlukHidup {nama='Anjing', jenis='Bulldog', umur=3, berat=12.5}
Nama: Kelinci
Jenis: kelinci polandia
Umur: 2
Berat: 3.4
Info: Nama: Kelinci, Jenis: kelinci polandia, Umur: 2, Berat: 3.4
Kelinci sedang makan.

```
### 📋Tabel Class TestAccess.java

| No  | Class        | Kode Error | Penyebab Salah                                                      | Perbaikan Benar                                    |
|-----|--------------|------------|---------------------------------------------------------------------|----------------------------------------------------|
| 1   | TestAccess | ERR11       | Mengakses atribut nama secara langsung padahal private | Gunakan Setter m.setNama("Kucing");                 |
| 2   | TestAccess | ERR12       | Memanggil constructor seperti method: m2.MakhlukHidup("Kuda");                   | Buat objek baru dengan constructor: m2=newMakhlukHidup("Kuda");                   |

### 💻SOURCE CODE Class TestAcces.java yang sudah diperbaiki
```
class TestAccess {
    public static void main(String[] args) {
        MakhlukHidup m = new MakhlukHidup();
        m.setNama("Kucing");  

        MakhlukHidup m2 = new MakhlukHidup("Harimau", "Hewan", 3, 120.0);
        MakhlukHidup m3 = new MakhlukHidup(m2);
 
        System.out.println(m.getInfo());
        System.out.println(m2.getInfo());
        
        m2 = new MakhlukHidup("Kuda");  
        System.out.println(m2.getInfo());
        
        m3.setUmur(-10);  
        System.out.println(m3.getInfo());
    }
}
```
### 📋OUTPUT CODE TestAcces.java

```
