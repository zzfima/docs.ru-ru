---
title: "Оператор ~ (справочник по C#) | Microsoft Docs"
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
  - "~_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "~ [C#], оператор поразрядного дополнения"
  - "~ - оператор [C#]"
  - "оператор поразрядного дополнения [C#]"
  - "тильда (~) - оператор дополнения до единицы [C#]"
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор ~ (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор `~` выполняет операцию поразрядного дополнения операнда, заключающуюся в инвертировании каждого бита.  Операторы поразрядного дополнения предопределены для типов [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) и [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
> [!NOTE]
>  Символ `~` также используется для объявления деструкторов.  Дополнительные сведения см. в разделе [Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## Заметки  
 Определенные пользователем типы могут перегружать оператор `~` .  Дополнительные сведения см. [оператор](../../../csharp/language-reference/keywords/operator.md).  Операции над целыми типами обычно разрешены в перечислениях.  
  
## Пример  
 [!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md)