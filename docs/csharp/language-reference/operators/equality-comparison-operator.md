---
title: "Оператор == (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "==_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "== - оператор [C#]"
  - "оператор равенства [C#]"
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Оператор == (справочник по C#)
Для предопределенных типов значений оператор равенства \(`==`\) возвращает значение true, если значения его операндов совпадают, в противном случае — значение `false`.  Для ссылочных типов, отличных от [string](../../../csharp/language-reference/keywords/string.md), оператор `==` возвращает значение `true`, если оба его операнда ссылаются на один и тот же объект.  Для типа `string` оператор `==` сравнивает значения строк.  
  
## Заметки  
 Типы значений, определенные пользователем, могут вызвать перегрузку оператора `==` \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Ее могут вызвать и пользовательские ссылочные типы, хотя по умолчанию оператор `==` работает в соответствии с приведенным выше описанием как для предопределенных, так и пользовательских ссылочных типов.  Если оператор `==` перегружен, то оператор [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md) тоже должен быть перегружен.  Операции над целыми типами обычно разрешены в перечислениях.  
  
## Пример  
 [!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#36)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)