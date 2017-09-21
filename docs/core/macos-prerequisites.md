---
title: "Необходимые компоненты для .NET Core в Mac"
description: "Поддерживаемые версии macOS и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 07/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8feaee2cbfa55e23bd49c0ab76d995f15be343b4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a>Необходимые компоненты для .NET Core в Mac

Эта статья описывает поддерживаемые версии macOS и зависимости .NET Core, необходимые для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS. Есть три разных способа для использования приведенных ниже поддерживаемых версий ОС и зависимостей при разработке приложений .NET Core на Mac: в [командной строке с помощью привычного вам редактора](tutorials/using-with-xplat-cli.md), в [Visual Studio Code](https://code.visualstudio.com/) и в [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

## <a name="supported-macos-versions"></a>Поддерживаемые версии macOS

Платформа .NET Core поддерживается на устройствах под управлением следующих версий macOS:

* macOS 10.12 "Sierra"
* macOS 10.11 El Capitan (только .NET Core 1.x).

Полный список поддерживаемых операционных систем см. в [этой статье](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions).

## <a name="net-core-dependencies"></a>Зависимости .NET Core

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

**.NET Core 2.x**

Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core). При возникновении проблем с установкой в macOS обратитесь к разделу с описанием [известных проблем](https://github.com/dotnet/core/tree/master/release-notes/2.0), соответствующему установленной версии.

## <a name="visual-studio-for-mac"></a>Visual Studio для Mac

Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор. Если же вы хотите разрабатывать приложения .NET Core в интегрированной среде разработки Mac, можно использовать [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/). 

Чтобы разрабатывать приложения .NET Core в macOS с помощью Visual Studio для Mac, нужны следующие компоненты:

* Поддерживаемая версия операционной системы macOS
* OpenSSL (Только .NET Core 1.x. .NET Core 2.x использует службы безопасности, по умолчанию доступные в macOS.)
* Пакет SDK .NET Core для Mac
* [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

