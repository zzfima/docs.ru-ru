---
title: 'Как: создание объекта TimeZoneInfo'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e15e7f8968d7edf87ae3cd709d8fb26a2f49826a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a>Как: создание объекта TimeZoneInfo

Наиболее распространенный способ создания экземпляра объекта <xref:System.TimeZoneInfo> — получение сведений о нем из реестра. В этом разделе описываются способы создания экземпляра объекта <xref:System.TimeZoneInfo> на основе локального системного реестра.

### <a name="to-instantiate-a-timezoneinfo-object"></a>Создание экземпляра объекта TimeZoneInfo

1. Объявите объект <xref:System.TimeZoneInfo> .

2. Вызовите `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> метод.

3. Обработайте исключения, созданные этим методом, особенно <xref:System.TimeZoneNotFoundException> , создаваемое, если в реестре не определен часовой пояс.

## <a name="example"></a>Пример

Следующий код извлекает объект <xref:System.TimeZoneInfo> , который представляет часовой пояс восточного времени США, и отображает время в этом поясе, соответствующее местному времени.

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> Единственный параметр метода является идентификатор часового пояса, которую требуется получить, соответствующий объекту <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> свойство. Идентификатор часового пояса — это важнейшее поле, которое уникально идентифицирует часовой пояс. Несмотря на то что большинство ключей являются относительно короткими, идентификатор часового пояса относительно длинный. В большинстве случаев его значение соответствует свойству <xref:System.TimeZoneInfo.StandardName%2A> объекта <xref:System.TimeZoneInfo> , которое используется для предоставления имени стандартного времени часового пояса. Однако существуют исключения. Лучше всего гарантировать, что передается действительный идентификатор, путем перечисления доступных в системе часовых поясов и отслеживания присутствующих в них идентификаторов часовых поясов. Пример см. в разделе [Практическое руководство. Перечисление присутствующих на компьютере часовых поясов](../../../docs/standard/datetime/enumerate-time-zones.md). Раздел [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) также содержит список идентификаторов избранных часовых поясов.

Если часовой пояс найден, метод возвращает его объект <xref:System.TimeZoneInfo> . Если часовой пояс не найден, метод создает <xref:System.TimeZoneNotFoundException>. Если часовой пояс найден, но его данные повреждены или неполны, метод создает <xref:System.InvalidTimeZoneException>.

Если приложение зависит от наличия часового пояса, необходимо сначала вызвать метод <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> для извлечения сведений о часовом поясе из реестра. Если вызов метода завершится сбоем, обработчик исключений должен создать новый экземпляр часового пояса или повторно создать его путем десериализации сериализованного объекта <xref:System.TimeZoneInfo> . В разделе [как: восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) в качестве примера.

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[поиск часового пояса, определенные в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[как: доступ к объектам стандартных UTC и местным временем зоны](../../../docs/standard/datetime/access-utc-and-local.md)
