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
