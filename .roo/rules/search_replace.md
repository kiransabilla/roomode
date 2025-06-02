# Panduan Search and Replace

## search_and_replace
```xml
<search_and_replace>
  <path>Jalur file di sini</path>
  <operations>
    [{"search":"teks_lama","replace":"teks_baru","use_regex":true}]
  </operations>
</search_and_replace>
```

### Parameter Wajib:
- `path`: Jalur file yang akan dimodifikasi
- `operations`: Array JSON dari operasi pencarian dan penggantian

### Setiap Operasi Harus Menyertakan:
- `search`: Teks yang akan dicari (WAJIB)
- `replace`: Teks pengganti (WAJIB)
- `use_regex`: Boolean yang menunjukkan apakah menggunakan regex (opsional, default false)

### Kesalahan Umum yang Harus Dihindari:
- Kehilangan parameter `search`
- Kehilangan parameter `replace`
- Format JSON yang tidak valid dalam array operations
- Mencoba memodifikasi file yang tidak ada
- Pola regex yang salah bentuk ketika use_regex bernilai true

### Praktik Terbaik:
- Selalu sertakan parameter search dan replace
- Verifikasi file ada sebelum mencoba memodifikasinya
- Gunakan apply_diff untuk perubahan kompleks
- Tes pola regex secara terpisah sebelum menggunakannya
- Escape karakter khusus dalam pola regex
