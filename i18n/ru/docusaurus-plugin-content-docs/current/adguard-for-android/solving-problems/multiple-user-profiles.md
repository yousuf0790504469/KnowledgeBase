---
title: Проблемы, вызванные использованием нескольких профилей пользователей
sidebar_position: 9
---

:::info

В этой статье рассказывается об AdGuard для Android — многофункциональном блокировщике рекламы, который защищает ваше устройство на системном уровне. Чтобы увидеть, как он работает, [скачайте приложение AdGuard](https://agrd.io/download-kb-adblock)

:::

В этой статье описаны способы решения проблем с AdGuard при настройке *нескольких аккаунтов* или *профилей с ограниченным доступом* на устройствах Android.

## Проблемы, вызванные использованием нескольких профилей пользователей

На Android 9 и более поздних версиях, если AdGuard установлен более чем для одного пользовательского профиля на вашем устройстве, вы можете столкнуться с проблемами при удалении приложения. Когда вы удаляете AdGuard из одного пользовательского профиля, приложение по-прежнему будет отображаться в списке приложений, но вы не сможете удалить или переустановить его. Это происходит потому, что AdGuard установлен для другого профиля пользователя на устройстве.

Если вы попытаетесь переустановить AdGuard после неудачной попытки удаления, вы увидите сообщение об ошибке «Вы не можете установить приложение на своё устройство».

Чтобы решить эту проблему, вам нужно удалить приложение для всех пользователей: перейдите в Настройки → Все приложения → AdGuard. Нажмите три точки в правом верхнем углу и выберите *Удалить для всех пользователей*.

![Удалить *mobile_border](https://cdn.adtidy.org/blog/new/tu49hmultiple_users.png)

## Проблемы, вызванные использованием профиля с ограниченным доступом

Владельцы телефонов, планшетов или телевизоров под операционной системой Android 7+ могут встретиться с проблемой, вызванной использованием на устройстве **профиля с ограниченным доступом**. При наличии такого профиля **AdGuard**, как и другие приложения, использующие VPN, получает ограничения на выборочную фильтрацию VPN-трафика. В результате AdGuard не может запустить защиту в режиме **локального VPN**. Кроме того, одной из причин этой ситуации может быть использование профиля **Dual App/Dual Messenger** на вашем устройстве. Ниже описаны рекомендации, которые можно применить при возникновении проблемы.

### Решения

Есть три пути решения проблемы:

### Вариант 1: Выдать разрешения для AdGuard с помощью ADB

:::note

Этот вариант доступен, начиная с версии **AdGuard 3.5 nightly 6**. Если вы используете более старую версию, получить последнее обновление можно [здесь](https://adguard.com/adguard-android/overview.html).

:::

1. Активируйте **режим разработчика** и включите **отладку по USB**:

    - Откройте приложение **Настройки** на своём телефоне;
    - Перейдите в раздел **О системе** (последний пункт в меню настроек). В этом разделе найдите подпункт **О телефоне**;
    - Нажмите на строку **Номер сборки** 7 раз. После этого вы получите уведомление о том, что **Теперь вы разработчик** (при необходимости введите код разблокировки устройства);
    - Откройте **Настройки системы** → **Для разработчиков** → Прокрутите вниз и включите **отладку по USB** → Подтвердите включение отладки в окне **Разрешить отладку по USB**, внимательно прочитав предупреждение.

    :::note

    Если у вас возникнут трудности или дополнительные вопросы, полные инструкции можно найти [здесь](https://developer.android.com/studio/debug/dev-options).


:::

1. [Установите и настройте](https://www.xda-developers.com/install-adb-windows-macos-linux/) ADB; На платформе Windows владельцам **Samsung** может потребоваться установить [эту утилиту](https://developer.samsung.com/mobile/android-usb-driver.html).

1. Подключите устройство с помощью кабеля USB **** к компьютеру или ноутбуку, на котором вы установили **ADB**;

1. Откройте **командную строку** на вашем ПК:

    - **Cmd.exe** если вы используете **Windows**;
    - **Terminal**, если вы используете **macOS**;

1. Введите команду `adb shell pm grant com.adguard.android android.permission.INTERACT_ACROSS_USERS` и нажмите **Enter**.

### Вариант 2: Удалить *учётную запись с ограниченным доступом*

[Узнайте](https://support.google.com/a/answer/6223444?hl=en), как управлять учётными записями пользователей с устройства Android.

:::note

В некоторых случаях аккаунты с ограниченным доступом создаются неявно и не могут быть удалены. Например, когда вы используете функции Dual Messenger или Dual App на **устройствах Samsung** или **LG**. Читайте ниже, как исправить проблему в этих случаях.

:::

### Вариант 3: Использовать AdGuard в режиме *Локального HTTP прокси* (необходимо наличие root-прав)

Чтобы включить этот режим, откройте **Настройки AdGuard** → **Сеть** → **Режим фильтрации** → **Локальный HTTP-прокси**

### Устройства LG и Samsung

Владельцы телефонов **LG** или **Samsung** также могут столкнуться с подобной проблемой. Она может быть вызвана использованием функции **Dual App/Dual Messenger** (которая автоматически создаёт ограниченный профиль). Чтобы решить эту проблему, вам нужно отключить эту функцию.

### Samsung

- Откройте **Настройки**;
- Нажмите **Расширенные**;
- Прокрутите вниз и нажмите **Dual Messenger**;
- Отключите **Dual Messenger** для всех приложений;
- Заблокируйте устройство на 5 минут;
- Разблокируйте экран и повторите попытку создания VPN-профиля.

### LG

- Откройте **Настройки**;
- Выберите вкладку **Основные**;
- Прокрутите вниз и нажмите **Dual App**;
- Удалите все приложения из списка;
- Перезагрузите устройство.
