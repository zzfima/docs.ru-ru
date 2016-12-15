---
title: "Оператор &lt;= (Справочник по C#) | Microsoft Docs"
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
  - "<=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<= - оператор [C#]"
  - "меньше или равно - оператор (<=) [C#]"
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор &lt;= (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Все числовые типы и типы перечисления определяют оператор сравнения "меньше или равно" \(`<=`\), который возвращает значение `true`, если первый операнд меньше или равен второму, в противном случае возвращается значение `false` otherwise.  
  
## Заметки  
 Типы определенные пользователем могут вызвать перегрузку оператора `<=`.  Дополнительные сведения см. [оператор](../../../csharp/language-reference/keywords/operator.md).  Если `<=` перегружен, [\>\=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) тоже должен быть перегружен.  Операции над целыми типами обычно разрешены в перечислениях.  
  
## Пример  
 [!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [явные](../../../csharp/language-reference/keywords/explicit.md)