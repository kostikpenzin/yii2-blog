Blog module for Yii2
====================
Blog module for Yii2

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist it-yakutia/yii2-blog "*"
```

or add

```
"it-yakutia/yii2-blog": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply add in your console config:

```php
'controllerMap' => [
    /* ... */
    'migrate' => [
            // 'class' => 'yii\console\controllers\MigrateController',
            'migrationPath' => [
                // '@console/migrations', // yii migrate/create app_init
                // '@yii/rbac/migrations',
                /* ... */
                '@it-yakutia/blog/migrations', // yii migrate/create add_some_table --migrationPath=@it-yakutia/blog/migrations
            ],
    ],
],
```

And just run the command:
```
php yii migrate
```

Set in common config params:

```php
return [
    /* ... */
    'domain' => 'https://yourdomain.example',
];
```

Add urls in your backend project:

```php
Url::toRoute('/blog/back/index');
```

Add RBAC roles:

```
blog
```

Custom view file:

```
'custom_view_for_modules' => [
    'article_front' => [
        'view' => '@frontend/views/front_page/view',
    ],
],
```