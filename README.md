<h1 align="center">Belajar Laravel 8</h1>

-   [x] Level Dasar
-   [x] PHP min versi 7.4 terinstall
-   [x] Composer terinstall

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
1.  Routes dengan variabel
    ```php
        Route::get('posts/{slug}', function () {
            return view('post');
        });
    ```

## Mengirim data

1.  Langsung dari Route

    Didalam Route

    ```php
        Route::get('/', function () {
            return view('welcome', [
                "name" => "Deocoding",
                "email" => "deocoding@gmail.com"
            ]);
        });
    ```

    Diluar Route

    ```php
        Route::get('/', function () {
            $data = [
                "var1" => "isi_data_var1",
                "var2" => "isi_data_var2"
            ];

            return view('welcome', [
                "name" => "Deocoding",
                "data" => $data
            ]);
        });
    ```

1.  Dari Controller (Recommended)

    ```php
        Route::get('/', function () {
            return view('welcome', [
                "name" => "Deocoding",
                "email" => "deocoding@gmail.com"
            ]);
        });
    ```

## Menampilkan data

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
-   Jika ada komponen yang ingin dimasukkan, misalnya `partials/navbar.blade.php` maka gunakan format :

    ```php
        <html>
            <head>
                <!-- isi head -->
            </head>
            <body>
                @include('partials.navbar')

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

## Format Conditional IF Ternary

Untuk menentukan navigasi active

```php
    ($title === "Home") ? 'active' : ''
```

## Die $ Dump

Untuk melakukan pengetesan data

```php
    @dd($data)
```

## Pemisahan Kode Berdasarkan Konsep MVC

Untuk melakukan pengetesan data

```php
    @dd($data)
```
