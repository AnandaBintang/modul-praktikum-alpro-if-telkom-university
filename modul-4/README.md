# Modul 4 Rekursif
## Pendahuluan
Rekursi adalah sebuah konsep dalam pemrograman di mana sebuah fungsi memanggil dirinya sendiri. Pada dasarnya, rekursi memungkinkan solusi masalah besar dengan cara memecahnya menjadi submasalah yang lebih kecil. Praktikum ini bertujuan untuk memberikan pemahaman dasar tentang rekursi dalam bahasa pemrograman Go (Golang) bagi pemula.
Tujuan Pembelajaran

Setelah mengikuti praktikum ini, peserta diharapkan dapat:

- Memahami konsep dasar rekursi.
- Mampu mengimplementasikan rekursi dalam bahasa Go.
- Memecahkan masalah sederhana menggunakan rekursi.

## Materi yang Diperlukan

Sebelum memulai, pastikan Anda sudah menguasai:

- Pengenalan dasar bahasa Go (variabel, fungsi, pengulangan).
- Pengaturan lingkungan kerja Go, termasuk instalasi Go di komputer Anda.
- Pemahaman dasar algoritma pemrograman.

## Pengenalan Konsep Rekursif

Dalam rekursi, fungsi yang memanggil dirinya sendiri disebut fungsi rekursif. Ada dua elemen utama yang harus diperhatikan dalam sebuah fungsi rekursif:

- Base Case (Kondisi Henti): Ini adalah kondisi di mana rekursi berhenti, agar tidak terjadi pemanggilan fungsi secara terus-menerus.
- Recursive Case: Kondisi di mana fungsi terus memanggil dirinya sendiri hingga base case tercapai.

```go
package main

import "fmt"

// Fungsi rekursif untuk menghitung faktorial
func faktorial(n int) int {
    // Base Case: Jika n = 0, faktorial adalah 1
    if n == 0 {
        return 1
    }
    // Recursive Case: n * faktorial(n-1)
    return n * faktorial(n-1)
}

func main() {
    var angka int
    fmt.Print("Masukkan bilangan: ")
    fmt.Scan(&angka)
    
    hasil := faktorial(angka)
    fmt.Printf("Faktorial dari %d adalah %d\n", angka, hasil)
}

// Output jika angka = 5

// faktorial(5)
//      return 5 * (5-1)
// faktorial(4)
//      return 4 * (4-1)
// faktorial(3)
//      return 3 * (3-1)
// faktorial(2)
//      return 2 * (2-1)
// faktorial(1)
//      return 1 * (1-1) => karena 1-1 = 0, jadi return 1

// Sehingga Outputnya jadi 5 * 4 * 3 * 2 * 1 = 120
```
Penjelasan:

- Base Case: Jika n == 0, maka faktorial dari 0 adalah 1.
- Recursive Case: Jika tidak, maka akan dilakukan pemanggilan fungsi rekursif faktorial(n-1) hingga mencapai base case.

## Latihan 1: Deret Fibonacci dengan Rekursif
Deret Fibonacci adalah deret angka yang dimulai dari 0 dan 1, di mana setiap angka berikutnya adalah hasil penjumlahan dari dua angka sebelumnya. Buatlah sebuah program untuk menghitung angka Fibonacci ke-n menggunakan rekursi.

Contoh Deret Fibonacci: 
```
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...
```
Hint:
- Buat fungsi bernama fibonacci yang menerima parameter n.
- Tambahkan base case di mana:
    - Jika n == 0, kembalikan 0.
    - Jika n == 1, kembalikan 1.
- Pada recursive case, kembalikan nilai fibonacci(n-1) + fibonacci(n-2).

## Latihan 2:
Buatlah program yang mengimplementasikan rekursif untuk menampilkan barisan bilangan ganjil.
Masukan terdiri dari sebuah bilangan bulat positif N.
Keluaran terdiri dari barisan bilangan ganjil dari 1 hingga N.
### Contoh Input 1:
```
5
```
### Contoh Output 1:
```
1 3 5
```
---
### Contoh Input 2:
```
20
```
### Contoh Output 2:
```
1 3 5 7 9 11 13 15 17 19
```

## Kesimpulan

Rekursi adalah teknik yang sangat berguna dalam pemrograman, terutama untuk masalah yang dapat dipecah menjadi submasalah yang lebih kecil. Praktikum ini memperkenalkan dasar-dasar rekursi di Go dengan implementasi sederhana untuk menghitung faktorial dan deret Fibonacci.