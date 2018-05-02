---
title: Необходимые компоненты для .NET Core в Mac
description: Поддерживаемые версии macOS и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS.
author: guardrex
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 2644cd491d1d3ba07f48f57fd9416ec84316f7d8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="2616e-103">Необходимые компоненты для .NET Core в macOS</span><span class="sxs-lookup"><span data-stu-id="2616e-103">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="2616e-104">Эта статья описывает поддерживаемые версии macOS и зависимости .NET Core, необходимые для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS.</span><span class="sxs-lookup"><span data-stu-id="2616e-104">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="2616e-105">Есть три разных способа для использования приведенных ниже поддерживаемых версий ОС и зависимостей при разработке приложений .NET Core на Mac: в [командной строке с помощью привычного вам редактора](tutorials/using-with-xplat-cli.md), в [Visual Studio Code](https://code.visualstudio.com/) и в [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="2616e-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="2616e-106">Поддерживаемые версии macOS</span><span class="sxs-lookup"><span data-stu-id="2616e-106">Supported macOS versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="2616e-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="2616e-107">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="2616e-108">Платформа .NET Core 2.x поддерживается на устройствах под управлением следующих версий macOS:</span><span class="sxs-lookup"><span data-stu-id="2616e-108">.NET Core 2.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="2616e-109">macOS 10.12 "Sierra" и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="2616e-109">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="2616e-110">Полный список операционных систем, поддерживаемых .NET Core 2.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="2616e-110">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2616e-111">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2616e-111">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="2616e-112">Платформа .NET Core 1.x поддерживается на устройствах под управлением следующих версий macOS:</span><span class="sxs-lookup"><span data-stu-id="2616e-112">.NET Core 1.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="2616e-113">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="2616e-113">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="2616e-114">macOS 10.11 "El Capitan"</span><span class="sxs-lookup"><span data-stu-id="2616e-114">macOS 10.11 "El Capitan"</span></span>

<span data-ttu-id="2616e-115">Полный список операционных систем, поддерживаемых .NET Core 1.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="2616e-115">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="net-core-dependencies"></a><span data-ttu-id="2616e-116">Зависимости .NET Core</span><span class="sxs-lookup"><span data-stu-id="2616e-116">.NET Core dependencies</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="2616e-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="2616e-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="2616e-118">Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="2616e-118">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="2616e-119">При возникновении проблем с установкой в macOS обратитесь к разделу с описанием [известных проблем](https://github.com/dotnet/core/tree/master/release-notes/2.0), соответствующему установленной версии.</span><span class="sxs-lookup"><span data-stu-id="2616e-119">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for the version you have installed.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2616e-120">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2616e-120">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="2616e-121">**.NET Core 1.x**</span><span class="sxs-lookup"><span data-stu-id="2616e-121">**.NET Core 1.x**</span></span>

<span data-ttu-id="2616e-122">При выполнении в macOS платформе .NET Core 1.x требуется OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="2616e-122">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="2616e-123">Легко получить OpenSSL можно с помощью диспетчера пакетов [Homebrew ("brew")](https://brew.sh/) для macOS.</span><span class="sxs-lookup"><span data-stu-id="2616e-123">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="2616e-124">После установки *brew* установите OpenSSL, выполнив следующие команды в окне терминала (аналог командной строки):</span><span class="sxs-lookup"><span data-stu-id="2616e-124">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="2616e-125">Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="2616e-125">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="2616e-126">При возникновении проблем с установкой в macOS см. к разделы с описанием [известных проблем в версии 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) и [в версии 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2616e-126">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a><span data-ttu-id="2616e-127">Увеличение максимального лимита на число открытых файлов (версии .NET Core до версии пакета SDK для .NET Core 2.0.2)</span><span class="sxs-lookup"><span data-stu-id="2616e-127">Increase the maximum open file limit (.NET Core versions before .NET Core SDK 2.0.2)</span></span> 

<span data-ttu-id="2616e-128">В прежних версиях .NET Core (до версии пакета SDK для .NET Core 2.0.2) лимит на число открытых файлов, используемый по умолчанию в macOS, может оказаться недостаточным для некоторых рабочих нагрузок .NET Core, таких как восстановление проектов или выполнение модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="2616e-128">In older .NET Core versions (before .NET Core SDK 2.0.2), the default open file limit on macOS may not be sufficient for some .NET Core workloads, such as restoring projects or running unit tests.</span></span>

<span data-ttu-id="2616e-129">Этот лимит можно увеличить, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2616e-129">You can increase this limit by following these steps:</span></span>

1. <span data-ttu-id="2616e-130">В текстовом редакторе создайте файл _/Library/LaunchDaemons/limit.maxfiles.plist_ и сохраните его со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="2616e-130">Using a text editor, create a new file _/Library/LaunchDaemons/limit.maxfiles.plist_, and save the file with this content:</span></span>

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

2. <span data-ttu-id="2616e-131">В окне терминала выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2616e-131">In a terminal window, run the following command:</span></span>

```console
echo 'ulimit -n 2048' | sudo tee -a /etc/profile
```

3. <span data-ttu-id="2616e-132">Перезагрузите Mac, чтобы применить эти параметры.</span><span class="sxs-lookup"><span data-stu-id="2616e-132">Reboot your Mac to apply these settings.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="2616e-133">Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="2616e-133">Visual Studio for Mac</span></span>

<span data-ttu-id="2616e-134">Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор.</span><span class="sxs-lookup"><span data-stu-id="2616e-134">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="2616e-135">Если же вы хотите разрабатывать приложения .NET Core в интегрированной среде разработки Mac, можно использовать [Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="2616e-135">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="2616e-136">Чтобы разрабатывать приложения .NET Core в macOS с помощью Visual Studio для Mac, нужны следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="2616e-136">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="2616e-137">Поддерживаемая версия операционной системы macOS</span><span class="sxs-lookup"><span data-stu-id="2616e-137">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="2616e-138">OpenSSL (Только .NET Core 1.x. .NET Core 2.x использует службы безопасности, по умолчанию доступные в macOS.)</span><span class="sxs-lookup"><span data-stu-id="2616e-138">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="2616e-139">Пакет SDK .NET Core для Mac</span><span class="sxs-lookup"><span data-stu-id="2616e-139">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="2616e-140">Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="2616e-140">Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)
