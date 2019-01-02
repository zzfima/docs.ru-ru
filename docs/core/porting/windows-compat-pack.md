---
title: Перенос кода в .NET Core с помощью пакета обеспечения совместимости Windows
description: Сведения о пакете обеспечения совместимости Windows и его использовании для переноса существующего кода .NET Framework на .NET Core
author: terrajobst
ms.date: 11/13/2017
ms.custom: seodec18
ms.openlocfilehash: 0a409c953ce38ed4c2959adaf4de9d3730ce37f4
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169941"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a>Перенос кода в .NET Core с помощью пакета обеспечения совместимости Windows

Часто проблемы при переносе существующего кода в .NET Core связаны с зависимостями от API и технологий, которые доступны только в .NET Framework. *Пакет обеспечения совместимости Windows* предоставляет многие из этих технологий. Это значительно упрощает создание приложений .NET Core и библиотек .NET Standard.

Этот пакет является логическим [расширением платформы .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support), который значительно расширяет набор API, в результате чего существующий код компилируется практически без изменений. Но для обеспечения согласованности .NET Standard ("это набор API, предоставляемых всеми реализациями .NET") он не включает технологии, которые не могут работать на всех платформах, таких как реестр, инструментарий управления Windows (WMI) или API порождения отражения.

*Пакет обеспечения совместимости Windows* основан на .NET Standard и обеспечивает доступ к технологиям, которые доступны только в Windows. Это особенно полезно для клиентов, которые хотят перейти на .NET Core, но на первом этапе планируют оставаться в Windows. В этом сценарии неспособность использовать технологии, предназначенные только для Windows, лишь создает препятствия для миграции, не давая никаких архитектурных преимуществ.

## <a name="package-contents"></a>Содержимое пакета

*Пакет обеспечения совместимости Windows* предоставляется с помощью пакета NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility), и на него можно ссылаться из проектов, предназначенных для .NET Core или .NET Standard.

Он предоставляет около 20 000 API, включая API только для Windows, а также кроссплатформенные API из следующих технологических областей:

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
* Шифрование Windows
* Windows EventLog
* инструментирование управления Windows (WMI)
* Счетчики производительности Windows
* Реестр Windows
* Кэширование среды выполнения Windows
* службы Windows

Дополнительные сведения см. в [характеристиках пакета обеспечения совместимости](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Начало работы

1. Перед переносом обязательно проверьте [процесс переноса](index.md).

2. При переносе существующего кода в .NET Core или .NET Standard установите пакет NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

3. Если вы хотите остаться на Windows, больше ничего не требуется.

4. Если вы хотите запускать приложение .NET Core или библиотеку .NET Standard в macOS или Linux, используйте [анализатор API](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/), чтобы найти используемые API, которые не будут работать на разных платформах.

5. Удалите случаи использования этих API, замените их на кроссплатформенные альтернативы или защитите с помощью проверки платформы, например:

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

