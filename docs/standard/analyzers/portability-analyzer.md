---
title: Анализатор переносимости .NET
description: Сведения о том, как применять анализатор переносимости .NET для оценки переносимости кода в разных реализациях .NET, включая .NET Core, .NET Standard, UWP и Xamarin.
ms.date: 04/26/2019
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: 7de6aa72b2d30c3e54d2ddf9a2d951688571d654
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063447"
---
# <a name="the-net-portability-analyzer"></a>Анализатор переносимости .NET

Хотите, чтобы ваши библиотеки работали на нескольких платформах? Хотите понять, как обеспечить поддержку совместимости приложения с другими реализациями и профилями .NET, включая .NET Core, .NET Standard, UWP и Xamarin для Mac, iOS и Android? [Анализатор переносимости .NET](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) — это средство формирования подробного отчета об уровне гибкости программы в рамках реализаций .NET на основе данных анализа сборок. Анализатор переносимости предлагается в виде расширения Visual Studio и консольного приложения.

## <a name="new-targets"></a>Новые цели

* [.NET Core](../../core/index.md). Имеет модульную архитектуру, использует сценарии параллельного выполнения и поддерживает работу на различных платформах. Принцип параллелизма позволяет внедрять новые версии .NET Core, не нарушая функционирования других приложений.
* [ASP.NET Core](/aspnet/core): представляет собой современную веб-платформу, созданную на основе .NET Core и в связи с этим предоставляющую разработчикам те же преимущества.
* [Универсальная платформа Windows](/uwp). Способствует повышению производительности приложений из Магазина Windows, работающих на компьютерах с архитектурой x64 и ARM, за счет статический компиляции .NET Native. 
* Платформа .NET Core и ее расширения. Включает API .NET Core наряду с другими API в экосистеме .NET, такие как WCF, ASP.NET Core, FSharp и Azure.
* Платформа .NET Standard и ее расширения. Включает API .NET Standard наряду с другими API в экосистеме .NET, такие как WCF, ASP.NET Core, FSharp и Azure.

## <a name="how-to-use-the-portability-analyzer"></a>Как использовать анализатор переносимости

Чтобы начать пользоваться анализатором переносимости .NET, скачайте и установите расширение из [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer). Оно работает в Visual Studio 2017 и более поздних версиях. Его можно настроить в Visual Studio, выбрав **Анализировать** > **Portability Analyzer Settings** (Параметры анализатора переносимости) и указав целевые платформы.

![Снимок экрана анализатора переносимости](./media/portability-analyzer/portability-screenshot.png)

Чтобы проанализировать весь проект, щелкните его правой кнопкой мыши в **обозревателе решений** и выберите пункт **Analyze Assembly Portability** (Анализировать переносимость сборки). Или в меню **Анализ** выберите **Анализировать переносимость сборки**. После этого выберите исполняемый файл или DLL-файл проекта.

![Анализатор переносимости из обозревателя решений](./media/portability-analyzer/portability-solution-explorer.png)

После выполнения анализа вы увидите отчет о переносимости .NET. В списке отображаются только типы, которые не поддерживаются целевой платформой. Рекомендации можно просмотреть на вкладке **Сообщения** в области **Список ошибок**. С вкладки **Сообщения** можно также напрямую перейти к проблемным областям.

![Отчет о переносимости](./media/portability-analyzer/portability-report.png)

Если вы не хотите использовать Visual Studio, можно использовать анализатор переносимости из командной строки. Просто скачайте анализатор переносимости API из репозитория [Microsoft/dotnet-apiport](https://github.com/Microsoft/dotnet-apiport/releases).

* Для анализа текущего каталога выполните следующую команду: `\...\ApiPort.exe analyze -f .`.
* Для анализа заданного списка DLL-файлов выполните следующую команду: `\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`.

Отчет о переносимости .NET сохраняется в файле Excel (*XLSX*) в текущем каталоге. Дополнительные сведения указаны на вкладке **Details** (Подробности) в книге Excel.

Дополнительные сведения об анализаторе переносимости .NET см. в [документации GitHub](https://github.com/Microsoft/dotnet-apiport#documentation) и видеоролике с [кратким обзором анализатора переносимости .NET](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer) на Channel 9.
