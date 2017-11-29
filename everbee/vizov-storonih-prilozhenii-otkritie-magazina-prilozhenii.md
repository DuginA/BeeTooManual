# Открыть стороннее приложение или магазин приложений \(AppStore, Google.Play\)

Вызов приложения и открытие магазина приложений на странице приложения осуществляется...

## window.plugins.launcher 

бла

## window.plugins.market

бла

## Package id

Чтобы найти package id...

Подробнее можно прочитать в статье: [http://niranjankaru.blogspot.ru/2014/02/get-package-name-android-app-app-id-ios.html](http://niranjankaru.blogspot.ru/2014/02/get-package-name-android-app-app-id-ios.html)

## Пример

```js
if ($ionicPlatform.is('ios')) {
    window.plugins.launcher.canLaunch({packageName: '950377168'}, function () {
        window.plugins.launcher.launch({packageName: '950377168'});
    }, function () {
        window.plugins.market.open('950377168');
    });
} else if ($ionicPlatform.is('android')) {
    window.plugins.launcher.canLaunch({packageName: 'org.decaflame.app'}, function () {
    window.plugins.launcher.launch({packageName: 'org.decaflame.app'});
    }, function () {
        window.plugins.market.open('950377168');
    });
}
```



