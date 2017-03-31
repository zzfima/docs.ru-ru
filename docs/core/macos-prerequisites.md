---
title: "Необходимые компоненты для .NET Core в Mac | Документы Майкрософт"
description: "Поддерживаемые версии macOS и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 03/16/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: ff143583ba62fc1d82561e739a75107e50ebee88
ms.openlocfilehash: da75f5fd56b7ce66b2c46ef488e6e26c55a63ee2
ms.lasthandoff: 03/20/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a>Необходимые компоненты для .NET Core в Mac

Эта статья описывает поддерживаемые версии macOS и зависимости .NET Core, необходимые для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS. Есть три разных способа для использования приведенных ниже поддерживаемых версий ОС и зависимостей при разработке приложений .NET Core на Mac: в [командной строке с помощью привычного вам редактора](tutorials/using-with-xplat-cli.md), в [Visual Studio Code (VS Code)](https://code.visualstudio.com/) и в [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

## <a name="supported-macos-versions"></a>Поддерживаемые версии macOS

Платформа .NET Core поддерживается следующими версиями macOS:

* macOS 10.12 "Sierra"
* macOS 10.11 "El Capitan"

Полный список поддерживаемых операционных систем см. в [заметках о выпуске .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md).

## <a name="net-core-dependencies"></a>Зависимости .NET Core

При выполнении в macOS платформе .NET Core требуется OpenSSL. Легко получить OpenSSL можно с помощью диспетчера пакетов [Homebrew ("brew")](http://brew.sh/) для macOS. После установки *brew* установите OpenSSL, выполнив следующие команды в окне терминала (аналог командной строки):

```Terminal
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

После установки OpenSSL получите официальный [установщик пакета SDK .NET Core для Mac](https://go.microsoft.com/fwlink/?linkid=843444). .NET Core 1.1.1 является последней версией. Другие версии и дополнительные загружаемые материалы доступны на странице [всех загружаемых материалов .NET](https://www.microsoft.com/net/download/core). При наличии проблем с установкой в macOS обратитесь к разделу [Известные проблемы и обходные пути](https://github.com/dotnet/core/blob/master/cli/known-issues.md).

## <a name="visual-studio-for-mac"></a>Visual Studio для Mac

Чтобы разрабатывать приложения .NET Core в macOS с помощью Visual Studio для Mac, нужны следующие компоненты:

* Поддерживаемая версия операционной системы macOS
* Openssl
* Пакет SDK .NET Core для Mac
* [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

