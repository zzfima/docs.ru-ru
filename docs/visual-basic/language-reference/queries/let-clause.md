---
title: "Предложение Let (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryLet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Let - предложение"
  - "Let - оператор"
  - "запросы [Visual Basic], Let"
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Предложение Let (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Вычисляет значение и присваивает его новой переменной внутри запроса.  
  
## Синтаксис  
  
```  
Let variable = expression [, ...]  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`variable`|Обязательный.  Псевдоним, который может использоваться для ссылки на результаты предоставленного выражения.|  
|`expression`|Обязательный.  Выражение, которое будет вычислено и присвоено указанной переменной.|  
  
## Заметки  
 Условие `Let` позволяет вычислить значения для каждого результата запроса и ссылаться на них с помощью псевдонима.  Псевдоним может использоваться в других условиях, таких как условие `Where`.  Условие `Let` позволяет создать оператор запроса, который проще прочесть, поскольку можно указать псевдоним для условия выражения, включенного в запрос, и заменять этот псевдоним при каждом использовании условия выражения.  
  
 Можно включить любое количество `variable` и назначений `expression` в условие `Let`.  Разделяйте каждое назначения запятой \(,\).  
  
## Пример  
 В следующем примере кода используется условие `Let` для вычисления 10% скидки на продукты.  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#16)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Where](../../../visual-basic/language-reference/queries/where-clause.md)