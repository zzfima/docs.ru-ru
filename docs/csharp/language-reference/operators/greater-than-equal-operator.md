---
title: "Оператор &gt;= (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">= - оператор [C#]"
  - "больше или равно - оператор (>=) [C#]"
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Оператор &gt;= (справочник по C#)
Во всех числовых типах и типах перечислений определен оператор сравнения "больше или равно" \(`>=`\), который возвращает значение `true`, если первый операнд больше или равен второму, в противном случае возвращается значение `false`.  
  
## Заметки  
 Типы, определенные пользователем, могут вызвать перегрузку оператора `>=`.  Дополнительные сведения см. [оператор](../../../csharp/language-reference/keywords/operator.md).  Если оператор `>=` перегружен, то оператор [\<\=](../../../csharp/language-reference/operators/less-than-equal-operator.md) тоже должен быть перегружен.  Операции над целыми типами обычно разрешены в перечислениях.  
  
## Пример  
 [!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)