---
title: "Сравнение свойств и индексаторов (Руководство по программированию в C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "индексаторы [C#], сравнение со свойствами"
  - "свойства [C#], сравнение с индексаторами"
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Сравнение свойств и индексаторов (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Индексаторы подобны свойствам.  За исключением различий, перечисленных в следующей таблице, все правила, определенные для методов доступа к свойствам, применимы и к методам доступа к индексаторам.  
  
|Свойство.|Индексатор|  
|---------------|----------------|  
|Позволяет вызывать методы как открытые элементы данных.|Обеспечивает доступ к элементам внутренней коллекции объекта с помощью представления массива самого объекта.|  
|Доступ посредством простого имени.|Доступ посредством индекса.|  
|Допускаются статические члены или члены экземпляров.|Допускаются только члены экземпляров.|  
|Метод доступа [get](../../../csharp/language-reference/keywords/get.md) свойства не имеет параметров.|Метод доступа `get` индексатора имеет такой же список формальных параметров, как и индексатор.|  
|Метод доступа [set](../../../csharp/language-reference/keywords/set.md) свойства содержит неявный параметр `value`.|Метод доступа `set` индексатора имеет такой же список формальных параметров, как и индексатор, а также параметр [value](../../../csharp/language-reference/keywords/value.md).|  
|Поддерживается сокращенный синтаксис с [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).|Сокращенный синтаксис не поддерживается.|  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)   
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)