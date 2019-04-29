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
ms.openlocfilehash: aae3e5145d2fa85cd55fc5b1288ef4aaa0fef48f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796413"
---
# <a name="how-to-resolve-ambiguous-times"></a>Практическое руководство. Разрешение проблемы неоднозначности времени

Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC. Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время. При обработке неоднозначного времени можно выполнить одно из следующих действий:

* Сделать предположение о том, насколько время соответствует времени в формате UTC. Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.

* Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.

В этом разделе показано, как устранить неоднозначное время, предполагая, что он представляет стандартное время часового пояса.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Сопоставление неоднозначного времени стандартному времени часового пояса

1. Вызовите <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> метод, чтобы определить, является ли время неоднозначным.

2. Если время является неоднозначным, вычитайте время из <xref:System.TimeSpan> объект, возвращаемый в часовом поясе <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойство.

3. Вызовите `static` (`Shared` в Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> метод для установки даты и времени значение в формате UTC <xref:System.DateTime.Kind%2A> свойства <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.

## <a name="example"></a>Пример

Следующий пример иллюстрирует, как преобразовать неоднозначное время в формат UTC, предполагая, что он представляет местного часового пояса (зима).

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

Пример состоит из метода с именем `ResolveAmbiguousTime` , определяет ли <xref:System.DateTime> переданное значение является неоднозначным. Если значение является неоднозначным, метод возвращает <xref:System.DateTime> значение, представляющее собой соответствующее время в формате UTC. Метод обрабатывает это преобразование путем вычитания значения местного часового пояса <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойство из локального времени.

Как правило, неоднозначное время обрабатывается вызовом <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> метод для извлечения массива <xref:System.TimeSpan> offsets объектов, содержащих возможные неоднозначное время в формате UTC. Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса. <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Возвращает смещение между временем UTC и временем стандартного часового пояса.

В этом примере все ссылки на местный часовой пояс выполняются через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство; в местный часовой пояс никогда не назначается переменной объекта. Это рекомендуется, поскольку вызов <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метод не делает недействительными все объекты, которые назначены местного часового пояса.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы добавить в проект ссылку на библиотеку System.Core.dll.

* Что <xref:System> импорт пространства имен с помощью `using` инструкции (обязательно в коде C#).

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
