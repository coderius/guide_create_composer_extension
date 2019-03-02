Инструкяция по созданию расширения.
===================================
_Создание расширения на примере расширения для yii2._

1. Создаем файл *composer.json* в корне расширения примерно такого плана:
```javascript
{
    "name": "coderius/yii2-lightbox2-widget",
    "description": "Yii 2 lightbox2-widget",
    "version": "1.0.0",
    "keywords": ["lightbox", "widget", "lightbox2", "yii2"],
    "type": "yii2-extension",
    "license": "MIT",
    "authors": [
        {
            "name": "Serg Coderius",
            "email": "sunrise4fun@gmail.com"
        }
    ],
    
    "require": {
        "php": ">=5.4.0",
        "yiisoft/yii2": "~2.0.0"
        
    },
    "require-dev": {
        "phpunit/phpunit": "*"
    },
    "autoload": {
        "psr-4": {
            "coderius\\lightbox2\\": "src/"
        }
    },
    "repositories": [
        {
            "type": "path",
            "url": "/opt/lampp/htdocs/yii2-extentions/yii2-lightbox2-widget"
        }
        
    ]
}

```
Для того, чтобы подключать расширение из локального компьютера (во время разработки) - указываем нужный адрес, где расширение 
расположено.

```javascript
"repositories": [
        {
            "type": "path",
            "url": "/opt/lampp/htdocs/yii2-extentions/yii2-lightbox2-widget"
        }
        
    ]
```
Также нужно указать версию как в примере.

2.Инициализируем git 
*
git init .
git add .
git commit -m "Commit"
*

3. В папке проекта yii2 в файле _composer.json_, куда включаем пакет добавляем:
```javascript
"repositories": [
        
        {
            "type": "path",
            "url": "/opt/lampp/htdocs/yii2-extentions/yii2-lightbox2-widget"
        }
        
    ], 
```
4.Переходим в консоли в папку проекта yii2, для которого подключаем расширение.
5.Устанавливаем пакет из локального компьютера:
```
composer clear-cache
composer require "coderius/yii2-lightbox2-widget" "*"
```    
6.Возможно расширение будет содержать зависимости из bower (например, какие-то скрипты типа jquery).
Для того, чтобы включить в composer.json расширения скрипты из bower нужно:
*Установить bower-asset плагин для взаимодействия с [https://asset-packagist.org](https://asset-packagist.org)
_Не забыть выполнить комманду *composer global require "fxp/composer-asset-plugin:^1.2.0"* для 
 установки плагина_
 * Также возможно нужно указать папки для хранения скриптов в проекте:
 ```
 "config": {
        "fxp-asset": {
            "installer-paths": {
                "npm-asset-library": "vendor/npm",
                "bower-asset-library": "vendor/bower"
            }
        }
    },
```   