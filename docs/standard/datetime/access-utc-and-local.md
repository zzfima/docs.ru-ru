---
title: Как получить доступ к стандартным объектам времени в формате UTC и местному часовому поясу
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
ms.openlocfilehash: ef22753d9934a52d955412a4493b608f265519aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132604"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Как получить доступ к стандартным объектам времени в формате UTC и местному часовому поясу

Класс <xref:System.TimeZoneInfo> предоставляет два свойства: <xref:System.TimeZoneInfo.Utc%2A> и <xref:System.TimeZoneInfo.Local%2A>, которые предоставляют коду доступ к предопределенным объектам часового пояса. В этом разделе рассматривается порядок работы с объектами <xref:System.TimeZoneInfo>, возвращаемыми этими свойствами.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Получение объекта TimeZoneInfo времени UTC

1. Для доступа к всеобщему скоординированному времени используйте свойство `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>.

2. Вместо того, чтобы назначать объект <xref:System.TimeZoneInfo>, возвращаемый свойством, в объектную переменную, продолжайте обращаться к времени в формате UTC через свойство <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>.

### <a name="to-access-the-local-time-zone"></a>Получение местного часового пояса

1. Используйте свойство `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> для доступа к часовому поясу локальной системы.

2. Вместо того чтобы назначать объект <xref:System.TimeZoneInfo>, возвращаемый свойством, в объектную переменную, продолжайте обращаться к местному часовому поясу через свойство <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>.

## <a name="example"></a>Пример

В следующем коде свойства <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> и <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> используются для преобразования времени из восточного стандартного часового пояса США и Канады, а также для вывода названия часового пояса на консоль.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Необходимо всегда обращаться к локальному часовому поясу через свойство <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>, а не назначать местный часовой пояс переменной объекта <xref:System.TimeZoneInfo>. Аналогичным образом следует всегда обращаться к всеобщему скоординированному времени через свойство <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>, а не назначать часовой пояс в <xref:System.TimeZoneInfo> объектной переменной. Это предотвращает невозможность сделать недействительным <xref:System.TimeZoneInfo>ную переменную объекта при вызове метода <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- , Что <xref:System> пространство имен должно быть импортировано с помощью оператора `using` C# (требуется в коде).

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [Практическое руководство. Создание экземпляра объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)
