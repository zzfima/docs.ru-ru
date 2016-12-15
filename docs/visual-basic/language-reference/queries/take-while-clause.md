---
title: "Предложение Take While (Visual Basic) | Microsoft Docs"
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
  - "vb.QueryTakeWhile"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "запросы [Visual Basic], Take While"
  - "Take While - предложение"
  - "Take While - оператор"
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Предложение Take While (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Включает элементы в коллекцию, пока заданное условие является `true`, и затем пропускает оставшиеся элементы.  
  
## Синтаксис  
  
```  
Take While expression  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`expression`|Обязательный.  Выражение, представляющее условие для проверки элементов.  Выражение должно возвращать значение `Boolean` или функциональный эквивалент, например `Integer`, обрабатываемый как `Boolean`.|  
  
## Заметки  
 Предложение `Take While` включает элементы от начала результата запроса до тех пор, пока предоставленное `expression` не вернет `false`.  После того, как `expression` вернет `false`, будут пропущены все оставшиеся элементы в запросе.  `expression` игнорируется для оставшихся результатов.  
  
 Предложение `Take While` отличается от предложения `Where` тем, что предложение `Where` может быть использовано, чтобы включить все элементы из запроса, удовлетворяющие определенному условию.  Предложение `Take While` включает элементы только до тех пор, пока условие будет ложным в первый раз.  Предложение `Take While` наиболее полезно при работе с упорядоченным результатом запроса.  
  
## Пример  
 В следующем примере кода используется предложение `Take While` для получения результатов, пока не будет найден первый клиент без заказов.  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)   
 [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Предложение Where](../../../visual-basic/language-reference/queries/where-clause.md)