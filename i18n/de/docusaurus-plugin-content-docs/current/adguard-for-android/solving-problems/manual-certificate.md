---
title: Zertifikatsinstallation auf Geräten mit Android 11+
sidebar_position: 12
---

:::info

Dieser Artikel behandelt AdGuard für Android, einem multifunktionalen Werbeblocker, der Ihr Gerät auf Systemebene schützt. Um zu sehen, wie es funktioniert, [laden Sie die AdGuard-App herunter](https://agrd.io/download-kb-adblock)

:::

To be able to [filter HTTPS traffic](/general/https-filtering/what-is-https-filtering.md) (which is extremely important as most ads use HTTPS), AdGuard needs to install its certificate into your device’s user storage. Bei älteren Versionen des Android-Betriebssystems geschah dies automatisch, aber bei Android 11 und später muss man es manuell installieren.

![Zertifikat *mobile_border](https://cdn.adtidy.org/content/kb/ad_blocker/android/solving_problems/manual-certificate/g.gif)

Folgen Sie diesen Schritten, um das AdGuard-Zertifikat zu installieren:

1. Open the app. On the *Home* screen, tap *HTTPS filtering is off*.

1. Then you’ll be presented with three screens:
    - HTTPS filtering is critical for ad blocking
    - AdGuard’s HTTPS filtering is safe
    - AdGuard certificate

    Consecutively, tap *Continue* → *Next* → *Save certificate*.

1. Tippen Sie auf *Speichern* unten im geöffneten Ordner *Download*.

1. Tippen Sie nach dem Speichern auf *Einstellungen öffnen*.

1. Open *Settings* and type *CA Certificate* in the search bar. Tap the respective option.

1. Möglicherweise wird eine Warnmeldung angezeigt. Wenn dies der Fall ist, tippen Sie auf *Trotzdem installieren* und geben Sie Ihre PIN ein, falls erforderlich.

1. Wählen Sie die AdGuard-Zertifikatsdatei aus. Sein Name sollte in etwa wie *adguard_1342_020322.crt* aussehen.

You’re all set! Once the certificate is installed successfully, you’ve enabled HTTPS filtering.

If you experience issues during the manual certificate installation (for example, you installed the certificate, but the application keeps ignoring it), you can follow one of the solutions below.

1. Starten Sie AdGuard neu.
2. Versuchen Sie noch einmal, das richtige Zertifikat (AdGuard Personal CA) zu installieren.

## Security warnings

In earlier versions of Android, the quick settings panel displayed the message “Network may be monitored.” Tapping it will open a window with detailed information.

Starting with Android 15, in addition to “Network may be monitored”, users will see a warning notification after installing a certificate and after restarting the device: “Certificate authorities installed by an unknown third party.” This means that the system has detected third-party certificates in the user certificate store. Tapping the notification opens a list of certificates in the user certificate store.

Despite these warnings, your traffic remains secure. Your connection to remote servers stays encrypted. What AdGuard does is simply verify the server’s certificate before deciding whether to filter the connection — similar to how a browser works.

[Learn more about HTTPS filtering and how the certificate works](/general/https-filtering/what-is-https-filtering.md).

If you still encounter a problem and can’t install the certificate, please contact our support team at <support@adguard.com>.
