---
title: "Оператор For Each для типа &lt;имяТипа&gt; неоднозначен, поскольку тип реализует несколько экземпляров System.Collections.Generic.IEnumerable (Of T) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32096"
  - "bc32096"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32096"
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Оператор For Each для типа &lt;имяТипа&gt; неоднозначен, поскольку тип реализует несколько экземпляров System.Collections.Generic.IEnumerable (Of T)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Оператор `For Each` использует переменную\-итератор, который имеет несколько методов <xref:System.Collections.IEnumerable.GetEnumerator%2A>.  
  
 Переменная\-итератор должна иметь тип, который реализует интерфейс <xref:System.Collections.IEnumerable?displayProperty=fullName> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> из пространств имен `Collections` в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  Класс может реализовывать несколько сконструированных универсальных интерфейсов, используя разные аргументы типа при каждом конструировании.  Если такой класс используется для объявления переменной\-итератора, то эта переменная будет содержать несколько методов <xref:System.Collections.IEnumerable.GetEnumerator%2A>.  В этом случае [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] не сможет выбрать вызываемый метод.  
  
 **Идентификатор ошибки:** BC32096  
  
### Чтобы исправить эту ошибку  
  
-   Используйте оператор [Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [Оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) для приведения типа переменной\-итератора к интерфейсу, в котором определен желаемый метод <xref:System.Collections.IEnumerable.GetEnumerator%2A>.  
  
## См. также  
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)