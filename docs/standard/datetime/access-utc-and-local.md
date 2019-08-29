---
title: Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8aa19118ce0837b9ce0eb523f3e086fcbcecb9e8
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106554"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов

Класс предоставляет два свойства, <xref:System.TimeZoneInfo.Utc%2A> и <xref:System.TimeZoneInfo.Local%2A>, которые предоставляют коду доступ к предопределенным объектам часового пояса. <xref:System.TimeZoneInfo> В этом разделе рассматривается порядок работы с объектами <xref:System.TimeZoneInfo>, возвращаемыми этими свойствами.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Получение объекта TimeZoneInfo времени UTC

1. Используйте свойство`Shared` <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> (в Visual Basic) для доступа к всеобщему скоординированному времени. `static`

2. Вместо того чтобы назначать <xref:System.TimeZoneInfo> объект, возвращаемый свойством, в объектную переменную, продолжайте обращаться к времени в <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> формате UTC через свойство.

### <a name="to-access-the-local-time-zone"></a>Получение местного часового пояса

1. Используйте свойство`Shared` <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> (в Visual Basic) для доступа к часовому поясу локальной системы. `static`

2. Вместо того чтобы назначать <xref:System.TimeZoneInfo> объект, возвращаемый свойством, в объектную переменную, продолжайте обращаться к местному <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> часовому поясу через свойство.

## <a name="example"></a>Пример

В следующем коде свойства <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> и <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> используются для преобразования времени из восточного стандартного часового пояса США и Канады, а также для вывода названия часового пояса на консоль.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Необходимо всегда обращаться к локальному часовому поясу через свойство, <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> а не назначать местный часовой пояс <xref:System.TimeZoneInfo> переменной объекта. Аналогичным образом следует всегда обращаться к всеобщему скоординированному <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> времени через свойство, не назначив часовой пояс <xref:System.TimeZoneInfo> в объектную переменную. Это предотвращает <xref:System.TimeZoneInfo> недействительность аннулирования переменной объекта при вызове <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метода.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- , Что `using` пространство имен должно быть импортировано с помощью оператора C# (требуется в коде). <xref:System>

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [Практическое руководство. Создание экземпляра объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)
