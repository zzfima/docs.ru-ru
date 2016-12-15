---
title: "Оператор &lt; (справочник по C#) | Microsoft Docs"
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
  - "<_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "< - оператор [C#]"
  - "меньше - оператор (<) [C#]"
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор &lt; (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Во всех числовых типах и типах перечислений определен оператор сравнения "меньше" \(`<`\), который возвращает значение `true`, если первый операнд меньше второго, в противном случае возвращается значение `false`.  
  
## Заметки  
 Типы, определенные пользователем, могут вызвать перегрузку оператора `<` \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Если оператор `<` перегружен, то оператор [\<](../../../csharp/language-reference/operators/greater-than-operator.md) тоже должен быть перегружен.  Если бинарный оператор перегружен, соответствующий оператор присваивания \(если таковой имеется\), также будет явно перегружен.  
  
## Пример  
 [!code-cs[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)