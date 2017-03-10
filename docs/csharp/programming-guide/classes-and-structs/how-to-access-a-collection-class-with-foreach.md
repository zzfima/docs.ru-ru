---
title: "Практическое руководство. Доступ к классу коллекции с помощью оператора foreach (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "классы коллекций [C#], foreach - оператор"
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Практическое руководство. Доступ к классу коллекции с помощью оператора foreach (Руководство по программированию в C#)
В следующем примере кода показано, как записать неуниверсальный класс коллекции, который можно использовать с оператором [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  В этом примере определяется класс строкового лексического анализатора.  
  
> [!NOTE]
>  Этот пример представляет рекомендованный способ, только если использование универсального класса коллекции невозможно.  Для примера реализации типобезопасного универсального класса коллекции, поддерживающего тип <xref:System.Collections.Generic.IEnumerable%601>, см. раздел [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
 В примере следующий сегмент кода использует класс `Tokens` для разделения предложения "Это предложение\-образец." на токены с помощью разделителей " " и "\-".  Затем код отображает эти токены с помощью оператора `foreach`.  
  
 [!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-access-a-collecti_1.cs)]  
  
## Пример  
 По сути, класс `Tokens` использует массив для хранения токенов.  Поскольку массивы реализуют типы <xref:System.Collections.IEnumerator> и <xref:System.Collections.IEnumerable>, пример кода может использовать методы перечисления массивов \(<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> и <xref:System.Collections.IEnumerator.Current%2A>\) вместо определения их в классе `Tokens`.  Определения методов содержатся в примере для уточнения способа их определения и предназначения каждого из них.  
  
 [!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-access-a-collecti_2.cs)]  
  
 В языке C\# классу коллекции необязательно реализовывать <xref:System.Collections.IEnumerable> и <xref:System.Collections.IEnumerator> для совместимости с `foreach`.  Если в классе содержатся обязательные члены <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> и <xref:System.Collections.IEnumerator.Current%2A>, он будет работать с оператором `foreach`.  Пропуск интерфейсов имеет преимущество, поскольку позволяет определить тип возврата для `Current`, который более специфичен, чем тип <xref:System.Object>.  Это повышает типобезопасность.  
  
 Например, измените следующие строки в предыдущем примере.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Поскольку `Current` возвращает строку, компилятор может определить, когда используется несовместимый тип в операторе `foreach`, как показано в следующем примере.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Недостатком пропуска типов <xref:System.Collections.IEnumerable> и <xref:System.Collections.IEnumerator> является то, что класс коллекции больше не может взаимодействовать с операторами `foreach` или эквивалентными операторами из других языков среды CLR.  
  
## См. также  
 <xref:System.Collections.Generic>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Коллекции](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)