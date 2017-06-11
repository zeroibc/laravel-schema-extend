laravel-schema-extend
=====================

- support MySQL 'table comment'.
- 'column comment' is built-in in greater than 5.1 version.
- support variable length for integer/tinyint/mediumint/smallint/bigint

---

> just extend the original class  


## Install

Require this package with composer using the following command:

```bash
composer require zedisdog/laravel-schema-extend
```


modify the alias `Schema` in `config/app.php`:

```php
'aliases' => [
    ...
    // 'Schema' => Illuminate\Support\Facades\Schema::class,
    'Schema'    => Jialeo\LaravelSchemaExtend\Schema::class,
],
```

## Usage

```php
Schema::create('tests', function ($table) {
    //this is alredy built-in.
    $table->increments('id')->comment('column comment');
    
    $table->integer('int')->default(1)->length(1);
    $table->bigInteger('big')->default(1)->length(1);
    $table->smallInteger('small')->default(1)->length(1);
    $table->tinyInteger('tiny')->default(1)->length(1);
    $table->mediumInteger('medium')->default(1)->length(1);
    
    $table->comment = 'table comment';
});
```

## Thanks

- [jialeo](https://github.com/jialeo)
- [ghostboyzone](https://github.com/ghostboyzone)
- [xuhuan](https://github.com/xuhuan)
- [xiaobeicn](https://github.com/xiaobeicn)
- [5-say](https://github.com/5-say)


## PS.
sorry for my bad english