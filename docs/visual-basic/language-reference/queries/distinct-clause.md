---
title: "Предложение Distinct (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryDistinct"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Distinct - предложение"
  - "Distinct - оператор"
  - "запросы [Visual Basic], Distinct"
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Предложение Distinct (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ограничивает значения текущего диапазона переменной, чтобы исключить повторяющиеся значения в предложениях последующих запросов.  
  
## Синтаксис  
  
```  
Distinct  
```  
  
## Заметки  
 Можно использовать предложение `Distinct` для возврата списка уникальных элементов.  Чтобы игнорировать повторяющиеся результаты запроса, используйте предложение `Distinct`.  Предложение `Distinct` применяется к повторяющимся значениям для всех возвращенных полей, заданных предложением `Select`.  Если предложение `Select` не указано, предложение `Distinct` применяется к переменной диапазона для запроса, указанного в предложении `From`.  Если переменная диапазона не имеет постоянного типа, запрос проигнорирует результаты запроса, если все члены типа соответствуют существующим результатам запроса.  
  
## Пример  
 Следующее выражение запроса соединяет список клиентов и заказы клиентов.  Предложение `Distinct` включается для возврата списка уникальных имен клиентов и дат заказов.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#20)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение Where](../../../visual-basic/language-reference/queries/where-clause.md)