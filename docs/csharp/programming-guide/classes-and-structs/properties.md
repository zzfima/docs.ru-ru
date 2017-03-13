---
title: "Свойства (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.properties"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, свойства"
  - "свойства [C#]"
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
caps.latest.revision: 38
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 38
---
# Свойства (Руководство по программированию в C#)
Свойство — это член, предоставляющий гибкий механизм для чтения, записи или вычисления значения частного поля.  Свойства можно использовать, как если бы они были членами общих данных, но фактически они представляют собой специальные методы, называемые *методами доступа*.  Это позволяет легко получать доступ к данным и помогает повысить безопасность и гибкость методов.  
  
 В этом примере класс `TimePeriod` хранит период времени.  Внутри класса время хранится в секундах, но свойство с именем `Hours` позволяет клиенту указать время в часах.  Методы доступа для свойства `Hours` выполняют преобразование между часами и секундами.  
  
## Пример  
 [!code-cs[csProgGuideProperties#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/properties_1.cs)]  
  
## Определения текста выражений  
 Обычно используются свойства, которые просто немедленно возвращаются с результатом выражения.  Существует сокращенный синтаксис для определения таких свойств с использованием `=>`:  
  
```c#  
public string Name => First + " " + Last;   
```  
  
 Свойства должны быть доступны только для чтения, и вы не должны использовать ключевое слово метода доступа `get`.  
  
## Общие сведения о свойствах  
  
-   Свойства позволяют классу предоставлять общий способ получения и задания значений, скрывая при этом код реализации или проверки.  
  
-   Метод доступа [get](../../../csharp/language-reference/keywords/get.md) используется для возврата значения свойства, а метод доступа [set](../../../csharp/language-reference/keywords/set.md) — для присвоения нового значения.  Эти методы доступа могут иметь различные уровни доступа.  Дополнительные сведения см. в разделе [Ограничение доступности методов доступа](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
-   Ключевое слово [value](../../../csharp/language-reference/keywords/value.md) используется для определения значения, присваиваемого методом доступа `set`.  
  
-   Свойства, которые не реализуют метод доступа `set`, предназначены только для чтения.  
  
-   Для простых свойств, которым не требуется пользовательский код метода доступа, рассмотрите возможность использования автоматически реализуемых свойств.  Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## Связанные разделы  
  
-   [Использование свойств](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [Свойства интерфейса](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [Сравнение свойств и индексаторов](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Ограничение доступности методов доступа](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
-   [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Использование свойств](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)