---
title: Анализатор переносимости .NET
description: Сведения о том, как применять анализатор переносимости .NET для оценки переносимости кода в разных реализациях .NET, включая .NET Core, .NET Standard, UWP и Xamarin.
author: blackdwarf
ms.author: mairaw
ms.date: 07/26/2017
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: 515dd7a393d87811377aa5d9fb02de35943b6966
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43415692"
---
# <a name="the-net-portability-analyzer"></a>Анализатор переносимости .NET

Хотите, чтобы ваши библиотеки работали на нескольких платформах? Хотите понять, как обеспечить поддержку совместимости приложения с другими реализациями и профилями .NET, включая .NET Core, .NET Standard, UWP и Xamarin для Mac, iOS и Android? [Анализатор переносимости .NET](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) — это средство формирования подробного отчета об уровне гибкости программы в рамках реализаций .NET на основе данных анализа сборок. Анализатор переносимости предлагается в виде расширения Visual Studio и консольного приложения.

## <a name="new-targets"></a>Новые цели

* [.NET Core](../../core/index.md): имеет модульную архитектуру, использует сценарии параллельного выполнения и поддерживает работу на различных платформах. Принцип параллелизма позволяет внедрять новые версии .NET Core, не нарушая функционирования других приложений.
* [ASP.NET Core](/aspnet/core): представляет собой современную веб-платформу, созданную на основе .NET Core и в связи с этим предоставляющую разработчикам те же преимущества.
* [Универсальная платформа Windows](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): способствует повышению производительности приложений из Магазина Windows, работающих на компьютерах с архитектурой x64 и ARM, за счет статический компиляции .NET Native. 
* .NET Core + расширения платформы: включает API-интерфейсы .NET Core помимо других API-интерфейсов в экосистеме .NET, такие как WCF, ASP.NET Core, FSharp и Azure.
* .NET Standard + расширения платформы: включает API-интерфейсы .NET Standard помимо других в экосистеме .NET, такие как WCF, ASP.NET Core, FSharp и Azure.

## <a name="how-to-use-portability-analyzer"></a>Как использовать анализатор переносимости

Чтобы начать пользоваться анализатором переносимости .NET, скачайте и установите расширение из [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer). Оно работает в Visual Studio 2015 и Visual Studio 2017. Его можно настроить в Visual Studio, выбрав **Анализировать** > **Portability Analyzer Settings** (Параметры анализатора переносимости) и указав целевые платформы.

![Снимок экрана анализатора переносимости](./media/portability-analyzer/portability-screenshot.png)

Чтобы проанализировать весь проект, щелкните его правой кнопкой мыши в **обозревателе решений** и выберите пункт **Analyze Assembly Portability** (Анализировать переносимость сборки). Или в меню **Анализ** выберите **Анализировать переносимость сборки**. После этого выберите исполняемый файл или DLL-файл проекта.

![Обозреватель решений переносимости](./media/portability-analyzer/portability-solution-explorer.png)

После выполнения анализа вы увидите отчет о переносимости .NET. В списке отображаются только типы, которые не поддерживаются целевой платформой. Рекомендации можно просмотреть на вкладке **Сообщения** в области **Список ошибок**. С вкладки **Сообщения** можно также напрямую перейти к проблемным областям.

![Отчет о переносимости](./media/portability-analyzer/portability-report.png)

Не хотите использовать Visual Studio? Вы также можете запустить анализатор переносимости из командной строки. Просто скачайте [API анализатора переносимости](https://www.microsoft.com/download/details.aspx?id=42678).

*   Для анализа текущего каталога выполните следующую команду: `\...\ApiPort.exe analyze -f .`.
*   Для анализа заданного списка DLL-файлов выполните следующую команду: `\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`.

Отчет о переносимости .NET сохраняется в файле Excel (*XLSX*) в текущем каталоге. Дополнительные сведения указаны на вкладке **Details** (Подробности) в книге Excel.

Дополнительные сведения об анализаторе переносимости .NET см. в [документации GitHub](https://github.com/Microsoft/dotnet-apiport#documentation) и видеоролике с [кратким обзором анализатора переносимости .NET](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer) на Channel 9.
