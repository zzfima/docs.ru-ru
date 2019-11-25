---
title: Инструменты для переноса в .NET Core
description: Дополнительные сведения о некоторых инструментах, которые можно использовать для переноса в .NET Core
author: cartermp
ms.author: mairaw
ms.date: 12/07/2018
ms.openlocfilehash: 0478719617741946768cfe8e220a1dd402667998
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521350"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>Инструменты для переноса в .NET Core

Инструменты в этой статье помогут вам при переносе:

- [Анализатор переносимости .NET](../../standard/analyzers/portability-analyzer.md) — цепочка инструментов, создающих отчеты о переносимости кода между .NET Framework и .NET Core:  Как [инструмент командной строки](https://github.com/Microsoft/dotnet-apiport/releases) Как [расширение Visual Studio](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)
- [Анализатор API .NET](../../standard/analyzers/api-analyzer.md) — анализатор на основе Roslyn выявляет риски совместимости для API на языке C# на разных платформах, а также отслеживает вызовы устаревших API.

Кроме того, можно попытаться перенести более мелкие решения или отдельные проекты в формат файла проекта .NET Core с помощью средства [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).

> [!WARNING] 
> CsprojToVs2017 — это стороннее средство. Нет никакой гарантии, что оно будет поддерживать все проекты. Кроме того, оно может вызвать незначительные изменения в ожидаемом поведении. CsprojToVs2017 следует использовать в качестве _начальной точки_, которая автоматизирует соответствующие основные процессы. Это решение не может гарантировать перенос форматов файлов проекта.
