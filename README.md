# Что такое BeeToo.Controller

BeeToo.Controller - это программный продукт для контроля и управления систем автоматизации и IoT.

Контроллер запускается на аппаратной платформе [Raspberry Pi](https://www.raspberrypi.org/) с установленной на ней карточкой, на которой записан образ контроллера \(как записать образ смотреть [здесь](https://www.gitbook.com/book/beetoo/beetoo-help-center/edit#/edit/master/beetoo-controller/howto-burn.md?_k=w7a4k2)\).

Контроллер хранит сценарии автоматизации, логику управления освещением, отоплением, шторами и т.д., а также позволяет вести учет потребления энергоресурсов, передает данные межу разными системами дома и отправляет уведомления.

Конфигурация логики построена на технологии [Node-RED](/nodered.org) - графическом конфигураторе, разработанном компанией IBM. Данная техгология позволяет создать логику работы без использования навыков программирования. Подробнее можно посмотреть [здесь](https://golos.io/smarthome/@ropox/node-red-pervye-shagi).

