---
title: "Оператор = (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "= - оператор [C#]"
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Оператор = (Справочник по C#)
Оператор назначения \(`=`\) сохраняет значение своего правого операнда в месте хранения, свойстве или индексаторе, обозначенном в левом операнде, и в результате возвращает значение.  Операнды должны быть одного типа \(или правый операнд должен допускать явное преобразование в тип левого операнда\).  
  
## Заметки  
 Оператор назначения перегрузить нельзя.  Однако можно определить неявные операторы преобразования для типа, которые позволят использовать оператор назначения с этими типами.  Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## Пример  
 [!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#49)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)