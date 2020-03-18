---
title: Перенос кода в .NET Core с помощью пакета обеспечения совместимости Windows
description: Сведения о пакете обеспечения совместимости Windows и его использовании для переноса существующего кода .NET Framework на .NET Core.
author: terrajobst
ms.date: 12/07/2018
ms.openlocfilehash: 91a653b2345d414c18ebdb6e8b7d6d49bbdbb83e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733609"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a>Перенос кода в .NET Core с помощью пакета обеспечения совместимости Windows

Некоторые из наиболее распространенных проблем при переносе существующего кода в .NET Core связаны с зависимостями от API и технологий, которые доступны только в .NET Framework. *Пакет обеспечения совместимости Windows* предоставляет многие из этих технологий. Это значительно упрощает создание приложений .NET Core и библиотек .NET Standard.

Пакет обеспечения совместимости является логическим [расширением платформы .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support), который значительно расширяет набор API. Существующий код компилируется практически без изменений. Чтобы сдержать обещание "это набор API, который предоставляет все реализации .NET", платформа .NET Standard не включает технологии, которые не могут работать на всех платформах, такие как реестр, инструментарий управления Windows (WMI) или API порождения отражения. Пакет обеспечения совместимости Windows основан на .NET Standard и обеспечивает доступ к таким технологиям, которые доступны только в Windows. Это особенно полезно для клиентов, которые хотят перейти на .NET Core, но по меньшей мере на первом этапе планируют оставаться в Windows. В этом сценарии возможность использования технологий, предназначенных только для Windows, устраняет препятствия для миграции.

## <a name="package-contents"></a>Содержимое пакета

Пакет обеспечения совместимости Windows предоставляется с помощью [пакета NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility), и на него можно ссылаться из проектов, предназначенных для .NET Core или .NET Standard.

Он предоставляет около 20 000 API, включая API только для Windows, а также кроссплатформенные API из следующих технологических областей:

- Кодовые страницы
- CodeDom
- Конфигурация
- Служба каталогов
- Рисование
- ODBC
- Разрешения
- порты;
- Списки управления доступом Windows (ACL)
- Windows Communication Foundation (WCF)
- Шифрование Windows
- Windows EventLog
- Инструментарий управления Windows (WMI)
- Счетчики производительности Windows
- Реестр Windows
- Кэширование среды выполнения Windows
- службы Windows

Дополнительные сведения см. в [характеристиках пакета обеспечения совместимости](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Начало работы

1. Перед переносом обязательно проверьте [процесс переноса](index.md).

2. При переносе существующего кода в .NET Core или .NET Standard установите [пакет NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

   Если вы хотите остаться на Windows, больше ничего не требуется.

3. Если вы хотите запускать приложение .NET Core или библиотеку .NET Standard в macOS или Linux, используйте [анализатор API](../../standard/analyzers/api-analyzer.md), чтобы найти используемые API, которые не будут работать на разных платформах.

4. Удалите случаи использования этих API, замените их на кроссплатформенные альтернативы или защитите с помощью проверки платформы, например:

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

Демонстрацию см. в [видео Channel 9 по пакету обеспечения совместимости Windows](https://channel9.msdn.com/Events/Connect/2017/T123).
