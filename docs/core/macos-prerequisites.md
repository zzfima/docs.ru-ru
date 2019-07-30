---
title: Необходимые компоненты для .NET Core в Mac
description: Поддерживаемые версии macOS и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS.
author: mairaw
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 07/13/2019
ms.openlocfilehash: 5086b185ee2d49c7b569ed0cb62b4c8995f9982c
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433912"
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="d7ef4-103">Необходимые компоненты для .NET Core в macOS</span><span class="sxs-lookup"><span data-stu-id="d7ef4-103">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="d7ef4-104">Эта статья описывает поддерживаемые версии macOS и зависимости .NET Core, необходимые для разработки, развертывания и запуска приложений .NET Core на компьютерах с macOS.</span><span class="sxs-lookup"><span data-stu-id="d7ef4-104">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="d7ef4-105">Есть три разных способа для использования приведенных ниже поддерживаемых версий ОС и зависимостей при разработке приложений .NET Core на Mac: в [командной строке с помощью привычного вам редактора](tutorials/using-with-xplat-cli.md), в [Visual Studio Code](https://code.visualstudio.com/) и в [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="d7ef4-106">Поддерживаемые версии macOS</span><span class="sxs-lookup"><span data-stu-id="d7ef4-106">Supported macOS versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d7ef4-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d7ef4-107">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d7ef4-108">Платформа .NET Core 2.x поддерживается на устройствах под управлением следующих версий macOS:</span><span class="sxs-lookup"><span data-stu-id="d7ef4-108">.NET Core 2.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="d7ef4-109">macOS 10.12 "Sierra" и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="d7ef4-109">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="d7ef4-110">Полный список операционных систем, дистрибутивов, версий, поддерживаемых .NET Core 2.1 и .NET Core 2.2, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на соответствующих страницах для [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) и [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-110">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="d7ef4-111">Ознакомьтесь с дополнительными сведениями и воспользуйтесь ссылками для скачивания для [.NET Core 2.2](https://www.microsoft.com/net/download/dotnet-core/2.2) или [.NET Core 2.1](https://www.microsoft.com/net/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-111">For download links and more information, see [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d7ef4-112">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d7ef4-112">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d7ef4-113">Платформа .NET Core 1.x поддерживается на устройствах под управлением следующих версий macOS:</span><span class="sxs-lookup"><span data-stu-id="d7ef4-113">.NET Core 1.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="d7ef4-114">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="d7ef4-114">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="d7ef4-115">macOS 10.11 "El Capitan"</span><span class="sxs-lookup"><span data-stu-id="d7ef4-115">macOS 10.11 "El Capitan"</span></span>

<span data-ttu-id="d7ef4-116">Полный список операционных систем, дистрибутивов, версий, поддерживаемых .NET Core 1.1 и .NET Core 1.0, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на соответствующих страницах для [.NET Core 1.1](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) и [.NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-116">See [.NET Core 1.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) and [.NET Core 1.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.1 and .NET Core 1.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="d7ef4-117">Ознакомьтесь с дополнительными сведениями и воспользуйтесь ссылками для скачивания для [.NET Core 1.1](https://www.microsoft.com/net/download/dotnet-core/1.1) или [.NET Core 1.0](https://www.microsoft.com/net/download/dotnet-core/1.0).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-117">For download links and more information, see [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="d7ef4-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d7ef4-118">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="d7ef4-119">Платформа .NET Core 3.0 поддерживается на устройствах под управлением следующих версий macOS:</span><span class="sxs-lookup"><span data-stu-id="d7ef4-119">.NET Core 3.0 is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="d7ef4-120">macOS 10.13 "High Sierra" и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="d7ef4-120">macOS 10.13 "High Sierra" and later versions</span></span>

<span data-ttu-id="d7ef4-121">Полный список операционных систем, дистрибутивов и версий, поддерживаемых .NET Core 3.0, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [версий ОС, поддерживаемых .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-121">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="d7ef4-122">Ознакомьтесь с дополнительными сведениями и воспользуйтесь ссылками для скачивания [.NET Core 3.0](https://www.microsoft.com/net/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-122">For download links and more information, see [.NET Core 3.0 downloads](https://www.microsoft.com/net/download/dotnet-core/3.0).</span></span>

---

## <a name="net-core-dependencies"></a><span data-ttu-id="d7ef4-123">Зависимости .NET Core</span><span class="sxs-lookup"><span data-stu-id="d7ef4-123">.NET Core dependencies</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d7ef4-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d7ef4-124">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d7ef4-125">Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-125">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="d7ef4-126">При возникновении проблем с установкой в macOS обратитесь к разделу с описанием [известных проблем](https://github.com/dotnet/core/tree/master/release-notes/2.1), соответствующему установленной версии.</span><span class="sxs-lookup"><span data-stu-id="d7ef4-126">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1) topic for the version you have installed.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d7ef4-127">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d7ef4-127">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d7ef4-128">При выполнении в macOS платформе .NET Core 1.x требуется OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="d7ef4-128">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="d7ef4-129">Легко получить OpenSSL можно с помощью диспетчера пакетов [Homebrew ("brew")](https://brew.sh/) для macOS.</span><span class="sxs-lookup"><span data-stu-id="d7ef4-129">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="d7ef4-130">После установки *brew* установите OpenSSL, выполнив следующие команды в окне терминала (аналог командной строки):</span><span class="sxs-lookup"><span data-stu-id="d7ef4-130">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="d7ef4-131">Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-131">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="d7ef4-132">При возникновении проблем с установкой в macOS см. к разделы с описанием [известных проблем в версии 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) и [в версии 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-132">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="d7ef4-133">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d7ef4-133">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="d7ef4-134">Скачайте и установите пакет SDK для .NET Core со страницы [Загрузки .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-134">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="d7ef4-135">При возникновении проблем с установкой в macOS обратитесь к статье с [заметками о выпуске](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md), соответствующей установленной версии.</span><span class="sxs-lookup"><span data-stu-id="d7ef4-135">If you have problems with the installation on macOS, consult the [Release notes](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) topic for the version you have installed.</span></span>

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a><span data-ttu-id="d7ef4-136">Увеличение максимального лимита на число открытых файлов (версии .NET Core до версии пакета SDK для .NET Core 2.0.2)</span><span class="sxs-lookup"><span data-stu-id="d7ef4-136">Increase the maximum open file limit (.NET Core versions before .NET Core SDK 2.0.2)</span></span>

<span data-ttu-id="d7ef4-137">В прежних версиях .NET Core (до версии пакета SDK для .NET Core 2.0.2) лимит на число открытых файлов, используемый по умолчанию в macOS, может оказаться недостаточным для некоторых рабочих нагрузок .NET Core, таких как восстановление проектов или выполнение модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="d7ef4-137">In older .NET Core versions (before .NET Core SDK 2.0.2), the default open file limit on macOS may not be sufficient for some .NET Core workloads, such as restoring projects or running unit tests.</span></span>

<span data-ttu-id="d7ef4-138">Этот лимит можно увеличить, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d7ef4-138">You can increase this limit by following these steps:</span></span>

1. <span data-ttu-id="d7ef4-139">В текстовом редакторе создайте файл _/Library/LaunchDaemons/limit.maxfiles.plist_ и сохраните его со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="d7ef4-139">Using a text editor, create a new file _/Library/LaunchDaemons/limit.maxfiles.plist_, and save the file with this content:</span></span>

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
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

2. <span data-ttu-id="d7ef4-140">В окне терминала выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d7ef4-140">In a terminal window, run the following command:</span></span>

   ```console
   echo 'ulimit -n 2048' | sudo tee -a /etc/profile
   ```

3. <span data-ttu-id="d7ef4-141">Перезагрузите Mac, чтобы применить эти параметры.</span><span class="sxs-lookup"><span data-stu-id="d7ef4-141">Reboot your Mac to apply these settings.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="d7ef4-142">Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="d7ef4-142">Visual Studio for Mac</span></span>

<span data-ttu-id="d7ef4-143">Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор.</span><span class="sxs-lookup"><span data-stu-id="d7ef4-143">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="d7ef4-144">Если же вы хотите разрабатывать приложения .NET Core в интегрированной среде разработки Mac, можно использовать [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="d7ef4-144">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span>

<span data-ttu-id="d7ef4-145">Чтобы разрабатывать приложения .NET Core в macOS с помощью Visual Studio для Mac, нужны следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="d7ef4-145">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="d7ef4-146">Поддерживаемая версия операционной системы macOS</span><span class="sxs-lookup"><span data-stu-id="d7ef4-146">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="d7ef4-147">OpenSSL (Только .NET Core 1.x. .NET Core 2.x использует службы безопасности, по умолчанию доступные в macOS.)</span><span class="sxs-lookup"><span data-stu-id="d7ef4-147">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="d7ef4-148">Пакет SDK .NET Core для Mac</span><span class="sxs-lookup"><span data-stu-id="d7ef4-148">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="d7ef4-149">Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="d7ef4-149">Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
