---
title: Руководство. разрешение неоднозначных времени
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 0b5b28c588237fb2f7f069aaef06f3f73d5268bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122253"
---
# <a name="how-to-resolve-ambiguous-times"></a>Руководство. разрешение неоднозначных времени

Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC. Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время. При обработке неоднозначного времени можно выполнить одно из следующих действий:

- Сделать предположение о том, насколько время соответствует времени в формате UTC. Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.

- Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.

В этом разделе показано, как устранить неоднозначное время, предполагая, что оно представляет стандартное время часового пояса.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Сопоставление неоднозначного времени стандартному времени часового пояса

1. Вызовите метод <xref:System.TimeZoneInfo.IsAmbiguousTime%2A>, чтобы определить, является ли время неоднозначным.

2. Если время неоднозначно, вычтите время из объекта <xref:System.TimeSpan>, возвращенного свойством <xref:System.TimeZoneInfo.BaseUtcOffset%2A> часового пояса.

3. Вызовите метод `static` (`Shared` в Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A>, чтобы задать для свойства <xref:System.DateTime.Kind%2A> значения даты и времени в формате UTC значение <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.

## <a name="example"></a>Пример

В следующем примере показано, как преобразовать неоднозначное время в формат UTC, предполагая, что он представляет стандартное время местного часового пояса.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

Пример состоит из метода с именем `ResolveAmbiguousTime`, определяющего, является ли передаваемое ему значение <xref:System.DateTime> неоднозначным. Если значение неоднозначно, метод возвращает <xref:System.DateTime> значение, представляющее соответствующее время в формате UTC. Метод обрабатывает это преобразование, вычитая значение свойства <xref:System.TimeZoneInfo.BaseUtcOffset%2A> местного часового пояса из местного времени.

Как правило, неоднозначное время обрабатывается путем вызова метода <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> для получения массива объектов <xref:System.TimeSpan>, содержащих возможные смещения времени в формате UTC неоднозначности. Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса. Свойство <xref:System.TimeZoneInfo.BaseUtcOffset%2A> возвращает смещение между временем UTC и стандартным временем часового пояса.

В этом примере все ссылки на местный часовой пояс выполняются через свойство <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>. местный часовой пояс никогда не назначается объектной переменной. Это рекомендуемый подход, поскольку вызов метода <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> делает недействительными все объекты, которым назначен местный часовой пояс.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- , Что <xref:System> пространство имен должно быть импортировано с помощью оператора `using` C# (требуется в коде).

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
