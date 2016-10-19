# EnkripsiDES
---------------------------------------------------------------------------------------------------------------
Membuat Enkripsi dengan menggunakan PHP dan Java
---------------------------------------------------------------------------------------------------------------
Tugas Kelompok kriptografi yang terdiri dari :<br />
Ahmad Raf Sanjani<br />
Kaishananda <br />
Destriyani (1411501792)<br />
Ardha Sena<br />
Agung Yuliyanto (1411502550)<br />

---------------------------------------------------------------------------------------------------------------
Penjelasan Tentang Source Code
---------------------------------------------------------------------------------------------------------------
<h3>Java</h3>
Untuk source code java saya sendiri tidak mengerti bagaimana bisa itu berjalan 
(bukan saya yang mengkoding), tapi :
yang saya simpulkan dari presentasi kemarin adalah program tersebut dapat dengan benar
mempresentasikan hasil dari Enkripsi dan Dekripsi DES.
Dan nilai output (cipherteks) tidak dapat digunakan secara benar bila di copy dan paste
kedalam program (untuk melakukan enkripsi dan dekripsi) secara terpisah.
Jadi program tersebut, setelah melakukan enkripsi dan menampikan hasil, selanjutnya
dilakukan proses dekripsi yang inputnya berasal dari ouput proses enkripsi tersebut.

Untuk permasalahan kemarin, "kenapa harus di modulus 16 untuk menambah sepasi kedalam 
input ", sebenarnya tanpa modulus 16 dan diganti modulus 8 bisa juga (dengan menghilangkan
perkalian kalo tidak salah)
jadi saya akan mengganti pertanyaan tersebut menjadi "kenapa harus di modulus 8"
jawabannya :
menurut saya misal kita inputkan karater berjumlah 15
maka hasil tersebut tidak dapat di olah (15 - 8 = 7) karena kurang 1 karakter lagi.
DES memerlukan input 64 bit dimana tiap 1 karakter mewakili 8 bit (8 karater * 8 bit = 64 bit).

Kita lanjut lagi, input tersebut akan di cek dengan menggunakan modulus 8 (15 mod 8 = 1) maka
input yang akan diolah tiap 8 karakter tersebut, dan input terakhir (input terakhir lah yang pasti
ditambah spasi bila kurang) akan ditambah dengan 1<br />
jadi,<br />
input = 15<br />
dicek (15 mod 8 = 1), jika ya tambahkan "1 spasi"<br />
dimana akan menghasilkan :<br />
input yang diolah (v1) = 8<br />
input yang diolah (v2) = 7 + 1 (spasi)<br />

<h3>PHP</h3>
Untuk PHP, saya yang membuat dan hanya sampai ke proses enkripsi saja, tidak sampai ke proses dekripsi

<b>File :</b><br />
Enkripsi1.php : Berisi form untuk input pesan dan key<br />
SetPesan.php : Berisi fungsi-fungsi untuk melakukan pengolahan enkripsi DES<br />
setting.php : Berisi pengaturan, pengaturan disini maksudnya adalah untuk menghasilkan IP, shift, dll
              (table untuk DES)
<br />setting_box.php : sama dengan setting.php, tapi hanya berisi table sbox (8 buah)<br />

Untuk rincian fungsi-fungsinya (setChr_to_bin, getPC1, dll) saya sarankan untuk membukanya saja
Enkripsi1.php dan SetPesan.php, karena saya sudah beri "//" (untuk memberi komentar di program dalam file .php) 
yang dsampingnya berupa komentar yang akan menjelaskan tiap fungsi tersebut.

NB : setting.php dan setting_box.php jangan diubah, karena pemberian sepasi saja bisa membuat program
     gagal melakukan enkripsi, karena setPesan.php membaca bedasarkan posisi baris dan kolom dalam file 
     tersebut agar dapat menghasilkan keluaran yang diinginkan

Saya melakukan enkripsi mengikuti alur dari video youtube : https://youtu.be/guT-eonams8 dan untuk fungsi
seperti "implode(), ord(), chr(), dll" berasal dari fungsi asli yang berasal dari php (saya gunakan).


---------------------------------------------------------------------------------------------------------------
Konstribusi :
---------------------------------------------------------------------------------------------------------------
Sebenarnya sebelum pertemuan minggu ini (17-10-2016) terjadi. 2 minggu yang lalu sudah diperintahkan akan meng
implementasikan DES, sehingga saya bermaksud membuat DES tersebut dari bahasa PHP.<br />
Tapi selang berapa hari (sebelum pertemuan tanggal 10-10-2016) program sudah jadi dalam bahasa pemrogram Java 
yang dikerjakan oleh teman saya (Enkripsi dan Dekripsi).<br />
Secara otomatis saya bingung "konstribusi apa" yang ada dalam program java tersebut, jadi saya mengambil kesim
pulan, "Kalo gitu saya lebih baik lanjut saja membuat DES tersebut dalam bahasa PHP", dengan maksud sebagai
backup / alternatif saja.<br />
Tapi sampai tanggal pertemuan minggu ini (17-10-2016) saya hanya dapat mengimplementasikan enkripsi DES saja, 
sehingga secara otomatis program dari bahasa Java teman saya yang dipilih untuk di presentasikan kedepan.
