# Rekayasa_Perangkat_Lunak

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
print(d)
