---
title: "Универсальные интерфейсы. (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, универсальные интерфейсы"
  - "универсальные шаблоны [C#], интерфейсы"
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Универсальные интерфейсы. (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Часто рекомендуется определять интерфейсы либо для универсальных классов коллекций, либо для универсальных классов, представляющих элементы в коллекции.  Приоритетным методом для универсальных классов является использование универсальных интерфейсов, таких как <xref:System.IComparable%601>, а не <xref:System.IComparable>, что позволяет избежать операций упаковки\-распаковки над типами значений.  Библиотека классов .NET Framework определяет несколько универсальных интерфейсов для использования с классами коллекций в пространстве имен <xref:System.Collections.Generic>.  
  
 Если интерфейс указан в качестве ограничения параметра типа, могут использоваться лишь типы, реализующие интерфейс.  В следующем примере кода показан класс `SortedList<T>`, который является производным от класса `GenericList<T>`.  Дополнительные сведения см. в разделе [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md).  `SortedList<T>` добавляет ограничение `where T : IComparable<T>`.  Это позволяет методу `BubbleSort` в `SortedList<T>` использовать универсальный метод <xref:System.IComparable%601.CompareTo%2A> в элементах списка.  В следующем примере элементы списка являются простым классом, `Person`, реализующим `IComparable<Person>`.  
  
 [!code-cs[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]  
  
 В качестве ограничений для одного типа можно указать несколько интерфейсов. Это выполняется следующим образом.  
  
 [!code-cs[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]  
  
 Интерфейс может определить несколько параметров типа, как показано далее.  
  
 [!code-cs[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]  
  
 Правила наследования, которые применяются для классов, применимы и к интерфейсам.  
  
 [!code-cs[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]  
  
 Универсальные интерфейсы могут наследовать от неуниверсальных, если первый тип интерфейсов является контравариантным, что означает использование его параметра типа в качестве возвращаемого значения.  В библиотеке классов .NET Framework <xref:System.Collections.Generic.IEnumerable%601> наследует от <xref:System.Collections.IEnumerable>, поскольку <xref:System.Collections.Generic.IEnumerable%601> использует только `T` в возвращаемом значении <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> и в методе считывания <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.  
  
 Конкретные классы могут реализовать закрытые конструируемые интерфейсы следующим образом.  
  
 [!code-cs[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]  
  
 Универсальные классы могут реализовать универсальные интерфейсы или закрытые конструируемые интерфейсы, если список параметров класса предоставляет все необходимые для интерфейса аргументы. Это выполняется следующим образом.  
  
 [!code-cs[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]  
  
 Правила, управляющие перегрузкой методов, совпадают с правилами для методов в универсальных классах, структурах или интерфейсах.  Дополнительные сведения см. в разделе [Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [интерфейс](../../../csharp/language-reference/keywords/interface.md)   
 [Универсальные шаблоны](../Topic/Generics%20in%20the%20.NET%20Framework.md)