# Absen Digital Codeigniter 3
 
Absen digital menggunakan Codeigniter 3 ini merupakan sebuah project saya yang telah dibuat pada saat saya memiliki waktu luang mungkin aplikasi ini tidak 100% complete dan masih ada
terjadinya bug pada aplikasi ini tetapi saya tetap berusaha untuk memperbaiki celah tersebut sebisa mungkin.

## Fitur

Fitur Yang Tersedia Pada Aplikasi Ini:
- ~~Absen Scan Barcode (Instant Absen [Beta])~~ [Removed Temporary]
- Remember Me
- Custom Setting Aplikasi
- Informasi Pada Saat Absen
- Sistem Login
- Export Absen (Support PDF & Excel)
- Absensi Dengan Maps (Beta)


## Issues
- Terdapat sedikit bug pada absensi
- Untuk fitur seperti scan barcode dan absen menggunakan lokasi diharuskan untuk menggunakan protokol HTTPS bukan HTTP dengan keamanan SSL pada web server
dikarena kebijakan keamanan terbaru dari masing - masing web browser versi saat ini agar fitur tersebut dapat berjalan normal.

## Server Requirement

> - PHP 7.4.8
> - Nginx 1.19.1 Or Apache 2.4.46
> - MariaDB 10.4.13

## Login Account (Default)

> - Username: admin
> - Password: 12345678

## Setting Database
Untuk menyesuaikan pengaturan pada database anda silakan dibuka:
> absendigital/application/config/database.php

Silakan ubah beberapa config ini saja untuk disesuaikan dengan pengaturan database anda:
```
'hostname' => 'localhost', |Ubah kolom hostname ini dengan url hostname database anda
	'username' => 'root', |Ubah kolom username ini jika berbeda
	'password' => '', |Ubah kolom password ini jika database anda mempunyai password
	'database' => 'absensi_online', |default (jika ada kesamaan nama pada nama database ini dengan yang hasil import silakan diubah)
```

## Demo / Screenshot
![Login Page](https://github.com/sandyh90/Codeigniter3-absen-digital/blob/master/images-demo/Screenshot_2021-02-03%20Login%20Absensi.png)
![Front Page](https://github.com/sandyh90/Codeigniter3-absen-digital/blob/master/images-demo/Screenshot_2020-09-12%20Absensi%20Online.png)

Ingin mencoba aplikasi web ini silakan kunjungi

[Demo Web](http://demo.nerosky.rf.gd/absendigitalci3/)

## Alasan Memakai Folder Public

Mengapa saya pindahkan untuk file index.php ke folder public dengan alasan untuk keamanan pada data sistem aplikasi ini, mungkin ini tidak begitu efektif tetapi ini sangat berguna untuk menghindari hal - hal yang tidak diinginkan dan juga
ini bukan cara yang paling akurat menurut saya 

Note: jika anda ingin tidak memakai folder public anda bisa pindahkan semua isi didalam folder public ke folder root aplikasi dan jangan lupa untuk mengganti path filenya dan cari confignya seperti ini pada file **index.php**.

```
/*
 *---------------------------------------------------------------
 * SYSTEM DIRECTORY NAME
 *---------------------------------------------------------------
 *
 * This variable must contain the name of your "system" directory.
 * Set the path if it is not in the same directory as this file.
 */
	$system_path = 'system'; <-- Sebelumnya ../system

/*
 *---------------------------------------------------------------
 * APPLICATION DIRECTORY NAME
 *---------------------------------------------------------------
 *
 * If you want this front controller to use a different "application"
 * directory than the default one you can set its name here. The directory
 * can also be renamed or relocated anywhere on your server. If you do,
 * use an absolute (full) server path.
 * For more info please see the user guide:
 *
 * https://codeigniter.com/userguide3/general/managing_apps.html
 *
 * NO TRAILING SLASH!
 */
	$application_folder = 'application'; <-- Sebelumnya ../application
```

Dan jangan lupa mengubah juga path autoloader composer di "**application/config/config.php**" dan cari confignya seperti ini

```
/*
|--------------------------------------------------------------------------
| Composer auto-loading
|--------------------------------------------------------------------------
|
| Enabling this setting will tell CodeIgniter to look for a Composer
| package auto-loader script in application/vendor/autoload.php.
|
|	$config['composer_autoload'] = TRUE;
|
| Or if you have your vendor/ directory located somewhere else, you
| can opt to set a specific path as well:
|
|	$config['composer_autoload'] = '/path/to/vendor/autoload.php';
|
| For more information about Composer, please visit http://getcomposer.org/
|
| Note: This will NOT disable or override the CodeIgniter-specific
|	autoloading (application/config/autoload.php)
*/
$config['composer_autoload'] = 'vendor/autoload.php'; <-- Sebelumnya ../vendor/autoload.php
```

## Change Log
### 9-13-2020
- Export dengan metode excel
- Mengubah bahasa pada datepicker bagian bulan

### 9-15-2020
- Penambahan fitur absensi dengan mengunakan lokasi
- Perbaikan beberapa bug yang telah ditemukan

### 10-05-2020
- Perbaikan bug pada edit user dibagian show password dan keterangan upload
- Penambahan aksi pada list absen bagian pegawai
- Perbaikan pada layout export excel
- Perbaikan beberapa bug yang telah ditemukan 
- Perubahan pada layout halaman setting user

### 11-21-2020
- Penambahan fitur untuk keterangan absen pada saat absen
- Perbaikan lokasi tidak terdeteksi pada fitur instant absen

### 2-3-2021
- Scan barcode pada fitur absensi dihapuskan karena adanya kebijakan baru tentang kebijakan keamanan pada web browser
- Perbaikan pada folder view dikarenakan terjadinya error 404 not found pada saat hosting
- Perubahan layout pada halaman login
- Fitur status Online / Offline pada aplikasi di hapuskan sementara
- Perbaikan pada list user jika hanya ada 1 user administrator tidak bisa dihapus [Tahap Percobaan]
- Perbaikan pada fungsi absen
