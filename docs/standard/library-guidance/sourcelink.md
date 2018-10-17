---
title: Библиотеки SourceLink и .NET
description: Практические рекомендации по использованию SourceLink для улучшения отладки для библиотеки .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: fa4af47eaa5dd1510640c2bf0ebb2187b56efae0
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49370317"
---
# <a name="sourcelink"></a>SourceLink

SourceLink — это технология, которая разрешает отладку исходного кода сборок .NET из NuGet разработчиками. SourceLink выполняет при создании пакета NuGet и внедряет источника метаданных элемента управления внутри сборки и пакет. Разработчики, загрузившие пакета и иметь SourceLink включена в Visual Studio можно зайти в его исходный код. SourceLink предоставляет источник метаданных элемента управления для создания удобной отладки.

## <a name="sourcelink-demo"></a>Демонстрация SourceLink

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a>С помощью SourceLink

Инструкции по использованию SourceLink можно найти на [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) репозитория GitHub.

Можно использовать [обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) для подтверждения того, что метаданные SourceLink успешно внедрен в пакете. Проверьте `Repository` присутствует метаданных с идентификатором комментарий и PDB-файлы находятся с DLL каждый целевой объект.

![SourceLink в обозревателе пакетов NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink в обозревателе пакетов NuGet")

**Рассмотрите ВОЗМОЖНОСТЬ ✔️** Добавление метаданных элемента управления источника сборки и пакет NuGet с помощью SourceLink.

**Рассмотрите ВОЗМОЖНОСТЬ ✔️** включая PDB-файлы в пакете NuGet.

>[!div class="step-by-step"]
[Назад](./dependencies.md)
[Вперед](./publish-nuget-package.md)
