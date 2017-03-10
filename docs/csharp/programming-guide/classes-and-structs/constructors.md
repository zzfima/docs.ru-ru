---
title: "Конструкторы (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "конструкторы [C#]"
  - "классы [C#], конструкторы"
  - "язык C#, конструкторы"
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Конструкторы (Руководство по программированию на C#)
Каждый раз, когда создается [класс](../../../csharp/language-reference/keywords/class.md) или [структура](../../../csharp/language-reference/keywords/struct.md), вызывается конструктор.  Класс или структура может иметь несколько конструкторов, принимающих различные аргументы.  Конструкторы позволяют программисту задавать значения по умолчанию, ограничивать число установок и писать код, который является гибким и удобным для чтения.  Дополнительные сведения и примеры см. в разделах [Использование конструкторов](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) и [Конструкторы экземпляров](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  
  
 Если не предоставить конструктор для объекта, C\# создаст конструктор по умолчанию, который создаст экземпляр объекта и задаст переменным\-членам значения по умолчанию, перечисленные в [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  Дополнительные сведения и примеры см. в разделе [Конструкторы экземпляров](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  
  
 Статические классы и структуры также могут иметь конструкторы.  Дополнительные сведения и примеры см. в разделе [Статические конструкторы](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## Содержание  
 [Использование конструкторов](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [Конструкторы экземпляров](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [Закрытые конструкторы](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [Статические конструкторы](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [Практическое руководство. Создание конструктора копий](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [статический](../../../csharp/language-reference/keywords/static.md)   
 [Почему инициализаторы выполняются в противоположном порядке в качестве конструкторов? Часть 1](http://go.microsoft.com/fwlink/?LinkId=112374)