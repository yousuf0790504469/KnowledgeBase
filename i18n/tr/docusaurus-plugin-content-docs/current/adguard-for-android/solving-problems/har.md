---
title: HAR dosyaları nasıl oluşturulur
sidebar_position: 5
---

:::info

This article is about AdGuard for Android, a multifunctional ad blocker that protects your device at the system level. Nasıl çalıştığını görmek için [AdGuard uygulamasını indirin](https://agrd.io/download-kb-adblock)

:::

:::note

HAR dosyaları [AdGuard Gizlilik Politikasına](https://adguard.com/en/privacy.html) uygun olarak işlenir.

:::

## HAR dosyaları nedir?

The HAR (HTTP ARchive) format is a JSON-formatted archive file for logging of a web browser's interaction with a site. The specifications of HAR format define archival data for HTTP transactions that a browser uses to export detailed information about the web pages it loads. More detailed description of HAR file format and its specification you can find at [softwareishard.com](http://www.softwareishard.com/blog/har-12-spec/) website.

## HAR dosyaları nasıl oluşturulur

Sometimes we need to analyze it to block specific ads that are difficult to reproduce for some reason. To get HAR files, follow these steps:

1. Open AdGuard and go to **Settings** (⚙ icon in the lower right corner).
2. Tap **General** →**Advanced** → **Low-level settings**.
3. Scroll down and activate **Capture HAR** in the Filtering section.
4. Open the app and perform the necessary actions to reproduce the problem.
5. Turn **Capture HAR** off.
6. **Gelişmiş** öğesine geri dön.
7. Tap **Export logs and system info** → **Allow** (if necessary) → **Save**.

**Send the generated file with the logs to the AdGuard support service.**

:::note

Our support team will process your ticket much faster if you specify the HelpDesk ticket number or the GitHub issue number in your message.

:::

## HAR dosyaları nasıl analiz edilir

Here are some sources that we can recommend to analyze HAR files:

- [HTTP Archive Viewer master](https://gitgrimbo.github.io/harviewer/master/) is a HAR analyzer tool, visualizes HTTP Archive (HAR) log files created by HTTP tracking tools.
- [Fiddler](https://www.telerik.com/fiddler) is a web debugging proxy, lets you capture, inspect, monitor all HTTP(S) traffic between your computer and the Internet, mock requests, and diagnose network issues.
