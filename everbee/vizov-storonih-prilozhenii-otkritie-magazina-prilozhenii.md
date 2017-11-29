```
Вызов приложения и открытие магазина приложений на странице приложения
```

Чтобы найти package id...

http://niranjankaru.blogspot.ru/2014/02/get-package-name-android-app-app-id-ios.html



```js
if ($ionicPlatform.is('ios')) {
    window.plugins.launcher.canLaunch({packageName: '950377168'}, function () {
        window.plugins.launcher.launch({packageName: '950377168'});
    }, function () {
        window.plugins.market.open('950377168');
    });
} else if ($ionicPlatform.is('android')) {
    window.plugins.launcher.canLaunch({packageName: '950377168'}, function () {
    window.plugins.launcher.launch({packageName: '950377168'});
    }, function () {
        window.plugins.market.open('950377168');
    });
}
```



