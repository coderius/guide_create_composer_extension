Инструкяция по созданию расширения.
===================================
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
    
