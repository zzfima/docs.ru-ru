---
title: Перенос кода в .NET Core с помощью пакета обеспечения совместимости Windows
description: Сведения о пакете обеспечения совместимости Windows и его использовании для переноса существующего кода .NET Framework на .NET Core.
author: terrajobst
ms.date: 12/07/2018
ms.openlocfilehash: 91a653b2345d414c18ebdb6e8b7d6d49bbdbb83e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733609"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a><span data-ttu-id="d4be8-103">Перенос кода в .NET Core с помощью пакета обеспечения совместимости Windows</span><span class="sxs-lookup"><span data-stu-id="d4be8-103">Use the Windows Compatibility Pack to port code to .NET Core</span></span>

<span data-ttu-id="d4be8-104">Некоторые из наиболее распространенных проблем при переносе существующего кода в .NET Core связаны с зависимостями от API и технологий, которые доступны только в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d4be8-104">Some of the most common issues found when porting existing code to .NET Core are dependencies on APIs and technologies that are only found in .NET Framework.</span></span> <span data-ttu-id="d4be8-105">*Пакет обеспечения совместимости Windows* предоставляет многие из этих технологий. Это значительно упрощает создание приложений .NET Core и библиотек .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d4be8-105">The *Windows Compatibility Pack* provides many of these technologies, so it's much easier to build .NET Core applications and .NET Standard libraries.</span></span>

<span data-ttu-id="d4be8-106">Пакет обеспечения совместимости является логическим [расширением платформы .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support), который значительно расширяет набор API.</span><span class="sxs-lookup"><span data-stu-id="d4be8-106">The compatibility pack is a logical [extension of .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) that significantly increases the API set.</span></span> <span data-ttu-id="d4be8-107">Существующий код компилируется практически без изменений.</span><span class="sxs-lookup"><span data-stu-id="d4be8-107">Existing code compiles with almost no modifications.</span></span> <span data-ttu-id="d4be8-108">Чтобы сдержать обещание "это набор API, который предоставляет все реализации .NET", платформа .NET Standard не включает технологии, которые не могут работать на всех платформах, такие как реестр, инструментарий управления Windows (WMI) или API порождения отражения.</span><span class="sxs-lookup"><span data-stu-id="d4be8-108">To keep its promise of "the set of APIs that all .NET implementations provide", .NET Standard doesn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span> <span data-ttu-id="d4be8-109">Пакет обеспечения совместимости Windows основан на .NET Standard и обеспечивает доступ к таким технологиям, которые доступны только в Windows.</span><span class="sxs-lookup"><span data-stu-id="d4be8-109">The Windows Compatibility Pack sits on top of .NET Standard and provides access to these Windows-only technologies.</span></span> <span data-ttu-id="d4be8-110">Это особенно полезно для клиентов, которые хотят перейти на .NET Core, но по меньшей мере на первом этапе планируют оставаться в Windows.</span><span class="sxs-lookup"><span data-stu-id="d4be8-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows, at least as a first step.</span></span> <span data-ttu-id="d4be8-111">В этом сценарии возможность использования технологий, предназначенных только для Windows, устраняет препятствия для миграции.</span><span class="sxs-lookup"><span data-stu-id="d4be8-111">In that scenario, being able to use Windows-only technologies removes the migration hurdle.</span></span>

## <a name="package-contents"></a><span data-ttu-id="d4be8-112">Содержимое пакета</span><span class="sxs-lookup"><span data-stu-id="d4be8-112">Package contents</span></span>

<span data-ttu-id="d4be8-113">Пакет обеспечения совместимости Windows предоставляется с помощью [пакета NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility), и на него можно ссылаться из проектов, предназначенных для .NET Core или .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d4be8-113">The Windows Compatibility Pack is provided via the [Microsoft.Windows.Compatibility NuGet package](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects that target .NET Core or .NET Standard.</span></span>

<span data-ttu-id="d4be8-114">Он предоставляет около 20 000 API, включая API только для Windows, а также кроссплатформенные API из следующих технологических областей:</span><span class="sxs-lookup"><span data-stu-id="d4be8-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

- <span data-ttu-id="d4be8-115">Кодовые страницы</span><span class="sxs-lookup"><span data-stu-id="d4be8-115">Code Pages</span></span>
- <span data-ttu-id="d4be8-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="d4be8-116">CodeDom</span></span>
- <span data-ttu-id="d4be8-117">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="d4be8-117">Configuration</span></span>
- <span data-ttu-id="d4be8-118">Служба каталогов</span><span class="sxs-lookup"><span data-stu-id="d4be8-118">Directory Services</span></span>
- <span data-ttu-id="d4be8-119">Рисование</span><span class="sxs-lookup"><span data-stu-id="d4be8-119">Drawing</span></span>
- <span data-ttu-id="d4be8-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="d4be8-120">ODBC</span></span>
- <span data-ttu-id="d4be8-121">Разрешения</span><span class="sxs-lookup"><span data-stu-id="d4be8-121">Permissions</span></span>
- <span data-ttu-id="d4be8-122">Порты</span><span class="sxs-lookup"><span data-stu-id="d4be8-122">Ports</span></span>
- <span data-ttu-id="d4be8-123">Списки управления доступом Windows (ACL)</span><span class="sxs-lookup"><span data-stu-id="d4be8-123">Windows Access Control Lists (ACL)</span></span>
- <span data-ttu-id="d4be8-124">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="d4be8-124">Windows Communication Foundation (WCF)</span></span>
- <span data-ttu-id="d4be8-125">Шифрование Windows</span><span class="sxs-lookup"><span data-stu-id="d4be8-125">Windows Cryptography</span></span>
- <span data-ttu-id="d4be8-126">Windows EventLog</span><span class="sxs-lookup"><span data-stu-id="d4be8-126">Windows EventLog</span></span>
- <span data-ttu-id="d4be8-127">инструментирование управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="d4be8-127">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="d4be8-128">Счетчики производительности Windows</span><span class="sxs-lookup"><span data-stu-id="d4be8-128">Windows Performance Counters</span></span>
- <span data-ttu-id="d4be8-129">Реестр Windows</span><span class="sxs-lookup"><span data-stu-id="d4be8-129">Windows Registry</span></span>
- <span data-ttu-id="d4be8-130">Кэширование среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="d4be8-130">Windows Runtime Caching</span></span>
- <span data-ttu-id="d4be8-131">службы Windows</span><span class="sxs-lookup"><span data-stu-id="d4be8-131">Windows Services</span></span>

<span data-ttu-id="d4be8-132">Дополнительные сведения см. в [характеристиках пакета обеспечения совместимости](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="d4be8-132">For more information, see the [specification of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="d4be8-133">Начало работы</span><span class="sxs-lookup"><span data-stu-id="d4be8-133">Get started</span></span>

1. <span data-ttu-id="d4be8-134">Перед переносом обязательно проверьте [процесс переноса](index.md).</span><span class="sxs-lookup"><span data-stu-id="d4be8-134">Before porting, make sure to take a look at the [Porting process](index.md).</span></span>

2. <span data-ttu-id="d4be8-135">При переносе существующего кода в .NET Core или .NET Standard установите [пакет NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="d4be8-135">When porting existing code to .NET Core or .NET Standard, install the [Microsoft.Windows.Compatibility NuGet package](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

   <span data-ttu-id="d4be8-136">Если вы хотите остаться на Windows, больше ничего не требуется.</span><span class="sxs-lookup"><span data-stu-id="d4be8-136">If you want to stay on Windows, you're all set.</span></span>

3. <span data-ttu-id="d4be8-137">Если вы хотите запускать приложение .NET Core или библиотеку .NET Standard в macOS или Linux, используйте [анализатор API](../../standard/analyzers/api-analyzer.md), чтобы найти используемые API, которые не будут работать на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="d4be8-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](../../standard/analyzers/api-analyzer.md) to find usage of APIs that won't work cross-platform.</span></span>

4. <span data-ttu-id="d4be8-138">Удалите случаи использования этих API, замените их на кроссплатформенные альтернативы или защитите с помощью проверки платформы, например:</span><span class="sxs-lookup"><span data-stu-id="d4be8-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

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

<span data-ttu-id="d4be8-139">Демонстрацию см. в [видео Channel 9 по пакету обеспечения совместимости Windows](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="d4be8-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>
