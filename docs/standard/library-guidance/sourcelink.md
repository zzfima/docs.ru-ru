---
title: SourceLink и библиотеки .NET
description: Практические рекомендации по использованию SourceLink для повышения эффективности отладки для библиотек .NET.
author: jamesnk
ms.author: mairaw
ms.date: 01/15/2019
ms.openlocfilehash: be97f868e2fcfc6c45e4bbac45b033f8914f4d99
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333542"
---
# <a name="sourcelink"></a>SourceLink

SourceLink — это технология, которая дает возможность разработчикам выполнять отладку исходного кода сборок .NET из NuGet. SourceLink выполняется при создании пакета NuGet и внедряет метаданные системы управления версиями внутри сборки и пакета. Разработчики, загрузившие пакет (функция SourceLink должна быть включена в Visual Studio), могут выполнить исходный код по шагам. SourceLink предоставляет метаданные системы управления версиями для создания эффективной среды отладки.

## <a name="sourcelink-demo"></a>Демонстрация SourceLink

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a>Использование SourceLink

Инструкции по использованию SourceLink можно найти в репозитории GitHub [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).

Вы можете использовать [обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), чтобы убедиться, что метаданные SourceLink успешно внедрены в пакет. Проверьте наличие метаданных `Repository` с идентификатором комментария и убедитесь, что для каждой DLL-библиотеки целевого пакета есть PDB-файлы.

![SourceLink в обозревателе пакетов NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")

**✔️ РЕКОМЕНДУЕТСЯ** использовать SourceLink для добавления метаданных системы управления версиями в сборки и пакеты NuGet.

> [!TIP]
> Вы можете дополнительно повысить эффективность отладки путем добавления атрибутов отладчика в типы.
> * <xref:System.Diagnostics.DebuggerDisplayAttribute> может определять, как класс или поле будет отображаться в окнах переменных отладчика.
> * <xref:System.Diagnostics.DebuggerStepThroughAttribute> дает отладчику указание о сквозной обработке кода (вместо выполнения по шагам).
> * <xref:System.Diagnostics.DebuggerBrowsableAttribute> определяет, будет ли член отображаться в окнах переменных отладчика.

**✔️ ДОПУСТИМО.** Публикация файлов символов (`*.pdb`).

> См. дополнительные сведения о [файлах и пакетах символов](./nuget.md#symbol-packages).

>[!div class="step-by-step"]
>[Назад](dependencies.md)
>[Вперед](publish-nuget-package.md)
