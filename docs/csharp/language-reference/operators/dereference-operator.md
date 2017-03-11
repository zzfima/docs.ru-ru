---
title: "Оператор -&gt; (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "->_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-> - оператор [C#]"
  - "оператор доступа к членам (->) [C#]"
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Оператор -&gt; (Справочник по C#)
Оператор `->` объединяет разыменование указателя и доступ к члену.  
  
## Заметки  
 Выражение формы  
  
```  
x->y  
```  
  
 \(где `x` — это указатель типа `T*`, а `y` — это член `T`\) эквивалентно  
  
```  
(*x).y  
```  
  
 Оператор `->` можно использовать только в коде, помеченном как [небезопасный](../../../csharp/language-reference/keywords/unsafe.md).  
  
 Оператор `->` перегрузить нельзя.  
  
## Пример  
 [!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#15)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)