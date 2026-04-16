
<h1 align="left"><b><u>TUGAS MINGGU 5 AUDIT KODE</u></b></h1>

<h3 align="left"><b>Nama: Muhammad Fajar Mauliddin</b></h3>
<h3 align="left"><b>NIM: 2411102441153</b></h3>
<h3 align="left"><b>Mata Kuliah: Rekayasa Perangkat Lunak</b></h3>

---
## 1. Kode Berantakan
def ms(a):
    if len(a)>1:
        m=len(a)//2
        l=a[:m]
        r=a[m:]

        ms(l);ms(r)

        i=0;j=0;k=0

        while i<len(l) and j<len(r):
            if l[i]<r[j]:
                a[k]=l[i];i+=1
            else:
                a[k]=r[j];j+=1
            k+=1

        while i<len(l):
            a[k]=l[i];i+=1;k+=1
        while j<len(r):
            a[k]=r[j];j+=1;k+=1

d=[12,16,90,88,73,40,5,43,21,33]
ms(d)

---
## 2. HASIL CODE AUDIT (TEMUAN)
A. Naming tidak jelas: 
ms, a, l, r, m = Tidak deskriptif

B. Tidak ada komentar: 
Tidak ada penjelasan algoritma dan Sulit dipahami orang lain

C. Penulisan tidak rapi: 
Banyak baris digabung: ms(l);ms(r)

D. Magic number / tidak ada konteks data: 
d=[12,16,90,88,73,40,5,43,21,33], Tidak dijelaskan ini data apa

E. Tidak modular / sulit dibaca: 
Semua logic dalam satu fungsi tanpa penjelasan struktur
print(d)

---
## 3. KODE CLEAN (SETELAH PERBAIKAN)
def merge_sort(arr):
    """
    Mengurutkan list menggunakan algoritma Merge Sort (ascending).
    """

    if len(arr) > 1:
        mid = len(arr) // 2
        left_half = arr[:mid]
        right_half = arr[mid:]

        # Rekursif untuk membagi array
        merge_sort(left_half)
        merge_sort(right_half)

        i = j = k = 0

        # Menggabungkan dua sub-array
        while i < len(left_half) and j < len(right_half):
            if left_half[i] < right_half[j]:
                arr[k] = left_half[i]
                i += 1
            else:
                arr[k] = right_half[j]
                j += 1
            k += 1

        # Menambahkan sisa elemen kiri
        while i < len(left_half):
            arr[k] = left_half[i]
            i += 1
            k += 1

        # Menambahkan sisa elemen kanan
        while j < len(right_half):
            arr[k] = right_half[j]
            j += 1
            k += 1


### Data uji (nilai acak)
data_angka = [12, 16, 90, 88, 73, 40, 5, 43, 21, 33]

merge_sort(data_angka)

print("Hasil Merge Sort:", data_angka)

---
## 4. PERBAIKAN YANG DILAKUKAN

| Aspek	| Sebelum |	Sesudah |
|-------|---------|---------|
| Naming |	ms, a, l |	merge_sort, arr, left_half |
| Komentar |	Tidak ada |	Ada penjelasan |
| Struktur |	Berantakan	| Rapi & terstruktur |
| Readability |	Rendah |	Tinggi |
| Standar Python |	Tidak konsisten |	Mengikuti best practice |
