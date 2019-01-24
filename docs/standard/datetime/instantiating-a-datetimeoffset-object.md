---
title: Создание экземпляра объекта DateTimeOffset
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
- DateTimeOffset structure, converting to DateTime
- DateTimeOffset structure, instantiating
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11f62b8fe8a28d6fe6401d53dac4b9bc1c45b21d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554609"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Создание экземпляра объекта DateTimeOffset

<xref:System.DateTimeOffset> Структуры имеют ряд способов для создания новых <xref:System.DateTimeOffset> значения. Многие из них в непосредственно соответствуют методам создания новых <xref:System.DateTime> значений, которые позволяют указывать смещение значения даты и времени в формате UTC (UTC). В частности, можно создать экземпляр <xref:System.DateTimeOffset> значение одним из следующих способов:

* С помощью литерал даты и времени.

* Путем вызова <xref:System.DateTimeOffset> конструктор.

* Путем неявного преобразования значение <xref:System.DateTimeOffset> значение.

* Разбором строкового представления даты и времени.

В этом разделе содержится больше сведений и примеры кода, иллюстрирующие эти методы создания новых <xref:System.DateTimeOffset> значения.

## <a name="date-and-time-literals"></a>Литералы даты и времени

Для языков, поддерживающих его одним из наиболее распространенных способов для создания экземпляра <xref:System.DateTime> значение которого укажите дату и время в виде жестко заданного литерала. Например, следующий код Visual Basic создает <xref:System.DateTime> объект, значение которого соответствует 1 января 2008 г., 10:00 AM.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset> значения также могут инициализироваться с помощью литералов даты и времени, при использовании языков, поддерживающих <xref:System.DateTime> литералы. Например, следующий код Visual Basic создает <xref:System.DateTimeOffset> объекта.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Как показано в выходных данных консоли, <xref:System.DateTimeOffset> созданные таким образом присваивается смещение локального часового пояса. Это означает, что <xref:System.DateTimeOffset> значение с помощью знакового литерала не определяет точки времени, если код выполняется на разных компьютерах.

## <a name="datetimeoffset-constructors"></a>Конструкторы DateTimeOffset

<xref:System.DateTimeOffset> Определено шесть конструкторов. Четыре из них непосредственно соответствуют <xref:System.DateTime> конструкторы, с дополнительным параметром типа <xref:System.TimeSpan> , определяющий дату и время смещение от UTC. Они позволяют определить <xref:System.DateTimeOffset> значение на основе значения из его отдельных компонентов даты и времени. Например, следующий код использует эти четыре конструктора для создания экземпляра <xref:System.DateTimeOffset> объектов с одинаковыми значениями 7/1/2008 Полудню: 05 + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Обратите внимание, что, когда значение <xref:System.DateTimeOffset> объект, созданный с помощью <xref:System.Globalization.PersianCalendar> объект как один из аргументов конструктора отображается в консоль, он выражается как дата по григорианскому календарю, а не по иранскому. Для вывода даты по персидскому календарю, см. пример в <xref:System.Globalization.PersianCalendar> разделе.

Два других конструктора создают <xref:System.DateTimeOffset> объекта из <xref:System.DateTime> значение. Первый из них имеет один параметр, <xref:System.DateTime> значение для преобразования в <xref:System.DateTimeOffset> значение. Смещение результирующего <xref:System.DateTimeOffset> значение зависит от <xref:System.DateTime.Kind%2A> свойство единственного параметра конструктора. Если его значение равно <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, смещение приравнивается к <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. В противном случае его смещение приравнивается к смещению местного часового пояса. Следующий пример иллюстрирует использование этого конструктора для создания <xref:System.DateTimeOffset> объектов, представляющих UTC и местный часовой пояс:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Вызов перегрузки <xref:System.DateTimeOffset> конструктор, который имеет один <xref:System.DateTime> параметр эквивалентен выполнению неявного преобразования из <xref:System.DateTime> значение <xref:System.DateTimeOffset> значение.

Второй конструктор, создающий <xref:System.DateTimeOffset> объекта из <xref:System.DateTime> значение имеет два параметра: <xref:System.DateTime> значение для преобразования и <xref:System.TimeSpan> значение, представляющее дату и время смещение от UTC. Это смещение должно соответствовать <xref:System.DateTime.Kind%2A> свойства первого параметра конструктора или <xref:System.ArgumentException> возникает исключение. Если <xref:System.DateTime.Kind%2A> свойство первый параметр — <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, значение второго параметра должно быть <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Если <xref:System.DateTime.Kind%2A> свойство первый параметр — <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, значение второго параметра должно быть смещение часового пояса локальной системы. Если <xref:System.DateTime.Kind%2A> свойство первый параметр — <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, то смещение может иметь любое допустимое значение. В следующем коде показано, как этот конструктор для преобразования <xref:System.DateTime> для <xref:System.DateTimeOffset> значения.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Неявное преобразование типов

<xref:System.DateTimeOffset> Тип поддерживает одно неявное преобразование: из <xref:System.DateTime> значение <xref:System.DateTimeOffset> значение. (Неявное преобразование типов — это преобразование одного типа в другой, не требующее явного приведения, как в языке C#, или преобразования, как в языке Visual Basic, в ходе которого не теряются данные.) Благодаря этому можно использовать код, аналогичный приведенному ниже.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

Смещение результирующего <xref:System.DateTimeOffset> значение зависит от <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> значение свойства. Если его значение равно <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, смещение приравнивается к <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Если его значение равно <xref:System.DateTimeKind.Local?displayProperty=nameWithType> или <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, смещение приравнивается к смещению локального часового пояса.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Разбор строкового представления даты и времени

<xref:System.DateTimeOffset> Четыре метода, которые позволяют преобразовать строковое представление даты и времени в <xref:System.DateTimeOffset> значение:

* <xref:System.DateTimeOffset.Parse%2A>, который предпринимает попытку преобразовать строковое представление даты и времени в <xref:System.DateTimeOffset> значение и создает исключение, если преобразование завершается неудачей.

* <xref:System.DateTimeOffset.TryParse%2A>, который предпринимает попытку преобразовать строковое представление даты и времени в <xref:System.DateTimeOffset> значения и возвращает `false` при сбое преобразования.

* <xref:System.DateTimeOffset.ParseExact%2A>, который предпринимает попытку преобразовать строковое представление даты и времени в определенном формате в <xref:System.DateTimeOffset> значение. Этот метод создает исключение при сбое преобразования.

* <xref:System.DateTimeOffset.TryParseExact%2A>, который предпринимает попытку преобразовать строковое представление даты и времени в определенном формате в <xref:System.DateTimeOffset> значение. При сбое преобразования метод возвращает значение `false`.

В следующем примере вызова каждого из этих четырех методов преобразования строк для создания экземпляра <xref:System.DateTimeOffset> значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
