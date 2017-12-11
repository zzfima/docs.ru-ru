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
ms.openlocfilehash: 04fdf26e150e6d489c0641588563f69f24835615
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="07e7f-104">Необходимые компоненты для .NET Core в Linux</span><span class="sxs-lookup"><span data-stu-id="07e7f-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="07e7f-105">В этой статье описываются зависимости, необходимые для разработки приложений .NET Core в Linux.</span><span class="sxs-lookup"><span data-stu-id="07e7f-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="07e7f-106">Поддерживаемые дистрибутивы и версии Linux, а также перечисленные ниже зависимости относятся к двум способам разработки приложений .NET Core в Linux:</span><span class="sxs-lookup"><span data-stu-id="07e7f-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="07e7f-107">командная строка и любой редактор;</span><span class="sxs-lookup"><span data-stu-id="07e7f-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="07e7f-108">Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="07e7f-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="07e7f-109">Поддерживаемые версии Linux</span><span class="sxs-lookup"><span data-stu-id="07e7f-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="07e7f-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="07e7f-111">.NET Core 2.0 воспринимает Linux как отдельную операционную систему.</span><span class="sxs-lookup"><span data-stu-id="07e7f-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="07e7f-112">Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="07e7f-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="07e7f-113">.NET Core 2.x поддерживается в следующих дистрибутивах и версиях 64-разрядной версии Linux (`x86_64` или `amd64`):</span><span class="sxs-lookup"><span data-stu-id="07e7f-113">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

 * <span data-ttu-id="07e7f-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="07e7f-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="07e7f-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="07e7f-115">CentOS 7</span></span>
 * <span data-ttu-id="07e7f-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="07e7f-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="07e7f-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="07e7f-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="07e7f-118">Debian 8.7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="07e7f-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="07e7f-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="07e7f-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="07e7f-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="07e7f-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="07e7f-121">openSUSE 42.2 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="07e7f-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="07e7f-122">SUSE Enterprise Linux (SLES) 12 с пакетом обновления 2 (SP2) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="07e7f-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="07e7f-123">Полный список операционных систем, поддерживаемых .NET Core 2.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="07e7f-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07e7f-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="07e7f-125">.NET Core 1.x поддерживается в следующих дистрибутивах и версиях 64-разрядной версии Linux (`x86_64` или `amd64`):</span><span class="sxs-lookup"><span data-stu-id="07e7f-125">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="07e7f-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="07e7f-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="07e7f-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="07e7f-127">CentOS 7</span></span>
* <span data-ttu-id="07e7f-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="07e7f-128">Oracle Linux 7</span></span>
* <span data-ttu-id="07e7f-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="07e7f-129">Fedora 24</span></span>
* <span data-ttu-id="07e7f-130">Debian 8.2 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="07e7f-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="07e7f-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="07e7f-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="07e7f-132">Ubuntu 16.10 поддерживается последним выпуском исправлений для .NET Core 1.1</span><span class="sxs-lookup"><span data-stu-id="07e7f-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="07e7f-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="07e7f-133">Linux Mint 17</span></span>
* <span data-ttu-id="07e7f-134">openSUSE 42.1 или более поздней версии (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="07e7f-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="07e7f-135">Полный список операционных систем, поддерживаемых .NET Core 1.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="07e7f-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="07e7f-136">Зависимости дистрибутивов Linux</span><span class="sxs-lookup"><span data-stu-id="07e7f-136">Linux distribution dependencies</span></span>

<span data-ttu-id="07e7f-137">Ниже должны быть примеры.</span><span class="sxs-lookup"><span data-stu-id="07e7f-137">The following are intended to be examples.</span></span> <span data-ttu-id="07e7f-138">Точные версии и имена могут немного отличаться на Ваш дистрибутив Linux, по выбору.</span><span class="sxs-lookup"><span data-stu-id="07e7f-138">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="07e7f-139">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="07e7f-139">Ubuntu</span></span>

<span data-ttu-id="07e7f-140">Для дистрибутивов Ubuntu должны быть установлены следующие библиотеки:</span><span class="sxs-lookup"><span data-stu-id="07e7f-140">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="07e7f-141">libunwind8</span><span class="sxs-lookup"><span data-stu-id="07e7f-141">libunwind8</span></span>
* <span data-ttu-id="07e7f-142">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="07e7f-142">liblttng-ust0</span></span>
* <span data-ttu-id="07e7f-143">libcurl3</span><span class="sxs-lookup"><span data-stu-id="07e7f-143">libcurl3</span></span>
* <span data-ttu-id="07e7f-144">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="07e7f-144">libssl1.0.0</span></span>
* <span data-ttu-id="07e7f-145">libuuid1</span><span class="sxs-lookup"><span data-stu-id="07e7f-145">libuuid1</span></span>
* <span data-ttu-id="07e7f-146">libkrb5</span><span class="sxs-lookup"><span data-stu-id="07e7f-146">libkrb5</span></span>
* <span data-ttu-id="07e7f-147">zlib1g</span><span class="sxs-lookup"><span data-stu-id="07e7f-147">zlib1g</span></span>
* <span data-ttu-id="07e7f-148">libicu52 (для 14.X)</span><span class="sxs-lookup"><span data-stu-id="07e7f-148">libicu52 (for 14.X)</span></span>
* <span data-ttu-id="07e7f-149">libicu55 (для 16.X)</span><span class="sxs-lookup"><span data-stu-id="07e7f-149">libicu55 (for 16.X)</span></span>
* <span data-ttu-id="07e7f-150">libicu57 (для 17.X)</span><span class="sxs-lookup"><span data-stu-id="07e7f-150">libicu57 (for 17.X)</span></span>

### <a name="centos"></a><span data-ttu-id="07e7f-151">CentOS</span><span class="sxs-lookup"><span data-stu-id="07e7f-151">CentOS</span></span>

<span data-ttu-id="07e7f-152">Для дистрибутивов CentOS должны быть установлены следующие библиотеки:</span><span class="sxs-lookup"><span data-stu-id="07e7f-152">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="07e7f-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="07e7f-153">libunwind</span></span>
* <span data-ttu-id="07e7f-154">изменить lttng</span><span class="sxs-lookup"><span data-stu-id="07e7f-154">lttng-ust</span></span>
* <span data-ttu-id="07e7f-155">libcurl</span><span class="sxs-lookup"><span data-stu-id="07e7f-155">libcurl</span></span>
* <span data-ttu-id="07e7f-156">библиотеки OpenSSL</span><span class="sxs-lookup"><span data-stu-id="07e7f-156">openssl-libs</span></span>
* <span data-ttu-id="07e7f-157">libuuid</span><span class="sxs-lookup"><span data-stu-id="07e7f-157">libuuid</span></span>
* <span data-ttu-id="07e7f-158">krb5 библиотеки</span><span class="sxs-lookup"><span data-stu-id="07e7f-158">krb5-libs</span></span>
* <span data-ttu-id="07e7f-159">libicu</span><span class="sxs-lookup"><span data-stu-id="07e7f-159">libicu</span></span>
* <span data-ttu-id="07e7f-160">zlib</span><span class="sxs-lookup"><span data-stu-id="07e7f-160">zlib</span></span>

<span data-ttu-id="07e7f-161">Дополнительные сведения о зависимостях см. в статье об [автономных приложениях Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="07e7f-161">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="07e7f-162">Установка зависимостей .NET Core с помощью собственных установщиков</span><span class="sxs-lookup"><span data-stu-id="07e7f-162">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="07e7f-163">Для поддерживаемых дистрибутивов и версий Linux доступны собственные установщики .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-163">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="07e7f-164">Собственные установщики требуют доступа администратора (sudo) к серверу.</span><span class="sxs-lookup"><span data-stu-id="07e7f-164">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="07e7f-165">Преимущество использования собственного установщика заключается в том, что он устанавливает все собственные зависимости .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-165">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="07e7f-166">Собственные установщики также устанавливают пакет SDK для .NET Core в масштабе всей системы.</span><span class="sxs-lookup"><span data-stu-id="07e7f-166">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="07e7f-167">В Linux есть два варианта выбора пакета установщика:</span><span class="sxs-lookup"><span data-stu-id="07e7f-167">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="07e7f-168">диспетчер пакетов на основе веб-канала, например apt-get для Ubuntu или yum для CentOS/RHEL;</span><span class="sxs-lookup"><span data-stu-id="07e7f-168">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="07e7f-169">сами пакеты (DEB или RPM).</span><span class="sxs-lookup"><span data-stu-id="07e7f-169">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="07e7f-170">Установка с помощью скрипта установщика .NET Core</span><span class="sxs-lookup"><span data-stu-id="07e7f-170">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="07e7f-171">Скрипты `dotnet-install` служат для установки цепочки инструментов CLI и общей среды выполнения без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="07e7f-171">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="07e7f-172">Можно загрузить скрипт из: https://dot.net/v1/dotnet-install.sh</span><span class="sxs-lookup"><span data-stu-id="07e7f-172">You can download the script from: https://dot.net/v1/dotnet-install.sh</span></span>

<span data-ttu-id="07e7f-173">Скрипт bash установщика используется в сценариях автоматизации и установки без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="07e7f-173">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="07e7f-174">Скрипт также считывает параметры PowerShell, чтобы их можно было использовать с этим скриптом в системах Linux и OS X.</span><span class="sxs-lookup"><span data-stu-id="07e7f-174">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07e7f-175">Перед запуском скрипта установите все необходимые [зависимости](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="07e7f-175">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="07e7f-176">Установка .NET Core для Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="07e7f-176">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="07e7f-177">Установка .NET Core в RHEL 7</span><span class="sxs-lookup"><span data-stu-id="07e7f-177">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="07e7f-178">Включите канал Red Hat .NET, доступный в рамках подписки на RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="07e7f-178">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="07e7f-179">Для Red Hat Enterprise 7 Server используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07e7f-179">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="07e7f-180">Для Red Hat Enterprise 7 Workstation используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07e7f-180">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="07e7f-181">For Red Hat Enterprise 7 HPC Compute Node используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07e7f-181">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="07e7f-182">Установите средство scl.</span><span class="sxs-lookup"><span data-stu-id="07e7f-182">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="07e7f-183">Установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="07e7f-183">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="07e7f-184">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-184">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="07e7f-185">Установка пакета SDK для .NET Core 2.0 и среды выполнения</span><span class="sxs-lookup"><span data-stu-id="07e7f-185">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="07e7f-186">Включите пакет SDK для .NET Core 2.0 или среду выполнения для своего окружения.</span><span class="sxs-lookup"><span data-stu-id="07e7f-186">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07e7f-187">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-187">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="07e7f-188">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="07e7f-188">**.NET Core 1.1**</span></span>

<span data-ttu-id="07e7f-189">Установка пакета SDK для .NET Core 1.1 и среды выполнения</span><span class="sxs-lookup"><span data-stu-id="07e7f-189">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="07e7f-190">Включите пакет SDK для .NET Core 1.1 или среду выполнения для своего окружения.</span><span class="sxs-lookup"><span data-stu-id="07e7f-190">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="07e7f-191">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="07e7f-191">**.NET Core 1.0**</span></span>

<span data-ttu-id="07e7f-192">Установка пакета SDK для .NET Core 1.0 и среды выполнения</span><span class="sxs-lookup"><span data-stu-id="07e7f-192">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="07e7f-193">Включите пакет SDK для .NET Core 1.0 или среду выполнения для своего окружения.</span><span class="sxs-lookup"><span data-stu-id="07e7f-193">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="07e7f-194">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="07e7f-194">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="07e7f-195">Справку по регистрации для доступа к каналу Red Hat .NET см. в [главе 1 руководства по началу работы с .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) на сайте Red Hat.</span><span class="sxs-lookup"><span data-stu-id="07e7f-195">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="07e7f-196">Установка .NET Core для Ubuntu 14.04, 16.04, 16.10 и Linux Mint 17 и 18 (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="07e7f-196">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="07e7f-197">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-197">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="07e7f-198">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-198">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="07e7f-199">Зарегистрируйте ключ продукта Майкрософт как доверенный.</span><span class="sxs-lookup"><span data-stu-id="07e7f-199">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="07e7f-200">Установите веб-канал пакета узла требуемой версии.</span><span class="sxs-lookup"><span data-stu-id="07e7f-200">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="07e7f-201">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="07e7f-201">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="07e7f-202">**Ubuntu 16.04 и Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="07e7f-202">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="07e7f-203">**Ubuntu 14.04 и Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="07e7f-203">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="07e7f-204">Установите .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-204">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="07e7f-205">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="07e7f-205">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07e7f-206">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-206">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="07e7f-207">Установите веб-канал пакета узла требуемой версии.</span><span class="sxs-lookup"><span data-stu-id="07e7f-207">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="07e7f-208">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="07e7f-208">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="07e7f-209">**Ubuntu 16.04 и Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="07e7f-209">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="07e7f-210">**Ubuntu 14.04 и Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="07e7f-210">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="07e7f-211">Установите .NET Core 1.x на Ubuntu или Linux Mint.</span><span class="sxs-lookup"><span data-stu-id="07e7f-211">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="07e7f-212">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="07e7f-212">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="07e7f-213">Установка .NET Core для Debian 8 или Debian 9 (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="07e7f-213">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="07e7f-214">Чтобы установить .NET Core на Debian 8 или Debian 9 (64-разрядной версии), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="07e7f-214">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="07e7f-215">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-215">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="07e7f-216">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="07e7f-216">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="07e7f-217">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-217">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="07e7f-218">Установите системные компоненты.</span><span class="sxs-lookup"><span data-stu-id="07e7f-218">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="07e7f-219">Зарегистрируйте доверенный ключ продукта корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="07e7f-219">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="07e7f-220">Зарегистрируйте канал продукта корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="07e7f-220">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="07e7f-221">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="07e7f-221">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="07e7f-222">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="07e7f-222">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="07e7f-223">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-223">Install .NET Core SDK.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="07e7f-224">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="07e7f-224">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. <span data-ttu-id="07e7f-225">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="07e7f-225">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07e7f-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-226">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="07e7f-227">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="07e7f-227">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="07e7f-228">Скачайте двоичные файлы пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="07e7f-228">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="07e7f-229">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-229">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="07e7f-230">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="07e7f-230">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. <span data-ttu-id="07e7f-231">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="07e7f-231">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="07e7f-232">Установка .NET Core на Fedora 24, Fedora 25 или Fedora 26 (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="07e7f-232">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="07e7f-233">Чтобы установить .NET Core 2.x на Fedora 26 или Fedora 25 или .NET Core 1.x на Fedora 24, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="07e7f-233">To install .NET Core 2.x on Fedora 26 or Fedora 25, or .NET Core 1.x on Fedora 24:</span></span>

1. <span data-ttu-id="07e7f-234">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-234">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="07e7f-235">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="07e7f-235">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="07e7f-236">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-236">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="07e7f-237">**Fedora 26 или Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="07e7f-237">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="07e7f-238">Зарегистрируйте ключ сигнатуры Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="07e7f-238">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="07e7f-239">Добавьте канал продукта dotnet.</span><span class="sxs-lookup"><span data-stu-id="07e7f-239">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="07e7f-240">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-240">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="07e7f-241">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="07e7f-241">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07e7f-242">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-242">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="07e7f-243">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="07e7f-243">**Fedora 24**</span></span>

2. <span data-ttu-id="07e7f-244">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="07e7f-244">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="07e7f-245">Скачайте двоичный файл пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="07e7f-245">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="07e7f-246">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-246">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="07e7f-247">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="07e7f-247">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="07e7f-248">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="07e7f-248">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="07e7f-249">Установка .NET Core для CentOS 7.1 (64-разрядной версии) и Oracle Linux 7.1 (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="07e7f-249">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="07e7f-250">Чтобы установить .NET Core для CentOS 7.1 (64-разрядной версии) и Oracle Linux 7.1 (64-разрядной версии), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="07e7f-250">To install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="07e7f-251">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-251">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="07e7f-252">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="07e7f-252">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="07e7f-253">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-253">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="07e7f-254">Зарегистрируйте ключ сигнатуры Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="07e7f-254">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="07e7f-255">Добавьте канал продукта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="07e7f-255">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="07e7f-256">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-256">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="07e7f-257">Добавьте каталог dotnet в переменную PATH.</span><span class="sxs-lookup"><span data-stu-id="07e7f-257">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07e7f-258">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-258">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="07e7f-259">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="07e7f-259">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="07e7f-260">Скачайте двоичный файл пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="07e7f-260">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="07e7f-261">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-261">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="07e7f-262">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="07e7f-262">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="07e7f-263">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="07e7f-263">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="07e7f-264">Установка .NET Core для SUSE Linux Enterprise Server (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="07e7f-264">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="07e7f-265">Чтобы установить .NET Core 2.x для SUSE Linux Enterprise Server (SLES) 12 с пакетом обновления 2 (SP2) (64-разрядной версии), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="07e7f-265">To install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="07e7f-266">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-266">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="07e7f-267">Добавьте канал продукта dotnet.</span><span class="sxs-lookup"><span data-stu-id="07e7f-267">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="07e7f-268">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-268">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="07e7f-269">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="07e7f-269">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="07e7f-270">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="07e7f-270">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="07e7f-271">Установка .NET Core для openSUSE (64-разрядной версии)</span><span class="sxs-lookup"><span data-stu-id="07e7f-271">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="07e7f-272">Чтобы установить .NET Core 2.x для openSUSE или .NET Core 1.x для openSUSE (64-разрядная версия), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="07e7f-272">To install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="07e7f-273">Удалите из системы все **предыдущие предварительные** версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-273">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="07e7f-274">Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.</span><span class="sxs-lookup"><span data-stu-id="07e7f-274">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="07e7f-275">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-275">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="07e7f-276">Зарегистрируйте ключ сигнатуры Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="07e7f-276">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="07e7f-277">Добавьте канал продукта dotnet.</span><span class="sxs-lookup"><span data-stu-id="07e7f-277">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="07e7f-278">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-278">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="07e7f-279">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="07e7f-279">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07e7f-280">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07e7f-280">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="07e7f-281">Получите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="07e7f-281">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="07e7f-282">Скачайте двоичный файл пакета SDK для .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="07e7f-282">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="07e7f-283">Извлеките двоичные файлы пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07e7f-283">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="07e7f-284">Добавьте каталог dotnet в PATH.</span><span class="sxs-lookup"><span data-stu-id="07e7f-284">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="07e7f-285">Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.</span><span class="sxs-lookup"><span data-stu-id="07e7f-285">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="07e7f-286">Если при установке .NET Core 2.x в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к разделу с описанием [известных проблем в версии 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0) для используемого дистрибутива и версии.</span><span class="sxs-lookup"><span data-stu-id="07e7f-286">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="07e7f-287">Если при установке .NET Core 1.x в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к разделам с описанием [известных проблем в версии 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) и [версии 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) для используемого дистрибутива и версии.</span><span class="sxs-lookup"><span data-stu-id="07e7f-287">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>
