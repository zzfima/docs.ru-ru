---
title: Практическое руководство. Разрешение проблемы неоднозначности времени
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
ms.openlocfilehash: 6e98d5d8240492ca30da2825b72277d7a35f97f6
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106780"
---
# <a name="how-to-resolve-ambiguous-times"></a>Практическое руководство. Разрешение проблемы неоднозначности времени

Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC. Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время. При обработке неоднозначного времени можно выполнить одно из следующих действий:

- Сделать предположение о том, насколько время соответствует времени в формате UTC. Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.

- Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.

В этом разделе показано, как устранить неоднозначное время, предполагая, что оно представляет стандартное время часового пояса.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Сопоставление неоднозначного времени стандартному времени часового пояса

1. Вызовите <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> метод, чтобы определить, является ли время неоднозначным.

2. Если время неоднозначно, вычтите время из <xref:System.TimeSpan> объекта, возвращенного <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойством часового пояса.

3. `Shared` <xref:System.DateTime.SpecifyKind%2A> <xref:System.DateTime.Kind%2A> Вызовите метод <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>(в Visual Basic .NET), чтобы задать свойству значения даты и времени в формате UTC значение. `static`

## <a name="example"></a>Пример

В следующем примере показано, как преобразовать неоднозначное время в формат UTC, предполагая, что он представляет стандартное время местного часового пояса.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

Пример состоит из метода с именем `ResolveAmbiguousTime` , который определяет, является <xref:System.DateTime> ли передаваемое ему значение неоднозначным. Если значение неоднозначно, метод возвращает <xref:System.DateTime> значение, представляющее соответствующее время в формате UTC. Метод обрабатывает это преобразование, вычитая значение <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойства местного часового пояса из местного времени.

Как правило, неоднозначное время обрабатывается путем <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> вызова метода для получения <xref:System.TimeSpan> массива объектов, содержащих неоднозначное смещение времени в формате UTC. Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса. <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Свойство возвращает смещение между временем UTC и стандартным временем часового пояса.

В этом примере все ссылки на местный часовой пояс выполняются через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство; местный часовой пояс никогда не назначается объектной переменной. Это рекомендуемый подход, поскольку вызов <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метода делает недействительными все объекты, которым назначен местный часовой пояс.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- , Что `using` пространство имен должно быть импортировано с помощью оператора C# (требуется в коде). <xref:System>

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Практическое руководство. Разрешить пользователям решать неоднозначные времена](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
