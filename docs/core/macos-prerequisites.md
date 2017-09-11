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

# <a name="prerequisites-for-net-core-on-mac"></a><span data-ttu-id="90283-104">Необходимые компоненты для .NET Core в Mac</span><span class="sxs-lookup"><span data-stu-id="90283-104">Prerequisites for .NET Core on Mac</span></span>

<span data-ttu-id="90283-105">Эта статья описывает поддерживаемые версии macOS и зависимости .NET Core, необходимые для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS.</span><span class="sxs-lookup"><span data-stu-id="90283-105">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="90283-106">Есть три разных способа для использования приведенных ниже поддерживаемых версий ОС и зависимостей при разработке приложений .NET Core на Mac: в [командной строке с помощью привычного вам редактора](tutorials/using-with-xplat-cli.md), в [Visual Studio Code](https://code.visualstudio.com/) и в [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="90283-106">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="90283-107">Поддерживаемые версии macOS</span><span class="sxs-lookup"><span data-stu-id="90283-107">Supported macOS versions</span></span>

<span data-ttu-id="90283-108">Платформа .NET Core поддерживается на устройствах под управлением следующих версий macOS:</span><span class="sxs-lookup"><span data-stu-id="90283-108">.NET Core is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="90283-109">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="90283-109">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="90283-110">macOS 10.11 El Capitan (только .NET Core 1.x).</span><span class="sxs-lookup"><span data-stu-id="90283-110">macOS 10.11 "El Capitan" (.NET Core 1.x only)</span></span>

<span data-ttu-id="90283-111">Полный список поддерживаемых операционных систем см. в [этой статье](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions).</span><span class="sxs-lookup"><span data-stu-id="90283-111">See [Supported OS Versions](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions) for the complete list of supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="90283-112">Зависимости .NET Core</span><span class="sxs-lookup"><span data-stu-id="90283-112">.NET Core dependencies</span></span>

<span data-ttu-id="90283-113">**.NET Core 1.x**</span><span class="sxs-lookup"><span data-stu-id="90283-113">**.NET Core 1.x**</span></span>

<span data-ttu-id="90283-114">При выполнении в macOS платформе .NET Core 1.x требуется OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="90283-114">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="90283-115">Легко получить OpenSSL можно с помощью диспетчера пакетов [Homebrew ("brew")](https://brew.sh/) для macOS.</span><span class="sxs-lookup"><span data-stu-id="90283-115">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="90283-116">После установки *brew* установите OpenSSL, выполнив следующие команды в окне терминала (аналог командной строки):</span><span class="sxs-lookup"><span data-stu-id="90283-116">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="90283-117">Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="90283-117">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="90283-118">При возникновении проблем с установкой в macOS см. к разделы с описанием [известных проблем в версии 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) и [в версии 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="90283-118">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

<span data-ttu-id="90283-119">**.NET Core 2.x**</span><span class="sxs-lookup"><span data-stu-id="90283-119">**.NET Core 2.x**</span></span>

<span data-ttu-id="90283-120">Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="90283-120">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="90283-121">При возникновении проблем с установкой в macOS обратитесь к разделу с описанием [известных проблем](https://github.com/dotnet/core/tree/master/release-notes/2.0), соответствующему установленной версии.</span><span class="sxs-lookup"><span data-stu-id="90283-121">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for the version you have installed.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="90283-122">Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="90283-122">Visual Studio for Mac</span></span>

<span data-ttu-id="90283-123">Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор.</span><span class="sxs-lookup"><span data-stu-id="90283-123">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="90283-124">Если же вы хотите разрабатывать приложения .NET Core в интегрированной среде разработки Mac, можно использовать [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="90283-124">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="90283-125">Чтобы разрабатывать приложения .NET Core в macOS с помощью Visual Studio для Mac, нужны следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="90283-125">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="90283-126">Поддерживаемая версия операционной системы macOS</span><span class="sxs-lookup"><span data-stu-id="90283-126">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="90283-127">OpenSSL (Только .NET Core 1.x. .NET Core 2.x использует службы безопасности, по умолчанию доступные в macOS.)</span><span class="sxs-lookup"><span data-stu-id="90283-127">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="90283-128">Пакет SDK .NET Core для Mac</span><span class="sxs-lookup"><span data-stu-id="90283-128">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="90283-129">Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="90283-129">Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

