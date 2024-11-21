# Praktikum 5 - Program Manajemen Data Mahasiswa

Program ini adalah aplikasi berbasis Python untuk mengelola data mahasiswa menggunakan struktur data **dictionary**. Dengan program ini, pengguna dapat menambahkan, mengubah, menghapus, menampilkan, dan mencari data mahasiswa. Program juga menghitung nilai akhir berdasarkan bobot tertentu untuk tugas, UTS, dan UAS.

## Fitur Program

1. **Tambah Data**: Menambahkan data mahasiswa baru ke dalam sistem.
2. **Ubah Data**: Mengubah data mahasiswa berdasarkan nama.
3. **Hapus Data**: Menghapus data mahasiswa berdasarkan nama.
4. **Tampilkan Data**: Menampilkan semua data mahasiswa dalam format tabel.
5. **Cari Data**: Mencari dan menampilkan data mahasiswa berdasarkan nama.
6. **Keluar**: Menghentikan program.

## Struktur Data

Data mahasiswa disimpan dalam struktur dictionary dengan format berikut:

```python
data_mahasiswa = {
    "Nama Mahasiswa": {
        "Tugas": nilai_tugas,
        "UTS": nilai_uts,
        "UAS": nilai_uas,
        "Nilai Akhir": nilai_akhir
    }
}
```
# Contoh 

```python

data_mahasiswa = {
    "Aprilia": {"Tugas": 80, "UTS": 85, "UAS": 90, "Nilai Akhir": 85.25},
    "shafa": {"Tugas": 75, "UTS": 80, "UAS": 70, "Nilai Akhir": 75.25}
}
```
# Perhitungan nilai akhir 

Nilai akhir di hitung dengan rumus 

```python

Nilai Akhir = (Tugas * 30%) + (UTS * 35%) + (UAS * 35%)

```
# Cara Menjalankan Program 

`Pastikan` Python sudah terinstal di komputer Anda.

`Simpan` kode program dalam file `manajemen_data_mahasiswa.py.`

`Jalankan` program dengan perintah :

```python

python manajemen_data_mahasiswa.py

```
`Ikuti` interaksi pada menu interaktif

# Penjelasan Fungsi 

1. **`Hitung_ Nilai_ Akhir`**
   
Fungsi ini menghitung nilai akhir mahasiswa berdasarkan bobot tugas, UTS, dan UAS.

``` python
def hitung_nilai_akhir(tugas, uts, uas):
    return (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
```
2. **`Tampilkan_Menu`**
   
```python
   def tampilkan_menu():
    print("\nMenu Pilihan:")
    print("1. Tambah Data")
    print("2. Ubah Data")
    print("3. Hapus Data")
    print("4. Tampilkan Data")
    print("5. Cari Data")
    print("6. Keluar")
```
3. **`Tambah_Data`**
   
Fungsi ini meminta input dari pengguna untuk menambahkan data mahasiswa baru.
   ```python
   def tambah_data(data):
    nama = input("Masukkan nama: ")
    tugas = float(input("Masukkan nilai tugas: "))
    uts = float(input("Masukkan nilai UTS: "))
    uas = float(input("Masukkan nilai UAS: "))
    nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
    data[nama] = {'Tugas': tugas, 'UTS': uts, 'UAS': uas, 'Nilai Akhir': nilai_akhir}
```
4. **`Ubah_data`**
   
Fungsi ini mengubah data mahasiswa berdasarkan nama.
```python
def ubah_data(data):
    nama = input("Masukkan nama data yang akan diubah: ")
    if nama in data:
        tugas = float(input("Masukkan nilai tugas baru: "))
        uts = float(input("Masukkan nilai UTS baru: "))
        uas = float(input("Masukkan nilai UAS baru: "))
        nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
        data[nama] = {'Tugas': tugas, 'UTS': uts, 'UAS': uas, 'Nilai Akhir': nilai_akhir}
```
5. **`Hapus_data`**
   
   Fungsi ini menghapus data mahasiswa berdasarkan nama.
   ```python
   def hapus_data(data):
    nama = input("Masukkan nama data yang akan dihapus: ")
    if nama in data:
        del data[nama]
   ```

6. **`Tampilkan_data`**
   
Fungsi ini menampilkan semua data mahasiswa dalam format tabel.
```python
def tampilkan_data(data):
    print(f"{'Nama':<15}{'Tugas':<10}{'UTS':<10}{'UAS':<10}{'Nilai Akhir':<15}")
    for nama, nilai in data.items():
        print(f"{nama:<15}{nilai['Tugas']:<10}{nilai['UTS']:<10}{nilai['UAS']:<10}{nilai['Nilai Akhir']:<15.2f}")
```












