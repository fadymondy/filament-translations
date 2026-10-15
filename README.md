![Screenshot of Login](./arts/screenshot.png)

# Filament Translations

Manage your translation with DB and cache, you can scan your languages tags like `trans()`, `__()`, and get the string inside and translate them use UI.

this plugin is build in [spatie/laravel-translation-loader](https://github.com/spatie/laravel-translation-loader)

## Screenshots

![Screenshot of list](./arts/list.png)
![Screenshot of settings](./arts/setting.png)
![Screenshot of edit](./arts/edit.png)


## Installation

You can install the package via composer:

```bash
composer require 3x1io/filament-translations
```

Run migration:

```bash
php artisan vendor:publish --tag="filament-translations"
php artisan vendor:publish --tag="filament-translations-config"
php artisan migrate
```

In `config/app.php` (Laravel) or `bootstrap/app.php` (Lumen) you should replace Laravel's translation service provider

```php
Illuminate\Translation\TranslationServiceProvider::class,
```

by the one included in this package:

```php
Spatie\TranslationLoader\TranslationServiceProvider::class,
```

## Add Language Middleware

go to app/Http/Kernel.php and add new middleware to $middlewareGroups

```php
    'web' => [
        //...
        \io3x1\FilamentTranslations\Http\Middleware\LanguageMiddleware::class,
    ],
```

go to config/filament.php and add middleware to middleware auth array

```php
    'middleware' => [
        'auth' => [
            //...
            \io3x1\FilamentTranslations\Http\Middleware\LanguageMiddleware::class
        ],
        //...
    ];
```

and now clear cache

```bash
php artisan optimize:clear
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Credits

-   [Fady Mondy](https://github.com/3x1io)

## Follow the build

Built in public by **[Fady Mondy](https://github.com/fadymondy)** (فادي مندي): open source, AI agents & MCP, Laravel and Go.
Release notes, deep-dives and behind-the-scenes go out here first:

[![Follow on X](https://img.shields.io/badge/X-@fadymondy-0B1429?style=flat-square&logo=x&logoColor=E2661C)](https://x.com/fadymondy)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Fady%20Mondy-0B1429?style=flat-square&logo=linkedin&logoColor=E2661C)](https://www.linkedin.com/in/fadymondy/)
[![YouTube](https://img.shields.io/badge/YouTube-@FadyMondy-0B1429?style=flat-square&logo=youtube&logoColor=E2661C)](https://www.youtube.com/@FadyMondy?sub_confirmation=1)
[![Bluesky](https://img.shields.io/badge/Bluesky-fadymondy-0B1429?style=flat-square&logo=bluesky&logoColor=E2661C)](https://bsky.app/profile/fadymondy.bsky.social)
[![Threads](https://img.shields.io/badge/Threads-@engfadymondy-0B1429?style=flat-square&logo=threads&logoColor=E2661C)](https://www.threads.com/@engfadymondy)
[![GitHub followers](https://img.shields.io/github/followers/fadymondy?label=Follow&style=flat-square&logo=github&color=0B1429&logoColor=E2661C)](https://github.com/fadymondy)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
