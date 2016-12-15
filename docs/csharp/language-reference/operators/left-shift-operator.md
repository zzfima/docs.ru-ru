---
title: "Оператор &lt;&lt; (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<<_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<< - оператор [C#]"
  - "оператор сдвига влево (<<) [C#]"
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор &lt;&lt; (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор сдвига влево \(`<<`\) сдвигает первый операнд влево в соответствии с количеством бит, заданным вторым операндом.  Тип второго операнда должен быть [int](../../../csharp/language-reference/keywords/int.md) или тип, имеющий предопределенное неявное числовое преобразование в `int`.  
  
## Заметки  
 Если тип первого операнда — [int](../../../csharp/language-reference/keywords/int.md) или [uint](../../../csharp/language-reference/keywords/uint.md) \(32\-разрядное число\), начало сдвига задается пятью младшими разрядами второго операнда.  Фактический сдвиг от 0 до 31 бит.  
  
 Если тип первого операнда — [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) \(64\-разрядное число\), начало сдвига задается шестью младшими разрядами второго операнда.  Фактический сдвиг от 0 до 63 бит.  
  
 Старшие разряды, которые находятся не в диапазоне тип первого операнда после смены отбрасываются, а пустые младшие разряды заполняются нулями.  Операторы сдвига никогда не вызывают переполнений.  
  
 Определенные пользователем типы могут вызвать перегрузку оператора `<<` \(см.[оператор](../../../csharp/language-reference/keywords/operator.md)\); тип первого операнда должен быть определен пользователем, а тип второго должен быть `int`.  Если бинарный оператор перегружен, соответствующий оператор присваивания \(если таковой имеется\), также будет явно перегружен.  
  
## Пример  
 [!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]  
  
## Комментарии  
 Обратите внимание, что `i<<1` и `i<<33`  дают одинаковый результат, поскольку 1 и 33 имеют те же пять младших разрядов.  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)