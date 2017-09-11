---
title: "Необходимые компоненты для .NET Core в Linux"
description: "Поддерживаемые версии Linux и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с Linux."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 7bbb8405f39a52d2798fd1dbc78f3116cb3bedbb
ms.openlocfilehash: 9864ffa31caa007cb649a9e6e8913863d9cb2c35
ms.contentlocale: ru-ru
ms.lasthandoff: 09/05/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="e8adf-104">Необходимые компоненты для .NET Core в Linux</span><span class="sxs-lookup"><span data-stu-id="e8adf-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="e8adf-105">В этой статье описываются зависимости, необходимые для разработки приложений .NET Core в Linux.</span><span class="sxs-lookup"><span data-stu-id="e8adf-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="e8adf-106">Поддерживаемые дистрибутивы и версии Linux, а также перечисленные ниже зависимости относятся к двум способам разработки приложений .NET Core в Linux:</span><span class="sxs-lookup"><span data-stu-id="e8adf-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="e8adf-107">командная строка и любой редактор;</span><span class="sxs-lookup"><span data-stu-id="e8adf-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="e8adf-108">Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="e8adf-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="e8adf-109">Поддерживаемые версии Linux</span><span class="sxs-lookup"><span data-stu-id="e8adf-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e8adf-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="e8adf-111">.NET Core 2.0 воспринимает Linux как отдельную операционную систему.</span><span class="sxs-lookup"><span data-stu-id="e8adf-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="e8adf-112">Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="e8adf-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="e8adf-113">.NET Core 2.x поддерживается в следующих дистрибутивах и версиях 64-разрядной Linux:</span><span class="sxs-lookup"><span data-stu-id="e8adf-113">NET Core 2.x is supported on the following Linux x64 distributions/versions:</span></span>

 * <span data-ttu-id="e8adf-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="e8adf-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="e8adf-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e8adf-115">CentOS 7</span></span>
 * <span data-ttu-id="e8adf-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="e8adf-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="e8adf-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="e8adf-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="e8adf-118">Debian 8.7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e8adf-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="e8adf-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="e8adf-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="e8adf-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="e8adf-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="e8adf-121">openSUSE 42.2 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e8adf-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="e8adf-122">SUSE Enterprise Linux (SLES) 12 с пакетом обновления 2 (SP2) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e8adf-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="e8adf-123">Полный список операционных систем, поддерживаемых .NET Core 2.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="e8adf-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e8adf-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e8adf-125">.NET Core 1.x поддерживается в следующих дистрибутивах и версиях 64-разрядной Linux:</span><span class="sxs-lookup"><span data-stu-id="e8adf-125">.NET Core 1.x is supported on the following Linux x64 distributions/versions:</span></span>

* <span data-ttu-id="e8adf-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="e8adf-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="e8adf-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e8adf-127">CentOS 7</span></span>
* <span data-ttu-id="e8adf-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="e8adf-128">Oracle Linux 7</span></span>
* <span data-ttu-id="e8adf-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="e8adf-129">Fedora 24</span></span>
* <span data-ttu-id="e8adf-130">Debian 8.2 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e8adf-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="e8adf-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="e8adf-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="e8adf-132">Ubuntu 16.10 поддерживается последним выпуском исправлений для .NET Core 1.1</span><span class="sxs-lookup"><span data-stu-id="e8adf-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="e8adf-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="e8adf-133">Linux Mint 17</span></span>
* <span data-ttu-id="e8adf-134">openSUSE 42.1 или более поздней версии (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="e8adf-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="e8adf-135">Полный список операционных систем, поддерживаемых .NET Core 1.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="e8adf-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="e8adf-136">Зависимости дистрибутивов Linux</span><span class="sxs-lookup"><span data-stu-id="e8adf-136">Linux distribution dependencies</span></span>

### <a name="ubuntu"></a><span data-ttu-id="e8adf-137">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="e8adf-137">Ubuntu</span></span>

<span data-ttu-id="e8adf-138">Для дистрибутивов Ubuntu должны быть установлены следующие библиотеки:</span><span class="sxs-lookup"><span data-stu-id="e8adf-138">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="e8adf-139">libunwind8</span><span class="sxs-lookup"><span data-stu-id="e8adf-139">libunwind8</span></span>
* <span data-ttu-id="e8adf-140">libunwind8-dev</span><span class="sxs-lookup"><span data-stu-id="e8adf-140">libunwind8-dev</span></span>
* <span data-ttu-id="e8adf-141">gettext</span><span class="sxs-lookup"><span data-stu-id="e8adf-141">gettext</span></span>
* <span data-ttu-id="e8adf-142">libicu-dev</span><span class="sxs-lookup"><span data-stu-id="e8adf-142">libicu-dev</span></span>
* <span data-ttu-id="e8adf-143">liblttng-ust-dev</span><span class="sxs-lookup"><span data-stu-id="e8adf-143">liblttng-ust-dev</span></span>
* <span data-ttu-id="e8adf-144">libcurl4-openssl-dev</span><span class="sxs-lookup"><span data-stu-id="e8adf-144">libcurl4-openssl-dev</span></span>
* <span data-ttu-id="e8adf-145">libssl-dev</span><span class="sxs-lookup"><span data-stu-id="e8adf-145">libssl-dev</span></span>
* <span data-ttu-id="e8adf-146">uuid-dev</span><span class="sxs-lookup"><span data-stu-id="e8adf-146">uuid-dev</span></span>
* <span data-ttu-id="e8adf-147">unzip</span><span class="sxs-lookup"><span data-stu-id="e8adf-147">unzip</span></span>

### <a name="centos"></a><span data-ttu-id="e8adf-148">CentOS</span><span class="sxs-lookup"><span data-stu-id="e8adf-148">CentOS</span></span>

<span data-ttu-id="e8adf-149">Для дистрибутивов CentOS должны быть установлены следующие библиотеки:</span><span class="sxs-lookup"><span data-stu-id="e8adf-149">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="e8adf-150">deltarpm</span><span class="sxs-lookup"><span data-stu-id="e8adf-150">deltarpm</span></span>
* <span data-ttu-id="e8adf-151">epel-release</span><span class="sxs-lookup"><span data-stu-id="e8adf-151">epel-release</span></span>
* <span data-ttu-id="e8adf-152">unzip</span><span class="sxs-lookup"><span data-stu-id="e8adf-152">unzip</span></span>
* <span data-ttu-id="e8adf-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="e8adf-153">libunwind</span></span>
* <span data-ttu-id="e8adf-154">gettext</span><span class="sxs-lookup"><span data-stu-id="e8adf-154">gettext</span></span>
* <span data-ttu-id="e8adf-155">libcurl-devel</span><span class="sxs-lookup"><span data-stu-id="e8adf-155">libcurl-devel</span></span>
* <span data-ttu-id="e8adf-156">openssl-devel</span><span class="sxs-lookup"><span data-stu-id="e8adf-156">openssl-devel</span></span>
* <span data-ttu-id="e8adf-157">zlib</span><span class="sxs-lookup"><span data-stu-id="e8adf-157">zlib</span></span>
* <span data-ttu-id="e8adf-158">libicu-devel</span><span class="sxs-lookup"><span data-stu-id="e8adf-158">libicu-devel</span></span>

<span data-ttu-id="e8adf-159">Дополнительные сведения о зависимостях см. в статье об [автономных приложениях Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="e8adf-159">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="e8adf-160">Установка зависимостей .NET Core с помощью собственных установщиков</span><span class="sxs-lookup"><span data-stu-id="e8adf-160">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="e8adf-161">Для поддерживаемых дистрибутивов и версий Linux доступны собственные установщики .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-161">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="e8adf-162">Собственные установщики требуют доступа администратора (sudo) к серверу.</span><span class="sxs-lookup"><span data-stu-id="e8adf-162">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="e8adf-163">Преимущество использования собственного установщика заключается в том, что он устанавливает все собственные зависимости .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-163">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="e8adf-164">Собственные установщики также устанавливают пакет SDK для .NET Core в масштабе всей системы.</span><span class="sxs-lookup"><span data-stu-id="e8adf-164">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="e8adf-165">В Linux есть два варианта выбора пакета установщика:</span><span class="sxs-lookup"><span data-stu-id="e8adf-165">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="e8adf-166">диспетчер пакетов на основе веб-канала, например apt-get для Ubuntu или yum для CentOS/RHEL;</span><span class="sxs-lookup"><span data-stu-id="e8adf-166">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="e8adf-167">сами пакеты (DEB или RPM).</span><span class="sxs-lookup"><span data-stu-id="e8adf-167">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="e8adf-168">Установка с помощью скрипта установщика .NET Core</span><span class="sxs-lookup"><span data-stu-id="e8adf-168">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="e8adf-169">Скрипты `dotnet-install` служат для установки цепочки инструментов CLI и общей среды выполнения без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="e8adf-169">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="e8adf-170">Скачать скрипты можно в [репозитории CLI GitHub](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain).</span><span class="sxs-lookup"><span data-stu-id="e8adf-170">You can download the scripts from the [CLI GitHub repo](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain).</span></span>

<span data-ttu-id="e8adf-171">Скрипт bash установщика используется в сценариях автоматизации и установки без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="e8adf-171">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="e8adf-172">Скрипт также считывает параметры PowerShell, чтобы их можно было использовать с этим скриптом в системах Linux и OS X.</span><span class="sxs-lookup"><span data-stu-id="e8adf-172">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8adf-173">Перед запуском скрипта установите все необходимые [зависимости](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="e8adf-173">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="e8adf-174">Установка .NET Core для Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e8adf-174">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="e8adf-175">Установка .NET Core в RHEL 7</span><span class="sxs-lookup"><span data-stu-id="e8adf-175">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="e8adf-176">Включите канал Red Hat .NET, доступный в рамках подписки на RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="e8adf-176">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="e8adf-177">Для Red Hat Enterprise 7 Server используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e8adf-177">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="e8adf-178">Для Red Hat Enterprise 7 Workstation используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e8adf-178">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="e8adf-179">For Red Hat Enterprise 7 HPC Compute Node используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e8adf-179">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="e8adf-180">Установите средство scl.</span><span class="sxs-lookup"><span data-stu-id="e8adf-180">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="e8adf-181">Установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="e8adf-181">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e8adf-182">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-182">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="e8adf-183">Установка пакета SDK для .NET Core 2.0 и среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e8adf-183">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="e8adf-184">Включите пакет SDK для .NET Core 2.0 или среду выполнения для своего окружения.</span><span class="sxs-lookup"><span data-stu-id="e8adf-184">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e8adf-185">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-185">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e8adf-186">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="e8adf-186">**.NET Core 1.1**</span></span>

<span data-ttu-id="e8adf-187">Установка пакета SDK для .NET Core 1.1 и среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e8adf-187">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="e8adf-188">Включите пакет SDK для .NET Core 1.1 или среду выполнения для своего окружения.</span><span class="sxs-lookup"><span data-stu-id="e8adf-188">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="e8adf-189">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="e8adf-189">**.NET Core 1.0**</span></span>

<span data-ttu-id="e8adf-190">Установка пакета SDK для .NET Core 1.0 и среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e8adf-190">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="e8adf-191">Включите пакет SDK для .NET Core 1.0 или среду выполнения для своего окружения.</span><span class="sxs-lookup"><span data-stu-id="e8adf-191">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="e8adf-192">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="e8adf-192">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="e8adf-193">Справку по регистрации для доступа к каналу Red Hat .NET см. в [главе 1 руководства по началу работы с .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) на сайте Red Hat.</span><span class="sxs-lookup"><span data-stu-id="e8adf-193">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="e8adf-194">Установка .NET Core для Ubuntu 14.04, 16.04, 16.10 и Linux Mint 17 и 18 (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="e8adf-194">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="e8adf-195">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-195">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e8adf-196">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-196">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="e8adf-197">Зарегистрируйте ключ продукта Майкрософт как доверенный.</span><span class="sxs-lookup"><span data-stu-id="e8adf-197">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="e8adf-198">Установите веб-канал пакета узла требуемой версии.</span><span class="sxs-lookup"><span data-stu-id="e8adf-198">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="e8adf-199">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="e8adf-199">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="e8adf-200">**Ubuntu 16.04 и Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="e8adf-200">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="e8adf-201">**Ubuntu 14.04 и Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="e8adf-201">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="e8adf-202">Установите .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-202">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="e8adf-203">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="e8adf-203">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e8adf-204">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-204">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="e8adf-205">Установите веб-канал пакета узла требуемой версии.</span><span class="sxs-lookup"><span data-stu-id="e8adf-205">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="e8adf-206">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="e8adf-206">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="e8adf-207">**Ubuntu 16.04 и Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="e8adf-207">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="e8adf-208">**Ubuntu 14.04 и Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="e8adf-208">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="e8adf-209">Установите .NET Core 1.x на Ubuntu или Linux Mint.</span><span class="sxs-lookup"><span data-stu-id="e8adf-209">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="e8adf-210">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="e8adf-210">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="e8adf-211">Установка .NET Core для Debian 8 или Debian 9 (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="e8adf-211">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="e8adf-212">Чтобы установить .NET Core на Debian 8 или Debian 9 (64-разрядной версии), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e8adf-212">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="e8adf-213">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-213">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="e8adf-214">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="e8adf-214">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e8adf-215">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-215">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="e8adf-216">Установите системные компоненты.</span><span class="sxs-lookup"><span data-stu-id="e8adf-216">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="e8adf-217">Зарегистрируйте доверенный ключ продукта корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e8adf-217">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="e8adf-218">Зарегистрируйте канал продукта корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e8adf-218">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="e8adf-219">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="e8adf-219">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="e8adf-220">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="e8adf-220">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="e8adf-221">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-221">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="e8adf-222">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="e8adf-222">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e8adf-223">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-223">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="e8adf-224">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="e8adf-224">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="e8adf-225">Скачайте двоичные файлы пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="e8adf-225">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="e8adf-226">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-226">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="e8adf-227">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="e8adf-227">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="e8adf-228">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="e8adf-228">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="e8adf-229">Установка .NET Core на Fedora 24, Fedora 25 или Fedora 26 (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="e8adf-229">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="e8adf-230">Чтобы установить .NET Core на Fedora 26, Fedora 25 (.NET Core 2.x) или Fedora 24 (.NET Core 1.x), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e8adf-230">To Install .NET Core for Fedora 26, Fedora 25 (.NET Core 2.x) or Fedora 24 (.NET Core 1.x):</span></span>

1. <span data-ttu-id="e8adf-231">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-231">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="e8adf-232">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="e8adf-232">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e8adf-233">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-233">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="e8adf-234">**Fedora 26 или Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="e8adf-234">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="e8adf-235">Зарегистрируйте ключ сигнатуры Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e8adf-235">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="e8adf-236">Добавьте канал продукта dotnet.</span><span class="sxs-lookup"><span data-stu-id="e8adf-236">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="e8adf-237">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-237">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="e8adf-238">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="e8adf-238">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e8adf-239">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-239">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e8adf-240">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="e8adf-240">**Fedora 24**</span></span>

2. <span data-ttu-id="e8adf-241">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="e8adf-241">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="e8adf-242">Скачайте двоичный файл пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="e8adf-242">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="e8adf-243">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-243">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="e8adf-244">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="e8adf-244">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="e8adf-245">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="e8adf-245">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="e8adf-246">Установка .NET Core для CentOS 7.1 (64-разрядной версии) и Oracle Linux 7.1 (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="e8adf-246">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="e8adf-247">Чтобы установить .NET Core для CentOS 7.1 (64-разрядной версии) и Oracle Linux 7.1 (64-разрядной версии), выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e8adf-247">To Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="e8adf-248">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-248">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="e8adf-249">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="e8adf-249">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e8adf-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-250">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="e8adf-251">Зарегистрируйте ключ сигнатуры Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e8adf-251">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="e8adf-252">Добавьте канал продукта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e8adf-252">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="e8adf-253">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-253">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="e8adf-254">Добавьте каталог dotnet в переменную PATH.</span><span class="sxs-lookup"><span data-stu-id="e8adf-254">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e8adf-255">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-255">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="e8adf-256">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="e8adf-256">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="e8adf-257">Скачайте двоичный файл пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="e8adf-257">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="e8adf-258">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-258">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="e8adf-259">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="e8adf-259">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="e8adf-260">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="e8adf-260">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="e8adf-261">Установка .NET Core для SUSE Linux Enterprise Server (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="e8adf-261">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="e8adf-262">Чтобы установить .NET Core 2.x для SUSE Linux Enterprise Server (SLES) 12 с пакетом обновления 2 (64-разрядной версии), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e8adf-262">To Install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="e8adf-263">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-263">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="e8adf-264">Добавьте канал продукта dotnet.</span><span class="sxs-lookup"><span data-stu-id="e8adf-264">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="e8adf-265">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-265">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="e8adf-266">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="e8adf-266">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="e8adf-267">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="e8adf-267">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="e8adf-268">Установка .NET Core для openSUSE (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="e8adf-268">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="e8adf-269">Чтобы установить .NET Core 2.x для openSUSE или .NET Core 1.x для openSUSE (64-разрядная версия), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e8adf-269">To Install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="e8adf-270">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-270">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="e8adf-271">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="e8adf-271">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e8adf-272">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-272">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="e8adf-273">Зарегистрируйте ключ сигнатуры Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e8adf-273">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="e8adf-274">Добавьте канал продукта dotnet.</span><span class="sxs-lookup"><span data-stu-id="e8adf-274">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="e8adf-275">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-275">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="e8adf-276">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="e8adf-276">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e8adf-277">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e8adf-277">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="e8adf-278">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="e8adf-278">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="e8adf-279">Скачайте двоичный файл пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="e8adf-279">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="e8adf-280">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8adf-280">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="e8adf-281">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="e8adf-281">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="e8adf-282">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="e8adf-282">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="e8adf-283">Если при установке .NET Core 2.x в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к разделу с описанием [известных проблем в версии 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0) для используемого дистрибутива и версии.</span><span class="sxs-lookup"><span data-stu-id="e8adf-283">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="e8adf-284">Если при установке .NET Core 1.x в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к разделам с описанием [известных проблем в версии 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) и [версии 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) для используемого дистрибутива и версии.</span><span class="sxs-lookup"><span data-stu-id="e8adf-284">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>

