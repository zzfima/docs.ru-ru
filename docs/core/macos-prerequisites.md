---
title: "Необходимые компоненты для .NET Core в Mac | Документы Майкрософт"
description: "Поддерживаемые версии macOS и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: Human Translation
ms.sourcegitcommit: 83200e452bccc20bfa82d94899514019e9d05a23
ms.openlocfilehash: 2aa685751fae9fa9771fa1cd86d211f742e06932
ms.contentlocale: ru-ru
ms.lasthandoff: 07/05/2017

---

# Необходимые компоненты для .NET Core в Mac
<a id="prerequisites-for-net-core-on-mac" class="xliff"></a>

Эта статья описывает поддерживаемые версии macOS и зависимости .NET Core, необходимые для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS. Есть три разных способа для использования приведенных ниже поддерживаемых версий ОС и зависимостей при разработке приложений .NET Core на Mac: в [командной строке с помощью привычного вам редактора](tutorials/using-with-xplat-cli.md), в [Visual Studio Code](https://code.visualstudio.com/) и в [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

## Поддерживаемые версии macOS
<a id="supported-macos-versions" class="xliff"></a>

Платформа .NET Core поддерживается следующими версиями macOS:

* macOS 10.12 "Sierra"
* macOS 10.11 "El Capitan"

Полный список поддерживаемых операционных систем см. в [заметках о выпуске .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md).

## Зависимости .NET Core
<a id="net-core-dependencies" class="xliff"></a>

**.NET Core 1.x**

При выполнении в macOS платформе .NET Core 1.x требуется OpenSSL. Легко получить OpenSSL можно с помощью диспетчера пакетов [Homebrew ("brew")](https://brew.sh/) для macOS. После установки *brew* установите OpenSSL, выполнив следующие команды в окне терминала (аналог командной строки):

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core). При наличии проблем с установкой в macOS обратитесь к разделу [Известные проблемы и обходные пути](https://github.com/dotnet/core/blob/master/cli/known-issues.md).

**.NET Core 2.x**

Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core). При наличии проблем с установкой в macOS обратитесь к разделу [Известные проблемы и обходные пути](https://github.com/dotnet/core/blob/master/cli/known-issues.md).

## Visual Studio для Mac
<a id="visual-studio-for-mac" class="xliff"></a>

Чтобы разрабатывать приложения .NET Core в macOS с помощью Visual Studio для Mac, нужны следующие компоненты:

* Поддерживаемая версия операционной системы macOS
* OpenSSL (Только .NET Core 1.x. .NET Core 2.x использует службы безопасности, по умолчанию доступные в macOS.)
* Пакет SDK .NET Core для Mac
* [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

