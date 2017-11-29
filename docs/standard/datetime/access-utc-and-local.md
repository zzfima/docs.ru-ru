---
title: "Как: доступ к объектам стандартных UTC и местным временем зоны"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4538407bc66ad7974a9a4998c8e5d7ccb38fab4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Как: доступ к объектам стандартных UTC и местным временем зоны

<xref:System.TimeZoneInfo> Класс содержит два свойства <xref:System.TimeZoneInfo.Utc%2A> и <xref:System.TimeZoneInfo.Local%2A>, что предоставляете доступ кода к предопределенных объекта часовых поясов. В этом разделе рассматривается порядок работы с объектами <xref:System.TimeZoneInfo>, возвращаемыми этими свойствами.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Получение объекта TimeZoneInfo времени UTC

1. Используйте `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> свойство для доступа к в формате UTC.

2. Вместо назначения <xref:System.TimeZoneInfo> объекты, возвращаемые этим свойством переменной объекта продолжать обращаться к Гринвичу через <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> свойство.

### <a name="to-access-the-local-time-zone"></a>Получение местного часового пояса

1. Используйте `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство для доступа к локальной системе часовым поясом.

2. Вместо назначения <xref:System.TimeZoneInfo> объекты, возвращаемые этим свойством переменной объекта продолжать обращаться к местного часового пояса через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство.

## <a name="example"></a>Пример

В следующем коде свойства <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> и <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> используются для преобразования времени из восточного стандартного часового пояса США и Канады, а также для вывода названия часового пояса на консоль.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Следует всегда обращаться к местного часового пояса через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство вместо назначения местное время зона на <xref:System.TimeZoneInfo> объектной переменной. Аналогичным образом, следует всегда обращаться к Гринвичу через <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> свойство вместо назначения в формате UTC зона на <xref:System.TimeZoneInfo> объектной переменной. Это предотвращает <xref:System.TimeZoneInfo> объектной переменной с помощью вызова недопустимого <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метод.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы ссылка на System.Core.dll была добавлена в проект.

* Что <xref:System> импортировать пространство имен с `using` инструкции (обязательно в коде C#).

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[поиск часового пояса, определенные в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[как: создание объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)
