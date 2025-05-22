# 🚀 Latihan Golang: Sistem Pencarian & Pengurutan Nilai Mahasiswa

Latihan ini dirancang untuk memahami dasar-dasar pemrograman menggunakan **bahasa Go** dengan studi kasus sederhana yaitu pencarian dan pengurutan nilai mahasiswa. Cocok untuk pemula yang ingin menguasai:

- ✅ Function & Procedure
- ✅ Array
- ✅ Sequential Search
- ✅ Binary Search
- ✅ Selection Sort
- ✅ Insertion Sort

---

## 📘 Studi Kasus

Kita ingin membuat sistem untuk:

1. Menyimpan data nilai mahasiswa dalam sebuah array
2. Menyortir array tersebut menggunakan metode:
   - Selection Sort
   - Insertion Sort
3. Mencari nilai tertentu menggunakan metode:
   - Sequential Search
   - Binary Search

---

## 📥 Contoh Input

```go
nilai := []int{75, 60, 90, 80, 70, 85}
target := 80
```

## 📥 Contoh Output
```go
Nilai mahasiswa (sebelum sorting):
75 60 90 80 70 85
Setelah Selection Sort:
60 70 75 80 85 90
Setelah Insertion Sort:
60 70 75 80 85 90

Sequential Search:
Nilai 80 ditemukan pada indeks 3

Binary Search:
Nilai 80 ditemukan pada indeks 3 (setelah sort)
```


---

## 🧱 Hint (Skeleton Code)

```go
package main

import "fmt"

// TODO: Function untuk mencetak array
func printArray(arr []int) {
	// Implementasi di sini
}

// TODO: Procedure untuk Selection Sort
func selectionSort(arr []int) {
	// Implementasi di sini
}

// TODO: Procedure untuk Insertion Sort
func insertionSort(arr []int) {
	// Implementasi di sini
}

// TODO: Function untuk Sequential Search
func sequentialSearch(arr []int, target int) int {
	// Implementasi di sini
	return -1
}

// TODO: Function untuk Binary Search
func binarySearch(arr []int, target int) int {
	// Implementasi di sini
	return -1
}

func main() {
	// Contoh array nilai mahasiswa
	nilai := []int{75, 60, 90, 80, 70, 85}
	target := 80

	fmt.Println("Nilai mahasiswa (sebelum sorting):")
	printArray(nilai)

	// Salin array untuk sort
	selectionSorted := make([]int, len(nilai))
	copy(selectionSorted, nilai)
	selectionSort(selectionSorted)
	fmt.Println("Setelah Selection Sort:")
	printArray(selectionSorted)

	insertionSorted := make([]int, len(nilai))
	copy(insertionSorted, nilai)
	insertionSort(insertionSorted)
	fmt.Println("Setelah Insertion Sort:")
	printArray(insertionSorted)

	// Sequential Search
	fmt.Println("\nSequential Search:")
	indexSeq := sequentialSearch(nilai, target)
	if indexSeq != -1 {
		fmt.Printf("Nilai %d ditemukan pada indeks %d\n", target, indexSeq)
	} else {
		fmt.Printf("Nilai %d tidak ditemukan\n", target)
	}

	// Binary Search
	fmt.Println("\nBinary Search:")
	// Gunakan built-in sort sebelum binary search
	// sort.Ints(nilai)
	// indexBin := binarySearch(nilai, target)
	// ...
}
