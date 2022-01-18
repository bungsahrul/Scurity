# Scurityl
Sistem keamanan rumah dengan Raspberry Pi dan mengirim notifikasi dengan bot Telegram
Linter
Tutorial membangun sistem keamanan rumah dengan Raspberry Pi dan mengirim notifikasi dengan bot Telegram.

Bagaimana itu bekerja
Ketika gerakan terdeteksi, aplikasi merekam video yang dikirim ke ponsel Anda oleh bot Telegram.
Setelah diinstal, sistem pengawasan dikelola dari ponsel cerdas Anda dengan perintah bot dari aplikasi Telegram.
Sistem dimulai oleh layanan systemd yang diaktifkan saat boot
Prasyarat.
Modul Kamera Raspberry Pi
Modul sensor gerak PIR
3 kabel jumper wanita-ke-wanita
Tutorial untuk membuat Bot Telegram Anda
Setelah memulai bot di ponsel cerdas Anda, Anda harus mengambil chat_id Anda di alamat berikut:
https://api.telegram.org/bot <token_id>/getUpdates
Hubungkan sensor PIR
gambar

Mempersiapkan
Buka config.pyfile dan konfigurasikan variabel TOKEN_ID dan CHAT_ID dengan token_id dan chat_id Anda
    # Variable to configure
    TOKEN_ID = 'Your token_id'
    CHAT_ID = 'Your chat_id'
Menginstal
Instalasi membutuhkan hak root:

Reboot akan dilakukan di akhir instalasi untuk mengaktifkan perangkat keras kamera

sudo make install
Perintah bot
/start : memulai pengawasan rumah
/stop : hentikan pengawasan rumah
/status : menunjukkan status pengawasan rumah
/foto: mengambil gambar
/video time= : merekam video, penundaan default adalah 60 detik
/clean : hapus semua file di folder video
/help : tunjukkan bantuan
rincian
Secara default, durasi video diatur ke 60 detik. Jika Anda ingin mengubah ini, Anda perlu mengubah konstanta VIDEO_TIME diconfig.py

Dimungkinkan untuk menambahkan perintah lain ke bot di app.py

Pengujian
make test
Copot pemasangan
sudo make uninstall
Reboot akan dilakukan di akhir untuk menonaktifkan perangkat keras kamera

Dibangun Dengan
Perangkat keras:
Raspberry Pi Nol WH
Kamera Inframerah v2 8MP
Modul Sensor Gerak PIR HC-SR501
Perpustakaan:
gpiozero
python-telegram-bot
kamera foto
