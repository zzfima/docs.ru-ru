---
title: "Оператор &lt;= (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<= - оператор [C#]"
  - "меньше или равно - оператор (<=) [C#]"
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Оператор &lt;= (Справочник по C#)
Все числовые типы и типы перечисления определяют оператор сравнения "меньше или равно" \(`<=`\), который возвращает значение `true`, если первый операнд меньше или равен второму, в противном случае возвращается значение `false` otherwise.  
  
## Заметки  
 Типы определенные пользователем могут вызвать перегрузку оператора `<=`.  Дополнительные сведения см. [оператор](../../../csharp/language-reference/keywords/operator.md).  Если `<=` перегружен, [\>\=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) тоже должен быть перегружен.  Операции над целыми типами обычно разрешены в перечислениях.  
  
## Пример  
 [!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#32)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [явные](../../../csharp/language-reference/keywords/explicit.md)