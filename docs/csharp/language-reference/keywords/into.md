---
title: "into (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f2400143e66c68942cdec3ebfa04cfdd8cfe983
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="into-c-reference"></a>into (Справочник по C#)
Контекстное слово `into` можно использовать для создания временного идентификатора для сохранения результатов предложений [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) или [select](../../../csharp/language-reference/keywords/select-clause.md) в новый идентификатор. Этот идентификатор может сам по себе стать источником дополнительных команд запроса. При использовании в предложениях `group` или `select` применение нового идентификатора может называться *продолжением*.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование ключевого слова `into` для создания временного идентификатора `fruitGroup`, который имеет выведенный тип `IGrouping`. С помощью идентификатора можно вызвать метод <xref:System.Linq.Enumerable.Count%2A> для каждой группы и выбрать только те группы, которые содержат несколько слов.  
  
 [!code-csharp[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]  
  
 Использование ключевого слова `into` в предложении `group` необходимо только в тех случаях, когда требуется выполнить дополнительные операции запроса для каждой группы. Дополнительные сведения см. в разделе [Предложение group](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Пример использования ключевого слова `into` в предложении `join` см. в разделе [Предложение join](../../../csharp/language-reference/keywords/join-clause.md).  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова запроса (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [предложение group](../../../csharp/language-reference/keywords/group-clause.md)
