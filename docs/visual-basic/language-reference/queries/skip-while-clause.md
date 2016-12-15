---
title: "Предложение Skip While (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.QuerySkipWhile"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "запросы [Visual Basic], Skip While"
  - "Skip While - предложение"
  - "Skip While - оператор"
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Предложение Skip While (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Пропускает элементы в коллекции, пока заданное условие является `true` и затем возвращает оставшиеся элементы.  
  
## Синтаксис  
  
```  
Skip While expression  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`expression`|Обязательный.  Выражение, представляющее условие для проверки элементов.  Выражение должно возвращать значение `Boolean` или функциональный эквивалент, например `Integer`, обрабатываемый как `Boolean`.|  
  
## Заметки  
 Предложение `Skip While` обходит элементы от начала результата запроса до тех пор, пока `expression` не вернет `false`.  После возврата `expression` значения `false`, запрос возвращает все оставшиеся элементы.  `expression` игнорируется для оставшихся результатов.  
  
 Предложение `Skip While` отличается от предложения `Where` тем, что предложение `Where` может быть использовано для исключения из запроса всех элементов, которые не удовлетворяют определенному условию.  Предложение `Skip While` исключает элементы только до тех пор, пока условие не будет выполнено в первый раз.  Предложение `Skip While` наиболее полезно при работе с упорядоченным результатом запроса.  
  
 Можно пропустить определенное количество результатов в начале результата запроса с помощью предложения `Skip`.  
  
## Пример  
 В следующем примере кода предложение `Skip While` используется для обхода результатов до первого заказчика, который находится в США.  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Skip](../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)   
 [Предложение Where](../../../visual-basic/language-reference/queries/where-clause.md)