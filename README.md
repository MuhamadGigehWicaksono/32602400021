# Muhamad GIGEH WICAKSONO
# 32602400021

# 📘 Tugas 1 Pemrograman Berorientasi Object
### Meliputi materi :
1. Class dan Object (Pertemuan 2)
2. Encapsulation (Pertemuan 3)
3. Constructor (Pertemuan 4)


---

## 💻 Analisa Kode Berikut

### Kode MakhlukHidup.java dan TestAccess.java versi ERROR
><div style="color: blue">
><strong>Tugas:<br/>
>1. Temukan, jelaskan, dan perbaiki setiap error berkaitan dengan materi pada MakhlukHidup.java dan TestAccess.java. Ada 10+ kesalahan. Setiap kesalahan memiliki skor (lihat pada tabel skor). Skor minimal LULUS = 60.
><br/>
>2. Tuliskan output dari TestAccess jika kode sudah diperbaiki
></strong>
</div>

java

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



java
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
Total skor : 100

## Petunjuk Pengerjaan

Temukan semua ERR#, jelaskan kenapa salah dalam bentuk table dengan kolom berikut, selanjutnya tulis kode perbaikannya.

| No | Class        | Kesalahan | Perbaikan |
|----|--------------|-----------|-----------|
| 1 | MakhlukHidup | [contoh] variable jumlah salah penulisan akses publik | seharusnya public jumlah = 10|

2. Kompilasi dan jalankan setelah diperbaiki.
3. Upload kode pada Github repository anda dan upload link nya ke dalam sinau di topik Tugas 1 PBO disertai file penjelasannya dalam format word atau markdown

> Peringatan : Penggunaan AI tidak menjamin jawaban anda semuanya benar




#   JAWABAN


###  💻 ANALISIS SOURCE CODE MakhlukHidup.java  dan TestAccess.java

java
public class MakhlukHidup {

    private string nama; //Salah pada penulisan "string"      
    private String jenis;
    public double berat = -1.0;  
    private int umur;


    public MakhlukHidup() {
        this.nama = "Unknown";
        this.jenis = "Unknown";
        this.umur = 15;
        this.berat = 10.0;
    }

    public void MakhlukHidup(String nama) { //Salah nya tidak perlu pakai void
        this.nama = nama;
        this.jenis = "Salah";
        this.umur = 12;
        this.berat = 170.0;
    }

    public makhlukHidup (String nama, String jenis, int umur, double berat) { //salah penulisan makhlukHidup
        this.nama = jenis; // salah pada jenis, harusnya = nama
        this.jenis = nama; // salah pada nama, harusnya jenis
        this.umur = umur;
        this.berat = berat;
    } // salah pada penulisan makhlukHidup

    public MakhlukHidup(MakhlukHidup other) {
        this.nama = nama; //salah pada nama, harusnya = other.nama
        this.jenis = other.jenis; 
        this.umur = this.umur; // salah pada this.umur, harusnya other.umur
        this.berat = other.berat;
    }


    public void setUmur(String umur) {  // parameternya harusnya int bukang String
        this.umur = umur; //karena String di ganti int, maka harus pakai if else untuk memasukkan nilai/assign
    }

    public void setNama(String nama) {
        nama = this.nama; //salah, harusnya this.nama = nama;
    }

    public int getInfo() { //salah, return type nya harusnya String bukan int
        return "Nama=" + nama + ", Jenis=" + jenis 
        + ", Umur=" + umur + ", Berat=" + berat;
    }
}


class TestAccess {
    public static void main(String[] args) {
        MakhlukHidup m = new MakhlukHidup();
        
        m.nama = "Kucing"; // nama itu bersifat private, tidak bisa di akses langsung
        
        MakhlukHidup m2 = new MakhlukHidup("Harimau", "Hewan", 3, 120.0);
        
        MakhlukHidup m3 = new MakhlukHidup(m2);
 
        System.out.println(m.getInfo());
        
        System.out.println(m2.getInfo());
        
        m2.MakhlukHidup("Kuda"); // method salah definisi
                
        System.out.println(m2.getInfo()); 
        
        m3.setUmur(-10); //method setUmur salah parameter, padahal sebelumnya String
        
        System.out.println(m3.getInfo());

        
    }
}

### 📋 TABLE class MahlukHidup dan TestAccess PERBAIKAN ERROR

| No | Class       | Kesalahan CODE                     | Perbaikan                                     |
|----|-------------|----------------------------------|-----------------------------------------------|
| 1  | MakhlukHidup | private string nama;             | private String nama;                           |
| 2  | MakhlukHidup | public void MakhlukHidup(Sring nama) | public MakhlukHidup(String nama)          |
| 3  | MakhlukHidup | public makhlukHidup              | public MakhlukHidup                            |
| 4  | MakhlukHidup | this.nama = jenis;               | this.nama = nama;                              |
| 5  | MakhlukHidup | this.jenis = nama;               | this.jenis = jenis;                            |
| 6  | MakhlukHidup | this.nama = nama;                | this.nama = other.nama;                        |
| 7  | MakhlukHidup | this.umur = this.umur;           | this.umur = other.umur;                        |
| 8  | MakhlukHidup | setUmur(String umur)             | setUmur(int umur)                              |
| 9  | MakhlukHidup | private string nama;             | if (umur < 0){this.umur = 0;}else{this.umur = umur;} |
| 10 | MakhlukHidup | nama = this.nama;                | this.nama = nama;                              |
| 11 | MakhlukHidup | public int getInfo()             | public String getInfo()                        |
| 12 | TestAccess   | m.nama = "kucing";               | m.setNama("kucing");                           |
| 13 | TestAccess   | m2.MakhlukHidup("Kuda");         | m2 = new MakhlukHidup("Kuda");                 |
| 14 | TestAccess   | m3.setUmur(-10);                 | m3.setUmur(-10); System.out.println(m3.getInfo()); |


### SOURCE CODE MakhlukHidup.java  dan TestAccess.java SUDAH DIPERBAIKI

java

public class MakhlukHidup {

    private String nama;       
    private String jenis;
    private double berat = -1.0;  
    private int umur;

    public MakhlukHidup() {
        this.nama = "Unknown";
        this.jenis = "Unknown";
        this.umur = 15;
        this.berat = 10.0;
    }

    public MakhlukHidup(String nama) {
        this.nama = nama;
        this.jenis = "Salah";
        this.umur = 12;
        this.berat = 170.0;
    }

    public MakhlukHidup(String nama, String jenis, int umur, double berat) {
        this.nama = nama;     
        this.jenis = jenis;   
        this.umur = umur;
        this.berat = berat;
    }

    public MakhlukHidup(MakhlukHidup other) {
        this.nama = other.nama;
        this.jenis = other.jenis;
        this.umur = other.umur;
        this.berat = other.berat;
    }

    public void setUmur(int umur) {
        if (umur < 0) {
            this.umur = 0; 
        } else {
            this.umur = umur;
        }
    }

    public void setNama(String nama) {
        this.nama = nama;
    }

    public String getInfo() {
        return "Nama=" + nama + ", Jenis=" + jenis 
        + ", Umur=" + umur + ", Berat=" + berat;
    }
}

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
### 📋 HASIL OUTPUT SUDAH PERBAIKAN

java
Nama=Kucing, Jenis=Unknown, Umur=15, Berat=10.0  
Nama=Harimau, Jenis=Hewan, Umur=3, Berat=120.0  
Nama=Kuda, Jenis=Salah, Umur=12, Berat=170.0  
Nama=Harimau, Jenis=Hewan, Umur=0, Berat=120.0
