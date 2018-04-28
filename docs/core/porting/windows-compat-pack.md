---
title: Перенос в .NET Core — использование пакета обеспечения совместимости Windows
description: Сведения о пакете обеспечения совместимости Windows и его использовании для переноса существующего кода .NET Framework на .NET Core
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 4ef7d9c847d48ae7bbb2d553b1c05cb90a1c5a7a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="e2425-103">Использование пакета обеспечения совместимости Windows</span><span class="sxs-lookup"><span data-stu-id="e2425-103">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="e2425-104">Одной из наиболее распространенных проблем, с которыми сталкиваются разработчики при переносе существующего кода в .NET Core, является зависимость от API и технологий, которые существуют только в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e2425-104">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="e2425-105">*Пакет обеспечения совместимости Windows* предоставляет многие из этих технологий, чтобы значительно расширить возможности сборки приложений .NET Core и библиотек .NET Standard для существующего кода.</span><span class="sxs-lookup"><span data-stu-id="e2425-105">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="e2425-106">Этот пакет является логическим [расширением платформы .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support), который значительно расширяет набор API, в результате чего существующий код компилируется практически без изменений.</span><span class="sxs-lookup"><span data-stu-id="e2425-106">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="e2425-107">Но для обеспечения согласованности .NET Standard ("это набор API, предоставляемых всеми реализациями .NET") он не включает технологии, которые не могут работать на всех платформах, таких как реестр, инструментарий управления Windows (WMI) или API порождения отражения.</span><span class="sxs-lookup"><span data-stu-id="e2425-107">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="e2425-108">*Пакет обеспечения совместимости Windows* основан на .NET Standard и обеспечивает доступ к технологиям, которые доступны только в Windows.</span><span class="sxs-lookup"><span data-stu-id="e2425-108">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="e2425-109">Это особенно полезно для клиентов, которые хотят перейти на .NET Core, но на первом этапе планируют оставаться в Windows.</span><span class="sxs-lookup"><span data-stu-id="e2425-109">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="e2425-110">В этом сценарии неспособность использовать технологии, предназначенные только для Windows, лишь создает препятствия для миграции, не давая никаких архитектурных преимуществ.</span><span class="sxs-lookup"><span data-stu-id="e2425-110">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="e2425-111">Содержимое пакета</span><span class="sxs-lookup"><span data-stu-id="e2425-111">Package contents</span></span>

<span data-ttu-id="e2425-112">*Пакет обеспечения совместимости Windows* предоставляется с помощью пакета NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility), и на него можно ссылаться из проектов, предназначенных для .NET Core или .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e2425-112">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="e2425-113">Он предоставляет около 20 000 API, включая API только для Windows, а также кроссплатформенные API из следующих технологических областей:</span><span class="sxs-lookup"><span data-stu-id="e2425-113">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="e2425-114">Кодовые страницы</span><span class="sxs-lookup"><span data-stu-id="e2425-114">Code Pages</span></span>
* <span data-ttu-id="e2425-115">CodeDom</span><span class="sxs-lookup"><span data-stu-id="e2425-115">CodeDom</span></span>
* <span data-ttu-id="e2425-116">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="e2425-116">Configuration</span></span>
* <span data-ttu-id="e2425-117">Служба каталогов</span><span class="sxs-lookup"><span data-stu-id="e2425-117">Directory Services</span></span>
* <span data-ttu-id="e2425-118">Рисование</span><span class="sxs-lookup"><span data-stu-id="e2425-118">Drawing</span></span>
* <span data-ttu-id="e2425-119">ODBC</span><span class="sxs-lookup"><span data-stu-id="e2425-119">ODBC</span></span>
* <span data-ttu-id="e2425-120">Разрешения</span><span class="sxs-lookup"><span data-stu-id="e2425-120">Permissions</span></span>
* <span data-ttu-id="e2425-121">Порты</span><span class="sxs-lookup"><span data-stu-id="e2425-121">Ports</span></span>
* <span data-ttu-id="e2425-122">Списки управления доступом Windows (ACL)</span><span class="sxs-lookup"><span data-stu-id="e2425-122">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="e2425-123">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="e2425-123">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="e2425-124">Шифрование Windows</span><span class="sxs-lookup"><span data-stu-id="e2425-124">Windows Cryptography</span></span>
* <span data-ttu-id="e2425-125">Windows EventLog</span><span class="sxs-lookup"><span data-stu-id="e2425-125">Windows EventLog</span></span>
* <span data-ttu-id="e2425-126">инструментирование управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="e2425-126">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="e2425-127">Счетчики производительности Windows</span><span class="sxs-lookup"><span data-stu-id="e2425-127">Windows Performance Counters</span></span>
* <span data-ttu-id="e2425-128">Реестр Windows</span><span class="sxs-lookup"><span data-stu-id="e2425-128">Windows Registry</span></span>
* <span data-ttu-id="e2425-129">Кэширование среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="e2425-129">Windows Runtime Caching</span></span>
* <span data-ttu-id="e2425-130">службы Windows</span><span class="sxs-lookup"><span data-stu-id="e2425-130">Windows Services</span></span>

<span data-ttu-id="e2425-131">Дополнительные сведения см. в [характеристиках пакета обеспечения совместимости](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e2425-131">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="e2425-132">Начало работы</span><span class="sxs-lookup"><span data-stu-id="e2425-132">Get started</span></span>

1. <span data-ttu-id="e2425-133">Перед переносом обязательно проверьте [процесс переноса](index.md).</span><span class="sxs-lookup"><span data-stu-id="e2425-133">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="e2425-134">При переносе существующего кода в .NET Core или .NET Standard установите пакет NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="e2425-134">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="e2425-135">Если вы хотите остаться на Windows, больше ничего не требуется.</span><span class="sxs-lookup"><span data-stu-id="e2425-135">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="e2425-136">Если вы хотите запускать приложение .NET Core или библиотеку .NET Standard в macOS или Linux, используйте [анализатор API](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/), чтобы найти используемые API, которые не будут работать на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="e2425-136">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="e2425-137">Удалите случаи использования этих API, замените их на кроссплатформенные альтернативы или защитите с помощью проверки платформы, например:</span><span class="sxs-lookup"><span data-stu-id="e2425-137">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

<span data-ttu-id="e2425-138">Демонстрацию см. в [видео Channel 9 по пакету обеспечения совместимости Windows](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="e2425-138">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

