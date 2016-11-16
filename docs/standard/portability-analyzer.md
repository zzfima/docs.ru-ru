---
title: "Анализатор переносимости .NET | .NET"
description: "Информация об оценке переносимости кода на различные платформы .NET при помощи анализатора переносимости .NET."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
manager: wpickett
ms.date: 07/05/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
translationtype: Human Translation
ms.sourcegitcommit: 8599be1eadcd6f005ef344bf173e8c06fce80725
ms.openlocfilehash: 479b141159de95c6a7e466220f935f9371b353db

---

# <a name="the-net-portability-analyzer"></a>Анализатор переносимости .NET

Хотите, чтобы ваши библиотеки работали на нескольких платформах? Хотите узнать, какой объем работ требуется проделать, чтобы сделать приложение совместимым с другими платформами .NET? [Анализатор переносимости .NET](http://go.microsoft.com/fwlink/?LinkID=507467) — это средство формирования подробного отчета об уровне гибкости программы в рамках платформ .NET на основе данных анализа сборок. Анализатор переносимости предлагается в виде расширения Visual Studio и консольного приложения.

## <a name="new-targets"></a>Новые цели

*   [.NET Core](https://www.dotnetfoundation.org/netcore): имеет модульную архитектуру, использует сценарии параллельного выполнения и поддерживает работу на различных платформах. Принцип параллелизма позволяет внедрять новые версии .NET Core, не нарушая функционирования других приложений.
*   [ASP.NET Core](https://www.dotnetfoundation.org/aspnet-core): представляет собой современную веб-платформу, созданную на основе .NET Core и в связи с этим предоставляющую разработчикам те же преимущества.
*   [.NET Native](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): способствует повышению производительности приложений из Магазина Windows, работающих на компьютерах с архитектурой x64 и ARM, за счет статический компиляции .NET Native.

## <a name="how-to-use-portability-analyzer"></a>Как использовать анализатор переносимости

Чтобы начать пользоваться анализатором переносимости .NET, скачайте и установите расширение из [коллекции Visual Studio](http://go.microsoft.com/fwlink/?LinkID=507467). Его можно настроить в Visual Studio, выбрав **Сервис** > **Параметры** > **.NET Portability Analyzer** (Анализатор переносимости .NET) и указав целевые платформы. На данный момент ASP.NET Core можно использовать как прокси для всех платформ на базе .NET Core (например, [приложения универсальной платформы Windows 10 .NET](http://blogs.windows.com/buildingapps/2015/03/02/a-first-look-at-the-windows-10-universal-app-platform/)).

![Снимок экрана анализатора переносимости](./media/portability-analyzer/portability-screenshot.png)

Чтобы проанализировать весь проект, щелкните его правой кнопкой мыши в **обозревателе решений** и выберите **Analyze** (Анализ) > **Analyze Assembly Portability** (Анализировать переносимость сборки). Или в меню **Анализ** выберите **Анализировать переносимость сборки**. После этого выберите исполняемый файл или DLL-файл проекта.

![Обозреватель решений переносимости](./media/portability-analyzer/portability-solution-explorer.png)

После выполнения анализа вы увидите отчет о переносимости .NET. В списке будут отображены только типы, которые не поддерживаются целевой платформой. Рекомендации можно просмотреть на вкладке **Сообщения** в области **Список ошибок**. С вкладки **Сообщения** можно также напрямую перейти к проблемным областям.

![Отчет о переносимости](./media/portability-analyzer/portability-report.png)

Не хотите использовать Visual Studio? Вы также можете запустить анализатор переносимости из командной строки. Просто скачайте [API анализатора переносимости](http://www.microsoft.com/download/details.aspx?id=42678).

*   Для анализа текущего каталога выполните следующую команду: `\...\ApiPort.exe .`.
*   Для анализа заданного списка DLL-файлов выполните следующую команду: `\...\ApiPort.exe first.dll second.dll third.dll`.

Отчет о переносимости .NET будет сохранен в файле Excel (*.xlsx*) в текущем каталоге. Дополнительные сведения указаны на вкладке **Details** (Подробности) в файле Excel.

Дополнительные сведения об анализаторе переносимости .NET см. в публикации [Leveraging existing code across .NET platforms](https://blogs.msdn.microsoft.com/dotnet/2014/08/06/leveraging-existing-code-across-net-platforms/) (Использование существующего кода на платформах .NET) в блоге .NET.



<!--HONumber=Nov16_HO1-->


