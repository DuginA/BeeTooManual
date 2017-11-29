# Открыть стороннее приложение или магазин приложений \(AppStore, Google.Play\)

Вызов приложения и открытие магазина приложений осуществляется через плагины `window.plugins.launcher` и `window.plugins.market`** **посредством** **`package id (package name)`приложения. 

Запускаемое приложение имеет свой `package id`**.**

## window.plugins.launcher

Плагин запускает приложение на устройстве при нажатии соответствующей кнопки в интерфейсе.

## window.plugins.market

Плагин открывает магазин приложений при нажатии соответствующей кнопки на интерфейсе устройства.

## Package id

Чтобы найти `package id`, зайдите в браузере в магазин приложений. Найдите необходимое приложение. 

`package id `указан в** URL-адресе** приложения.

В Google.Play `package id` - начинается после "**id**" и продолжается либо до конца адреса **URL**, либо заканчивается перед "**&**".

В AppStore `package id` - начинается после "**id**" и продолжается либо до конца адреса **URL**, либо заканчивается перед "**?**".

**Пример: **`package id`для приложения _musiccast_ по адресу [https://itunes.apple.com/ru/app/musiccast-controller/id1012248381?mt=8](https://itunes.apple.com/ru/app/musiccast-controller/id1012248381?mt=8) является "**1012248381**".

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
        window.plugins.market.open('org.decaflame.app');
    });
}
```



