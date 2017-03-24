---
title: "into (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "into_CSharpKeyword"
  - "into"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "into - ключевое слово [C#]"
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# into (Справочник по C#)
Контекстно\-зависимое ключевое слово `into` можно использовать для создания временного идентификатора с целью сохранения результатов предложения [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) или [select](../../../csharp/language-reference/keywords/select-clause.md) в новом идентификаторе.  Этот идентификатор может стать источником дополнительных команд запросов.  Использование нового идентификатора в предложении `group` или `select` иногда называют *продолжением*.  
  
## Пример  
 В приведенном ниже примере показано использование ключевого слова `into` для разрешения временного идентификатора `fruitGroup`, имеющего выведенный тип `IGrouping`.  Используя этот идентификатор, можно вызвать метод <xref:System.Linq.Enumerable.Count%2A> для каждой группы и выбрать только те группы, которые содержат два и более слова.  
  
 [!code-cs[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]  
  
 Использование ключевого слова `into` в предложении `group` необходимо только в том случае, если нужно выполнить дополнительные операции запроса для каждой группы.  Дополнительные сведения см. в разделе [Предложение group](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Пример использования ключевого слова `into` в предложении `join` см. в разделе [Предложение join](../../../csharp/language-reference/keywords/join-clause.md).  
  
## См. также  
 [Ключевые слова запроса \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Предложение group](../../../csharp/language-reference/keywords/group-clause.md)