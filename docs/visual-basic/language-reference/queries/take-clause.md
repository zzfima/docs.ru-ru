---
title: "Предложение Take (Visual Basic) | Microsoft Docs"
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
  - "vb.QueryTake"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "запросы [Visual Basic], Take"
  - "Take - предложение"
  - "Take - оператор"
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Предложение Take (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Возвращает указанное число последовательных элементов от начала коллекции.  
  
## Синтаксис  
  
```  
Take count  
```  
  
## Части  
 `count`  
 Обязательный.  Значение или выражение, вычисление которого дает число возвращаемых элементов последовательности.  
  
## Заметки  
 Предложение `Take` указывает запросу включить заданное количество смежных элементов, начиная от начала списка результатов.  Число включаемых элементов задается параметром `count`.  
  
 Пользователь может использовать предложение `Take` с предложением `Skip` для возврата диапазона данных из любого сегмента запроса.  Для этого передайте индекс первого элемента диапазона в предложение `Skip` и размер диапазона в предложение `Take`.  В этом случае предложение `Take` должно быть указано после предложения `Skip`.  
  
 При использовании в запросе предложения `Take`, возможно, необходимо будет убедиться, что результаты возвращаются в порядке, позволяющем предложению `Take` включать выбранные результаты.  Дополнительные сведения о сортировке результатов запроса содержатся в разделе [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Можно использовать предложение `TakeWhile` для указания того, что включаются только определенные элементы в зависимости от предоставленного условия.  
  
## Пример  
 В следующем примере кода для возвращения данных из запроса на страницах предложение `Take` используется вместе с предложением `Skip`.  Функция `Skip` использует предложение `Take` для пропуска в списке всех клиентов до предоставленного начального значения индекса и использует предложение для возвращения страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)   
 [Предложение Skip](../../../visual-basic/language-reference/queries/skip-clause.md)