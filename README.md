# Rangkuman_Komdat-Jarkom_Pertemuan-Minggu-14

# Transport Layer

![image](https://github.com/user-attachments/assets/235a298a-dc61-40f9-8f69-9bb36beac79b)


Transport Layer adalah lapisan keempat dalam model OSI (Open Systems Interconnection). Fungsinya adalah memastikan pengiriman data yang andal antara aplikasi di perangkat yang berbeda dalam jaringan. Lapisan ini memainkan peran penting dalam komunikasi data end-to-end dengan menyediakan segmentasi, pengendalian koneksi, pengendalian aliran, deteksi kesalahan, dan multiplexing.

## Fungsi Utama Transport Layer

Transport Layer memastikan data dapat dikirim dan diterima dengan benar, lengkap, dan dalam urutan yang sesuai.

1. **Segmentasi dan Reassembly**  
   Transport Layer memecah data besar menjadi segmen kecil (*segmentasi*) agar dapat dikirim melalui jaringan dengan efisien. Di sisi penerima, segmen-segmen ini disusun kembali dalam urutan aslinya (*reassembly*).  
   - **Segmentasi**: Membagi data menjadi segmen agar sesuai dengan batas ukuran jaringan (*Maximum Transmission Unit*). Proses ini mencegah terjadinya pemblokiran pengiriman data.  
   - **Reassembly**: Menyatukan segmen-segmen berdasarkan nomor urutnya sehingga data yang diterima oleh penerima utuh dan sesuai aslinya.

2. **Pengendalian Koneksi**  
   Transport Layer mengelola koneksi komunikasi antara pengirim dan penerima untuk memastikan pengiriman data yang sesuai dengan kebutuhan aplikasi.  
   - Pada protokol *connection-oriented* seperti TCP, koneksi dibangun menggunakan proses *three-way handshake*:  
     - **SYN**: Pengirim meminta koneksi.  
     - **SYN-ACK**: Penerima menyetujui permintaan.  
     - **ACK**: Pengirim mengonfirmasi koneksi sudah siap.  
   - Pada protokol *connectionless* seperti UDP, data langsung dikirim tanpa pembentukan koneksi terlebih dahulu, yang lebih cepat tetapi tanpa jaminan keandalan.

## Pengendalian Aliran dan Kesalahan

![image](https://github.com/user-attachments/assets/34c26f60-5aec-489b-a0f5-b6a0e04d5e63) ![image](https://github.com/user-attachments/assets/ec8d5815-eddb-4ba0-80cf-8fcd0694194c)


Transport Layer mengatur kecepatan pengiriman data agar tidak membebani penerima, serta mendeteksi dan menangani kesalahan selama pengiriman.

1. **Flow Control**  
   Flow control memastikan data tidak dikirim terlalu cepat sehingga penerima bisa memprosesnya tanpa kesalahan.  
   - **Sliding Window**: Pengirim hanya mengirimkan sejumlah segmen sesuai kapasitas penerima. Ketika penerima memproses sebagian data, jendela bergeser untuk memungkinkan lebih banyak data dikirim.  

2. **Error Control**  
   Kesalahan selama pengiriman data dideteksi dan diperbaiki agar data yang diterima tetap valid.  
   - **Checksum**: Digunakan untuk memverifikasi integritas data. Jika nilai checksum tidak cocok, data dianggap rusak.  
   - **Acknowledgment (ACK)**: Digunakan untuk mengonfirmasi segmen yang berhasil diterima. Jika tidak ada ACK, data yang rusak atau hilang akan dikirim ulang.

## Multiplexing

Multiplexing memungkinkan banyak aplikasi untuk menggunakan saluran komunikasi yang sama secara bersamaan. Setiap aplikasi diberi nomor port unik untuk identifikasi.  
- Contoh nomor port:  
  - HTTP menggunakan port 80 untuk komunikasi web.  
  - FTP menggunakan port 21 untuk transfer file.  
  - SMTP menggunakan port 25 untuk pengiriman email.  

## Protokol Utama

Transport Layer mendukung dua protokol utama untuk komunikasi:

1. **Transmission Control Protocol (TCP)**  
   TCP adalah protokol *connection-oriented* yang memastikan pengiriman data yang andal dan berurutan.  
   - TCP cocok untuk aplikasi seperti web browsing dan transfer file, di mana integritas data sangat penting.  

2. **User Datagram Protocol (UDP)**  
   UDP adalah protokol *connectionless* yang lebih cepat karena tidak membutuhkan koneksi terlebih dahulu.  
   - UDP digunakan untuk aplikasi seperti streaming video atau VoIP, yang memprioritaskan kecepatan daripada keandalan.  

## Kesimpulan

Transport Layer adalah komponen penting dalam jaringan komputer. Lapisan ini bertanggung jawab atas segmentasi, pengendalian koneksi, pengendalian aliran, deteksi kesalahan, dan multiplexing. Dengan mendukung protokol TCP untuk keandalan dan UDP untuk kecepatan, Transport Layer menjamin pengiriman data sesuai dengan kebutuhan aplikasi.
