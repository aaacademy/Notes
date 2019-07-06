# Laravel Intro

## Cara Install

```bash
composer create-project --prefer-dist laravel/laravel learnLara
```

## Cara menjalankan server local
```bash
php artisan serve
```

## Lakukan Migrate Untuk Pertamakali

Jika error, maka setting database dengan kode berikut pada **`App\Provider\AppServiceProvider.php`**
```php
<?php

namespace App\Providers;

use Illuminate\Support\ServiceProvider;
use Illuminate\Support\Facades\Schema; // Tambah ini

class AppServiceProvider extends ServiceProvider
{
    /**
     * Register any application services.
     *
     * @return void
     */
    public function register()
    {
        //
    }

    /**
     * Bootstrap any application services.
     *
     * @return void
     */
    public function boot()
    {
        Schema::defaultStringLength(191); // Tambah ini
    }
}
```
