---
title: Kurulum
sidebar_position: 2
---

:::info

Bu makale, cihazınızı sistem düzeyinde koruyan çok işlevli bir reklam engelleyici olan Windows için AdGuard'ı ele alır. Nasıl çalıştığını görmek için [AdGuard uygulamasını indirin](https://agrd.io/download-kb-adblock)

:::

## Sistem gereksinimleri

**Operating system:** Microsoft Windows 11, 10, 8.1, 8.

**RAM:** at least 1 GB.

**Boş disk alanı:** 150 Mbyte.

**Tarayıcı:** Microsoft Edge, Microsoft Internet Explorer (tüm sürümler), Opera, Google Chrome, Yandex.Browser, Mozilla Firefox ve diğer birçok tarayıcı.

## AdGuard kurulumu

AdGuard'ı bir Windows PC veya tablete kurmak için şu adımları izleyin:

1. [AdGuard sitesine](http://adguard.com) gidin ve *İndir* öğesine tıklayın. Kurulum programını [indirme sayfasından](https://adguard.com/download.html?auto=1) da edinebilirsiniz — indirme otomatik olarak başlar.

   ![Download AdGuard *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/installation_new/website_en.png)

2. Once the download is complete, open the file *adguardInstaller.exe*.

   ![Downloaded file](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/installation_new/download_en.png)

3. You’ll see a User Account Control prompt asking if you want to allow the app to make changes to your PC. *Evet* öğesine tıklayın.

   ![Değişikliklere izin ver *mobile](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/allow-changes.png)

4. Choose the folder where you want AdGuard to be installed.

   ![Klasör seç *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/installation_new/installer1_en.png)

   If you want to select a different location, click *Browse*, choose the folder, and click *OK*. You can also create a new folder by clicking *Make New Folder* and naming it. If you’d like a desktop shortcut, check the box *Create a desktop shortcut*. Then click *Install* to start the installation.

   ![Kurulumu başlat *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/installation_new/installer2_en.png)

5. Kurulumun tamamlanmasını bekleyin ve *Bitir* öğesine tıklayın.

   ![Kurulumu bitir *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/installation_new/installer3_en.png)

   Tebrikler! AdGuard has been successfully installed. You’ll be prompted to set up protection according to your preferences.

   ![Koruma ayarlanıyor *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/installation_new/setting_up_protection_en.png)

   Bundan sonra, uygulamanın ayarlarını yapabileceğiniz ana pencere açılır.

## Windows için AdGuard nasıl kaldırılır {#uninstall}

### Regular method

AdGuard'ı kaldırmanız veya yeniden kurmanız gerekirse aşağıdakileri yapın:

- Microsoft Windows 10 & 11 için: *Başlat* öğesine tıklayarak *Başlat Menüsünü* açın, ardından *Ayarlar* öğesini seçin. Açılan pencerede *Uygulamalar* → *Yüklü uygulamalar* öğesine tıklayın. Select *AdGuard* from the list of your installed apps, click the three-dot menu, and select *Uninstall*.

   ![Windows 10 & 11 uninstallation *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/installation_new/win11_uninstall_adguard.png)

- For Microsoft Windows 8: Right-click the *empty space* in the lower left corner of the task bar and select *Control Panel*. Click *Uninstall a program* in the *Programs* section, then select *AdGuard* from the list of installed apps and press the *Uninstall* button located right above the list. Confirm the action by clicking *Uninstall AdGuard* in the window that opens.

- For Microsoft Windows 8.1: Right-click the *Start button* and select *Control Panel*. Click *Uninstall a program* in the *Programs* section, then select *AdGuard* from the list of installed apps and press the *Uninstall* button located right above the list. Confirm the action by clicking *Uninstall AdGuard* in the window that opens.

- For Microsoft Windows 7: Open *Start Menu*. In the search box, type *Control Panel*. Click *Uninstall a program* in the *Programs* section, then select *AdGuard* from the list of installed apps and press the *Uninstall* button located right above the list. Confirm the action by clicking *Uninstall AdGuard* in the window that opens.

### Gelişmiş yöntem {#advanced}

In case regular uninstall doesn't work for any reason, you can try to use an advanced method. First of all, you need to [download the uninstaller tool](https://static.adtidy.org/windows/uninstaller/uninstal_utility.zip) created by our developers. Extract the archive to any folder on your PC and run the **Adguard.UninstallUtility.exe** file, and allow the app to make changes to your device. Then follow the instruction below:

- Select *AdGuard Ad Blocker* and *Standard* uninstall type, then click *Uninstall*.

   ![Standard uninstall *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/ab_standard.jpg)

- Click *OK* once the warning window pops up:

   ![Standard uninstall warning *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/ab_extended_warning.jpg)

- Wait until uninstall is finished — there will be a phrase **Uninstall complete** and a prompt to restart your computer:

   ![Uninstall finished *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/ab_standard_complete.jpg)

:::caution

Follow the next steps only if performing the first two steps wasn’t enough for some reason. We strongly suggest contacting our support before using steps 3-4 of advanced uninstall instruction.

:::

- Select *AdGuard Ad Blocker* and *Extended* uninstall type, then click *Uninstall*. Click *Yes, continue* in the window prompt.

   ![Extended uninstall *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/ab_extended.jpg)

- Click *OK* once the warning window pops up:

   ![Extended uninstall warning *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/ab_extended_warning.jpg)

- Wait until uninstall is finished — there will be a phrase **Uninstall complete** and a prompt to restart your computer:

   ![Extended uninstall finished *border](https://cdn.adtidy.org/content/kb/ad_blocker/windows/installation/ab_extended_complete.jpg)

AdGuard is successfully uninstalled!

#### Running the uninstaller in console mode

Besides running the advanced uninstaller in its user-interactive mode, you can also use command-line arguments to uninstall AdGuard for Windows. To do this, follow the instructions below:

1. Başlat menüsünden *cmd* yazarak Komut İstemi'ni açın.
2. Use `/console` to run the uninstaller in console mode, without the interactive UI. All the command-line parameters below will be ignored if the `/console` mode is not activated.
3. Use `/adblocker` to uninstall AdGuard for Windows. Bu şöyle görünmelidir:

   `Adguard.UninstallUtility.exe /console /adblocker`

4. You can also use `/advanced` to force the uninstaller to run in *Advanced mode* and `/settings` to force the uninstaller to remove user settings along with the application.

:::note

The use of the parameters `/console` and `/adblocker` is necessary for a successful uninstall. The parameters `/advanced` and `/settings` are optional.

:::
