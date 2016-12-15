---
title: "Практическое руководство. Доступ к члену с использованием указателя (Руководство по программированию в C#) | Microsoft Docs"
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
  - "указатели [C#], доступ к членам"
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Доступ к члену с использованием указателя (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Для осуществления доступа к члену структуры, объявленной в небезопасном контексте, можно использовать оператор доступа к члену, как показано в следующем примере, где `p` — это указатель на [структуру](../../../csharp/language-reference/keywords/struct.md) содержащую член `x`.  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## Пример  
 В этом примере объявлена [структура](../../../csharp/language-reference/keywords/struct.md) `CoOrds`, содержащая две координаты `x` и `y`, после чего создан ее экземпляр.  С помощью оператора доступа к членам `->` и указателя на экземпляр `home` координатам `x` и `y` присваиваются значения.  
  
> [!NOTE]
>  Обратите внимание, что выражение `p->x` эквивалентно выражению `(*p).x`, и можно получить одинаковый результат, используя любое из этих двух выражений.  
  
 [!code-cs[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]  
  
 [!code-cs[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)