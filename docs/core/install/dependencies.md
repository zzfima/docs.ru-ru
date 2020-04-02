---
title: Зависимости пакета SDK для .NET Core и среды выполнения .NET Core — .NET Core
description: Сведения о предварительных требованиях к операционной системе и архитектуре ЦП для установки пакета SDK для .NET Core и среды выполнения .NET Core в Windows, Linux и macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 023b8fdf029dd6b17fe2186296d87dd7507c60b5
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546566"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="c3686-103">Зависимости и требования для .NET Core</span><span class="sxs-lookup"><span data-stu-id="c3686-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="c3686-104">Эта статья описывает, какие операционные системы и архитектура ЦП поддерживаются в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c3686-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="c3686-105">Поддерживаемые операционные системы</span><span class="sxs-lookup"><span data-stu-id="c3686-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="c3686-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c3686-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="c3686-107">.NET Core 3.1 поддерживает следующие версии Windows:</span><span class="sxs-lookup"><span data-stu-id="c3686-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="c3686-108">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="c3686-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3686-109">Операционная система</span><span class="sxs-lookup"><span data-stu-id="c3686-109">OS</span></span>                            | <span data-ttu-id="c3686-110">Version</span><span class="sxs-lookup"><span data-stu-id="c3686-110">Version</span></span>                        | <span data-ttu-id="c3686-111">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="c3686-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c3686-112">Клиент Windows</span><span class="sxs-lookup"><span data-stu-id="c3686-112">Windows Client</span></span>                | <span data-ttu-id="c3686-113">7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1</span><span class="sxs-lookup"><span data-stu-id="c3686-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c3686-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-114">x64, x86</span></span>        |
| <span data-ttu-id="c3686-115">Клиент Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3686-115">Windows 10 Client</span></span>             | <span data-ttu-id="c3686-116">Версия 1607+</span><span class="sxs-lookup"><span data-stu-id="c3686-116">Version 1607+</span></span>                  | <span data-ttu-id="c3686-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-117">x64, x86</span></span>        |
| <span data-ttu-id="c3686-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c3686-118">Windows Server</span></span>                | <span data-ttu-id="c3686-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="c3686-119">2012 R2+</span></span>                       | <span data-ttu-id="c3686-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-120">x64, x86</span></span>        |
| <span data-ttu-id="c3686-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c3686-121">Nano Server</span></span>                   | <span data-ttu-id="c3686-122">Версия 1803+</span><span class="sxs-lookup"><span data-stu-id="c3686-122">Version 1803+</span></span>                  | <span data-ttu-id="c3686-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c3686-123">x64, ARM32</span></span>      |

<span data-ttu-id="c3686-124">Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 3.1, см. в статье [Поддерживаемые .NET Core 3.1 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="c3686-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c3686-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="c3686-126">*Сейчас .NET Core 3.0 не поддерживается. Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c3686-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c3686-127">.NET Core 3.0 поддерживает следующие версии Windows:</span><span class="sxs-lookup"><span data-stu-id="c3686-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="c3686-128">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="c3686-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3686-129">Операционная система</span><span class="sxs-lookup"><span data-stu-id="c3686-129">OS</span></span>                            | <span data-ttu-id="c3686-130">Version</span><span class="sxs-lookup"><span data-stu-id="c3686-130">Version</span></span>                        | <span data-ttu-id="c3686-131">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="c3686-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c3686-132">Клиент Windows</span><span class="sxs-lookup"><span data-stu-id="c3686-132">Windows Client</span></span>                | <span data-ttu-id="c3686-133">7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1</span><span class="sxs-lookup"><span data-stu-id="c3686-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c3686-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-134">x64, x86</span></span>        |
| <span data-ttu-id="c3686-135">Клиент Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3686-135">Windows 10 Client</span></span>             | <span data-ttu-id="c3686-136">Версия 1607+</span><span class="sxs-lookup"><span data-stu-id="c3686-136">Version 1607+</span></span>                  | <span data-ttu-id="c3686-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-137">x64, x86</span></span>        |
| <span data-ttu-id="c3686-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c3686-138">Windows Server</span></span>                | <span data-ttu-id="c3686-139">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="c3686-139">2012 R2+</span></span>                       | <span data-ttu-id="c3686-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-140">x64, x86</span></span>        |
| <span data-ttu-id="c3686-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c3686-141">Nano Server</span></span>                   | <span data-ttu-id="c3686-142">Версия 1803+</span><span class="sxs-lookup"><span data-stu-id="c3686-142">Version 1803+</span></span>                  | <span data-ttu-id="c3686-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c3686-143">x64, ARM32</span></span>      |

<span data-ttu-id="c3686-144">Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 3.0, см. в статье [Поддерживаемые .NET Core 3.0 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="c3686-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c3686-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="c3686-146">*Сейчас .NET Core 2.2 не поддерживается. Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c3686-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c3686-147">.NET Core 2.2 поддерживает следующие версии Windows:</span><span class="sxs-lookup"><span data-stu-id="c3686-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="c3686-148">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="c3686-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3686-149">Операционная система</span><span class="sxs-lookup"><span data-stu-id="c3686-149">OS</span></span>                            | <span data-ttu-id="c3686-150">Version</span><span class="sxs-lookup"><span data-stu-id="c3686-150">Version</span></span>                        | <span data-ttu-id="c3686-151">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="c3686-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c3686-152">Клиент Windows</span><span class="sxs-lookup"><span data-stu-id="c3686-152">Windows Client</span></span>                | <span data-ttu-id="c3686-153">7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1</span><span class="sxs-lookup"><span data-stu-id="c3686-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c3686-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-154">x64, x86</span></span>        |
| <span data-ttu-id="c3686-155">Клиент Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3686-155">Windows 10 Client</span></span>             | <span data-ttu-id="c3686-156">Версия 1607+</span><span class="sxs-lookup"><span data-stu-id="c3686-156">Version 1607+</span></span>                  | <span data-ttu-id="c3686-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-157">x64, x86</span></span>        |
| <span data-ttu-id="c3686-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c3686-158">Windows Server</span></span>                | <span data-ttu-id="c3686-159">2008 R2 с пакетом обновления 1 или более поздней версии (SP1+)</span><span class="sxs-lookup"><span data-stu-id="c3686-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="c3686-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-160">x64, x86</span></span>        |
| <span data-ttu-id="c3686-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c3686-161">Nano Server</span></span>                   | <span data-ttu-id="c3686-162">Версия 1803+</span><span class="sxs-lookup"><span data-stu-id="c3686-162">Version 1803+</span></span>                   | <span data-ttu-id="c3686-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c3686-163">x64, ARM32</span></span>      |

<span data-ttu-id="c3686-164">Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 2.2, см. в статье [Поддерживаемые .NET Core 2.2 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c3686-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c3686-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c3686-166">.NET Core 2.1 поддерживает следующие версии Windows:</span><span class="sxs-lookup"><span data-stu-id="c3686-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="c3686-167">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="c3686-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3686-168">Операционная система</span><span class="sxs-lookup"><span data-stu-id="c3686-168">OS</span></span>                            | <span data-ttu-id="c3686-169">Version</span><span class="sxs-lookup"><span data-stu-id="c3686-169">Version</span></span>                        | <span data-ttu-id="c3686-170">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="c3686-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c3686-171">Клиент Windows</span><span class="sxs-lookup"><span data-stu-id="c3686-171">Windows Client</span></span>                | <span data-ttu-id="c3686-172">7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1</span><span class="sxs-lookup"><span data-stu-id="c3686-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c3686-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-173">x64, x86</span></span>        |
| <span data-ttu-id="c3686-174">Клиент Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3686-174">Windows 10 Client</span></span>             | <span data-ttu-id="c3686-175">Версия 1607+</span><span class="sxs-lookup"><span data-stu-id="c3686-175">Version 1607+</span></span>                  | <span data-ttu-id="c3686-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-176">x64, x86</span></span>        |
| <span data-ttu-id="c3686-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c3686-177">Windows Server</span></span>                | <span data-ttu-id="c3686-178">2008 R2 с пакетом обновления 1 или более поздней версии (SP1+)</span><span class="sxs-lookup"><span data-stu-id="c3686-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="c3686-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c3686-179">x64, x86</span></span>        |
| <span data-ttu-id="c3686-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c3686-180">Nano Server</span></span>                   | <span data-ttu-id="c3686-181">Версия 1803+</span><span class="sxs-lookup"><span data-stu-id="c3686-181">Version 1803+</span></span>                  | <span data-ttu-id="c3686-182">x64,</span><span class="sxs-lookup"><span data-stu-id="c3686-182">x64,</span></span>            |

<span data-ttu-id="c3686-183">Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 2.1, см. в статье [Поддерживаемые .NET Core 2.1 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="c3686-184">Windows 7/Vista/8.1/Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c3686-184">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="c3686-185">При установке пакета SDK для .NET или среды выполнения .NET в следующих версиях Windows требуются дополнительные зависимости:</span><span class="sxs-lookup"><span data-stu-id="c3686-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="c3686-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="c3686-186">Windows 7 SP1</span></span>
- <span data-ttu-id="c3686-187">Windows Vista с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="c3686-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="c3686-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c3686-188">Windows 8.1</span></span>
- <span data-ttu-id="c3686-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c3686-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="c3686-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c3686-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="c3686-191">Установите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="c3686-191">Install the following:</span></span>

- <span data-ttu-id="c3686-192">[Распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="c3686-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="c3686-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="c3686-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="c3686-194">Приведенные выше требования также применяются, если возникает одна из следующих ошибок:</span><span class="sxs-lookup"><span data-stu-id="c3686-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="c3686-195">Запуск программы невозможен, так как на компьютере отсутствует *api-ms-win-crt-runtime-l1-1-0.dll*.</span><span class="sxs-lookup"><span data-stu-id="c3686-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="c3686-196">Попробуйте переустановить программу.</span><span class="sxs-lookup"><span data-stu-id="c3686-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="c3686-197">\- или -</span><span class="sxs-lookup"><span data-stu-id="c3686-197">\- or -</span></span>
>
> <span data-ttu-id="c3686-198">Библиотека *hostfxr.dll* найдена, но при ее загрузке из *C:\\\<путь_к_приложению>\\hostfxr.dll* произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="c3686-198">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="c3686-199">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c3686-199">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="c3686-200">.NET Core 3.1 воспринимает Linux как отдельную операционную систему.</span><span class="sxs-lookup"><span data-stu-id="c3686-200">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="c3686-201">Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="c3686-201">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c3686-202">.NET Core 3.1 поддерживается в следующих дистрибутивах и версиях Linux:</span><span class="sxs-lookup"><span data-stu-id="c3686-202">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c3686-203">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="c3686-203">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3686-204">Операционная система</span><span class="sxs-lookup"><span data-stu-id="c3686-204">OS</span></span>                             | <span data-ttu-id="c3686-205">Version</span><span class="sxs-lookup"><span data-stu-id="c3686-205">Version</span></span>               | <span data-ttu-id="c3686-206">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="c3686-206">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="c3686-207">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-207">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="c3686-208">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="c3686-208">6, 7, 8</span></span>               | <span data-ttu-id="c3686-209">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-209">x64</span></span> |
| <span data-ttu-id="c3686-210">CentOS</span><span class="sxs-lookup"><span data-stu-id="c3686-210">CentOS</span></span>                         | <span data-ttu-id="c3686-211">7 или выше</span><span class="sxs-lookup"><span data-stu-id="c3686-211">7+</span></span>                    | <span data-ttu-id="c3686-212">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-212">x64</span></span> |
| <span data-ttu-id="c3686-213">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-213">Oracle Linux</span></span>                   | <span data-ttu-id="c3686-214">7 или выше</span><span class="sxs-lookup"><span data-stu-id="c3686-214">7+</span></span>                    | <span data-ttu-id="c3686-215">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-215">x64</span></span> |
| <span data-ttu-id="c3686-216">Fedora</span><span class="sxs-lookup"><span data-stu-id="c3686-216">Fedora</span></span>                         | <span data-ttu-id="c3686-217">30 или выше</span><span class="sxs-lookup"><span data-stu-id="c3686-217">30+</span></span>                   | <span data-ttu-id="c3686-218">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-218">x64</span></span> |
| <span data-ttu-id="c3686-219">Debian</span><span class="sxs-lookup"><span data-stu-id="c3686-219">Debian</span></span>                         | <span data-ttu-id="c3686-220">9+</span><span class="sxs-lookup"><span data-stu-id="c3686-220">9+</span></span>                    | <span data-ttu-id="c3686-221">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c3686-221">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c3686-222">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c3686-222">Ubuntu</span></span>                         | <span data-ttu-id="c3686-223">16.04+</span><span class="sxs-lookup"><span data-stu-id="c3686-223">16.04+</span></span>                | <span data-ttu-id="c3686-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c3686-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c3686-225">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c3686-225">Linux Mint</span></span>                     | <span data-ttu-id="c3686-226">18+</span><span class="sxs-lookup"><span data-stu-id="c3686-226">18+</span></span>                   | <span data-ttu-id="c3686-227">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-227">x64</span></span> |
| <span data-ttu-id="c3686-228">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c3686-228">openSUSE</span></span>                       | <span data-ttu-id="c3686-229">15+</span><span class="sxs-lookup"><span data-stu-id="c3686-229">15+</span></span>                   | <span data-ttu-id="c3686-230">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-230">x64</span></span> |
| <span data-ttu-id="c3686-231">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c3686-231">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="c3686-232">12 с пакетом обновления 2+</span><span class="sxs-lookup"><span data-stu-id="c3686-232">12 SP2+</span></span>               | <span data-ttu-id="c3686-233">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-233">x64</span></span> |
| <span data-ttu-id="c3686-234">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-234">Alpine Linux</span></span>                   | <span data-ttu-id="c3686-235">3.10+</span><span class="sxs-lookup"><span data-stu-id="c3686-235">3.10+</span></span>                 | <span data-ttu-id="c3686-236">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="c3686-236">x64, ARM64</span></span> |

<span data-ttu-id="c3686-237">Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 3.1, см. в статье [Поддерживаемые .NET Core 3.1 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-237">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="c3686-238">Дополнительные сведения об установке .NET Core 3.1 в ARM64 (ядро 4.14+) см. в статье [Установка .NET Core 3.0 в Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="c3686-238">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3686-239">Для поддержки ARM64 требуется ядро Linux 4.14 или более высокой версии.</span><span class="sxs-lookup"><span data-stu-id="c3686-239">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="c3686-240">Некоторые дистрибутивы Linux отвечают этому требованию, а другие — нет.</span><span class="sxs-lookup"><span data-stu-id="c3686-240">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="c3686-241">Например, Ubuntu 18.04 поддерживается, а Ubuntu 16.04 — нет.</span><span class="sxs-lookup"><span data-stu-id="c3686-241">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="c3686-242">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c3686-242">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="c3686-243">*Сейчас .NET Core 3.0 не поддерживается. Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c3686-243">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c3686-244">.NET Core 3.0 воспринимает Linux как отдельную операционную систему.</span><span class="sxs-lookup"><span data-stu-id="c3686-244">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="c3686-245">Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="c3686-245">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c3686-246">.NET Core 3.0 поддерживается в следующих дистрибутивах и версиях Linux:</span><span class="sxs-lookup"><span data-stu-id="c3686-246">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c3686-247">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="c3686-247">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3686-248">Операционная система</span><span class="sxs-lookup"><span data-stu-id="c3686-248">OS</span></span>                             | <span data-ttu-id="c3686-249">Version</span><span class="sxs-lookup"><span data-stu-id="c3686-249">Version</span></span>               | <span data-ttu-id="c3686-250">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="c3686-250">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="c3686-251">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-251">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="c3686-252">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="c3686-252">6, 7, 8</span></span>               | <span data-ttu-id="c3686-253">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-253">x64</span></span> |
| <span data-ttu-id="c3686-254">CentOS</span><span class="sxs-lookup"><span data-stu-id="c3686-254">CentOS</span></span>                         | <span data-ttu-id="c3686-255">7 или выше</span><span class="sxs-lookup"><span data-stu-id="c3686-255">7+</span></span>                    | <span data-ttu-id="c3686-256">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-256">x64</span></span> |
| <span data-ttu-id="c3686-257">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-257">Oracle Linux</span></span>                   | <span data-ttu-id="c3686-258">7 или выше</span><span class="sxs-lookup"><span data-stu-id="c3686-258">7+</span></span>                    | <span data-ttu-id="c3686-259">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-259">x64</span></span> |
| <span data-ttu-id="c3686-260">Fedora</span><span class="sxs-lookup"><span data-stu-id="c3686-260">Fedora</span></span>                         | <span data-ttu-id="c3686-261">29+</span><span class="sxs-lookup"><span data-stu-id="c3686-261">29+</span></span>                   | <span data-ttu-id="c3686-262">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-262">x64</span></span> |
| <span data-ttu-id="c3686-263">Debian</span><span class="sxs-lookup"><span data-stu-id="c3686-263">Debian</span></span>                         | <span data-ttu-id="c3686-264">9+</span><span class="sxs-lookup"><span data-stu-id="c3686-264">9+</span></span>                    | <span data-ttu-id="c3686-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c3686-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c3686-266">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c3686-266">Ubuntu</span></span>                         | <span data-ttu-id="c3686-267">16.04+</span><span class="sxs-lookup"><span data-stu-id="c3686-267">16.04+</span></span>                | <span data-ttu-id="c3686-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c3686-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c3686-269">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c3686-269">Linux Mint</span></span>                     | <span data-ttu-id="c3686-270">18+</span><span class="sxs-lookup"><span data-stu-id="c3686-270">18+</span></span>                   | <span data-ttu-id="c3686-271">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-271">x64</span></span> |
| <span data-ttu-id="c3686-272">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c3686-272">openSUSE</span></span>                       | <span data-ttu-id="c3686-273">15+</span><span class="sxs-lookup"><span data-stu-id="c3686-273">15+</span></span>                   | <span data-ttu-id="c3686-274">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-274">x64</span></span> |
| <span data-ttu-id="c3686-275">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c3686-275">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="c3686-276">12 с пакетом обновления 2+</span><span class="sxs-lookup"><span data-stu-id="c3686-276">12 SP2+</span></span>               | <span data-ttu-id="c3686-277">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-277">x64</span></span> |
| <span data-ttu-id="c3686-278">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-278">Alpine Linux</span></span>                   | <span data-ttu-id="c3686-279">3.8+</span><span class="sxs-lookup"><span data-stu-id="c3686-279">3.8+</span></span>                  | <span data-ttu-id="c3686-280">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="c3686-280">x64, ARM64</span></span> |

<span data-ttu-id="c3686-281">Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 3.0, см. в статье [Поддерживаемые .NET Core 3.0 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-281">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="c3686-282">Дополнительные сведения об установке .NET Core 3.0 в ARM64 см. в [этой статье](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="c3686-282">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="c3686-283">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c3686-283">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="c3686-284">*Сейчас .NET Core 2.2 не поддерживается. Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c3686-284">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c3686-285">.NET Core 2.2 воспринимает Linux как отдельную операционную систему.</span><span class="sxs-lookup"><span data-stu-id="c3686-285">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="c3686-286">Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="c3686-286">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c3686-287">.NET Core 2.2 поддерживается в следующих дистрибутивах и версиях Linux.</span><span class="sxs-lookup"><span data-stu-id="c3686-287">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c3686-288">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="c3686-288">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3686-289">Операционная система</span><span class="sxs-lookup"><span data-stu-id="c3686-289">OS</span></span>                             |  <span data-ttu-id="c3686-290">Version</span><span class="sxs-lookup"><span data-stu-id="c3686-290">Version</span></span>                |  <span data-ttu-id="c3686-291">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="c3686-291">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="c3686-292">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-292">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="c3686-293">6, 7</span><span class="sxs-lookup"><span data-stu-id="c3686-293">6, 7</span></span>                   | <span data-ttu-id="c3686-294">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-294">x64</span></span> |
| <span data-ttu-id="c3686-295">CentOS</span><span class="sxs-lookup"><span data-stu-id="c3686-295">CentOS</span></span>                         |  <span data-ttu-id="c3686-296">7</span><span class="sxs-lookup"><span data-stu-id="c3686-296">7</span></span>                      | <span data-ttu-id="c3686-297">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-297">x64</span></span> |
| <span data-ttu-id="c3686-298">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-298">Oracle Linux</span></span>                   |  <span data-ttu-id="c3686-299">7</span><span class="sxs-lookup"><span data-stu-id="c3686-299">7</span></span>                      | <span data-ttu-id="c3686-300">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-300">x64</span></span> |
| <span data-ttu-id="c3686-301">Fedora</span><span class="sxs-lookup"><span data-stu-id="c3686-301">Fedora</span></span>                         |  <span data-ttu-id="c3686-302">29, 30</span><span class="sxs-lookup"><span data-stu-id="c3686-302">29, 30</span></span>                 | <span data-ttu-id="c3686-303">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-303">x64</span></span> |
| <span data-ttu-id="c3686-304">Debian</span><span class="sxs-lookup"><span data-stu-id="c3686-304">Debian</span></span>                         |  <span data-ttu-id="c3686-305">9</span><span class="sxs-lookup"><span data-stu-id="c3686-305">9</span></span>                      | <span data-ttu-id="c3686-306">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c3686-306">x64, ARM32</span></span> |
| <span data-ttu-id="c3686-307">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c3686-307">Ubuntu</span></span>                         |  <span data-ttu-id="c3686-308">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="c3686-308">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="c3686-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c3686-309">x64, ARM32</span></span> |
| <span data-ttu-id="c3686-310">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c3686-310">Linux Mint</span></span>                     |  <span data-ttu-id="c3686-311">17, 18</span><span class="sxs-lookup"><span data-stu-id="c3686-311">17, 18</span></span>                 | <span data-ttu-id="c3686-312">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-312">x64</span></span> |
| <span data-ttu-id="c3686-313">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c3686-313">openSUSE</span></span>                       |  <span data-ttu-id="c3686-314">15+</span><span class="sxs-lookup"><span data-stu-id="c3686-314">15+</span></span>                    | <span data-ttu-id="c3686-315">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-315">x64</span></span> |
| <span data-ttu-id="c3686-316">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c3686-316">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="c3686-317">12 с пакетом обновления 2+</span><span class="sxs-lookup"><span data-stu-id="c3686-317">12 SP2+</span></span>                | <span data-ttu-id="c3686-318">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-318">x64</span></span> |
| <span data-ttu-id="c3686-319">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-319">Alpine Linux</span></span>                   |  <span data-ttu-id="c3686-320">3.8+</span><span class="sxs-lookup"><span data-stu-id="c3686-320">3.8+</span></span>                   | <span data-ttu-id="c3686-321">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-321">x64</span></span> |

<span data-ttu-id="c3686-322">Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 2.2, см. в статье [Поддерживаемые .NET Core 2.2 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-322">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c3686-323">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c3686-323">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c3686-324">.NET Core 2.1 воспринимает Linux как отдельную операционную систему.</span><span class="sxs-lookup"><span data-stu-id="c3686-324">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="c3686-325">Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="c3686-325">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c3686-326">.NET Core 2.1 поддерживается в следующих дистрибутивах и версиях Linux.</span><span class="sxs-lookup"><span data-stu-id="c3686-326">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c3686-327">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="c3686-327">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3686-328">Операционная система</span><span class="sxs-lookup"><span data-stu-id="c3686-328">OS</span></span>                             |  <span data-ttu-id="c3686-329">Version</span><span class="sxs-lookup"><span data-stu-id="c3686-329">Version</span></span>                |  <span data-ttu-id="c3686-330">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="c3686-330">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="c3686-331">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-331">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="c3686-332">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="c3686-332">6, 7, 8</span></span>                | <span data-ttu-id="c3686-333">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-333">x64</span></span> |
| <span data-ttu-id="c3686-334">CentOS</span><span class="sxs-lookup"><span data-stu-id="c3686-334">CentOS</span></span>                         |  <span data-ttu-id="c3686-335">7 или выше</span><span class="sxs-lookup"><span data-stu-id="c3686-335">7+</span></span>                     | <span data-ttu-id="c3686-336">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-336">x64</span></span> |
| <span data-ttu-id="c3686-337">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-337">Oracle Linux</span></span>                   |  <span data-ttu-id="c3686-338">7 или выше</span><span class="sxs-lookup"><span data-stu-id="c3686-338">7+</span></span>                     | <span data-ttu-id="c3686-339">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-339">x64</span></span> |
| <span data-ttu-id="c3686-340">Fedora</span><span class="sxs-lookup"><span data-stu-id="c3686-340">Fedora</span></span>                         |  <span data-ttu-id="c3686-341">30 или выше</span><span class="sxs-lookup"><span data-stu-id="c3686-341">30+</span></span>                    | <span data-ttu-id="c3686-342">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-342">x64</span></span> |
| <span data-ttu-id="c3686-343">Debian</span><span class="sxs-lookup"><span data-stu-id="c3686-343">Debian</span></span>                         |  <span data-ttu-id="c3686-344">9</span><span class="sxs-lookup"><span data-stu-id="c3686-344">9</span></span>                      | <span data-ttu-id="c3686-345">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c3686-345">x64, ARM32</span></span> |
| <span data-ttu-id="c3686-346">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c3686-346">Ubuntu</span></span>                         |  <span data-ttu-id="c3686-347">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="c3686-347">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="c3686-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c3686-348">x64, ARM32</span></span> |
| <span data-ttu-id="c3686-349">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c3686-349">Linux Mint</span></span>                     |  <span data-ttu-id="c3686-350">17+</span><span class="sxs-lookup"><span data-stu-id="c3686-350">17+</span></span>                    | <span data-ttu-id="c3686-351">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-351">x64</span></span> |
| <span data-ttu-id="c3686-352">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c3686-352">openSUSE</span></span>                       |  <span data-ttu-id="c3686-353">15+</span><span class="sxs-lookup"><span data-stu-id="c3686-353">15+</span></span>                    | <span data-ttu-id="c3686-354">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-354">x64</span></span> |
| <span data-ttu-id="c3686-355">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c3686-355">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="c3686-356">12 с пакетом обновления 2+</span><span class="sxs-lookup"><span data-stu-id="c3686-356">12 SP2+</span></span>                | <span data-ttu-id="c3686-357">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-357">x64</span></span> |
| <span data-ttu-id="c3686-358">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-358">Alpine Linux</span></span>                   |  <span data-ttu-id="c3686-359">3.8+</span><span class="sxs-lookup"><span data-stu-id="c3686-359">3.8+</span></span>                   | <span data-ttu-id="c3686-360">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-360">x64</span></span> |

<span data-ttu-id="c3686-361">Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 2.1, см. в статье [Поддерживаемые .NET Core 2.1 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-361">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="c3686-362">Зависимости дистрибутивов Linux</span><span class="sxs-lookup"><span data-stu-id="c3686-362">Linux distribution dependencies</span></span>

<span data-ttu-id="c3686-363">В зависимости от дистрибутива Linux может потребоваться установить дополнительные зависимости.</span><span class="sxs-lookup"><span data-stu-id="c3686-363">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3686-364">Точные версии и имена могут немного отличаться в зависимости от используемого дистрибутива Linux.</span><span class="sxs-lookup"><span data-stu-id="c3686-364">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="c3686-365">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c3686-365">Ubuntu</span></span>

<span data-ttu-id="c3686-366">Для дистрибутивов Ubuntu должны быть установлены следующие библиотеки:</span><span class="sxs-lookup"><span data-stu-id="c3686-366">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="c3686-367">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="c3686-367">liblttng-ust0</span></span>
- <span data-ttu-id="c3686-368">libcurl3 (для 14.x и 16.x)</span><span class="sxs-lookup"><span data-stu-id="c3686-368">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="c3686-369">libcurl4 (для 18.x)</span><span class="sxs-lookup"><span data-stu-id="c3686-369">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="c3686-370">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="c3686-370">libssl1.0.0</span></span>
- <span data-ttu-id="c3686-371">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="c3686-371">libkrb5-3</span></span>
- <span data-ttu-id="c3686-372">zlib1g</span><span class="sxs-lookup"><span data-stu-id="c3686-372">zlib1g</span></span>
- <span data-ttu-id="c3686-373">libicu52 (для 14.x)</span><span class="sxs-lookup"><span data-stu-id="c3686-373">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="c3686-374">libicu55 (для 16.x)</span><span class="sxs-lookup"><span data-stu-id="c3686-374">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="c3686-375">libicu57 (для 17.x)</span><span class="sxs-lookup"><span data-stu-id="c3686-375">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="c3686-376">libicu60 (для 18.x)</span><span class="sxs-lookup"><span data-stu-id="c3686-376">libicu60 (for 18.x)</span></span>

<span data-ttu-id="c3686-377">Для приложений .NET Core, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:</span><span class="sxs-lookup"><span data-stu-id="c3686-377">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="c3686-378">libgdiplus (версия 6.0.1 или выше)</span><span class="sxs-lookup"><span data-stu-id="c3686-378">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="c3686-379">В большинство версий Ubuntu входит более ранняя версия libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="c3686-379">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="c3686-380">Вы можете установить последнюю версию libgdiplus, добавив в систему репозиторий Mono.</span><span class="sxs-lookup"><span data-stu-id="c3686-380">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="c3686-381">Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="c3686-381">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="c3686-382">CentOS и Fedora</span><span class="sxs-lookup"><span data-stu-id="c3686-382">CentOS and Fedora</span></span>

<span data-ttu-id="c3686-383">Для дистрибутивов CentOS должны быть установлены следующие библиотеки:</span><span class="sxs-lookup"><span data-stu-id="c3686-383">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="c3686-384">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="c3686-384">lttng-ust</span></span>
- <span data-ttu-id="c3686-385">libcurl</span><span class="sxs-lookup"><span data-stu-id="c3686-385">libcurl</span></span>
- <span data-ttu-id="c3686-386">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="c3686-386">openssl-libs</span></span>
- <span data-ttu-id="c3686-387">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="c3686-387">krb5-libs</span></span>
- <span data-ttu-id="c3686-388">libicu</span><span class="sxs-lookup"><span data-stu-id="c3686-388">libicu</span></span>
- <span data-ttu-id="c3686-389">zlib</span><span class="sxs-lookup"><span data-stu-id="c3686-389">zlib</span></span>

<span data-ttu-id="c3686-390">Для пользователей Fedora: Если ваша версия OpenSSL не ниже 1.1, потребуется установить **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="c3686-390">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="c3686-391">Для .NET Core 2.0 также требуются следующие зависимости:</span><span class="sxs-lookup"><span data-stu-id="c3686-391">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="c3686-392">libunwind</span><span class="sxs-lookup"><span data-stu-id="c3686-392">libunwind</span></span>
- <span data-ttu-id="c3686-393">libuuid</span><span class="sxs-lookup"><span data-stu-id="c3686-393">libuuid</span></span>

<span data-ttu-id="c3686-394">Дополнительные сведения о зависимостях см. в статье об [автономных приложениях Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-394">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="c3686-395">Для приложений .NET Core, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:</span><span class="sxs-lookup"><span data-stu-id="c3686-395">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="c3686-396">libgdiplus (версия 6.0.1 или выше)</span><span class="sxs-lookup"><span data-stu-id="c3686-396">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="c3686-397">В большинство версий CentOS и Fedora входит более ранняя версия libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="c3686-397">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="c3686-398">Вы можете установить последнюю версию libgdiplus, добавив в систему репозиторий Mono.</span><span class="sxs-lookup"><span data-stu-id="c3686-398">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="c3686-399">Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="c3686-399">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="c3686-400">Платформа .NET Core поддерживается в следующих выпусках macOS:</span><span class="sxs-lookup"><span data-stu-id="c3686-400">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="c3686-401">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="c3686-401">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3686-402">Версия .NET Core</span><span class="sxs-lookup"><span data-stu-id="c3686-402">.NET Core Version</span></span> | <span data-ttu-id="c3686-403">macOS</span><span class="sxs-lookup"><span data-stu-id="c3686-403">macOS</span></span>                 | <span data-ttu-id="c3686-404">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="c3686-404">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="c3686-405">3.1</span><span class="sxs-lookup"><span data-stu-id="c3686-405">3.1</span></span>               | <span data-ttu-id="c3686-406">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="c3686-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="c3686-407">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-407">x64</span></span> | [<span data-ttu-id="c3686-408">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c3686-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="c3686-409">3.0</span><span class="sxs-lookup"><span data-stu-id="c3686-409">3.0</span></span>               | <span data-ttu-id="c3686-410">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="c3686-410">High Sierra (10.13+)</span></span>  | <span data-ttu-id="c3686-411">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-411">x64</span></span> | [<span data-ttu-id="c3686-412">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c3686-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="c3686-413">2.2</span><span class="sxs-lookup"><span data-stu-id="c3686-413">2.2</span></span>               | <span data-ttu-id="c3686-414">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="c3686-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="c3686-415">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-415">x64</span></span> | [<span data-ttu-id="c3686-416">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c3686-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="c3686-417">2.1</span><span class="sxs-lookup"><span data-stu-id="c3686-417">2.1</span></span>               | <span data-ttu-id="c3686-418">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="c3686-418">Sierra (10.12+)</span></span>       | <span data-ttu-id="c3686-419">X64</span><span class="sxs-lookup"><span data-stu-id="c3686-419">x64</span></span> | [<span data-ttu-id="c3686-420">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c3686-420">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="c3686-421">Начиная с macOS Catalina (версия 10.15) все программное обеспечение, созданное после 1 июня 2019 года и распространяемое с идентификатором разработчика, должно быть заверено.</span><span class="sxs-lookup"><span data-stu-id="c3686-421">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="c3686-422">Это требование относится к среде выполнения .NET Core, пакету SDK для .NET Core и программному обеспечению, созданному с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c3686-422">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="c3686-423">Установщики для .NET Core (среда выполнения и пакет SDK) версии 3.1, 3.0 и 2.1 были заверены с 18 февраля 2020 г.</span><span class="sxs-lookup"><span data-stu-id="c3686-423">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="c3686-424">Более ранние версии не заверены.</span><span class="sxs-lookup"><span data-stu-id="c3686-424">Prior released versions aren't notarized.</span></span> <span data-ttu-id="c3686-425">При запуске незаверенного приложения появится ошибка, аналогичная следующей:</span><span class="sxs-lookup"><span data-stu-id="c3686-425">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Оповещение о заверении macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="c3686-427">Дополнительные сведения о том, как принудительное заверение влияет на .NET Core (и ваши приложения .NET Core), см. в разделе [Работа с заверением macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-427">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="c3686-428">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="c3686-428">libgdiplus</span></span>

<span data-ttu-id="c3686-429">Приложения .NET Core, которые используют сборку *System.Drawing.Common*, требуют установки libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="c3686-429">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="c3686-430">Легко получить libgdiplus можно с помощью диспетчера пакетов [Homebrew ("brew")](https://brew.sh/) для macOS.</span><span class="sxs-lookup"><span data-stu-id="c3686-430">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="c3686-431">После установки *brew* установите libgdiplus, выполнив следующие команды в окне терминала (аналог командной строки):</span><span class="sxs-lookup"><span data-stu-id="c3686-431">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="c3686-432">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="c3686-432">Next steps</span></span>

- <span data-ttu-id="c3686-433">Для разработки и запуска приложений установите [пакет SDK для .NET Core](sdk.md) (включает в себя среду выполнения).</span><span class="sxs-lookup"><span data-stu-id="c3686-433">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="c3686-434">Для запуска приложений, созданных другими пользователями, установите [среду выполнения .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="c3686-434">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
