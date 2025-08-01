---
title: Как вернуться к предыдущей версии после обновления до 8.0
sidebar_position: 11
---

:::info

В этой статье рассказывается об AdGuard для Windows — многофункциональном блокировщике рекламы, который защищает ваше устройство на системном уровне. [Скачайте приложение AdGuard](https://agrd.io/download-kb-adblock), чтобы увидеть, как оно работает

:::

AdGuard для Windows 8.0 существенно изменился — надеемся, вам понравится новая версия. Но есть вероятность, что что-то пойдёт не так, как вы ожидали. Версия 8.0 очень отличается — в конце концов, это первая nightly-сборка. Если интерфейс версии 8.0 кажется вам неудобным или вы столкнулись с проблемами функциональности/стабильности, вы можете восстановить предыдущую версию вместе с её настройками.

Рекомендуем экспортировать настройки перед обновлением до версии 8.0, чтобы в случае необходимости можно было переустановить версию 7 и импортировать сохранённые настройки обратно.

В качестве альтернативы можно использовать другой метод:

1. После обновления до версии 8 откройте папку `C:\ProgramData\Adguard\Backups` и найдите ZIP-файл с названием, похожим на `adguard_settings_7.21.5008.0-08-04-2025-13_42_15.276.zip`.
2. Скопируйте этот ZIP-файл куда-нибудь за пределы папки `C:\ProgramData\Adguard`, например, на рабочий стол — это важно, на следующем шаге файл будет удалён.
3. Удалите версию 8.0, включив опцию **удаление настроек**.
4. Установите сборку версии 7, которая была установлена до обновления.
5. Чтобы остановить фильтрацию, выйдите из версии 7 в системном трей-меню.
6. Извлеките содержимое ZIP-файла из первого шага и замените следующие файлы:
   - `adguard.db` → `C:\ProgramData\Adguard`
   - `agflm_dns.db` и `agflm_standard.db` → `C:\ProgramData\Adguard\FLM`
7. Запустите AdGuard.

Готово!
