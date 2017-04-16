---
title: "Создание экземпляра объекта DateTimeOffset | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "создание экземпляров объектов часовых поясов"
  - "объекты часовых поясов [платформа .NET Framework], создание экземпляров"
  - "структура DateTimeOffset, преобразование к типу DateTime"
  - "структура DateTimeOffset, создание экземпляров"
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Создание экземпляра объекта DateTimeOffset
В структуре <xref:System.DateTimeOffset> есть несколько способов создания новых значений <xref:System.DateTimeOffset>.  Многие из них непосредственно соответствуют методам создания новых значений класса <xref:System.DateTime>; отличающие их усовершенствования позволяют указывать смещение значения даты и времени относительно универсального синхронизированного времени \(UTC\).  В частности, экземпляр значения <xref:System.DateTimeOffset> можно создать следующими способами.  
  
-   Используя литерал даты и времени.  
  
-   Вызвав конструктор <xref:System.DateTimeOffset>.  
  
-   Неявным преобразованием в значение типа <xref:System.DateTimeOffset>.  
  
-   Разбором строкового представления даты и времени.  
  
 В этом разделе приводятся более подробные сведения и примеры кода, призванные иллюстрировать данные методы создания новых значений типа <xref:System.DateTimeOffset>.  
  
## Литералы даты и времени  
 Одним из наиболее распространенных способов создания экземпляров значений <xref:System.DateTime> в языках, допускающих такую возможность, является представление даты и времени в виде жестко заданного литерала.  Например, в следующем коде на языке Visual Basic создается объект <xref:System.DateTime>, значение которого соответствует 1 января 2008 г., 10:00.  
  
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]  
  
 При использовании языков, поддерживающих литералы типа <xref:System.DateTime>, значения <xref:System.DateTimeOffset> также могут инициализироваться с помощью литералов даты и времени.  Например, в следующем коде на языке Visual Basic создается объект <xref:System.DateTimeOffset>.  
  
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]  
  
 По результату, выведенному на консоль, видно, что созданному таким способом значению <xref:System.DateTimeOffset> присваивается смещение локального часового пояса.  Отсюда следует, что значение <xref:System.DateTimeOffset>, заданное с помощью знакового литерала, не будет определять один и тот же момент времени при выполнении кода на разных компьютерах.  
  
## Конструкторы DateTimeOffset  
 В классе <xref:System.DateTimeOffset> определено шесть конструкторов.  Четыре из них непосредственно соответствуют конструкторам <xref:System.DateTime>, отличаясь от них дополнительным параметром типа <xref:System.TimeSpan>, который задает смещение даты и времени относительно времени UTC.  Они позволяют определить значение <xref:System.DateTimeOffset> на основе значений отдельных компонентов даты и времени.  К примеру, в следующем коде эти четыре конструктора используются для создания объектов <xref:System.DateTimeOffset> с одинаковыми значениями 01.07.2008, 12:05 \+01:00.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]  
  
 Обратите внимание, что при инициализации значения объекта <xref:System.DateTimeOffset> путем передачи в качестве одного из аргументов конструктора объекта <xref:System.Globalization.PersianCalendar> при последующем выводе значения на консоль дата выражается по григорианскому календарю, а не по иранскому.  Пример вывода даты, выраженной по иранскому календарю, см. в разделе <xref:System.Globalization.PersianCalendar>.  
  
 Два других конструктора создают объект <xref:System.DateTimeOffset> по значению <xref:System.DateTime>.  Единственный параметр первого из них — это значение <xref:System.DateTime>, преобразуемое в значение типа <xref:System.DateTimeOffset>.  Смещение результирующего значения <xref:System.DateTimeOffset> зависит от свойства <xref:System.DateTime.Kind%2A> единственного параметра конструктора.  Если его значение равно <xref:System.DateTimeKind?displayProperty=fullName>, то смещение приравнивается к <xref:System.TimeSpan.Zero?displayProperty=fullName>.  В противном случае его смещение приравнивается к смещению местного часового пояса.  В следующем примере приведен пример использования этого конструктора для создания объектов <xref:System.DateTimeOffset>, представляющих UTC и местный часовой пояс:  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]  
  
> [!NOTE]
>  Вызов перегрузки конструктора <xref:System.DateTimeOffset>, принимающей одиночный параметр <xref:System.DateTime>, эквивалентен выполнению неявного преобразования значения типа <xref:System.DateTime> в значение типа <xref:System.DateTimeOffset>.  
  
 Второй конструктор, создающий объект класса <xref:System.DateTimeOffset> по значению <xref:System.DateTime>, имеет два параметра: преобразуемое значение <xref:System.DateTime> и значение <xref:System.TimeSpan>, задающее смещение даты и времени относительно UTC.  Это смещение должно соответствовать свойству <xref:System.DateTime.Kind%2A> первого параметра конструктора — в противном случае будет создано исключение <xref:System.ArgumentException>.  Если свойство <xref:System.DateTime.Kind%2A> первого параметра имеет значение <xref:System.DateTimeKind?displayProperty=fullName>, то значение второго параметра должно быть равно <xref:System.TimeSpan.Zero?displayProperty=fullName>.  Если свойство <xref:System.DateTime.Kind%2A> первого параметра имеет значение <xref:System.DateTimeKind?displayProperty=fullName>, то значение второго параметра должно быть равно смещению локального часового пояса.  Если свойство <xref:System.DateTime.Kind%2A> первого параметра имеет значение <xref:System.DateTimeKind?displayProperty=fullName>, то смещение может иметь произвольное допустимое значение.  В следующем коде показано, как этот конструктор позволяет преобразовывать значения <xref:System.DateTime> в значения <xref:System.DateTimeOffset>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]  
  
## Неявное преобразование типов  
 Тип <xref:System.DateTimeOffset> поддерживает только одно неявное преобразование: из значения типа <xref:System.DateTime> в значение типа <xref:System.DateTimeOffset>. \(неявное преобразование типов \- это преобразование одного типа в другой, не требующее явного приведения, как в языке C\#, или преобразования, как в языке Visual Basic, в ходе которого не теряются данные\).  Благодаря этому можно использовать код, аналогичный приведенному ниже.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]  
  
 Смещение результирующего объекта <xref:System.DateTimeOffset> зависит от значения свойства <xref:System.DateTime.Kind%2A?displayProperty=fullName>.  Если его значение равно <xref:System.DateTimeKind?displayProperty=fullName>, то смещение приравнивается к <xref:System.TimeSpan.Zero?displayProperty=fullName>.  Если его значение равно <xref:System.DateTimeKind?displayProperty=fullName> или <xref:System.DateTimeKind?displayProperty=fullName>, то смещение приравнивается к смещению местного часового пояса.  
  
## Разбор строкового представления даты и времени  
 В классе <xref:System.DateTimeOffset> присутствует четыре метода, позволяющих преобразовывать строковое представление даты и времени в значение типа <xref:System.DateTimeOffset>:  
  
-   Метод <xref:System.DateTimeOffset.Parse%2A>, который пытается преобразовать строковое представление даты и времени в значение <xref:System.DateTimeOffset> и создает исключение при сбое преобразования.  
  
-   Метод <xref:System.DateTimeOffset.TryParse%2A>, который предпринимает попытку преобразовать строковое представление даты и времени в значение <xref:System.DateTimeOffset> и возвращает `false` при сбое преобразования.  
  
-   Метод <xref:System.DateTimeOffset.ParseExact%2A>, который предпринимает попытку преобразовать строковое представление даты и времени в определенном формате в значение <xref:System.DateTimeOffset>.  Этот метод создает исключение при сбое преобразования.  
  
-   Метод <xref:System.DateTimeOffset.TryParseExact%2A>, который предпринимает попытку преобразовать строковое представление даты и времени в определенном формате в значение <xref:System.DateTimeOffset>.  При сбое преобразования метод возвращает значение `false`.  
  
 В следующем коде приведены примеры вызова каждого из этих четырех методов преобразования строк, формирующие значения типа <xref:System.DateTimeOffset>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]  
  
## См. также  
 [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)