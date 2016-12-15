---
title: "Практическое руководство. Обработка значений NULL в выражениях запросов (Руководство по программированию в C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "значения null [LINQ в C#]"
  - "запросы [LINQ в C#], значения null"
  - "выражения запросов [LINQ в C#], значения null"
ms.assetid: cb34f7a1-7ef5-466a-90ba-91da30ab525d
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Обработка значений NULL в выражениях запросов (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом примере показана обработка значений NULL, которые могут встретиться в исходной коллекции.  Коллекция объектов, например <xref:System.Collections.Generic.IEnumerable%601>, может содержать элементы, значение которых равно [NULL](../../../csharp/language-reference/keywords/null.md).  Если исходная коллекция равняется NULL или содержит элемент, значение которого равно NULL, а запрос не обрабатывает значения NULL, то при выполнении запроса возникнет исключение <xref:System.NullReferenceException>.  
  
## Пример  
 В код можно включить механизм защиты, позволяющий избежать появления ссылок на значения NULL, как показано в следующем примере.  
  
 [!code-cs[csProgGuideLINQ#82](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 В приведенном выше примере предложение `where` позволяет отфильтровать все элементы NULL в последовательности категорий.  Такой подход не зависит от проверки на значения NULL в предложении join.  Условное выражение в этом примере работает потому, что значение `Products.CategoryID` имеет тип `int?` что является сокращенной записью для `Nullable<int>`.  
  
## Пример  
 Если в предложении join только один из ключей сравнения имеет тип значения, допускающий значения NULL, можно привести второй ключ в выражении запроса к типу, допускающему значение NULL.  В следующем примере предполагается, что `EmployeeID` — столбец значений типа `int?`:  
  
 [!code-cs[csProgGuideLINQ#83](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## См. также  
 <xref:System.Nullable%601>   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)