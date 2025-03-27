# Simulasi Pengeboran Minyak

## Deskripsi Soal

Sebuah perusahaan minyak ingin mensimulasikan pengeboran sumur minyak menggunakan program yang dibuat dengan **Golang**. Dalam simulasi ini, pengeboran dilakukan secara bertahap hingga kedalaman tertentu dengan mempertimbangkan beberapa faktor.

## Aturan Simulasi

1. **Pengeboran dimulai dari kedalaman 0 meter**.
2. Setiap langkah pengeboran, pengguna dapat memilih dua metode:
   - **Bor Normal:** Menambah kedalaman pengeboran sebanyak `X` meter (input pengguna setiap langkah).
   - **Bor Turbo:** Menggandakan kedalaman yang ada saat ini.
3. Pengeboran **harus berhenti** setelah mencapai kedalaman target `D` meter.
4. Jika kedalaman **melebihi** batas `D`, pengeboran dianggap gagal.
5. Minimal pengeboran harus dilakukan dalam **3 langkah** agar berhasil.

## Konstraint Implementasi

1. **Gunakan rekursi** untuk melakukan simulasi pengeboran.
2. Harus ada **fungsi terpisah** untuk pengeboran dan validasi kedalaman.
3. Program meminta input `D` (kedalaman target) dari pengguna di awal.
4. Kedalaman akhir \*\*harus tepat \*\*\`\` agar dianggap berhasil.

## Contoh Input & Output

### **Contoh 1: Pengeboran Berhasil**

#### **Input:**

```
Masukkan kedalaman target: 10  
Langkah 1 - Pilih jenis pengeboran (1: Normal, 2: Turbo): 1  
Masukkan kedalaman yang ingin ditambahkan: 3  
Langkah 2 - Pilih jenis pengeboran (1: Normal, 2: Turbo): 1  
Masukkan kedalaman yang ingin ditambahkan: 2  
Langkah 3 - Pilih jenis pengeboran (1: Normal, 2: Turbo): 2  
```

#### **Output:**

```
Total kedalaman: 10 meter  
Pengeboran berhasil!
```

---

### **Contoh 2: Pengeboran Gagal (Melebihi Kedalaman Target)**

#### **Input:**

```
Masukkan kedalaman target: 15  
Langkah 1 - Pilih jenis pengeboran (1: Normal, 2: Turbo): 1  
Masukkan kedalaman yang ingin ditambahkan: 6  
Langkah 2 - Pilih jenis pengeboran (1: Normal, 2: Turbo): 2  
```

#### **Output:**

```
Total kedalaman: 12 meter  
Pengeboran gagal!
```

---

### **Contoh 3: Pengeboran Gagal (Kurang dari Kedalaman Target)**

#### **Input:**

```
Masukkan kedalaman target: 20  
Langkah 1 - Pilih jenis pengeboran (1: Normal, 2: Turbo): 1  
Masukkan kedalaman yang ingin ditambahkan: 7  
Langkah 2 - Pilih jenis pengeboran (1: Normal, 2: Turbo): 1  
Masukkan kedalaman yang ingin ditambahkan: 3  
Langkah 3 - Pilih jenis pengeboran (1: Normal, 2: Turbo): 2  
```

#### **Output:**

```
Total kedalaman: 20 meter  
Pengeboran berhasil!
```

---

## Petunjuk Implementasi

1. **Buat fungsi rekursif** untuk menjalankan simulasi pengeboran.
2. **Validasi input pengguna** agar selalu dalam format yang benar.
3. **Gunakan percabangan** untuk memproses pilihan "Bor Normal" dan "Bor Turbo".
4. **Pastikan hasil akhir** memenuhi syarat "berhasil" sebelum mencetak output.

Selamat mengerjakan! 🚀

