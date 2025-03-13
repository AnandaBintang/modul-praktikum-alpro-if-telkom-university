# Modul 3: Fungsi

## 3.1 Pengertian Fungsi
Fungsi merupakan satu kesatuan rangkaian instruksi yang memberikan atau menghasilkan suatu nilai dan biasanya memetakkan input ke suatu nilai yang lain. Oleh karena itu, fungsi selalu menghasilkan/mengembalikan nilai. Suatu subprogram dikatakan fungsi apabila:

1. Ada deklarasi tipe nilai yang dikembalikan.
2. Terdapat kata kunci `return` dalam badan subprogram.

Fungsi digunakan jika suatu nilai diperlukan, seperti:
- Assignment nilai ke suatu variabel
- Bagian dari ekspresi
- Bagian dari argumen suatu subprogram, dsb.

Karena itu selalu pilih nama fungsi yang menggambarkan nilai, seperti kata benda dan kata sifat. Contoh nama-nama fungsi: `median`, `rerata`, `nilaiTerbesar`, `ketemu`, `selesai`, dll.

---

## 3.2 Deklarasi Function
Deklarasi fungsi sama dengan prosedur, yaitu berada pada blok yang terpisah dengan program utama.

### Notasi Algoritma
```pseudo
function <nama_function> (<params>) -> <type>
    kamus
        {deklarasi variabel lokal dari fungsi}
    algoritma
        {badan algoritma fungsi}
        return <value/variabel>
endfunction
```

### Notasi dalam Bahasa Go
```go
func <nama_function>(<params>) <type> {
    // deklarasi variabel lokal dari fungsi
    ...
    // badan algoritma fungsi
    ...
    return <value/variabel>
}
```

Contoh fungsi untuk menghitung volume tabung:

```go
func volumeTabung(jari_jari, tinggi int) float64 {
    var luasAlas, volume float64
    luasAlas = 3.14 * float64(jari_jari * jari_jari)
    volume = luasAlas * float64(tinggi)
    return volume
}
```

---

## 3.3 Cara Pemanggilan Function

### Notasi Algoritma
```pseudo
program ContohProsedur
    kamus
        r, t : integer
        v1, v2 : real
    algoritma
        r <- 5;
        t <- 10
        v1 <- volumeTabung(r,t) // cara pemanggilan #1
        v2 <- volumeTabung(r,t) + volumeTabung(15,t) // cara pemanggilan #2
        output(volumeTabung(14,100)) // cara pemanggilan #3
endprogram
```

### Notasi dalam Bahasa Go
```go
func main() {
    var r, t int
    var v1, v2 float64
    r = 5
    t = 10
    v1 = volumeTabung(r, t) // cara pemanggilan #1
    v2 = volumeTabung(r, t) + volumeTabung(15, t) // cara pemanggilan #2
    fmt.Println(volumeTabung(14, 100)) // cara pemanggilan #3
}
```

---

## 3.4 Contoh Program dengan Function
Berikut ini adalah contoh penulisan fungsi pada suatu program lengkap untuk menghitung faktorial dan permutasi.

```go
package main
import "fmt"

func main() {
    var a, b int
    fmt.Scan(&a, &b)
    if a >= b {
        fmt.Println(permutasi(a, b))
    } else {
        fmt.Println(permutasi(b, a))
    }
}

func faktorial(n int) int {
    var hasil int = 1
    for i := 1; i <= n; i++ {
        hasil *= i
    }
    return hasil
}

func permutasi(n, r int) int {
    return faktorial(n) / faktorial(n-r)
}
```

---

## 3.5 Soal Latihan Modul 3

### 1. Permutasi dan Kombinasi
Jonas ingin mengimplementasikan permutasi dan kombinasi ke dalam suatu program.

#### Rumus:
```math
P(n, r) = n! / (n-r)!
C(n, r) = n! / (r! (n-r)!)
```

#### Contoh Program
```go
func kombinasi(n, r int) int {
    return faktorial(n) / (faktorial(r) * faktorial(n-r))
}
```

---

### 2. Fungsi Komposisi
Diberikan tiga buah fungsi matematika:
```math
f(x) = x^2
g(x) = x - 2
h(x) = x + 1
```
Implementasikan fungsi komposisi `(f o g o h)(x)` dalam program Go.

```go
func f(x int) int {
    return x * x
}

func g(x int) int {
    return x - 2
}

func h(x int) int {
    return x + 1
}

func fogoh(x int) int {
    return f(g(h(x)))
}
```

---

### 3. Menentukan Posisi Titik terhadap Lingkaran
Diberikan dua lingkaran dengan koordinat pusat `(cx, cy)` dan radius `r`, serta titik `(x, y)`, tentukan apakah titik berada di dalam atau di luar lingkaran.

#### Rumus Jarak Euclidean:
```math
d = sqrt((x - cx)^2 + (y - cy)^2)
```

#### Implementasi dalam Go:
```go
import "math"

func jarak(a, b, c, d float64) float64 {
    return math.Sqrt((a-c)*(a-c) + (b-d)*(b-d))
}

func didalam(cx, cy, r, x, y float64) bool {
    return jarak(cx, cy, x, y) <= r
}
```

Dengan fungsi ini, kita bisa menentukan apakah titik berada di dalam lingkaran 1, lingkaran 2, atau keduanya.

---

## Catatan
Gunakan paket `math` dalam Go untuk fungsi `math.Sqrt()` guna menghitung akar kuadrat.

---

### **Selesai!** 🚀 Happy Coding! 🎯

