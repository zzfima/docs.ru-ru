---
title: "Предложение let (справочник по C#) | Microsoft Docs"
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
  - "let_CSharpKeyword"
  - "let"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "let - предложение [C#]"
  - "let - ключевое слово [C#]"
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Предложение let (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В выражении запроса иногда полезно сохранить результат выполнения какой\-то составной части выражения, чтобы использовать его в последующих предложениях.  Это можно выполнить с помощью ключевого слова `let`, создающего новую переменную диапазона и инициализирующего ее результатом предоставленного выражения.  После инициализации значением переменная диапазона не может использоваться для хранения другого значения.  Однако, если в переменной диапазона хранится запрашиваемый тип, то его можно запросить.  
  
## Пример  
 В следующем примере ключевое слово `let` используется двумя способами:  
  
1.  Для создания перечислимого типа, который сам может запрашиваться.  
  
2.  Для обеспечения возможности запросу вызывать метод `ToLower` для переменной диапазона `word` только один раз.  Без ключевого слова `let` метод `ToLower` пришлось бы вызвать в каждом предикате предложения `where`.  
  
 [!code-cs[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Ключевые слова запроса \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Практическое руководство. Обработка исключений в выражениях запросов](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)