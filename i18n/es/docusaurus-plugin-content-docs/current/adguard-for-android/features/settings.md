---
title: Configuración
sidebar_position: 4
---

:::info

Este artículo trata sobre AdGuard para Android, un bloqueador de anuncios multifuncional que protege tu dispositivo a nivel del sistema. Para ver cómo funciona, [descarga la aplicación AdGuard](https://agrd.io/download-kb-adblock)

:::

Se puede acceder a la pestaña _Configuración_ tocando el ícono más a la derecha en la parte inferior de la pantalla. Esta sección contiene varias configuraciones, información sobre tu aplicación, licencia y suscripción, y varios recursos de soporte.

## General

Esta sección te ayuda a administrar la apariencia y el comportamiento de la aplicación: puedes configurar el tema de color y el idioma, administrar notificaciones y más. Si deseas ayudar al equipo de AdGuard a detectar fallas de la aplicación e investigar la usabilidad, puedes habilitar _Informar automáticamente fallas_ y _Enviar datos técnicos y de interacción_.

![General \*mobile_border](https://cdn.adtidy.org/blog/new/my5quggeneral.png)

En _Actualizaciones de aplicaciones y filtros_, puedes configurar actualizaciones automáticas de filtros y seleccionar un canal de actualización de aplicaciones. Elige _Release_ para una mayor estabilidad y _Beta_ o _Nightly_ para acceder antes a las nuevas funciones.

Updates \*mobile_border](https://cdn.adtidy.org/blog/new/hqm8kupdates.png)

### Configuración avanzada

_Automatización_ te permite administrar AdGuard a través de aplicaciones de tareas.

_Watchdog_ ayuda a proteger AdGuard para que no sea desactivado por el sistema ([leer más sobre el modo de ahorro de batería de Android](/adguard-for-android/solving-problems/background-work/)). El valor que ingreses será el intervalo en segundos entre verificaciones del watchdog.

_Nivel de registro_ define qué datos sobre el funcionamiento de la aplicación deben registrarse. De forma predeterminada, la aplicación recopila datos sobre sus eventos. El nivel _Debug_ registra más eventos; habilítalo si el equipo de AdGuard lo solicita para ayudarlos a comprender mejor el problema. [Más información sobre la recopilación y el envío de registros](/adguard-for-android/solving-problems/log/)

![Avanzado \*mobile_border](https://cdn.adtidy.org/blog/new/vshfnadvanced.png)

La sección _Configuración de bajo nivel_ es para usuarios expertos. [Más información sobre la configuración de bajo nivel](/adguard-for-android/features/low-level-settings/)

Configuración de bajo nivel \*mobile_border](https://cdn.adtidy.org/blog/new/n9ztplow_level.png)

## Filtrado

Esta sección te permite administrar la configuración de filtrado HTTPS, los filtros y las secuencias de comandos de usuario, y configurar un servidor proxy.

![Filtering \*mobile_border](https://cdn.adtidy.org/content/kb/ad_blocker/android/features/filtering.jpg)

### Filtros

AdGuard bloquea anuncios, rastreadores y molestias aplicando reglas de sus filtros. La mayoría de las funciones de la sección _Protección_ funcionan con [filtros AdGuard](/general/ad-filtering/adguard-filters/#adguard-filters). Si habilitas la _Protección básica_, se activará automáticamente el filtro AdGuard Base y el filtro AdGuard Mobile Ads. Y viceversa: si desactivas ambos filtros, la _Protección básica_ también se desactivará.

![Filtros \*mobile_border](https://cdn.adtidy.org/blog/new/7osjdfilters.png)

Los filtros habilitados de forma predeterminada son suficientes para el funcionamiento normal de AdGuard. Sin embargo, si deseas personalizar el bloqueo de anuncios, puedes utilizar otros filtros de AdGuard o de terceros. Para ello, selecciona una categoría y activa los filtros que desees. Para agregar un filtro personalizado, toca _Filtros personalizados_ → _Agregar filtro personalizado_ e ingresa tu URL o ruta de archivo.

:::note

Si activas demasiados filtros, es posible que algunos sitios web funcionen incorrectamente.

:::

[Más información sobre filtros](https://adguard.com/en/blog/what-are-filters.html)

### Extensiones

Extensions allow you to add userscripts and userstyles.

![Extensions \*mobile_border](https://cdn.adtidy.org/content/kb/ad_blocker/android/features/extensions.jpg)

Userscripts are miniprograms written in JavaScript that extend the functionality of one or more websites. To install a userscripts, you need a special userscript manager. AdGuard has such a functionality and allows you to add userscripts by URL or from file.

Userstyles are like userscripts that allow you to change how web pages look in the browser without modifying their content. They work by adding CSS styles to the website’s existing styles. For example, if you want a dark theme on a website that doesn’t offer one, you can use a userstyle to do it.

To add a userstyle, go to _Settings_ → _Filtering_ → _Extensions_→ _Add extension_ → _Import from file or URL_. You can find ready-made user styles [online](https://userstyles.world/).

To create your own style, tap _Add extension_ → _Create userstyle_.

#### AdGuard Extra

AdGuard Extra is a custom userscript that blocks complex ads and mechanisms that reinject ads to websites.

#### Disable AMP

Disable AMP is a userscript that disables [Accelerated mobile pages](https://en.wikipedia.org/wiki/Accelerated_Mobile_Pages) on the Google search results page.

### Red

#### Filtrado HTTPS

To block ads and trackers on most websites and in most apps, AdGuard needs to filter their HTTPS traffic. [Read more about HTTPS filtering](/general/https-filtering/what-is-https-filtering)

##### Security certificates

To manage encrypted traffic, AdGuard installs its CA certificate on your device. It's safe: the traffic is filtered locally and AdGuard verifies the security of the connection.

On older versions of Android, the certificate is installed automatically. On Android 11 and later, you need to install it manually. [Installation instructions](/adguard-for-android/solving-problems/manual-certificate/)

The CA certificate in the user store is enough to filter HTTPS traffic in browsers and some apps. However, there are apps that only trust certificates from the system store. To filter HTTPS traffic there, you need to install AdGuard's CA certificate into the system store. [Instructions](/adguard-for-android/solving-problems/https-certificate-for-rooted/)

##### HTTPS-filtered apps

This section contains the list of apps for which AdGuard filters HTTPS traffic. Please note that the setting can be applied for all apps only if you have CA certificates both in the user store and in the system store.

##### HTTPS-filtered websites

This setting allows you to manage websites for which AdGuard should filter HTTPS traffic.

HTTPS filtering allows AdGuard to filter the content of requests and responses, but we never collect or store this data. However, to increase security, we [exclude websites that contain potentially sensitive information from HTTPS filtering](/general/https-filtering/what-is-https-filtering/#financial-websites-and-websites-with-sensitive-personal-data).

You can also add websites that you consider necessary to exclusions by selecting one of the modes:

- Exclude specific websites from HTTPS filtering
- Filter HTTPS traffic only on the websites added to exclusions

By default, we also do not filter websites with Extended Validation (EV) certificates, such as financial websites. Si es necesario, puedes habilitar la opción _Filtrar sitios web con certificados EV_.

#### Proxy

You can set up AdGuard to route all your device's traffic through your proxy server. [How to set up an outbound proxy](/adguard-for-android/solving-problems/outbound-proxy)

In this section, you can also set up a third-party VPN to work with AdGuard, if your VPN provider allows it.

Under _Apps operating through proxy_, you can select apps that will route their traffic through your specified proxy. If you have _Integration with AdGuard VPN_ enabled, this setting plays the role of AdGuard VPN's app exclusions: it allows you to specify apps to be routed through the AdGuard VPN tunnel.

#### Routing mode

This section allows you to select the traffic filtering method.

- _Local VPN_ filters traffic through a locally created VPN. This is the most reliable mode. Due to Android restrictions, it is also the only system-wide traffic filtering method available on non-rooted devices.

:::note

The _Local VPN_ mode doesn't allow AdGuard to be used simultaneously with other VPNs. To use another VPN with AdGuard, you need to reconfigure it to work in proxy mode and set up an outbound proxy in AdGuard. For AdGuard VPN, this is done automatically with the help of the [_Integrated mode_](/adguard-for-android/features/integration-with-vpn).

:::

- _Automatic proxy_ is an alternative traffic routing method that does not require the use of a VPN. One significant advantage is that it can be run in parallel with a VPN. This mode requires root access.

:::note

Please note that DNS filtering will still be active in _Automatic proxy_ routing mode, and your device may not be able to filter DNS requests from specific apps. In _VPN_ routing mode, apps are excluded from the local VPN by system means. Therefore, the system resolver sees which apps are included in the VPN and which are not. It either allows them into the local VPN or lets them bypass it. However, DNS requests come from the system resolver, not the application. In _Automatic proxy_ mode, it is only possible to exclude traffic from applications, not their DNS queries, because AdGuard sees them as system queries.

:::

- _Manual proxy_ involves setting up a proxy server on a specific port, which can then be configured in Wi-Fi settings. This mode requires root access for Android 10 and above.

## Licencia

In this section, you can find information about your license and manage it:

- Buy an AdGuard license to activate [the full version's features](/adguard-for-android/features/free-vs-full)
- Log in to your AdGuard account or enter the license key to activate your license
- Sign up to activate your 7-day trial period if you haven't used it yet
- Refresh the license status from the three-dots menu (⋮)
- Open the AdGuard account to manage your license there
- Reset your license — for example, if you've reached device limit for this license and want to apply another one

![License screen \*mobile_border](https://cdn.adtidy.org/blog/new/3wyh5hlicense.png)

## Asistencia técnica

Use this section if you have any questions or suggestions regarding AdGuard for Android. We recommend consulting _[FAQ](https://adguard.com/support/adguard_for_android.html)_ or this knowledge base before contacting support.

![Support \*mobile_border](https://cdn.adtidy.org/blog/new/cz55usupport.png)

If you notice a missed ad, please report it via _Report incorrect blocking_.

For unexpected app behavior, select _Report a bug_. If possible, describe your problem in detail and add app logs. [How to describe an issue](/guides/report-bugs/#how-to-describe-a-problem)

For your suggestions, use _Request a feature_.

:::note

GitHub is an alternative way to report bugs and suggest new features. [Instructions and repository links](/guides/report-bugs/#adguard-for-android)

:::
