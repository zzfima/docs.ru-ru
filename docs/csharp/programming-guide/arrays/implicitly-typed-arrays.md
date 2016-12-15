---
title: "Неявно типизированные массивы (Руководство по программированию на C#) | Microsoft Docs"
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
  - "массивы [C#], неявно типизированный"
  - "C# - язык, неявно типизированные массивы"
  - "неявно типизированные массивы [C#]"
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Неявно типизированные массивы (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Можно создать неявно типизированный массив, в котором тип экземпляра массива получается из элементов, указанных в инициализаторе массива.  Правила для неявно типизированной переменной также применяются к неявно типизированным массивам.  Дополнительные сведения см. в разделе [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
 Неявно типизированные массивы обычно используются в выражениях запроса вместе с анонимными типами и инициализаторами объектов и коллекций.  
  
 В следующих примерах показано, как создать неявно типизированный массив:  
  
 [!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]  
  
 В предыдущем примере обратите внимание на то, что для неявно типизированных массивов квадратные скобки в левой части оператора инициализации не используются.  Кроме того, следует обратить внимание на то, что инициализация массивов массивов, как и одномерных массивов, выполняется с помощью `new []`.  
  
## Неявно типизированные массивы в инициализаторах объектов  
 При создании анонимного типа, содержащего массив, этот массив неявно типизируется в инициализаторе объекта типа.  В следующем примере `contacts` является неявно типизированным массивом анонимных типов, каждый из которых содержит массив с именем `PhoneNumbers`.  Обратите внимание на то, что ключевое слово `var` внутри инициализаторов объектов не используется.  
  
 [!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)