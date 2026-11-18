# Pengujian per modul

Jalankan perintah dari direktori utama proyek, tempat `manage.py` berada,
setelah mengaktifkan virtual environment dan memasang dependensi sesuai
[panduan integrasi](integrasi.md#7-migrasi-dan-pengujian). Gunakan konfigurasi
lokal dengan `PRODUCTION=False`.

Perintah berikut memilih tes tanpa browser. Django membuat database pengujian
sementara; hasilnya perlu diperiksa setiap kali perintah dijalankan.

## UserProfile

```powershell
python manage.py test userprofile.tests userprofile.test_auth userprofile.test_profile userprofile.test_delete userprofile.test_integration userprofile.test_migrations --noinput
```

Cakupannya meliputi registrasi, login/logout, perubahan profil, penghapusan akun,
integrasi lintas modul, dan migrasi lokasi bawaan. Lihat juga
[dokumentasi UserProfile](../userprofile/AI_DISCLOSURE.md).

## FoodItem

```powershell
python manage.py test FoodItem.test_integration --noinput
```

Tes integrasi memeriksa inventori milik pengguna, hubungan makanan dengan
penawaran, serta pemrosesan pengingat setelah transaksi berhasil. Berkas
`FoodItem/tests.py` masih berupa kerangka; gunakan `FoodItem.test_integration`
untuk memilih skenario integrasi yang sudah tersedia.
