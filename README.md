# Contoh Menggunakan Composer, PSR4 & Unit Test 

Ini adalah proyek contoh sederhana tentang bagaimana membuat dan menggunakan sebuah package menggunakan PHP Composer, PSR4 dan Unit test.

Untuk menggunakan package ini anda memerlukan software:

* [Git](https://git-scm.com/downloads)
* [Composer](https://getcomposer.org/download/)
* PHP minimal versi 5.4

Untuk mempelajari contoh ini, silahkan clone dengan cara:

```sh
git clone git@github.com:jauharimalik/belajarcomposer.git
```

atau dengan cara [download](https://github.com/jauharimalik/belajarcomposer/).


## Cara menggunakan package

### Membuat composer.json

Buatlah sebuah folder misalnya `demo_kalkulator`, kemudian buatlah sebuah file dengan nama `composer.json` dengan isi seperti ini:

```json
{
    "name": "demo/belajarcomposer",
    "description": "Coba composer",
    "require-dev": {
        "phpunit/phpunit": "4.0.*"
    },
    "require": {
        "jauharimalik/belajarcomposer": "dev-master"
    },
    "authors": [
        {
            "name": "jauharimalik",
            "email": "jauharimalikupil@gmail.com"
        }
    ],
    "minimum-stability": "dev"
}

``` 

### Membuat file index.php

Masih dalam folder `demo_kalkulator`, buatlah sebuah file baru dengan nama `index.php` dengan isi sebagai berikut:

```php
<?php

require_once __DIR__ .'/vendor/autoload.php';

use Jauharimalik\Belajarcomposer\ujicoba1;

$o = new ujicoba1;

echo "<html><body style='margin:30px;font-family:sans-serif;font-size:1.25rem'>";

echo "<h3>Demo Kalkulator dengan Composer</h3>";
echo "<pre>";
echo "100 + 5 = ". $o->tambah(100,5)."<br/>";
echo "100 - 5 = ". $o->kurang(100,5)."<br/>";
echo "100 * 5 = ". $o->kali(100,5)."<br/>";
echo "100 / 5 = ". $o->bagi(100,5);
echo "</pre>";
echo "</body></html>";
```

## Jalankan composer
Masih dalam folder `Belajarcomposer`, jalankan composer dengan perintah:
```sh
composer install
```
Anda harus terhubung dengan internet untuk menjalankan perintah composer ini, dan akan membutuhkan waktu beberapa menit, tergantung kecepatan koneksi internet anda.

Composer akan otomatis mendownload package ini (`komputronika/kalkulator`) dan package-package yang dibutuhkan ke dalam folder `vendor`,  sesuai dengan yang dituliskan pada file `composer.json`.

Struktur folder di dalam `demo_kalkulator` akan seperti ini:

```
.
├── composer.json
├── composer.lock
├── index.php
└── vendor
    ├── autoload.php
    ├── bin
    ├── composer
    ├── belajarcomposer
    ├── phpunit
    ├── sebastian
    └── symfony
```

## Test di browser

Buka browser anda pada alamat `http://localhost/belajarcomposer`

Kalau instalasi anda sudah benar, maka tampilan di browser akan seperti ini:

```
Demo Kalkulator dengan Composer

100 + 5 = 105
100 - 5 = 95
100 * 5 = 500
100 / 5 = 20
```
---




