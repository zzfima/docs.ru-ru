---
title: Необходимые компоненты для .NET Core в Linux
description: Поддерживаемые версии Linux и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с Linux.
author: thraka
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: 29256259c66b909ad65691230bd652f38583184e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084917"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="96014-103">Необходимые компоненты для .NET Core в Linux</span><span class="sxs-lookup"><span data-stu-id="96014-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="96014-104">В этой статье описываются зависимости, необходимые для разработки приложений .NET Core в Linux.</span><span class="sxs-lookup"><span data-stu-id="96014-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="96014-105">Поддерживаемые дистрибутивы и версии Linux, а также перечисленные ниже зависимости относятся к двум способам разработки приложений .NET Core в Linux:</span><span class="sxs-lookup"><span data-stu-id="96014-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="96014-106">командная строка и любой редактор;</span><span class="sxs-lookup"><span data-stu-id="96014-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="96014-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="96014-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="96014-108">Пакет SDK для .NET Core не требуется для рабочих серверов и сред.</span><span class="sxs-lookup"><span data-stu-id="96014-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="96014-109">Для приложений, развертываемых в рабочих средах, требуется только пакет среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="96014-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="96014-110">Среда выполнения .NET Core развертывается вместе с приложениями в рамках автономного развертывания, однако для приложений, зависимых от платформы, ее необходимо развертывать отдельно.</span><span class="sxs-lookup"><span data-stu-id="96014-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="96014-111">Дополнительные сведения о зависимых от платформы и автономных типах развертывания см. в статье [Развертывание приложений .NET Core](./deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="96014-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="96014-112">Также см. статью [Автономные приложения Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="96014-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="96014-113">Поддерживаемые версии Linux</span><span class="sxs-lookup"><span data-stu-id="96014-113">Supported Linux versions</span></span>

# [<a name="net-core-2x"></a><span data-ttu-id="96014-114">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="96014-114">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="96014-115">.NET Core 2.x воспринимает Linux как отдельную операционную систему.</span><span class="sxs-lookup"><span data-stu-id="96014-115">.NET Core 2.x treats Linux as a single operating system.</span></span> <span data-ttu-id="96014-116">Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="96014-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="96014-117">Ознакомьтесь с дополнительными сведениями и воспользуйтесь ссылками для скачивания для [.NET Core 2.2](https://www.microsoft.com/net/download/dotnet-core/2.2) или [.NET Core 2.1](https://www.microsoft.com/net/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="96014-117">For download links and more information, see [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="96014-118">.NET Core 2.x поддерживается в следующих дистрибутивах и версиях Linux:</span><span class="sxs-lookup"><span data-stu-id="96014-118">.NET Core 2.x is supported on the following Linux distributions/versions:</span></span>

* <span data-ttu-id="96014-119">Red Hat Enterprise Linux 7, 6 — 64-разрядная версия (`x86_64` или `amd64`);</span><span class="sxs-lookup"><span data-stu-id="96014-119">Red Hat Enterprise Linux 7, 6 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="96014-120">CentOS 7 — 64-разрядная версия (`x86_64` или `amd64`);</span><span class="sxs-lookup"><span data-stu-id="96014-120">CentOS 7  - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="96014-121">Oracle Linux 7 — 64-разрядная версия (`x86_64` или `amd64`);</span><span class="sxs-lookup"><span data-stu-id="96014-121">Oracle Linux 7 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="96014-122">Fedora 28, 27 — 64-разрядная версия (`x86_64` или `amd64`);</span><span class="sxs-lookup"><span data-stu-id="96014-122">Fedora 28, 27 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="96014-123">Debian 9 (64-разрядная версия, версия `arm32`), а также версия 8.7 или более поздние для 64-разрядных платформ — (`x86_64` или `amd64`)</span><span class="sxs-lookup"><span data-stu-id="96014-123">Debian 9 (64-bit, `arm32`), 8.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="96014-124">Ubuntu 18.04 (64-разрядная версия, версия `arm32`), а также версии 16.04 и 14.04 для 64-разрядных платформ (`x86_64` или `amd64`)</span><span class="sxs-lookup"><span data-stu-id="96014-124">Ubuntu 18.04 (64-bit, `arm32`), 16.04, 14.04 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="96014-125">Linux Mint 18, 17 — 64-разрядная версия (`x86_64` или `amd64`);</span><span class="sxs-lookup"><span data-stu-id="96014-125">Linux Mint 18, 17 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="96014-126">openSUSE 42.3 или более поздней версии — 64-разрядная версия (`x86_64` или `amd64`);</span><span class="sxs-lookup"><span data-stu-id="96014-126">openSUSE 42.3 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="96014-127">SUSE Enterprise Linux (SLES) 12 с пакетом обновления 2 (SP2) или более поздней версии — 64-разрядная версия (`x86_64` или `amd64`);</span><span class="sxs-lookup"><span data-stu-id="96014-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 or later - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="96014-128">Alpine Linux 3.7 или более поздней версии — 64-разрядная версия (`x86_64` или `amd64`).</span><span class="sxs-lookup"><span data-stu-id="96014-128">Alpine Linux 3.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>

<span data-ttu-id="96014-129">Полный список операционных систем, дистрибутивов, версий, поддерживаемых .NET Core 2.1 и .NET Core 2.2, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на соответствующих страницах для [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) и [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="96014-129">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# [<a name="net-core-1x"></a><span data-ttu-id="96014-130">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="96014-130">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="96014-131">Ознакомьтесь с дополнительными сведениями и воспользуйтесь ссылками для скачивания для [.NET Core 1.1](https://www.microsoft.com/net/download/dotnet-core/1.1) или [.NET Core 1.0](https://www.microsoft.com/net/download/dotnet-core/1.0).</span><span class="sxs-lookup"><span data-stu-id="96014-131">For download links and more information, see [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span></span>

<span data-ttu-id="96014-132">.NET Core 1.x поддерживается в следующих дистрибутивах и версиях 64-разрядной версии Linux (`x86_64` или `amd64`):</span><span class="sxs-lookup"><span data-stu-id="96014-132">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="96014-133">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="96014-133">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="96014-134">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="96014-134">CentOS 7</span></span>
* <span data-ttu-id="96014-135">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="96014-135">Oracle Linux 7</span></span>
* <span data-ttu-id="96014-136">Fedora 28 (.NET Core 1.1), 27</span><span class="sxs-lookup"><span data-stu-id="96014-136">Fedora 28 (.NET Core 1.1), 27</span></span>
* <span data-ttu-id="96014-137">Debian 8.2 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="96014-137">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="96014-138">Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04</span><span class="sxs-lookup"><span data-stu-id="96014-138">Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04</span></span>
* <span data-ttu-id="96014-139">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="96014-139">Linux Mint 17</span></span>
* <span data-ttu-id="96014-140">openSUSE 42.3 или более поздней версии (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="96014-140">openSUSE 42.3 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="96014-141">Полный список операционных систем, поддерживаемых .NET Core 1.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="96014-141">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# [<a name="net-core-30-preview-1"></a><span data-ttu-id="96014-142">.NET Core 3.0 (предварительная версия 1)</span><span class="sxs-lookup"><span data-stu-id="96014-142">.NET Core 3.0 Preview 1</span></span>](#tab/netcore30)

<span data-ttu-id="96014-143">.NET Core 3.0 (предварительная версия 1) воспринимает Linux как отдельную операционную систему.</span><span class="sxs-lookup"><span data-stu-id="96014-143">.NET Core 3.0 Preview 1 treats Linux as a single operating system.</span></span> <span data-ttu-id="96014-144">Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="96014-144">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="96014-145">Ознакомьтесь с дополнительными сведениями и воспользуйтесь ссылками для скачивания [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="96014-145">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="96014-146">.NET Core 3.0 (предварительная версия 1) поддерживается в следующих дистрибутивах и версиях Linux:</span><span class="sxs-lookup"><span data-stu-id="96014-146">.NET Core 3.0 Preview 1 is supported on the following Linux distributions/versions.</span></span> 

<span data-ttu-id="96014-147">Операционная система</span><span class="sxs-lookup"><span data-stu-id="96014-147">OS</span></span>                            | <span data-ttu-id="96014-148">Версия</span><span class="sxs-lookup"><span data-stu-id="96014-148">Version</span></span>               | <span data-ttu-id="96014-149">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="96014-149">Architectures</span></span>  
------------------------------|-----------------------|----------------
<span data-ttu-id="96014-150">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="96014-150">Red Hat Enterprise Linux</span></span>      | <span data-ttu-id="96014-151">6</span><span class="sxs-lookup"><span data-stu-id="96014-151">6</span></span>                     | <span data-ttu-id="96014-152">X64</span><span class="sxs-lookup"><span data-stu-id="96014-152">x64</span></span>
<span data-ttu-id="96014-153">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="96014-153">Red Hat Enterprise Linux</span></span><br><span data-ttu-id="96014-154">CentOS</span><span class="sxs-lookup"><span data-stu-id="96014-154">CentOS</span></span><br><span data-ttu-id="96014-155">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="96014-155">Oracle Linux</span></span>  | <span data-ttu-id="96014-156">7</span><span class="sxs-lookup"><span data-stu-id="96014-156">7</span></span>                     | <span data-ttu-id="96014-157">X64</span><span class="sxs-lookup"><span data-stu-id="96014-157">x64</span></span>
<span data-ttu-id="96014-158">Fedora</span><span class="sxs-lookup"><span data-stu-id="96014-158">Fedora</span></span>                        | <span data-ttu-id="96014-159">28</span><span class="sxs-lookup"><span data-stu-id="96014-159">28</span></span>                    | <span data-ttu-id="96014-160">X64</span><span class="sxs-lookup"><span data-stu-id="96014-160">x64</span></span>
<span data-ttu-id="96014-161">Debian</span><span class="sxs-lookup"><span data-stu-id="96014-161">Debian</span></span>                        | <span data-ttu-id="96014-162">9</span><span class="sxs-lookup"><span data-stu-id="96014-162">9</span></span>                     | <span data-ttu-id="96014-163">x64, ARM32\*, ARM64\*</span><span class="sxs-lookup"><span data-stu-id="96014-163">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="96014-164">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="96014-164">Ubuntu</span></span>                        | <span data-ttu-id="96014-165">16.04+, 18.04+</span><span class="sxs-lookup"><span data-stu-id="96014-165">16.04+, 18.04+</span></span>        | <span data-ttu-id="96014-166">x64, ARM32\*, ARM64\*</span><span class="sxs-lookup"><span data-stu-id="96014-166">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="96014-167">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="96014-167">Linux Mint</span></span>                    | <span data-ttu-id="96014-168">18</span><span class="sxs-lookup"><span data-stu-id="96014-168">18</span></span>                    | <span data-ttu-id="96014-169">X64</span><span class="sxs-lookup"><span data-stu-id="96014-169">x64</span></span>
<span data-ttu-id="96014-170">openSUSE</span><span class="sxs-lookup"><span data-stu-id="96014-170">openSUSE</span></span>                      | <span data-ttu-id="96014-171">42.3+</span><span class="sxs-lookup"><span data-stu-id="96014-171">42.3+</span></span>                 | <span data-ttu-id="96014-172">X64</span><span class="sxs-lookup"><span data-stu-id="96014-172">x64</span></span>
<span data-ttu-id="96014-173">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="96014-173">SUSE Enterprise Linux (SLES)</span></span>  | <span data-ttu-id="96014-174">12 с пакетом обновления 2+</span><span class="sxs-lookup"><span data-stu-id="96014-174">12 SP2+</span></span>               | <span data-ttu-id="96014-175">X64</span><span class="sxs-lookup"><span data-stu-id="96014-175">x64</span></span>
<span data-ttu-id="96014-176">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="96014-176">Alpine Linux</span></span>                  | <span data-ttu-id="96014-177">3.8+</span><span class="sxs-lookup"><span data-stu-id="96014-177">3.8+</span></span>                  | <span data-ttu-id="96014-178">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="96014-178">x64, ARM64</span></span>

<span data-ttu-id="96014-179">\* Поддержка ARM32 и ARM64 начинается с Debian 9 и Ubuntu 16.04.</span><span class="sxs-lookup"><span data-stu-id="96014-179">\* ARM32 and ARM64 support starts with Debian 9 and Ubuntu 16.04.</span></span> <span data-ttu-id="96014-180">Более ранние версии этих дистрибутивов не поддерживаются на микросхемах ARM.</span><span class="sxs-lookup"><span data-stu-id="96014-180">Earlier versions of those distros are not supported on ARM chips.</span></span>

<span data-ttu-id="96014-181">Полный список операционных систем, дистрибутивов и версий, поддерживаемых .NET Core 3.0, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [версий ОС, поддерживаемых .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="96014-181">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="96014-182">Дополнительные сведения об установке .NET Core 3.0 в ARM64 см. в [этой статье](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="96014-182">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="96014-183">Зависимости дистрибутивов Linux</span><span class="sxs-lookup"><span data-stu-id="96014-183">Linux distribution dependencies</span></span>

<span data-ttu-id="96014-184">Ниже представлены примеры.</span><span class="sxs-lookup"><span data-stu-id="96014-184">The following are intended to be examples.</span></span> <span data-ttu-id="96014-185">Точные версии и имена могут немного отличаться в зависимости от используемого дистрибутива Linux.</span><span class="sxs-lookup"><span data-stu-id="96014-185">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="96014-186">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="96014-186">Ubuntu</span></span>

<span data-ttu-id="96014-187">Для дистрибутивов Ubuntu должны быть установлены следующие библиотеки:</span><span class="sxs-lookup"><span data-stu-id="96014-187">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="96014-188">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="96014-188">liblttng-ust0</span></span>
* <span data-ttu-id="96014-189">libcurl3 (для 14.x и 16.x)</span><span class="sxs-lookup"><span data-stu-id="96014-189">libcurl3 (for 14.x and 16.x)</span></span>
* <span data-ttu-id="96014-190">libcurl4 (для 18.x)</span><span class="sxs-lookup"><span data-stu-id="96014-190">libcurl4 (for 18.x)</span></span>
* <span data-ttu-id="96014-191">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="96014-191">libssl1.0.0</span></span>
* <span data-ttu-id="96014-192">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="96014-192">libkrb5-3</span></span>
* <span data-ttu-id="96014-193">zlib1g</span><span class="sxs-lookup"><span data-stu-id="96014-193">zlib1g</span></span>
* <span data-ttu-id="96014-194">libicu52 (для 14.x)</span><span class="sxs-lookup"><span data-stu-id="96014-194">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="96014-195">libicu55 (для 16.x)</span><span class="sxs-lookup"><span data-stu-id="96014-195">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="96014-196">libicu57 (для 17.x)</span><span class="sxs-lookup"><span data-stu-id="96014-196">libicu57 (for 17.x)</span></span>
* <span data-ttu-id="96014-197">libicu60 (для 18.x)</span><span class="sxs-lookup"><span data-stu-id="96014-197">libicu60 (for 18.x)</span></span>

<span data-ttu-id="96014-198">Для версий более ранних, чем .NET Core 2.1, также требуются следующие зависимости:</span><span class="sxs-lookup"><span data-stu-id="96014-198">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="96014-199">libunwind8</span><span class="sxs-lookup"><span data-stu-id="96014-199">libunwind8</span></span>
* <span data-ttu-id="96014-200">libuuid1</span><span class="sxs-lookup"><span data-stu-id="96014-200">libuuid1</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="96014-201">CentOS и Fedora</span><span class="sxs-lookup"><span data-stu-id="96014-201">CentOS and Fedora</span></span>

<span data-ttu-id="96014-202">Для дистрибутивов CentOS должны быть установлены следующие библиотеки:</span><span class="sxs-lookup"><span data-stu-id="96014-202">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="96014-203">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="96014-203">lttng-ust</span></span>
* <span data-ttu-id="96014-204">libcurl</span><span class="sxs-lookup"><span data-stu-id="96014-204">libcurl</span></span>
* <span data-ttu-id="96014-205">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="96014-205">openssl-libs</span></span>
* <span data-ttu-id="96014-206">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="96014-206">krb5-libs</span></span>
* <span data-ttu-id="96014-207">libicu</span><span class="sxs-lookup"><span data-stu-id="96014-207">libicu</span></span>
* <span data-ttu-id="96014-208">zlib</span><span class="sxs-lookup"><span data-stu-id="96014-208">zlib</span></span>

<span data-ttu-id="96014-209">Для пользователей Fedora: если вы используете openssl версии до 1.1, вам потребуется установить compat-openssl10.</span><span class="sxs-lookup"><span data-stu-id="96014-209">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="96014-210">Для версий более ранних, чем .NET Core 2.1, также требуются следующие зависимости:</span><span class="sxs-lookup"><span data-stu-id="96014-210">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="96014-211">libunwind</span><span class="sxs-lookup"><span data-stu-id="96014-211">libunwind</span></span>
* <span data-ttu-id="96014-212">libuuid</span><span class="sxs-lookup"><span data-stu-id="96014-212">libuuid</span></span>

<span data-ttu-id="96014-213">Дополнительные сведения о зависимостях см. в статье об [автономных приложениях Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="96014-213">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="96014-214">Установка зависимостей .NET Core с помощью собственных установщиков</span><span class="sxs-lookup"><span data-stu-id="96014-214">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="96014-215">Для поддерживаемых дистрибутивов и версий Linux доступны собственные установщики .NET Core.</span><span class="sxs-lookup"><span data-stu-id="96014-215">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="96014-216">Собственные установщики требуют доступа администратора (sudo) к серверу.</span><span class="sxs-lookup"><span data-stu-id="96014-216">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="96014-217">Преимущество использования собственного установщика заключается в том, что он устанавливает все собственные зависимости .NET Core.</span><span class="sxs-lookup"><span data-stu-id="96014-217">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="96014-218">Собственные установщики также устанавливают пакет SDK для .NET Core в масштабе всей системы.</span><span class="sxs-lookup"><span data-stu-id="96014-218">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="96014-219">В Linux есть два варианта выбора пакета установщика:</span><span class="sxs-lookup"><span data-stu-id="96014-219">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="96014-220">диспетчер пакетов на основе веб-канала, например apt-get для Ubuntu или yum для CentOS/RHEL;</span><span class="sxs-lookup"><span data-stu-id="96014-220">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="96014-221">сами пакеты (DEB или RPM).</span><span class="sxs-lookup"><span data-stu-id="96014-221">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="96014-222">Установка с помощью скрипта установщика .NET Core</span><span class="sxs-lookup"><span data-stu-id="96014-222">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="96014-223">[Скрипты dotnet-install](./tools/dotnet-install-script.md) служат для установки цепочки инструментов CLI и общей среды выполнения без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="96014-223">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="96014-224">Скрипт можно скачать на странице [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).</span><span class="sxs-lookup"><span data-stu-id="96014-224">You can download the script from [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).</span></span>

<span data-ttu-id="96014-225">Скрипт по умолчанию устанавливает последнюю версию LTS. В данный момент это .NET Core 1.1.</span><span class="sxs-lookup"><span data-stu-id="96014-225">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="96014-226">Чтобы установить .NET Core 2.1, запустите скрипт с таким параметром.</span><span class="sxs-lookup"><span data-stu-id="96014-226">To install .NET Core 2.1, run the script with the following switch:</span></span>

```console
./dotnet-install.sh -c Current
```

<span data-ttu-id="96014-227">Скрипт bash установщика используется в сценариях автоматизации и установки без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="96014-227">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="96014-228">Скрипт также считывает параметры PowerShell, чтобы их можно было использовать с этим скриптом в системах Linux и OS X.</span><span class="sxs-lookup"><span data-stu-id="96014-228">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="96014-229">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="96014-229">Troubleshoot</span></span>

<span data-ttu-id="96014-230">Если при установке .NET Core в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к статье для используемого дистрибутива и версии:</span><span class="sxs-lookup"><span data-stu-id="96014-230">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

* [<span data-ttu-id="96014-231">Известные проблемы в .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="96014-231">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [<span data-ttu-id="96014-232">Известные проблемы в .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="96014-232">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [<span data-ttu-id="96014-233">Известные проблемы в .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="96014-233">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [<span data-ttu-id="96014-234">Известные проблемы в .NET Core 1.1</span><span class="sxs-lookup"><span data-stu-id="96014-234">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [<span data-ttu-id="96014-235">Известные проблемы в .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="96014-235">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
