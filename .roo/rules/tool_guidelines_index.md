# Indeks Panduan Penggunaan Alat

Untuk mencegah kesalahan umum saat menggunakan alat, rujuk panduan terperinci ini:

## Operasi File
- [Panduan Operasi File](.roo/rules-code/file_operations.md) - Panduan untuk read_file, write_to_file, dan list_files

## Pengeditan Kode
- [Panduan Pengeditan Kode](.roo/rules-code/code_editing.md) - Panduan untuk apply_diff
- [Panduan Search and Replace](.roo/rules-code/search_replace.md) - Panduan untuk search_and_replace
- [Panduan Insert Content](.roo/rules-code/insert_content.md) - Panduan untuk insert_content

## Pencegahan Kesalahan Umum
- [Pencegahan Kesalahan apply_diff](.roo/rules-code/apply_diff_guidelines.md) - Panduan khusus untuk mencegah kesalahan dengan apply_diff

## Poin Penting yang Harus Diingat:
1. Selalu sertakan semua parameter wajib untuk setiap alat
2. Verifikasi keberadaan file sebelum mencoba modifikasi
3. Untuk apply_diff, jangan pernah menyertakan penanda diff literal dalam contoh kode
4. Untuk search_and_replace, selalu sertakan parameter search dan replace
5. Untuk write_to_file, selalu sertakan parameter line_count
6. Untuk insert_content, selalu sertakan start_line dan content yang valid dalam array operations
