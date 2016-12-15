---
title: "Оператор &lt;&lt;= (Справочник по C#) | Microsoft Docs"
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
  - "<<=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<<= - оператор (назначение сдвига влево) [C#]"
  - "оператор назначения сдвига влево (<<=) [C#]"
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор &lt;&lt;= (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор присваивания сдвига влево.  
  
## Заметки  
 Выражение формы  
  
```  
x <<= y  
```  
  
 вычисляется как  
  
```  
x = x << y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  Оператор [\<\<](../../../csharp/language-reference/operators/left-shift-operator.md)сдвигает`x` влево на число бит, указанное в `y`.  
  
 Оператор `<<=` нельзя перегрузить непосредственно, однако пользовательские типы могут перегрузить [оператор \<\<](../../../csharp/language-reference/operators/left-shift-operator.md) \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Пример  
 [!code-cs[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)