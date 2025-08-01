---
title: How to get system logs
sidebar_position: 4
---

:::info

This article is about AdGuard for Android, a multifunctional ad blocker that protects your device at the system level. Nasıl çalıştığını görmek için [AdGuard uygulamasını indirin](https://agrd.io/download-kb-adblock)

:::

:::note

Günlüklerde sağlanan veriler ve/veya dosyalar [AdGuard Gizlilik Politikasına](https://adguard.com/en/privacy.html) uygun olarak işlenir.

:::

Bazen normal bir günlük, sorunun kaynağını belirlemek için yeterli olmayabilir. In such cases a system log is needed. Aşağıda nasıl toplanacağı ve alınacağı ile ilgili talimatlar bulunmaktadır: Geliştirici seçenekleri ve Logcat aracılığıyla.

:::note

AdGuard gizliliğinizi korumaya kararlıdır. [Gizlilik Politikamıza](https://adguard.com/privacy/android.html) kesinlikle uyuyoruz ve kullanıcılar hakkında herhangi bir özel bilgi toplamıyoruz. Günlüklerinizi destek ekibine göndermeden önce, paylaşmak istemediğiniz ek bilgiler içerebileceğinden lütfen dosyayı inceleyin. Bu tür kişisel bilgiler içeriyorsa öncelikle onu silmenizi öneririz.

:::

## Capture a bug report from a device

To get a bug report directly from your device, do the following:

1. Be sure you have [Developer options](https://developer.android.com/studio/run/device.html#developer-device-options) enabled.

1. In **Developer options**, tap **Take bug report**.

    ![Hata raporu *mobile](https://cdn.adtidy.org/public/Adguard/kb/newscreenshots/En/Android3.1/bugreporten.png)

1. Select the type of bug report you want and tap **Report**.

    :::note

    After a moment, you will see a notification that the bug report is ready (see Figure 2).


:::

    ![Hata raporu *mobile](https://cdn.adtidy.org/public/Adguard/kb/newscreenshots/En/Android3.1/bugreporteen.png)

1. To share the bug report, tap the notification.

    ![Bug report *mobile_border](https://cdn.adtidy.org/public/Adguard/kb/newscreenshots/En/Android3.1/bugreport3en.png)

1. Send this log to our support team.

    :::note

    Our support team will process your ticket much faster if you specify the HelpDesk ticket number or the GitHub issue number in your message to support.


:::

## Capture a bug report via Logcat

On devices with Android 7 and below, it is not possible to send a bug report automatically. Then you can capture it manually via Logcat — a standard Android command-line tool that dumps a log of system messages.

Bu talimatı izleyin:

### Part #1: prepare the device

1. Cihazı geliştirici moduna geçirin. To do this: go to **Settings** → **About** → tap **Build Number** 7 times.

1. Go to **Developer Options**.

1. Enable **USB debugging**.

1. Increase **Logger buffer** sizes to 4 MB per log buffer.

4 MB should be enough for storing the logs we need until you're able to do the second part (getting the log from the device);

### Part #2: reproduce the problem

It is important to reproduce the problem after you're done with the first part.

1. Sorunu yeniden oluşturun.

1. Remember/write down the date and time of reproduction and include it in the email to our support later.

### Part #3: get the log

1. Connect your device to a PC with a USB cable.

1. Download [Android SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools#downloads). Choose the appropriate download link for your OS from the Downloads section. Once you tap the link, a ZIP file will be downloaded. You can extract the ADB (Android Debug Bridge) files from the ZIP file and store them wherever you want.

1. Test whether ADB is working properly: connect your Android device to your computer using a USB cable, open the Command Prompt, PowerShell or Terminal and run the following command:

    `adb devices`

    An example of a successful result:

    ![3. Adım](https://cdn.adtidy.org/content/kb/ad_blocker/android/logcat/logcat_step-3.png)

1. Then run the following command (insert the relevant path):

    `adb logcat -v threadtime -d > C:\Program Files\platform-tools\logs.txt`

    Email the created `txt` file as well as the time the problem was reproduced (from part #2) to our support team at <support@adguard.com>.

### ROOT kullanıcıları için alternatif yol

1. Download and run [Logcat](https://play.google.com/store/apps/details?id=com.pluscubed.matlog).

1. Choose **Record** in the menu. Choose a name for a log file or just press **OK**. Now you can press **Home** button, CatLog will continue recording the log in background.

1. Reproduce the issue.

1. Open CatLog and press **Stop record** in the menu.

1. Send this log to our support team.

:::note

Our support team will process your ticket much faster if you specify the HelpDesk ticket number or the GitHub issue number in your message to support.

:::
