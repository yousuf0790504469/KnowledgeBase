---
title: iCloud Özel Geçişi ve AdGuard
sidebar_position: 7
---

:::info

Bu makale, cihazınızı sistem düzeyinde koruyan çok işlevli bir reklam engelleyici olan Mac için AdGuard hakkındadır. Nasıl çalıştığını görmek için [AdGuard uygulamasını indirin](https://agrd.io/download-kb-adblock)

:::

## Problem description in a nutshell

By default, AdGuard uses the "default route" which disables iCloud Private Relay.

Currently, AdGuard and iCloud Private Relay cannot work at the same time. AdGuard cannot block ads because iCloud Private Relay encrypts traffic before AdGuard can filter network connections. When iCloud Private Relay is active, any filtering (including local filtering) becomes impossible. Thus, AdGuard can't filter traffic or perform DNS filtering in Safari. Yet, AdGuard still filters traffic in other browsers. To keep using iCloud Private Relay, consider installing [AdGuard for Safari](https://adguard.com/adguard-safari/overview.html).

The same applies to using any VPN apps on Mac: you have to choose between using iCloud Private Relay or a VPN service.

## Ayrıntılı olarak

Mac için AdGuard artık ağ uzantıları API'sine dayalı macOS yerleşik soket filtrelemesini kullanıyor. Bu yeni ve oldukça hatalı mekanizma eski güzel Kernel uzantılarının yerini aldı. Over the last 1.5 years, we've reported more than 20(!) bugs to Apple regarding their new filtering method.

The network extensions API has a VPN-like configuration with a list of route-like entries. On Big Sur, AdGuard developed "split-tunnel" rules to avoid creating the "default route" rule because it causes problems on early Big Sur releases.

Monterey'de iCloud Özel Geçişi tanıtıldı. Mail uygulamasının gizlilik özellikleri de Özel Geçiş sunucularını kullanır.

As a consequence, AdGuard can’t work together with iCloud Private Relay and the Mail app privacy features:

1. iCloud Private Relay is applied to connections at the library level — before they reach the socket level, where AdGuard operates.
2. iCloud Private Relay is implemented with HTTP/3 CONNECT proxies.
3. Since AdGuard does not filter CONNECT HTTP/3 requests yet, it attempts to downgrade HTTP/3 proxy connections to HTTP/1.1, which results in blocking iCloud Private Relay traffic.
4. When you use iCloud Private Relay and switch AdGuard into the Split-Tunnel mode, you can’t open websites in Safari.
5. To work around this issue for Monterey, we apply the “default route” rule. When Private Relay sees that rule, it disables itself automatically. So, AdGuard works seamlessly on Monterey, but iCloud Private Relay gets disabled.

The `network.extension.monterey.force.split.tunnel` option restores the “Big Sur” behavior, but this option may break access to websites due to (3) and (4). Bu soruna bir çözüm aramaya devam ediyoruz. One of the options is implementing HTTP/3 proxy filtering.

## Önerilen çözüm

We recommend using AdGuard together with a more traditional VPN service such as [AdGuard VPN](https://adguard-vpn.com/).

## Alternatif çözüm

You can prevent AdGuard from using the "default route" by disabling the "default route". It can be done via Advanced Settings → `network.extension.monterey.force.split.tunnel`.

![Disable default route in advanced settings *border](https://cdn.adtidy.org/content/kb/ad_blocker/mac/mac_adguard_advanced_settings.jpg)

Bear in mind that, in this case, you'll face the issues described above.
