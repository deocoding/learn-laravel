<h1 align="center">Belajar Laravel 8</h1>

-   [x] Level Dasar
-   [x] PHP min versi 7.4 terinstall
-   [x] Composer terinstall

## Instalasi via Composer

```bash
    composer create-project laravel/laravel <nama_folder>

    cd <nama_folder>

    php artisan serve
```

## Instalasi menggunakan Laravel Installer

Install global Composer dependensi :

```bash
    composer global require laravel/installer
```

Pastikan meletakkan direktori bin milik Composer pada `$PATH` sehingga `laravel` dapat dieksekusi secara mandiri oleh sistem. Direktori ini terletak pada lokasi yang berbeda tergantung dari Sistem Operasi yang digunakan :

-   macOS: `$HOME/.composer/vendor/bin`
-   Windows: `%USERPROFILE%\AppData\Roaming\Composer\vendor\bin`
-   GNU / Linux Distributions: `$HOME/.config/composer/vendor/bin` or `$HOME/.composer/vendor/bin`

Kemudian jalankan perintah berikut untuk instalasi laravel :

```bash
    laravel new <nama_folder>

    cd <nama_folder>

    php artisan serve
```

## Setting file .env

```bash
    APP_URL=http://127.0.0.1:8000/
```

## Tipe-tipe Routes Web

1.  Routes untuk menampilkan View
    ```php
        Route::get('/', function () {
            return view('welcome');
        });
    ```
1.  Routes untuk menampilkan String
    ```php
        Route::get('/', function () {
            return 'Kata';
        });
    ```

## Mengirim data

1.  Langsung dari Route

    ```php
        Route::get('/', function () {
            return view('welcome', [
                "name" => "Deocoding",
                "email" => "deocoding@gmail.com"
            ]);
        });
    ```

    Menampilkan data

    ```php
        <h3>{{ $name }}</h3>
        <p>{{ $email }}</p>
    ```

## Blade Templating Engine

-   Buat folder baru di views, yaitu folder `layouts`.
-   Buat file `guest.blade.php` didalam folder layout, dengan format :
    ```php
        <html>
            <head>
                <!-- isi head -->
            </head>
            <body>
                @yield('content')
            </body>
        </html>
    ```
-   Buat folder baru di views, yaitu folder `guest` untuk meletekan file-file untuk guest.
-   Buat file `home.blade.php` didalam folder guest, dengan format :
    ```php
        @extends('layouts.guest')

        @section('content')
            <!-- isi content home -->
        @endsection
    ```
