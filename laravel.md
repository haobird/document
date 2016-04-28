## some document


### 获取框架版本

```
composer create-project laravel/laravel=5.1.* --prefer-dist
```

### 框架使用帮助

##### 生成Model包括migration

`php artisan make:model Model/User --migration`

##### 生成控制器

`php artisan make:controller Back/UserController`

*注：--plain 命令用于创建一个空的控制器而不是标准的 RESTful 风格控制器。*

##### 生成随机数据

`php artisan make:seeder PostTableSeeder`

##### 重新建表

`php artisan migrate:refresh`

##### 重新建表并填充数据

`php artisan migrate:refresh --seed`

##### 填充数据

`php artisan db:seed`

##### 使用中间件需要在app\Http\Kernel.php中添加

`'role' => \App\Http\Middleware\RoleMiddleware::class,`

##### 有外键索引的情况下清空数据表的方法语句

```
DB::statement('SET FOREIGN_KEY_CHECKS=0;');
App\Models\Post::truncate();
DB::statement('SET FOREIGN_KEY_CHECKS=1;');
```

### 框架配置遇到的各种问题

#### Composer 相关问题

##### 问题代码:

```
The following exception is caused by a lack of memory and not having swap configured
Check https://getcomposer.org/doc/articles/troubleshooting.md#proc-open-fork-failed-errors for details
PHP Fatal error:  Uncaught exception 'ErrorException' with message 'proc_open(): fork failed - Cannot allocate memory' in phar:///usr/local/bin/composer/vendor/symfony/console/Symfony/Component/Console/Application.php:974
Stack trace:
解决方法：依次运行三条命令
sudo dd if=/dev/zero of=/swapfile bs=1024 count=512k
mkswap /swapfile
swapon /swapfile
```

##### 问题代码:

```
Loading composer repositories with package information Updating dependencies (including require-dev)
Fatal error: Allowed memory size of 536870912 bytes exhausted (tried to allocate 67108864 bytes) in phar:///usr/local/Cellar/composer/1.0.0-alpha8/libexec/composer.phar/src/Composer/DependencyResolver/Solver.php on line 170
解决：
php -dmemory_limit=1G /usr/local/bin/composer update
或者
php -dmemory_limit=1G /usr/local/bin/composer install
```

##### 问题:

<https://laracasts.com/discuss/channels/laravel/composer-update-error-5>

```
The following exception is caused by a lack of memory and not having swap configured
Check https://getcomposer.org/doc/articles/troubleshooting.md#proc-open-fork-failed-errors for details
解决方法：sudo composer update -vvv —profile
php -d memory_limit=-1 /usr/local/bin/composer update
```

##### 问题：

```
使用composer 安装lumen 项目，执行composer create-project laravel/lumen --prefer-dist，命令报 [ErrorException]    zlib_decode(): data error 错
解决办法：执行 composer self-update 即可
```

#### Node 错误

##### 

```
问题1：npm WARN optional dep failed, continuing fsevents@1.0.6
解决：npm install -g npm@3.3.12
```

#### phpinit 错误问题

```
解决：
rm -rf vendor/bin vendor/classpreloader vendor/phpspec vendor/phpunit vendor/psy
然后  composer install
```

#### bower 的权限问题

```
问题：bower ESUDO         Cannot be run with sudo 
解决：sudo bower install jquery bootstrap --save --allow-root
```

#### 


