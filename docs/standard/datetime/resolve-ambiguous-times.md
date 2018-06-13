---
title: 'Как: разрешение проблемы неоднозначности времени'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a92081a164d15e5150c582b37c6c688cd15e619e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571203"
---
# <a name="how-to-resolve-ambiguous-times"></a>Как: разрешение проблемы неоднозначности времени

Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC. Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время. При обработке неоднозначного времени можно выполнить одно из следующих действий:

* Сделать предположение о том, насколько время соответствует времени в формате UTC. Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.

* Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.

В этом разделе показано, как устранить неоднозначное время, предполагая, что он представляет зимнего времени часового пояса.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Сопоставление неоднозначного времени стандартному времени часового пояса

1. Вызовите <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> метод, чтобы определить, является ли время неоднозначным.

2. Если время является неоднозначным, вычитать время из <xref:System.TimeSpan> объект, возвращаемый часового пояса <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойство.

3. Вызовите `static` (`Shared` в Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> метод, чтобы задать UTC значения даты и времени <xref:System.DateTime.Kind%2A> свойства <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.

## <a name="example"></a>Пример

Следующий пример показывает, как преобразовать неоднозначное время в формат UTC, предполагая, что он представляет зимнего времени часового пояса.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

Пример состоит из метода с именем `ResolveAmbiguousTime` , определяющее, является ли <xref:System.DateTime> переданное значение является неоднозначным. Если значение является неоднозначным, метод возвращает <xref:System.DateTime> значение, представляющее собой соответствующее время UTC. Метод обрабатывает это преобразование путем вычитания значения местного часового пояса <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойство из местного времени.

Как правило, неоднозначное время обрабатывается вызовом <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> метод для извлечения массива <xref:System.TimeSpan> объектов, содержащих неоднозначное время (UTC) возможные смещения. Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса. <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Свойство Возвращает смещение между временем UTC и зимнего времени часового пояса.

В этом примере все ссылки на местный часовой пояс выполняются через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство; местное время, зоны никогда не назначается переменной объекта. Это рекомендуется, поскольку вызов <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метод делает недействительными все объекты, которые назначены местного часового пояса.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы ссылка на System.Core.dll была добавлена в проект.

* Что <xref:System> импортировать пространство имен с `using` инструкции (обязательно в коде C#).

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[как: разрешить пользователям разрешение проблемы неоднозначности времени](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
