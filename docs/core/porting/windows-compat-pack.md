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
# <a name="using-the-windows-compatibility-pack"></a>С помощью пакета совместимости Windows

Одним из наиболее распространенных проблем, с которыми сталкиваются разработчики, при переносе существующего кода, .NET Core — что они используют API-интерфейсы и технологии, которые существуют только в .NET Framework. *Пакет обеспечения совместимости Windows* заключается в предоставлении многих из этих технологий, чтобы построения приложений .NET Core, а также .NET стандартные библиотеки становится более приемлемым для существующего кода.

Этот пакет является логического [расширения платформы .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) том, что значительно повышает набор API и существующий код компилируется практически без изменений. Но для сохранения согласованности promise стандарта .NET («это набор API-интерфейсов, которые предоставляют все реализации .NET»), это не относится к технологии, которые не могут работать на всех платформах, такие как реестр, инструментарий управления Windows (WMI) или порождение отражения API-интерфейсы.

*Пакет обеспечения совместимости Windows* располагается в верхней части .NET Standard и обеспечивает доступ к технологии, которые доступны только в Windows. Это особенно полезно для пользователей, чтобы перейти к .NET Core, но плана оставаться в Windows в качестве первого шага. В этом сценарии не имея возможности применять технологии только для Windows является только препятствие миграции с нуля преимущества архитектуры.

## <a name="package-contents"></a>Содержимое пакета

*Пакет обеспечения совместимости Windows* обеспечивается за счет пакета NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) и может указываться в проектах, предназначенных для .NET Core или .NET Standard.

Он предоставляет около 20 000 API, в том числе только для Windows, а также между различными платформами API из области следующих технологий:

* Кодовые страницы
* CodeDom
* Конфигурация
* Служба каталогов
* Рисование
* ODBC
* Разрешения
* Порты
* Списки управления доступом Windows (ACL)
* Windows Communication Foundation (WCF)
* Криптография Windows
* Журнал событий Windows
* инструментирование управления Windows (WMI)
* Счетчики производительности Windows
* Реестр Windows
* Кэширование среды выполнения Windows
* службы Windows

Дополнительные сведения см. в разделе [характеристик пакета совместимости](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Начало работы

1. Перед развертыванием, убедитесь, что взгляните на [процесс портировании](index.md).

2. При переносе существующего кода в .NET Core или .NET Standard, установите пакет NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

3. Если вы хотите остаться на Windows, всех настроек.

4. Если вы хотите запускать приложение .NET Core или .NET стандартной библиотеки на macOS или Linux, используйте [API анализатора](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) найти использование API-интерфейсов, не будут работать на разных платформах.

5. Удалите примеры использования этих интерфейсов API, замените альтернативы кросс платформенных или защитить их с помощью проверки платформы, например:

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

Для демонстрации, извлечь [видео Channel 9 пакета совместимости Windows](https://channel9.msdn.com/Events/Connect/2017/T123).

