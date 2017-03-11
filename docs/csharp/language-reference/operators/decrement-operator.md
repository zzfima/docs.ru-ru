---
title: "Оператор -- (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "--_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-- - оператор [C#]"
  - "оператор уменьшения (--) [C#]"
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Оператор -- (Справочник по C#)
Оператор декремента \(`--`\) уменьшает свой операнд на 1.  Оператор декремента может находиться как перед операндом, так и после него: `--variable` или `variable--`.  Первой формой является префиксная операция декремента.  Результатом этой операции является значение операнда после его декремента.  Второй формой является постфиксная операция декремента.  Результатом этой операции является значение операнда до его декремента.  
  
## Заметки  
 Числовые типы и типы перечисления имеют предопределенные операторы декремента.  
  
 Типы, определенные пользователем, могут вызвать перегрузку оператора `--` \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Операции над целыми типами обычно разрешены в перечислениях.  
  
## Пример  
 [!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#8)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)