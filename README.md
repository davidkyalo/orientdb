
# Orientdb Driver for Laravel 4


Orientdb Graph Eloquent Driver for Laravel 4

## Quick Reference

 - [Installation](#installation)
 - [Configuration](#configuration)
 - [Migration](#migration)

## Installation

Add the package to your `composer.json` and run `composer update`.

```json
{
    "require": {
        "sgpatil/orientdb": "@dev"
    }
}
```

Add the service provider in `app/config/app.php`:

```php
'Sgpatil\Orientdb\OrientdbServiceProvider',
```

This will register all the required classes for this package.

## Database Configuration

Open `app/config/database.php`
make `orientdb` your default connection:

```php
'default' => 'orientdb',
```

Add the connection defaults:

```php
'connections' => [
    'orientdb' => [
        'driver' => 'orientdb',
        'host'   => 'localhost',
        'port'   => '2480',
        'database' => 'database_name',
        'username' => 'root',
        'password' => 'root'
    ]
]
```

Add your database username and password in 'username' and 'password' field. In 'database_name' add name of orientdb database which you want to connect and use.

## Migration

To create a migration, you may use the orientdb:migration command on the Artisan CLI:

```php
php artisan orientdb:migration create_users_table
```

The migration will be placed in your database/migrations folder, and will contain a timestamp which allows the framework to determine the order of the migrations.

The --table and --create options may also be used to indicate the name of the table, and whether the migration will be creating a new table:
```php
php artisan orientdb:migration add_votes_to_users_table --table=users

php artisan orientdb:migration create_users_table --create=users
```
To run migration 
```php
php artisan migrate
```
