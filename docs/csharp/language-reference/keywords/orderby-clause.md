---
title: "Предложение orderby (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "orderby"
  - "orderby_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "orderby - предложение [C#]"
  - "orderby - ключевое слово [C#]"
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Предложение orderby (Справочник по C#)
В выражении запроса предложение `orderby` осуществляет сортировку возвращенной последовательности по возрастанию или по убыванию.  Для выполнения одной или нескольких операций последующей сортировки можно указать несколько ключей.  Сортировка выполняется функцией сравнения по умолчанию для данного типа элементов.  По умолчанию используется порядок сортировки по возрастанию.  Можно также указать пользовательскую функцию по умолчанию.  Это возможно только с помощью синтаксиса на основе методов.  Дополнительные сведения см. в разделе [Sorting Data](../../../visual-basic/programming-guide/concepts/linq/sorting-data.md).  
  
## Пример  
 В следующем примере первый запрос сортирует слова в алфавитном порядке по возрастанию \(начиная с буквы А\), а второй запрос сортирует эти же слова по убыванию.  \(Ключевое слово `ascending` является значением сортировки по умолчанию, поэтому его использовать не обязательно.\)  
  
 [!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Orderby.cs#20)]  
  
## Пример  
 В следующем примере первая сортировка выполняется по фамилиям учащихся, а вторая — по их именам.  
  
 [!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Orderby.cs#22)]  
  
## Заметки  
 Во время компиляции предложение `orderby` преобразуются в вызов метода <xref:System.Linq.Enumerable.OrderBy%2A>.  Ключи в предложении `orderby` преобразуются в вызовы метода <xref:System.Linq.Enumerable.ThenBy%2A>.  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Ключевые слова запроса \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Предложение group](../../../csharp/language-reference/keywords/group-clause.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)