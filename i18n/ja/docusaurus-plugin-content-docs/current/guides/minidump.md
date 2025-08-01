---
title: BSoDエラーを修正するためのminidumpファイルを作成する方法
sidebar_position: 8
---

ほとんどのWindowsユーザーは、残念ながら[ブルースクリーンオブデス（BSoD）](https://en.wikipedia.org/wiki/Blue_screen_of_death)エラーに直面したりすることがよくあります。 BSoDは、Windowsシステムが、サードパーティのドライバーコード、ハードウェア、マイクロソフトのコードの問題のような、安全なシステム操作に影響を与える問題に遭遇したときに発生します。 ブルースクリーンエラーを解決するには、ミニダンプ（minidump）ファイルを使用することができます。

## ミニダンプ（minidump）ファイルとは何ですか?

ミニダンプファイルは、システムクラッシュの性質に関する情報を含むファイルです。 ブルースクリーンが表示される直前に作成され、問題解決に使える最低限の有益な情報が含まれています。 ミニダンプファイルの拡張子は通常*.dmp*です。

:::note
Windows 10では、ブルースクリーンにストップコードとQRコードが表示されます。 ユーザーはこの情報を使って、特定の問題をウェブで検索することができます。

:::

ミニダンプファイルを作成するオプションはデフォルトでは無効になっているので、ファイルの使い方を詳しく説明する前に、作成を有効にする方法を詳しく見てみましょう。

## minidumpファイルを作成するためにWindowsをセットアップする方法

BSoDクラッシュエラーが発生しない場合でも、このオプションを設定しておくことができます。AdGuard製品に関係なく、これは一般的におすすめです。 ミニダンプファイルを自動的に作成するには、以下の手順に従ってください:

 1. Type *sysdm.cpl* in the Windows search bar and click **Open**. The **System Properties Control Panel Menu** window will appear on the screen.

    :::tip

    Alternatively, click **Settings** → **System** → **About** → **Advanced system settings**.


:::

    ![System Properties *mobile_border](https://cdn.adtidy.org/blog/new/c2huSystem_Properties.jpeg)

 1. Go to the **Advanced** tab.
 1. In the **Startup and Recovery** section, click **Settings**.

    ![Startup and Recovery *mobile_border](https://cdn.adtidy.org/blog/new/1dmybiStartup_and_Recovery.png)

 1. Enable the following three options:

    - システムログにイベントを書き込む
    - 自動的に再起動
    - デバッグ情報の書き込み → 小型メモリーダンプ（256kb）

    ![3つのオプション *mobile_border](https://cdn.adtidy.org/blog/new/nmr4eThree_options.png)

 1. **OK**をクリックして設定を適用します。
 1. コンピュータを再起動します。

これでミニダンプファイルが有効になりました。 これで、システムがクラッシュしたときに自動的に作成されます。

:::note

デフォルトでは、ミニダンプファイルは**%SystemRoot%\Minidump**フォルダに保存されます。 ディレクトリの場所は好きなように変更できますが、多くのプログラムはデフォルトでこの場所を探すように設定されていることにご注意ください。

:::

## Collecting wfpdiag.cab file

Our support team may request a wfpdiag.cab file, along with a minidump file, to analyze system logs more thoroughly and diagnose issues. To collect the file, please follow these steps:

1. AdGuard 保護をオンにする

1. Click *Start* and type `cmd` to open Command Prompt

1. Right-click Command Prompt and choose *Run as administrator*

    :::note

    A wfpdiag.cab file is created in your current directory. You can change the location by typing `cd <folder_name>`.


:::

1. To start logging, enter the following command: `netsh wfp capture start`

1. Visit any website to route traffic through AdGuard and log the filtering process

1. To stop logging, enter `netsh wfp capture stop`
