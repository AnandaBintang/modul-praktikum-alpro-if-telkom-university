# Selection Sort
## Pengertian Selection Sort
Algoritma Selection Sort merupakan salah satu algoritma pengurutan data yang bertujuan untuk mengurutkan elemen-elemen data dari yang terkecil sampai yang terbesar atau sebaliknya. Cara kerja algoritma ini adalah dengan memilih elemen terkecil pada setiap iterasi, kemudian menukarkannya dengan elemen pada indeks yang sesuai. Proses ini dilakukan terus-menerus sampai semua elemen terurut dengan benar. Algoritma ini relatif sederhana, namun tidak efisien dibandingkan dengan algoritma pengurutan lainnya.

![](https://zaxrosenberg.com/wp-content/uploads/2017/12/sort_complexity.png)

Salah satu alasan mengapa selection sort tidak efisien adalah karena ia memerlukan banyak operasi pertukaran untuk mengurutkan elemen-elemen data. Algoritma ini mencari elemen terkecil pada setiap iterasi dan menukarkannya dengan elemen pada indeks yang sesuai, yang berarti ia harus melakukan banyak pertukaran elemen untuk mengurutkan seluruh data. Selain itu, algoritma ini juga memerlukan banyak operasi perbandingan untuk mencari elemen terkecil pada setiap iterasi, yang dapat memperlambat proses pengurutan.

## Ilustrasi Selection Sort
![](https://codingconnect.net/wp-content/uploads/2016/09/Selection-Sort.gif)<br>
Warna **merah** merupakan nilai paling kecil yang ditemukan saat ini, nilai ini dapat berubah apabila ditemukan nilai lain yang lebih kecil dalam satu iterasi, warna **biru** merupakan proses pencarian nilai terkecil pada list, dan warna **kuning** merupakan list yang telah diurutkan.<br><br>
Untuk dapat lebih memahami ilustrasi di atas, mari kita pahami proses berjalannya ilustrasi tersebut dengan membedah proses dari tiap iterasinya.<br>
Kita memiliki data [8, 5, 2, 6, 9, 3, 1, 4, 0, 7] dan kita mengurutkannya dengan metode ascending.<br><br>
Angka di dalam kurung merupakan angka yang telah terurut.<br>
Iterasi 1: <br>
<u>8</u>, 5, 2, 6, 9, 3, 1, 4, 0, 7 → Min 8 <br>
8, <u>5</u>, 2, 6, 9, 3, 1, 4, 0, 7 → Min 5 <br>
8, 5, <u>2</u>, 6, 9, 3, 1, 4, 0, 7 → Min 2 <br>
8, 5, 2, <u>6</u>, 9, 3, 1, 4, 0, 7 → Min 2 <br>
8, 5, 2, 6, <u>9</u>, 3, 1, 4, 0, 7 → Min 2 <br>
8, 5, 2, 6, 9, <u>3</u>, 1, 4, 0, 7 → Min 2 <br>
8, 5, 2, 6, 9, 3, <u>1</u>, 4, 0, 7 → Min 1 <br>
8, 5, 2, 6, 9, 3, 1, <u>4</u>, 0, 7 → Min 1 <br>
8, 5, 2, 6, 9, 3, 1, 4, <u>0</u>, 7 → Min 0 <br>
8, 5, 2, 6, 9, 3, 1, 4, 0, <u>7</u> → Min 0 <br>
(0), 5, 2, 6, 9, 3, 1, 4, 8, 7 → Swap 8 dan 0
<br><br>
Iterasi 2: <br>
(0), <u>5</u>, 2, 6, 9, 3, 1, 4, 8, 7 → Min 5 <br>
(0), 5, <u>2</u>, 6, 9, 3, 1, 4, 8, 7 → Min 2 <br>
(0), 5, 2, <u>6</u>, 9, 3, 1, 4, 8, 7 → Min 2 <br>
(0), 5, 2, 6, <u>9</u>, 3, 1, 4, 8, 7 → Min 2 <br>
(0), 5, 2, 6, 9, <u>3</u>, 1, 4, 8, 7 → Min 2 <br>
(0), 5, 2, 6, 9, 3, <u>1</u>, 4, 8, 7 → Min 1 <br>
(0), 5, 2, 6, 9, 3, 1, <u>4</u>, 8, 7 → Min 1 <br>
(0), 5, 2, 6, 9, 3, 1, 4, <u>8</u>, 7 → Min 1 <br>
(0), 5, 2, 6, 9, 3, 1, 4, 8, <u>7</u> → Min 1 <br>
(0, 1), 2, 6, 9, 3, 5, 4, 8, 7 → Swap 5 dan 1
<br><br>
Iterasi 3: <br>
(0, 1), <u>2</u>, 6, 9, 3, 5, 4, 8, 7 → Min 2 <br>
(0, 1), 2, <u>6</u>, 9, 3, 5, 4, 8, 7 → Min 2 <br>
(0, 1), 2, 6, <u>9</u>, 3, 5, 4, 8, 7 → Min 2 <br>
(0, 1), 2, 6, 9, <u>3</u>, 5, 4, 8, 7 → Min 2 <br>
(0, 1), 2, 6, 9, 3, <u>5</u>, 4, 8, 7 → Min 2 <br>
(0, 1), 2, 6, 9, 3, 5, <u>4</u>, 8, 7 → Min 2 <br>
(0, 1), 2, 6, 9, 3, 5, 4, <u>8</u>, 7 → Min 2 <br>
(0, 1), 2, 6, 9, 3, 5, 4, 8, <u>7</u> → Min 2 <br>
(0, 1, 2), 6, 9, 3, 5, 4, 8, 7 → Tidak terjadi swap
<br><br>
Iterasi 4: <br>
(0, 1, 2), <u>6</u>, 9, 3, 5, 4, 8, 7 → Min 6 <br>
(0, 1, 2), 6, <u>9</u>, 3, 5, 4, 8, 7 → Min 6 <br>
(0, 1, 2), 6, 9, <u>3</u>, 5, 4, 8, 7 → Min 3 <br>
(0, 1, 2), 6, 9, 3, <u>5</u>, 4, 8, 7 → Min 3 <br>
(0, 1, 2), 6, 9, 3, 5, <u>4</u>, 8, 7 → Min 3 <br>
(0, 1, 2), 6, 9, 3, 5, 4, <u>8</u>, 7 → Min 3 <br>
(0, 1, 2), 6, 9, 3, 5, 4, 8, <u>7</u> → Min 3 <br>
(0, 1, 2, 3), 9, 6, 5, 4, 8, 7 → Swap 6 dan 3
<br><br>
Iterasi 5: <br>
(0, 1, 2, 3), <u>9</u>, 6, 5, 4, 8, 7 → Min 9 <br>
(0, 1, 2, 3), 9, <u>6</u>, 5, 4, 8, 7 → Min 6 <br>
(0, 1, 2, 3), 9, 6, <u>5</u>, 4, 8, 7 → Min 5 <br>
(0, 1, 2, 3), 9, 6, 5, <u>4</u>, 8, 7 → Min 4 <br>
(0, 1, 2, 3), 9, 6, 5, 4, <u>8</u>, 7 → Min 4 <br>
(0, 1, 2, 3), 9, 6, 5, 4, 8, <u>7</u> → Min 4 <br>
(0, 1, 2, 3, 4), 6, 5, 9, 8, 7 → Swap 9 dan 4
<br><br>
Iterasi 6: <br>
(0, 1, 2, 3, 4), <u>6</u>, 5, 9, 8, 7 → Min 6 <br>
(0, 1, 2, 3, 4), 6, <u>5</u>, 9, 8, 7 → Min 5 <br>
(0, 1, 2, 3, 4), 6, 5, <u>9</u>, 8, 7 → Min 5 <br>
(0, 1, 2, 3, 4), 6, 5, 9, <u>8</u>, 7 → Min 5 <br>
(0, 1, 2, 3, 4), 6, 5, 9, 8, <u>7</u> → Min 5 <br>
(0, 1, 2, 3, 4, 5), 6, 9, 8, 7 → Swap 6 dan 5
<br><br>
Iterasi 7: <br>
(0, 1, 2, 3, 4, 5), <u>6</u>, 9, 8, 7 → Min 6 <br>
(0, 1, 2, 3, 4, 5), 6, <u>9</u>, 8, 7 → Min 6 <br>
(0, 1, 2, 3, 4, 5), 6, 9, <u>8</u>, 7 → Min 6 <br>
(0, 1, 2, 3, 4, 5), 6, 9, 8, <u>7</u> → Min 6 <br>
(0, 1, 2, 3, 4, 5, 6), 9, 8, 7 → Tidak terjadi swap
<br><br>
Iterasi 8: <br>
(0, 1, 2, 3, 4, 5, 6), <u>9</u>, 8, 7 → Min 9 <br>
(0, 1, 2, 3, 4, 5, 6), 9, <u>8</u>, 7 → Min 8 <br>
(0, 1, 2, 3, 4, 5, 6), 9, 8, <u>7</u> → Min 7 <br>
(0, 1, 2, 3, 4, 5, 6, 7), 8, 9 → Swap 9 dan 7
<br><br>
Iterasi 9: <br>
(0, 1, 2, 3, 4, 5, 6, 7), <u>8</u>, 9 → Min 8 <br>
(0, 1, 2, 3, 4, 5, 6, 7), 8, <u>9</u> → Min 8 <br>
(0, 1, 2, 3, 4, 5, 6, 7, 8), 9 → Tidak terjadi swap
<br><br>
Iterasi 10 : <br>
(0, 1, 2, 3, 4, 5, 6, 7, 8), <u>9</u> → Min 9 <br>
(0, 1, 2, 3, 4, 5, 6, 7, 8, 9) → Tidak terjadi swap (Hasil Akhir)
<br><br>

Proses Dalam Tabel (Angka Awal: 8, 5, 2, 6, 9, 3, 1, 4, 0, 7): 
| Iterasi | Langkah Perbandingan                                                                 | Status Swap           | Hasil Sementara                         |
|---------|----------------------------------------------------------------------------------------|------------------------|------------------------------------------|
| 1       | Min: 8 → 5 → 2 → 2 → 2 → 2 → 1 → 1 → 0 → 0                                            | Swap(8, 0)             | (0), 5, 2, 6, 9, 3, 1, 4, 8, 7            |
| 2       | Min: 5 → 2 → 2 → 2 → 2 → 1 → 1 → 1 → 1                                                | Swap(5, 1)             | (0, 1), 2, 6, 9, 3, 5, 4, 8, 7            |
| 3       | Min: 2 → 2 → 2 → 2 → 2 → 2 → 2 → 2                                                    | No Swap                | (0, 1, 2), 6, 9, 3, 5, 4, 8, 7            |
| 4       | Min: 6 → 6 → 3 → 3 → 3 → 3 → 3                                                        | Swap(6, 3)             | (0, 1, 2, 3), 9, 6, 5, 4, 8, 7            |
| 5       | Min: 9 → 6 → 5 → 4 → 4 → 4                                                            | Swap(9, 4)             | (0, 1, 2, 3, 4), 6, 5, 9, 8, 7            |
| 6       | Min: 6 → 5 → 5 → 5 → 5                                                                | Swap(6, 5)             | (0, 1, 2, 3, 4, 5), 6, 9, 8, 7            |
| 7       | Min: 6 → 6 → 6 → 6                                                                    | No Swap                | (0, 1, 2, 3, 4, 5, 6), 9, 8, 7            |
| 8       | Min: 9 → 8 → 7                                                                        | Swap(9, 7)             | (0, 1, 2, 3, 4, 5, 6, 7), 8, 9            |
| 9       | Min: 8 → 8                                                                            | No Swap                | (0, 1, 2, 3, 4, 5, 6, 7, 8), 9            |
| 10      | Min: 9                                                                                | No Swap                | (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)            |

**Keterangan:**
- Nilai dalam kurung `( )` adalah bagian array yang sudah terurut.
- Nilai yang di-*swap* dituliskan sebagai `Swap(a, b)`, artinya `a` dan `b` ditukar posisinya.
- "No Swap" berarti nilai terkecil sudah berada di posisi yang benar.

## Contoh Selection Sort
```go
package main

import (
	"fmt"
)

func main() {
	angka := [10]int{8, 5, 2, 6, 9, 3, 1, 4, 0, 7}

	// Melakukan looping sebanyak jumlah data
	for i := 0; i < len(angka); i++ {
		// Anggap index ke i adalah angka terkecil
		indexNilaiMinimal := i
		// Looping untuk mencari angka yang terkecil dengan membandingkan setiap angka
		for j := i; j < len(angka); j++ {
			if angka[j] < angka[indexNilaiMinimal] {
				// Ganti indexNilaiMinimal jika ditemukan yang lebih kecil
				indexNilaiMinimal = j
			}
		}
		// Swap value
		angka[i], angka[indexNilaiMinimal] = angka[indexNilaiMinimal], angka[i]
	}

	// Cetak data
	for _, v := range angka {
		fmt.Printf("%d ", v)
	}
	fmt.Println()
}

```

## Latihan Soal
Buatlah program yang menerima input dari user berupa jumlah tim dan skor dari tiap tim (3 skor), lalu jumlahkan skor dari setiap tim dan urutkan hasil penjumlahan skor dari yang terbesar menggunakan selection sort.. <br><br>
Input 1:
```go
Jumlah Tim : 3
Skor tim 1 : 30 40 20
Skor tim 2 : 10 30 20
Skor tim 3 : 80 50 40
```

Output 1:
```go
170
90
50
```

Input 2:
```go
Jumlah Tim : 3
Skor Tim 1 : 40 40 40
Skor Tim 2 : 30 30 30
Skor Tim 3 : 35 35 35
```

Output 2:
```go
120
105
90
```