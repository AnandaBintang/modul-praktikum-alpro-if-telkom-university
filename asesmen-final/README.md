# 🧪 Praktikum Golang – Struktur Data Dasar & Studi Kasus Sederhana

Selamat datang di assesmen praktikum Golang! Pada tugas ini, Anda akan menyelesaikan **5 soal berbasis studi kasus sederhana** yang melibatkan konsep dasar pemrograman seperti **function, procedure, array, sorting, dan searching**.

---

## 📌 Petunjuk Umum

- Lengkapi skeleton code yang tersedia di setiap soal.
- Jalankan program untuk setiap soal.
- Ambil **screenshot output** dari program yang berhasil dijalankan.
- Tulis **penjelasan singkat (1–2 kalimat)** tentang bagaimana solusi Anda bekerja.
- Kumpulkan hasil pengerjaan Anda dalam **satu file PDF** atau **folder ZIP** berisi file `.go`, screenshot, dan penjelasan.

---

## 📚 Daftar Soal

### ✅ Soal 1: Menghitung Total Harga Belanja (Function + Array)
**Studi Kasus:**  
Seorang kasir ingin menghitung total harga dari item yang dibeli pelanggan. Harga produk disimpan dalam array.

**Skeleton Code:**
```go
package main

import "fmt"

func totalBelanja(harga []float64) float64 {
    // TODO: Hitung total dari semua elemen
    return 0
}

func main() {
    daftarHarga := []float64{10000, 15000, 7500, 20000}
    total := totalBelanja(daftarHarga)
    fmt.Println("Total belanja pelanggan adalah:", total)
}
```

### ✅ Soal 2: Pencarian Nama Mahasiswa (Sequential Search + Procedure)
**Studi Kasus:**
Dosen ingin memeriksa apakah seorang mahasiswa hadir di dalam daftar absensi hari ini.

**Skeleton Code:**
```go
package main

import "fmt"

func cariMahasiswa(absen []string, nama string) {
    // TODO: Lakukan pencarian sekuensial dan tampilkan hasil
}

func main() {
    daftarHadir := []string{"Joko", "Prabo", "Gibra", "Ani", "Ganjas"}
    cariMahasiswa(daftarHadir, "Ani")
}
```

### ✅ Soal 3: Login Sistem Perpustakaan (Binary Search + Array Terurut)
**Studi Kasus:**
Sistem login perpustakaan ingin mencari apakah ID tertentu sudah terdaftar di sistem.

**Skeleton Code:**
```go
package main

import "fmt"

func cariID(ids []int, target int) int {
    // TODO: Binary search
    return -1
}

func main() {
    daftarID := []int{1001, 1005, 1010, 1020, 1030}
    hasil := cariID(daftarID, 1010)
    if hasil != -1 {
        fmt.Println("Akses diberikan")
    } else {
        fmt.Println("ID tidak ditemukan")
    }
}
```

### ✅ Soal 4: Mengurutkan Nilai Mahasiswa (Selection Sort)
**Studi Kasus:**
Dosen ingin mengurutkan nilai akhir mahasiswa untuk menentukan ranking.


**Skeleton Code:**
```go
package main

import "fmt"

func selectionSort(nilai []int) {
    // TODO: Implementasi selection sort
}

func main() {
    nilaiMahasiswa := []int{78, 95, 60, 88, 70}
    fmt.Println("Sebelum diurutkan:", nilaiMahasiswa)
    selectionSort(nilaiMahasiswa)
    fmt.Println("Setelah diurutkan:", nilaiMahasiswa)
}
```

### ✅ Soal 5: Menyusun Urutan Antrian Tiket (Insertion Sort + Function)
**Studi Kasus:**
Panitia konser ingin mengurutkan daftar antrian nomor tiket pembeli.

**Skeleton Code:**
```go
package main

import "fmt"

func urutAntrian(antrian []int) {
    // TODO: Implementasi insertion sort
}

func main() {
    nomorTiket := []int{45, 23, 10, 55, 32}
    fmt.Println("Nomor antrian awal:", nomorTiket)
    urutAntrian(nomorTiket)
    fmt.Println("Nomor antrian terurut:", nomorTiket)
}
```

### 📝 Format Pengumpulan
- Format file: `.zip` atau `.pdf`
- Isi:
  - Semua file kode (`.go`)
  - Screenshot output masing-masing program
  - Penjelasan singkat untuk setiap soal

## Contoh Struktur Folder
```
praktikum-golang/
├── soal1.go
├── soal2.go
├── soal3.go
├── soal4.go
├── soal5.go
├── output-screenshots/
│   ├── soal1.png
│   └── ...
└── penjelasan.txt
```

## Link Pengumpulan
[Pengumpulan Asesmen Final Alpro](https://forms.office.com/r/BXdaxe0FNz)