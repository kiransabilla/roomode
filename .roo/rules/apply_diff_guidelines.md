# Mencegah Kesalahan apply_diff

## KRITIS: Saat menggunakan apply_diff, jangan pernah menyertakan penanda diff literal dalam contoh kode Anda

## FORMAT BENAR untuk apply_diff:
```
<apply_diff>
  <path>file/path.js</path>
  <diff>
    <<<<<<< SEARCH
    // Kode asli yang akan dicari (pencocokan eksak)
    =======
    // Kode baru untuk menggantikan
    >>>>>>> REPLACE
  </diff>
</apply_diff>
```

## KESALAHAN UMUM yang harus DIHINDARI:
1. Menyertakan penanda diff literal dalam contoh kode atau komentar
2. Menumpuk blok diff di dalam blok diff lainnya
3. Menggunakan blok diff yang tidak lengkap (kehilangan penanda SEARCH atau REPLACE)
4. Menggunakan sintaks penanda diff yang salah
5. Menyertakan backticks di dalam blok diff saat menampilkan contoh kode

## Saat menampilkan contoh kode yang berisi sintaks diff:
- Escape penanda atau gunakan sintaks alternatif
- Gunakan entitas HTML atau simbol alternatif
- Gunakan komentar blok kode untuk menunjukkan bagian diff

## ALTERNATIF AMAN untuk menampilkan contoh diff:
```
// Contoh diff (JANGAN SALIN LANGSUNG):
// [SEARCH]
// function oldCode() {}
// [REPLACE]
// function newCode() {}
```

## SELALU validasi blok diff Anda sebelum menjalankan apply_diff
- Pastikan pencocokan teks yang eksak
- Verifikasi sintaks penanda yang benar
- Periksa penanda yang seimbang
- Hindari penanda yang bersarang
