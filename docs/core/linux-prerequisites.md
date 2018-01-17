---
title: "Необходимые компоненты для .NET Core в Linux"
description: "Поддерживаемые версии Linux и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с Linux."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.workload: dotnetcore
ms.openlocfilehash: ec08d9fa3ad672400b61c269da0c6a70ed9ef2f5
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="6d2b8-104">Необходимые компоненты для .NET Core в Linux</span><span class="sxs-lookup"><span data-stu-id="6d2b8-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="6d2b8-105">В этой статье описываются зависимости, необходимые для разработки приложений .NET Core в Linux.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="6d2b8-106">Поддерживаемые дистрибутивы и версии Linux, а также перечисленные ниже зависимости относятся к двум способам разработки приложений .NET Core в Linux:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="6d2b8-107">командная строка и любой редактор;</span><span class="sxs-lookup"><span data-stu-id="6d2b8-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="6d2b8-108">Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="6d2b8-109">Поддерживаемые версии Linux</span><span class="sxs-lookup"><span data-stu-id="6d2b8-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6d2b8-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="6d2b8-111">.NET Core 2.0 воспринимает Linux как отдельную операционную систему.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="6d2b8-112">Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="6d2b8-113">.NET Core 2.x поддерживается в следующих дистрибутивах и версиях 64-разрядной версии Linux (`x86_64` или `amd64`):</span><span class="sxs-lookup"><span data-stu-id="6d2b8-113">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

 * <span data-ttu-id="6d2b8-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="6d2b8-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="6d2b8-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="6d2b8-115">CentOS 7</span></span>
 * <span data-ttu-id="6d2b8-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="6d2b8-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="6d2b8-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="6d2b8-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="6d2b8-118">Debian 8.7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="6d2b8-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="6d2b8-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="6d2b8-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="6d2b8-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="6d2b8-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="6d2b8-121">openSUSE 42.2 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="6d2b8-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="6d2b8-122">SUSE Enterprise Linux (SLES) 12 с пакетом обновления 2 (SP2) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="6d2b8-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="6d2b8-123">Полный список операционных систем, поддерживаемых .NET Core 2.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6d2b8-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6d2b8-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6d2b8-125">.NET Core 1.x поддерживается в следующих дистрибутивах и версиях 64-разрядной версии Linux (`x86_64` или `amd64`):</span><span class="sxs-lookup"><span data-stu-id="6d2b8-125">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="6d2b8-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="6d2b8-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="6d2b8-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="6d2b8-127">CentOS 7</span></span>
* <span data-ttu-id="6d2b8-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="6d2b8-128">Oracle Linux 7</span></span>
* <span data-ttu-id="6d2b8-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="6d2b8-129">Fedora 24</span></span>
* <span data-ttu-id="6d2b8-130">Debian 8.2 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="6d2b8-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="6d2b8-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\\*</span><span class="sxs-lookup"><span data-stu-id="6d2b8-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\\*</span></span>
 * <span data-ttu-id="6d2b8-132">Ubuntu 16.10 поддерживается последним выпуском исправлений для .NET Core 1.1</span><span class="sxs-lookup"><span data-stu-id="6d2b8-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="6d2b8-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="6d2b8-133">Linux Mint 17</span></span>
* <span data-ttu-id="6d2b8-134">openSUSE 42.1 или более поздней версии (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="6d2b8-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="6d2b8-135">Полный список операционных систем, поддерживаемых .NET Core 1.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6d2b8-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="6d2b8-136">Зависимости дистрибутивов Linux</span><span class="sxs-lookup"><span data-stu-id="6d2b8-136">Linux distribution dependencies</span></span>

<span data-ttu-id="6d2b8-137">Ниже представлены примеры.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-137">The following are intended to be examples.</span></span> <span data-ttu-id="6d2b8-138">Точные версии и имена могут немного отличаться в зависимости от используемого дистрибутива Linux.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-138">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="6d2b8-139">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6d2b8-139">Ubuntu</span></span>

<span data-ttu-id="6d2b8-140">Для дистрибутивов Ubuntu должны быть установлены следующие библиотеки:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-140">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="6d2b8-141">libunwind8</span><span class="sxs-lookup"><span data-stu-id="6d2b8-141">libunwind8</span></span>
* <span data-ttu-id="6d2b8-142">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="6d2b8-142">liblttng-ust0</span></span>
* <span data-ttu-id="6d2b8-143">libcurl3</span><span class="sxs-lookup"><span data-stu-id="6d2b8-143">libcurl3</span></span>
* <span data-ttu-id="6d2b8-144">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="6d2b8-144">libssl1.0.0</span></span>
* <span data-ttu-id="6d2b8-145">libuuid1</span><span class="sxs-lookup"><span data-stu-id="6d2b8-145">libuuid1</span></span>
* <span data-ttu-id="6d2b8-146">libkrb5</span><span class="sxs-lookup"><span data-stu-id="6d2b8-146">libkrb5</span></span>
* <span data-ttu-id="6d2b8-147">zlib1g</span><span class="sxs-lookup"><span data-stu-id="6d2b8-147">zlib1g</span></span>
* <span data-ttu-id="6d2b8-148">libicu52 (для 14.X)</span><span class="sxs-lookup"><span data-stu-id="6d2b8-148">libicu52 (for 14.X)</span></span>
* <span data-ttu-id="6d2b8-149">libicu55 (для 16.X)</span><span class="sxs-lookup"><span data-stu-id="6d2b8-149">libicu55 (for 16.X)</span></span>
* <span data-ttu-id="6d2b8-150">libicu57 (для 17.X)</span><span class="sxs-lookup"><span data-stu-id="6d2b8-150">libicu57 (for 17.X)</span></span>

### <a name="centos"></a><span data-ttu-id="6d2b8-151">CentOS</span><span class="sxs-lookup"><span data-stu-id="6d2b8-151">CentOS</span></span>

<span data-ttu-id="6d2b8-152">Для дистрибутивов CentOS должны быть установлены следующие библиотеки:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-152">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="6d2b8-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="6d2b8-153">libunwind</span></span>
* <span data-ttu-id="6d2b8-154">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="6d2b8-154">lttng-ust</span></span>
* <span data-ttu-id="6d2b8-155">libcurl</span><span class="sxs-lookup"><span data-stu-id="6d2b8-155">libcurl</span></span>
* <span data-ttu-id="6d2b8-156">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="6d2b8-156">openssl-libs</span></span>
* <span data-ttu-id="6d2b8-157">libuuid</span><span class="sxs-lookup"><span data-stu-id="6d2b8-157">libuuid</span></span>
* <span data-ttu-id="6d2b8-158">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="6d2b8-158">krb5-libs</span></span>
* <span data-ttu-id="6d2b8-159">libicu</span><span class="sxs-lookup"><span data-stu-id="6d2b8-159">libicu</span></span>
* <span data-ttu-id="6d2b8-160">zlib</span><span class="sxs-lookup"><span data-stu-id="6d2b8-160">zlib</span></span>

<span data-ttu-id="6d2b8-161">Дополнительные сведения о зависимостях см. в статье об [автономных приложениях Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="6d2b8-161">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="6d2b8-162">Установка зависимостей .NET Core с помощью собственных установщиков</span><span class="sxs-lookup"><span data-stu-id="6d2b8-162">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="6d2b8-163">Для поддерживаемых дистрибутивов и версий Linux доступны собственные установщики .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-163">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="6d2b8-164">Собственные установщики требуют доступа администратора (sudo) к серверу.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-164">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="6d2b8-165">Преимущество использования собственного установщика заключается в том, что он устанавливает все собственные зависимости .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-165">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="6d2b8-166">Собственные установщики также устанавливают пакет SDK для .NET Core в масштабе всей системы.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-166">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="6d2b8-167">В Linux есть два варианта выбора пакета установщика:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-167">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="6d2b8-168">диспетчер пакетов на основе веб-канала, например apt-get для Ubuntu или yum для CentOS/RHEL;</span><span class="sxs-lookup"><span data-stu-id="6d2b8-168">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="6d2b8-169">сами пакеты (DEB или RPM).</span><span class="sxs-lookup"><span data-stu-id="6d2b8-169">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="6d2b8-170">Установка с помощью скрипта установщика .NET Core</span><span class="sxs-lookup"><span data-stu-id="6d2b8-170">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="6d2b8-171">Скрипты `dotnet-install` служат для установки цепочки инструментов CLI и общей среды выполнения без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-171">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="6d2b8-172">Вы можете скачать скрипт по адресу: https://dot.net/v1/dotnet-install.sh</span><span class="sxs-lookup"><span data-stu-id="6d2b8-172">You can download the script from: https://dot.net/v1/dotnet-install.sh</span></span>

<span data-ttu-id="6d2b8-173">Скрипт bash установщика используется в сценариях автоматизации и установки без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-173">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="6d2b8-174">Скрипт также считывает параметры PowerShell, чтобы их можно было использовать с этим скриптом в системах Linux и OS X.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-174">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d2b8-175">Перед запуском скрипта установите все необходимые [зависимости](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="6d2b8-175">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="6d2b8-176">Установка .NET Core для Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="6d2b8-176">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="6d2b8-177">Установка .NET Core в RHEL 7</span><span class="sxs-lookup"><span data-stu-id="6d2b8-177">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="6d2b8-178">Включите канал Red Hat .NET, доступный в рамках подписки на RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-178">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="6d2b8-179">Для Red Hat Enterprise 7 Server используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-179">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="6d2b8-180">Для Red Hat Enterprise 7 Workstation используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-180">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="6d2b8-181">For Red Hat Enterprise 7 HPC Compute Node используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-181">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="6d2b8-182">Установите средство scl.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-182">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="6d2b8-183">Установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="6d2b8-183">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6d2b8-184">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-184">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="6d2b8-185">Установка пакета SDK для .NET Core 2.0 и среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6d2b8-185">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="6d2b8-186">Включите пакет SDK для .NET Core 2.0 или среду выполнения для своего окружения.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-186">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6d2b8-187">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-187">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6d2b8-188">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-188">**.NET Core 1.1**</span></span>

<span data-ttu-id="6d2b8-189">Установка пакета SDK для .NET Core 1.1 и среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6d2b8-189">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="6d2b8-190">Включите пакет SDK для .NET Core 1.1 или среду выполнения для своего окружения.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-190">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="6d2b8-191">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-191">**.NET Core 1.0**</span></span>

<span data-ttu-id="6d2b8-192">Установка пакета SDK для .NET Core 1.0 и среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6d2b8-192">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="6d2b8-193">Включите пакет SDK для .NET Core 1.0 или среду выполнения для своего окружения.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-193">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="6d2b8-194">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-194">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="6d2b8-195">Справку по регистрации для доступа к каналу Red Hat .NET см. в [главе 1 руководства по началу работы с .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) на сайте Red Hat.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-195">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="6d2b8-196">Установка .NET Core для Ubuntu 14.04, 16.04, 16.10 и Linux Mint 17 и 18 (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="6d2b8-196">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="6d2b8-197">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-197">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6d2b8-198">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-198">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="6d2b8-199">Зарегистрируйте ключ продукта Майкрософт как доверенный.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-199">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="6d2b8-200">Установите веб-канал пакета узла требуемой версии.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-200">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="6d2b8-201">**Ubuntu 17.10**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-201">**Ubuntu 17.10**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-artful-prod artful main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```
   <span data-ttu-id="6d2b8-202">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-202">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="6d2b8-203">**Ubuntu 16.04 и Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-203">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="6d2b8-204">**Ubuntu 14.04 и Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-204">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="6d2b8-205">Установите .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-205">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.1.3
   ```

4. <span data-ttu-id="6d2b8-206">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-206">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6d2b8-207">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-207">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="6d2b8-208">Установите веб-канал пакета узла требуемой версии.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-208">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="6d2b8-209">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-209">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="6d2b8-210">**Ubuntu 16.04 и Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-210">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="6d2b8-211">**Ubuntu 14.04 и Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-211">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="6d2b8-212">Установите .NET Core 1.x на Ubuntu или Linux Mint.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-212">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="6d2b8-213">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-213">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="6d2b8-214">Установка .NET Core для Debian 8 или Debian 9 (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="6d2b8-214">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="6d2b8-215">Чтобы установить .NET Core на Debian 8 или Debian 9 (64-разрядной версии), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-215">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="6d2b8-216">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-216">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="6d2b8-217">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-217">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6d2b8-218">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-218">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="6d2b8-219">Установите системные компоненты.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-219">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="6d2b8-220">Зарегистрируйте доверенный ключ продукта корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-220">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="6d2b8-221">Зарегистрируйте канал продукта корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-221">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="6d2b8-222">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-222">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="6d2b8-223">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-223">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="6d2b8-224">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-224">Install .NET Core SDK.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="6d2b8-225">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-225">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. <span data-ttu-id="6d2b8-226">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-226">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6d2b8-227">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-227">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="6d2b8-228">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-228">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="6d2b8-229">Скачайте двоичные файлы пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="6d2b8-229">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="6d2b8-230">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-230">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="6d2b8-231">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-231">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. <span data-ttu-id="6d2b8-232">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-232">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="6d2b8-233">Установка .NET Core на Fedora 24, Fedora 25 или Fedora 26 (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="6d2b8-233">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="6d2b8-234">Чтобы установить .NET Core 2.x на Fedora 26 или Fedora 25 или .NET Core 1.x на Fedora 24, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-234">To install .NET Core 2.x on Fedora 26 or Fedora 25, or .NET Core 1.x on Fedora 24:</span></span>

1. <span data-ttu-id="6d2b8-235">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-235">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="6d2b8-236">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-236">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6d2b8-237">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-237">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="6d2b8-238">**Fedora 26 или Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-238">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="6d2b8-239">Зарегистрируйте ключ сигнатуры Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-239">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="6d2b8-240">Добавьте канал продукта dotnet.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-240">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="6d2b8-241">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-241">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="6d2b8-242">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-242">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6d2b8-243">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-243">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6d2b8-244">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="6d2b8-244">**Fedora 24**</span></span>

2. <span data-ttu-id="6d2b8-245">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-245">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="6d2b8-246">Скачайте двоичный файл пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="6d2b8-246">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="6d2b8-247">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-247">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="6d2b8-248">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-248">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="6d2b8-249">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-249">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="6d2b8-250">Установка .NET Core для CentOS 7.1 (64-разрядной версии) и Oracle Linux 7.1 (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="6d2b8-250">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="6d2b8-251">Чтобы установить .NET Core для CentOS 7.1 (64-разрядной версии) и Oracle Linux 7.1 (64-разрядной версии), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-251">To install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="6d2b8-252">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-252">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="6d2b8-253">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-253">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6d2b8-254">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-254">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="6d2b8-255">Зарегистрируйте ключ сигнатуры Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-255">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="6d2b8-256">Добавьте канал продукта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-256">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="6d2b8-257">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-257">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="6d2b8-258">Добавьте каталог dotnet в переменную PATH.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-258">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6d2b8-259">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-259">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="6d2b8-260">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-260">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="6d2b8-261">Скачайте двоичный файл пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="6d2b8-261">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="6d2b8-262">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-262">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="6d2b8-263">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-263">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="6d2b8-264">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-264">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="6d2b8-265">Установка .NET Core для SUSE Linux Enterprise Server (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="6d2b8-265">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="6d2b8-266">Чтобы установить .NET Core 2.x для SUSE Linux Enterprise Server (SLES) 12 с пакетом обновления 2 (SP2) (64-разрядной версии), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-266">To install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="6d2b8-267">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-267">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="6d2b8-268">Добавьте канал продукта dotnet.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-268">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="6d2b8-269">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-269">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="6d2b8-270">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-270">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="6d2b8-271">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-271">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="6d2b8-272">Установка .NET Core для openSUSE (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="6d2b8-272">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="6d2b8-273">Чтобы установить .NET Core 2.x для openSUSE или .NET Core 1.x для openSUSE (64-разрядная версия), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6d2b8-273">To install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="6d2b8-274">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-274">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="6d2b8-275">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-275">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6d2b8-276">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-276">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="6d2b8-277">Зарегистрируйте ключ сигнатуры Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-277">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="6d2b8-278">Добавьте канал продукта dotnet.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-278">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="6d2b8-279">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-279">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="6d2b8-280">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-280">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6d2b8-281">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6d2b8-281">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="6d2b8-282">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-282">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="6d2b8-283">Скачайте двоичный файл пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="6d2b8-283">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="6d2b8-284">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-284">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="6d2b8-285">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-285">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="6d2b8-286">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-286">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="6d2b8-287">Если при установке .NET Core 2.x в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к разделу с описанием [известных проблем в версии 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0) для используемого дистрибутива и версии.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-287">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="6d2b8-288">Если при установке .NET Core 1.x в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к разделам с описанием [известных проблем в версии 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) и [версии 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) для используемого дистрибутива и версии.</span><span class="sxs-lookup"><span data-stu-id="6d2b8-288">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>
