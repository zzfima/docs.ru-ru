---
title: "Перенос приложений в .NET Core — с помощью пакета совместимости Windows"
description: "Дополнительные сведения о пакете совместимости Windows и как можно использовать его для порта для существующего кода .NET Framework на .NET Core"
keywords: ".NET, .NET core, Windows, совместимость"
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 5094baee77aba4d1e148f807d842a4a2d3405cf7
ms.sourcegitcommit: 86cf9b4c7104485a9870645705b9a1a4b6ca8e2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2017
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="4a4dc-104">С помощью пакета совместимости Windows</span><span class="sxs-lookup"><span data-stu-id="4a4dc-104">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="4a4dc-105">Одним из наиболее распространенных проблем, с которыми сталкиваются разработчики, при переносе существующего кода, .NET Core — что они используют API-интерфейсы и технологии, которые существуют только в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a4dc-105">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="4a4dc-106">*Пакет обеспечения совместимости Windows* заключается в предоставлении многих из этих технологий, чтобы построения приложений .NET Core, а также .NET стандартные библиотеки становится более приемлемым для существующего кода.</span><span class="sxs-lookup"><span data-stu-id="4a4dc-106">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="4a4dc-107">Этот пакет является логического [расширения платформы .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) том, что значительно повышает набор API и существующий код компилируется практически без изменений.</span><span class="sxs-lookup"><span data-stu-id="4a4dc-107">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="4a4dc-108">Но для сохранения согласованности promise стандарта .NET («это набор API-интерфейсов, которые предоставляют все реализации .NET»), это не относится к технологии, которые не могут работать на всех платформах, такие как реестр, инструментарий управления Windows (WMI) или порождение отражения API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="4a4dc-108">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="4a4dc-109">*Пакет обеспечения совместимости Windows* располагается в верхней части .NET Standard и обеспечивает доступ к технологии, которые доступны только в Windows.</span><span class="sxs-lookup"><span data-stu-id="4a4dc-109">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="4a4dc-110">Это особенно полезно для пользователей, чтобы перейти к .NET Core, но плана оставаться в Windows в качестве первого шага.</span><span class="sxs-lookup"><span data-stu-id="4a4dc-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="4a4dc-111">В этом сценарии не имея возможности применять технологии только для Windows является только препятствие миграции с нуля преимущества архитектуры.</span><span class="sxs-lookup"><span data-stu-id="4a4dc-111">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="4a4dc-112">Содержимое пакета</span><span class="sxs-lookup"><span data-stu-id="4a4dc-112">Package contents</span></span>

<span data-ttu-id="4a4dc-113">*Пакет обеспечения совместимости Windows* обеспечивается за счет пакета NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) и может указываться в проектах, предназначенных для .NET Core или .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4a4dc-113">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="4a4dc-114">Он предоставляет около 20 000 API, в том числе только для Windows, а также между различными платформами API из области следующих технологий:</span><span class="sxs-lookup"><span data-stu-id="4a4dc-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="4a4dc-115">Кодовые страницы</span><span class="sxs-lookup"><span data-stu-id="4a4dc-115">Code Pages</span></span>
* <span data-ttu-id="4a4dc-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="4a4dc-116">CodeDom</span></span>
* <span data-ttu-id="4a4dc-117">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="4a4dc-117">Configuration</span></span>
* <span data-ttu-id="4a4dc-118">Служба каталогов</span><span class="sxs-lookup"><span data-stu-id="4a4dc-118">Directory Services</span></span>
* <span data-ttu-id="4a4dc-119">Рисование</span><span class="sxs-lookup"><span data-stu-id="4a4dc-119">Drawing</span></span>
* <span data-ttu-id="4a4dc-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="4a4dc-120">ODBC</span></span>
* <span data-ttu-id="4a4dc-121">Разрешения</span><span class="sxs-lookup"><span data-stu-id="4a4dc-121">Permissions</span></span>
* <span data-ttu-id="4a4dc-122">Порты</span><span class="sxs-lookup"><span data-stu-id="4a4dc-122">Ports</span></span>
* <span data-ttu-id="4a4dc-123">Списки управления доступом Windows (ACL)</span><span class="sxs-lookup"><span data-stu-id="4a4dc-123">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="4a4dc-124">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="4a4dc-124">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="4a4dc-125">Криптография Windows</span><span class="sxs-lookup"><span data-stu-id="4a4dc-125">Windows Cryptography</span></span>
* <span data-ttu-id="4a4dc-126">Журнал событий Windows</span><span class="sxs-lookup"><span data-stu-id="4a4dc-126">Windows EventLog</span></span>
* <span data-ttu-id="4a4dc-127">инструментирование управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="4a4dc-127">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="4a4dc-128">Счетчики производительности Windows</span><span class="sxs-lookup"><span data-stu-id="4a4dc-128">Windows Performance Counters</span></span>
* <span data-ttu-id="4a4dc-129">Реестр Windows</span><span class="sxs-lookup"><span data-stu-id="4a4dc-129">Windows Registry</span></span>
* <span data-ttu-id="4a4dc-130">Кэширование среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="4a4dc-130">Windows Runtime Caching</span></span>
* <span data-ttu-id="4a4dc-131">службы Windows</span><span class="sxs-lookup"><span data-stu-id="4a4dc-131">Windows Services</span></span>

<span data-ttu-id="4a4dc-132">Дополнительные сведения см. в разделе [характеристик пакета совместимости](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4a4dc-132">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="4a4dc-133">Начало работы</span><span class="sxs-lookup"><span data-stu-id="4a4dc-133">Get started</span></span>

1. <span data-ttu-id="4a4dc-134">Перед развертыванием, убедитесь, что взгляните на [процесс портировании](index.md).</span><span class="sxs-lookup"><span data-stu-id="4a4dc-134">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="4a4dc-135">При переносе существующего кода в .NET Core или .NET Standard, установите пакет NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="4a4dc-135">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="4a4dc-136">Если вы хотите остаться на Windows, всех настроек.</span><span class="sxs-lookup"><span data-stu-id="4a4dc-136">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="4a4dc-137">Если вы хотите запускать приложение .NET Core или .NET стандартной библиотеки на macOS или Linux, используйте [API анализатора](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) найти использование API-интерфейсов, не будут работать на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="4a4dc-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="4a4dc-138">Удалите примеры использования этих интерфейсов API, замените альтернативы кросс платформенных или защитить их с помощью проверки платформы, например:</span><span class="sxs-lookup"><span data-stu-id="4a4dc-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

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

<span data-ttu-id="4a4dc-139">Для демонстрации, извлечь [видео Channel 9 пакета совместимости Windows](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="4a4dc-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

