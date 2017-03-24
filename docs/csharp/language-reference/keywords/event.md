---
title: "event (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "event"
  - "remove"
  - "event_CSharpKeyword"
  - "add"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "event - ключевое слово [C#]"
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# event (Справочник по C#)
Используйте ключевое слово `event` для объявления события в классе издателя.  
  
## Пример  
 В следующем примере показано как объявить и инициировать событие, использующее <xref:System.EventHandler> в качестве базового типа делегата.  Полный пример кода, демонстрирующий использование универсального типа делегата <xref:System.EventHandler%601>, а также подписку на событие и создание метода обработчика событий см. в разделе [Практическое руководство. Публикация событий, соответствующих рекомендациям .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).  
  
 [!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]  
  
 События это особый тип многоадресных делегатов, которые можно вызвать только из класса или структуры, в которой они объявлены \(класс издателя\).  Если на событие подписаны другие классы или структуры, их методы обработчиков событий будут вызваны когда класс издателя инициирует событие.  Дополнительные сведения и примеры кода см. в разделах [События](../../../csharp/programming-guide/events/index.md) и [Делегаты](../../../csharp/programming-guide/delegates/index.md).  
  
 События можно пометить как [открытые \(public\)](../../../csharp/language-reference/keywords/public.md), [закрытые \(private\)](../../../csharp/language-reference/keywords/private.md), [защищенные \(protected\)](../../../csharp/language-reference/keywords/protected.md), [внутренние \(internal\)](../../../csharp/language-reference/keywords/internal.md) или `protected` `internal`.  Эти модификаторы доступа определяют порядок доступа к классу для пользователей класса.  Дополнительные сведения см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
## Ключевые слова и события  
 К событиям применяются следующие ключевые слова.  
  
|Ключевое слово|Описание|Дополнительные сведения|  
|--------------------|--------------|-----------------------------|  
|[static](../../../csharp/language-reference/keywords/static.md)|Делает событие доступным для вызова в любое время, даже если экземпляр класса отсутствует.|[Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[virtual](../../../csharp/language-reference/keywords/virtual.md)|Позволяет производным классам переопределять поведение события при помощи ключевого слова [override](../../../csharp/language-reference/keywords/override.md).|[Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[sealed](../../../csharp/language-reference/keywords/sealed.md)|Указывает, что для производных классов событие более не является виртуальным.||  
|[abstract](../../../csharp/language-reference/keywords/abstract.md)|Компилятор не создаст блоки методов доступа к событиям `add` и `remove` и, следовательно, производные классы должны предоставлять собственную реализацию.||  
  
 Событие можно объявить как статическое событие при помощи ключевого слова [static](../../../csharp/language-reference/keywords/static.md).  При этом событие становится доступным для вызова в любое время, даже если экземпляр класса отсутствует.  Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Событие может быть помечено как виртуальное событие при помощи ключевого слова [virtual](../../../csharp/language-reference/keywords/virtual.md).  Это позволяет производным классам переопределять поведение события при помощи ключевого слова [override](../../../csharp/language-reference/keywords/override.md).  Дополнительные сведения см. в разделе [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  Событие, переопределяющее виртуальное событие, может также быть [sealed](../../../csharp/language-reference/keywords/sealed.md), что определяет, что для производных классов оно более не является виртуальным.  И наконец, событие можно объявить как [abstract](../../../csharp/language-reference/keywords/abstract.md), что означает, что компилятор не создаст блоки методов доступа к событию `add` и `remove`.  Таким образом, производные классы должны предоставлять собственную реализацию.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [добавить](../../../csharp/language-reference/keywords/add.md)   
 [удалить](../../../csharp/language-reference/keywords/remove.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [Практическое руководство. Объединение делегатов \(многоадресные делегаты\)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)