# Panduan Insert Content

## insert_content
```xml
<insert_content>
  <path>Jalur file di sini</path>
  <operations>
    [{"start_line":10,"content":"Kode baru"}]
  </operations>
</insert_content>
```

### Parameter Wajib:
- `path`: Jalur file yang akan dimodifikasi
- `operations`: Array JSON dari operasi penyisipan

### Setiap Operasi Harus Menyertakan:
- `start_line`: Nomor baris di mana konten harus disisipkan (WAJIB)
- `content`: Konten yang akan disisipkan (WAJIB)

### Kesalahan Umum yang Harus Dihindari:
- Kehilangan parameter `start_line`
- Kehilangan parameter `content`
- Format JSON yang tidak valid dalam array operations
- Menggunakan nilai non-numerik untuk start_line
- Mencoba menyisipkan pada nomor baris yang melebihi panjang file
- Mencoba memodifikasi file yang tidak ada

### Praktik Terbaik:
- Selalu verifikasi file ada sebelum mencoba memodifikasinya
- Periksa panjang file sebelum menentukan start_line
- Gunakan read_file terlebih dahulu untuk mengkonfirmasi konten dan struktur file
- Pastikan format JSON yang benar dalam array operations
- Gunakan untuk menambahkan konten baru daripada memodifikasi konten yang ada
- Lebih disukai untuk penambahan dokumentasi dan blok kode baru
