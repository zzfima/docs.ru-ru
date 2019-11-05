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
ms.openlocfilehash: 1b1178623258393eab28a7087eb04c47b55a9176
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122315"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Создание экземпляра объекта DateTimeOffset

Структура <xref:System.DateTimeOffset> предлагает несколько способов создания новых <xref:System.DateTimeOffset> значений. Многие из них непосредственно соответствуют методам, доступным для создания новых <xref:System.DateTime> значений, с улучшенными возможностями, которые позволяют указать смещение значения даты и времени относительно времени в формате UTC. В частности, можно создать экземпляр <xref:System.DateTimeOffset> значения следующими способами.

- С помощью литерала даты и времени.

- Путем вызова конструктора <xref:System.DateTimeOffset>.

- Путем неявного преобразования значения в <xref:System.DateTimeOffset> значение.

- Разбором строкового представления даты и времени.

В этом разделе приведены более подробные сведения и примеры кода, иллюстрирующие эти методы создания новых <xref:System.DateTimeOffset> значений.

## <a name="date-and-time-literals"></a>Литералы даты и времени

Для языков, поддерживающих эту возможность, одним из наиболее распространенных способов создания экземпляра <xref:System.DateTime> является предоставление даты и времени в виде жестко запрограммированного литерального значения. Например, следующий код Visual Basic создает объект <xref:System.DateTime>, значение которого равно 1 января 2008, в 10:00 AM.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset> значения можно также инициализировать с помощью литералов даты и времени при использовании языков, поддерживающих литералы <xref:System.DateTime>. Например, следующий код Visual Basic создает объект <xref:System.DateTimeOffset>.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Как видно из выходных данных консоли, значение <xref:System.DateTimeOffset>, созданное таким образом, назначается смещению местного часового пояса. Это означает, что значение <xref:System.DateTimeOffset>, назначенное с помощью символьного литерала, не определяет единственный момент времени, если код выполняется на разных компьютерах.

## <a name="datetimeoffset-constructors"></a>Конструкторы DateTimeOffset

Тип <xref:System.DateTimeOffset> определяет шесть конструкторов. Четыре из них непосредственно соответствуют <xref:System.DateTime>ным конструкторам с дополнительным параметром типа <xref:System.TimeSpan>, который определяет смещение даты и времени относительно времени в формате UTC. Они позволяют определить <xref:System.DateTimeOffset> значение на основе значений отдельных компонентов даты и времени. Например, следующий код использует эти четыре конструктора для создания экземпляров <xref:System.DateTimeOffset> объектов с одинаковыми значениями 7/1/2008 12:05 AM + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Обратите внимание, что, когда значение объекта <xref:System.DateTimeOffset>, созданного с помощью объекта <xref:System.Globalization.PersianCalendar> в качестве одного из аргументов конструктора, отображается в консоли, оно выражается как дата в григорианском, а не в персидском календаре. Чтобы вывести дату в персидском календаре, ознакомьтесь с примером в разделе <xref:System.Globalization.PersianCalendar>.

Два других конструктора создают объект <xref:System.DateTimeOffset> из значения <xref:System.DateTime>. Первый из них содержит один параметр, <xref:System.DateTime> значение для преобразования в <xref:System.DateTimeOffset> значение. Смещение результирующего <xref:System.DateTimeOffset>ного значения зависит от свойства <xref:System.DateTime.Kind%2A> единственного параметра конструктора. Если его значение равно <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, то смещение устанавливается равным <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. В противном случае его смещение приравнивается к смещению местного часового пояса. В следующем примере показано использование этого конструктора для создания экземпляра <xref:System.DateTimeOffset> объектов, представляющих время в формате UTC и местный часовой пояс:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Вызов перегрузки конструктора <xref:System.DateTimeOffset> с одним параметром <xref:System.DateTime> эквивалентен выполнению неявного преобразования <xref:System.DateTime> значения в <xref:System.DateTimeOffset> значение.

Второй конструктор, создающий объект <xref:System.DateTimeOffset> из <xref:System.DateTime> значения, имеет два параметра: <xref:System.DateTime> значение для преобразования и значение <xref:System.TimeSpan>, представляющее смещение даты и времени относительно времени в формате UTC. Это значение смещения должно соответствовать свойству <xref:System.DateTime.Kind%2A> первого параметра конструктора или выбрасывается <xref:System.ArgumentException>. Если свойство <xref:System.DateTime.Kind%2A> первого параметра имеет <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, значение второго параметра должно быть <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Если свойство <xref:System.DateTime.Kind%2A> первого параметра имеет <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, значение второго параметра должно быть смещением часового пояса локальной системы. Если свойство <xref:System.DateTime.Kind%2A> первого параметра имеет значение <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, смещение может быть любым допустимым значением. Следующий код иллюстрирует вызов этого конструктора для преобразования <xref:System.DateTime> в значения <xref:System.DateTimeOffset>.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Неявное преобразование типов

Тип <xref:System.DateTimeOffset> поддерживает одно неявное преобразование типов: из значения <xref:System.DateTime> в значение <xref:System.DateTimeOffset>. (Неявное преобразование типов — это преобразование одного типа в другой, не требующее явного приведения, как в языке C#, или преобразования, как в языке Visual Basic, в ходе которого не теряются данные.) Благодаря этому можно использовать код, аналогичный приведенному ниже.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

Смещение результирующего <xref:System.DateTimeOffset>ного значения зависит от значения свойства <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>. Если его значение равно <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, то смещение устанавливается равным <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Если его значение равно <xref:System.DateTimeKind.Local?displayProperty=nameWithType> или <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, то смещение устанавливается равным значению местного часового пояса.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Анализ строкового представления даты и времени

Тип <xref:System.DateTimeOffset> поддерживает четыре метода, позволяющие преобразовать строковое представление даты и времени в <xref:System.DateTimeOffset> значение:

- <xref:System.DateTimeOffset.Parse%2A>, который пытается преобразовать строковое представление даты и времени в <xref:System.DateTimeOffset> значение и создает исключение, если преобразование завершается неудачей.

- <xref:System.DateTimeOffset.TryParse%2A>, который пытается преобразовать строковое представление даты и времени в <xref:System.DateTimeOffset> значение и возвращает `false` в случае сбоя преобразования.

- <xref:System.DateTimeOffset.ParseExact%2A>, который пытается преобразовать строковое представление даты и времени в указанном формате в значение <xref:System.DateTimeOffset>. Этот метод создает исключение при сбое преобразования.

- <xref:System.DateTimeOffset.TryParseExact%2A>, который пытается преобразовать строковое представление даты и времени в указанном формате в значение <xref:System.DateTimeOffset>. При сбое преобразования метод возвращает значение `false`.

В следующем примере показаны вызовы каждого из этих четырех методов преобразования строк для создания экземпляра значения <xref:System.DateTimeOffset>.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
