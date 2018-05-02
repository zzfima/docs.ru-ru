---
title: Необходимые компоненты для .NET Core в Mac
description: Поддерживаемые версии macOS и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS.
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.workload:
- dotnetcore
ms.openlocfilehash: 4bad51e7d0d705ea730382edf80850bca15c5e7a
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="prerequisites-for-net-core-on-macos"></a>Необходимые компоненты для .NET Core в macOS

Эта статья описывает поддерживаемые версии macOS и зависимости .NET Core, необходимые для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS. Есть три разных способа для использования приведенных ниже поддерживаемых версий ОС и зависимостей при разработке приложений .NET Core на Mac: в [командной строке с помощью привычного вам редактора](tutorials/using-with-xplat-cli.md), в [Visual Studio Code](https://code.visualstudio.com/) и в [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

## <a name="supported-macos-versions"></a>Поддерживаемые версии macOS

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Платформа .NET Core 2.x поддерживается на устройствах под управлением следующих версий macOS:

* macOS 10.12 "Sierra" и более поздних версий

Полный список операционных систем, поддерживаемых .NET Core 2.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Платформа .NET Core 1.x поддерживается на устройствах под управлением следующих версий macOS:

* macOS 10.12 "Sierra"
* macOS 10.11 "El Capitan"

Полный список операционных систем, поддерживаемых .NET Core 1.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).

---

## <a name="net-core-dependencies"></a>Зависимости .NET Core

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core). При возникновении проблем с установкой в macOS обратитесь к разделу с описанием [известных проблем](https://github.com/dotnet/core/tree/master/release-notes/2.0), соответствующему установленной версии.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.x**

При выполнении в macOS платформе .NET Core 1.x требуется OpenSSL. Легко получить OpenSSL можно с помощью диспетчера пакетов [Homebrew ("brew")](https://brew.sh/) для macOS. После установки *brew* установите OpenSSL, выполнив следующие команды в окне терминала (аналог командной строки):

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core). При возникновении проблем с установкой в macOS см. к разделы с описанием [известных проблем в версии 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) и [в версии 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md).

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a>Увеличение максимального лимита на число открытых файлов (версии .NET Core до версии пакета SDK для .NET Core 2.0.2) 

В прежних версиях .NET Core (до версии пакета SDK для .NET Core 2.0.2) лимит на число открытых файлов, используемый по умолчанию в macOS, может оказаться недостаточным для некоторых рабочих нагрузок .NET Core, таких как восстановление проектов или выполнение модульных тестов.

Этот лимит можно увеличить, выполнив следующие действия:

1. В текстовом редакторе создайте файл _/Library/LaunchDaemons/limit.maxfiles.plist_ и сохраните его со следующим содержимым:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
        "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>Label</key>
    <string>limit.maxfiles</string>
    <key>ProgramArguments</key>
    <array>
      <string>launchctl</string>
      <string>limit</string>
      <string>maxfiles</string>
      <string>2048</string>
      <string>4096</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>ServiceIPC</key>
    <false/>
  </dict>
</plist>
```

2. В окне терминала выполните следующую команду:

```console
echo 'ulimit -n 2048' | sudo tee -a /etc/profile
```

3. Перезагрузите Mac, чтобы применить эти параметры.

## <a name="visual-studio-for-mac"></a>Visual Studio для Mac

Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор. Если же вы хотите разрабатывать приложения .NET Core в интегрированной среде разработки Mac, можно использовать [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/). 

Чтобы разрабатывать приложения .NET Core в macOS с помощью Visual Studio для Mac, нужны следующие компоненты:

* Поддерживаемая версия операционной системы macOS
* OpenSSL (Только .NET Core 1.x. .NET Core 2.x использует службы безопасности, по умолчанию доступные в macOS.)
* Пакет SDK .NET Core для Mac
* [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/)
