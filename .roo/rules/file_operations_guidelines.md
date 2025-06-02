# Panduan Operasi File

## read_file
```xml
<read_file>
  <path>Jalur file di sini</path>
</read_file>
```

### Parameter Wajib:
- `path`: Jalur file yang akan dibaca

### Kesalahan Umum yang Harus Dihindari:
- Mencoba membaca file yang tidak ada
- Menggunakan jalur yang salah atau relatif
- Kehilangan parameter `path`

### Praktik Terbaik:
- Selalu periksa apakah file ada sebelum mencoba memodifikasinya
- Gunakan `read_file` sebelum `apply_diff` atau `search_and_replace` untuk memverifikasi konten
- Untuk file besar, pertimbangkan menggunakan parameter start_line dan end_line untuk membaca bagian tertentu

## write_to_file
```xml
<write_to_file>
  <path>Jalur file di sini</path>
  <content>Konten file Anda di sini
