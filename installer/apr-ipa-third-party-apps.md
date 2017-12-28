# Приложения для мобильных платформ

Как и для большого компьютера \(PC\), приложения для мобильных устройств поставляются одним установочным файлом. Именно этот файл скачивается из магазина приложений.

* для Andoid файлы `*.apk`
* для iOs файлы `*.ipa`

# Зачем качать эти файлы?

Установочный файл можно легко открыть архиватором и внутри обнаружить файлы и директории.

Любое приложение состоит из:

* исполняемый код, скомпилированный под данную платформу
* статические ресурсы: картинки, аудио файлы, шрифты и т.д.
* файлы метаданных описания приложения и его возможностей:
  * для Android файл `AndroidManifest.xml`
  * для iOs файл `Info.plist`

Исходя из структуры директорий и ресурсов можно определить технологию, на основе которой сделано приложение:

* классическое натиное приложение
* Android NDK приложение
* гибридное приложение
* read native / NativeScript приложение
* и так далее

Что более важно, в файле описания описания метаданных приложения можно прочитать о характерных особенностях приложения, например, Custom URL scheme:

* [iOs Custom URL introduction](https://developer.apple.com/library/content/featuredarticles/iPhoneURLScheme_Reference/Introduction/Introduction.html#//apple_ref/doc/uid/TP40007899-CH1-SW1)
* [Android Custom URL introduction](https://developer.android.com/training/basics/intents/sending.html?hl=ru#Build)

# Скачать файл приложения

## Android APK

Достаточно воспользоваться бесплатным сервисом \(сайтом\) [PureAPK](https://apkpure.com), рже можно найти любое приложение из магазина Google.Play. Для этого, воспользуйтесь поиском на сайте [https://apkpure.com](https://apkpure.com).

## iOs IPA

Чтобы скачать IPA файл потребуется:

* аккаунт AppleID
* компьютер с macOs
* бесплатная программа Apple Configurator 2
* устройство с iOs

Установим приложение Apple Configurator 2 при помощи AppStore:

![](/assets/Снимок экрана 2017-12-21 в 13.41.07.png)Подключите устройство iOs по USB компьютеру с macOs и нажите "Доверять этому компьютеру" во всплывающем окне на экране устройства \(если вы подключили впервые\).

Откройте Apple Configurator, вы увидите ваше устройство.

![](/assets/Снимок экрана 2017-12-21 в 13.52.32.png)Залогиньтесь в программе Apple Configurator под тем же AppleId, который используется на данном iOs устройстве.

Кнопка входа вызывается из главного меню \(вверху экрана\), пункт меню **Account**.

![](/assets/Снимок экрана 2017-12-21 в 13.53.09.png)

Нажмите зеленую кнопку "Add" для установки приложения на iOs устройтво прямо из Apple Configurator:![](/assets/Снимок экрана 2017-12-21 в 13.52.38.png)Выбираете интересующее вас приложение.

**ВАЖНО: это приложение уже должно быть установлено на устройстве!**

![](/assets/Снимок экрана 2017-12-21 в 13.54.08.png)Выберите приложение, нажмите "Add" в правом нижнем углу окна.

Начнется установка:![](/assets/Снимок экрана 2017-12-21 в 13.54.17.png)И остановится со следующим предупреждением:![](/assets/Снимок экрана 2017-12-21 в 13.57.13.png)**ВАЖНО: не нажимайте ни один из предложенных вариантов. Оставьте данное окно открытым.**

Откройте фалойвый менеджер "Finder" в следующей директории: `/Users/example_user/Library/Group Containers/K36BKF7T3D.group.com.apple.configurator/Library/Caches/Assets/TemporaryItems/MobileApps`

В данной директории будет одна или несколько директорий с именем, похожим на `99502DFC-BC70-4694-A2D0-1BB695BB0164/843129434`.

Содержимое директории выглядит следующим образом:![](/assets/Снимок экрана 2017-12-21 в 14.02.08.png)Переименуем файл `ipa` в `zip` и разархивируем:![](/assets/Снимок экрана 2017-12-21 в 14.02.38.png)Внутри распакованного архива есть поддиректория Payload, в ней лежит распакованная структура всего содержимого приложения, целый набор файлов. Если в директории лежит один файл \(например, с именем `AMP`\), тогда необходимо в контекстном меню вызывать "Показать содержимое пакета":

![](/assets/Снимок экрана 2017-12-21 в 14.04.01.png)

Внутри можно найти файл `Info.plist`:![](/assets/Снимок экрана 2017-12-21 в 14.04.45.png)Откроем его любым текстовым редактором:

![](/assets/Снимок экрана 2017-12-21 в 14.05.10.png)

И найдем раздел конфигурации `CFBundleURLTypes`:

![](/assets/Снимок экрана 2017-12-21 в 14.06.30.png)

Каждый из параметров `CFBundleURLSchemes` определяет Custom URL scheme, с которой может быть вызвано данное приложение. Из предыдущего экрана видно, что указаны следующие `uri`:

* `heosbydenon://`
* `heoscompanion://`
* `heosbydenonoauth://`
* `heosbydenondiscoverytest://`

Раздела `CFBundleURLSchemes` может и не оказаться в `Info.plist`. Это означает, что приложение не может быть вызвано через custom url scheme.
