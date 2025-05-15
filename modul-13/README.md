# Pengertian Insertion Sort
Insertion sort merupakan salah satu jenis dari algoritma sorting yang masuk ke dalam comparasion sort atau algoritma yang melakukan perbandingan antar elemen guna menentukkan urutan yang sesuai dari sebuah data. Seperti algoritma sorting sebelumnya yaitu `Bubble Sort` dan `Selection Sort`, algoritma insertion sort memiliki kompleksitas yang sama dengan kedua algoritma tersebut yaitu `O(n^2)` untuk kondisi rata-ratanya. Algoritma ini juga dapat digunakan untuk mengurutkan sebuah data secara Ascending maupun Descending. 

Cara  kerja Insertion Sort sangatlah sederhana yaitu membandingkan sebuah elemen dengan elemen sebelumnya. Untuk ascending maka sebuah elemen akan dibandingkan apakah elemen tersebut lebih kecil dari elemen sebelumnya, jika iya maka penukaran element terjadi. 

Cara kerja algoritma `Insertion Sort` dapat dilihat pada gambar di bawah ini : 

![](https://upload.wikimedia.org/wikipedia/commons/9/9c/Insertion-sort-example.gif)

![](https://miro.medium.com/max/765/0*1zi2XtjiLXa3LYZh.PNG)

Berikut merupakan kode program dari selection sort : 
``````go
package main

import "fmt"

func insertionSort(angka []int) {
	for a := 1; a < len(angka); a++ {
		key := angka[a]
		b := a - 1

		for b >= 0 && angka[b] > key {
			angka[b+1] = angka[b]
			b = b - 1
		}
		angka[b+1] = key
	}
}

func show(angka []int) {
	for _, val := range angka {
		fmt.Printf("%d ", val)
	}
	fmt.Println()
}

func main() {
	angka := []int{10, 5, 3, 1, 2, 9, 7, 4, 6}
	insertionSort(angka)
	show(angka)
}

``````
Output : 
``````
1 2 3 4 5 6 7 8 9 10
``````
Versi lain dari algoritma `Insertion Sort` adalah sebagai berikut : 
``````go
package main

import "fmt"

func insertionSort(angka []int) {
	for a := 1; a < len(angka); a++ {
		if angka[a] < angka[a-1] {
			b := a
			for b > 0 && angka[b] < angka[b-1] {
				// Swap angka[b] dan angka[b-1]
				angka[b], angka[b-1] = angka[b-1], angka[b]
				b--
			}
		}
	}
}

func show(angka []int) {
	for _, val := range angka {
		fmt.Printf("%d ", val)
	}
	fmt.Println()
}

func main() {
	angka := []int{10, 5, 3, 1, 2, 9, 7, 4, 6}
	insertionSort(angka)
	show(angka)
}

``````
Output : 
``````
1 2 3 4 5 6 7 8 9 10
``````
Karena `Insertion Sort` adalah sebuah algoritma, maka insertion sort dapat memiliki berbagai jenis versi kode program. 

| Aspek                     | Versi 1: Menggeser Elemen (`key`)                  | Versi 2: Menukar Elemen (`swap`)                     |
|---------------------------|----------------------------------------------------|------------------------------------------------------|
| Teknik Penyisipan         | Menyimpan nilai `key`, geser elemen ke kanan       | Menukar elemen satu per satu ke posisi yang tepat    |
| Jumlah Operasi            | Lebih sedikit (1 penempatan akhir untuk `key`)     | Lebih banyak (3 operasi per `swap`)                  |
| Efisiensi Waktu           | Lebih efisien, terutama pada data besar            | Kurang efisien, cocok untuk array kecil atau demo    |
| Struktur Kode             | Menggunakan penyimpanan sementara (`key`)          | Langsung menggunakan pertukaran (swap)               |
| Kompleksitas Waktu        | O(n²)                                              | O(n²)                                                |
| Operasi Dominan           | Assignment (`=`, geser)                            | Swap (tukar: 3 assignment per langkah)               |
| Kemudahan Dipahami        | Sedikit lebih kompleks untuk pemula                | Lebih mudah dipahami (mirip Bubble Sort)             |
| Stabilitas Sorting        | Stabil (tidak mengubah urutan elemen yang sama)    | Stabil (jika swap dilakukan hati-hati)               |
| Kinerja pada Data Terurut | Sangat baik (hampir O(n))                          | Masih O(n²), meskipun lebih cepat dari worst-case    |


# Soal Latihan
Bocchi adalah seorang siswa SMA introvert yang sedang menikmati liburan musim panasnya dirumah. Suatu hari karena bosan di rumah, Bocchi memilih untuk tidur namun tidak bisa, ia ingat suatu metode untuk tidur dengan menghitung sebuah baris angka. Namun, Bocchi bingung untuk menghitung baris angka dari kecil ke besar atau besar ke kecil. Untuk itu, Bocchi memilih mengkombinasikan keduanya. Bantu Bocchi untuk membuat sebuah baris angka yang mengkombinasikan kedua urutan baris angka tersebut dengan menggunakan insertion sort, sehingga Bocchi dapat tidur dengan nyenyak.

Input merupakan sebuah baris array yang terdiri dari angka seperti di bawah ini :  
``````
1 9 4 5 6 7 2 3 8 1 9 4 5 6 7 2 3 8
``````
Output : 
``````
Baris 1 : 1 1 2 2 3 3 4 4 5 5 9 9 8 8 7 7 6 6
Baris 2 : 1 9 2 8 3 7 4 6 5 5 6 4 7 3 8 2 9 1 
``````