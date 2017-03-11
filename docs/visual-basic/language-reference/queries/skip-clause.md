---
title: "Предложение Skip (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QuerySkip"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "запросы [Visual Basic], Пропустить"
  - "Skip - предложение"
  - "Skip - оператор"
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Предложение Skip (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Пропускает заданное число элементов в коллекции и возвращает остальные элементы.  
  
## Синтаксис  
  
```  
Skip count  
```  
  
## Части  
 `count`  
 Обязательный.  Значение или выражение, вычисление которого дает число пропускаемых элементов последовательности.  
  
## Заметки  
 Предложение `Skip` вызывает запрос для пропуска элементов в начале списка результатов и возвращения остальных элементов.  Число пропускаемых элементов определяется параметром `count`.  
  
 Пользователь может использовать предложение `Skip` с предложением `Take` для возврата диапазона данных из любого сегмента запроса.  Для этого передайте индекс первого элемента диапазона в предложение `Skip` и размер диапазона в предложение `Take`.  
  
 При использовании в запросе предложения `Skip` может быть необходимо убедиться, что результаты возвращаются в том порядке, который позволяет предложению `Skip` пропускать намеченные результаты.  Дополнительные сведения о сортировке результатов запроса содержатся в разделе [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Для указания того, что пропускаются только определенные элементы в зависимости от предоставленного условия, пользователь может использовать предложение `SkipWhile`.  
  
## Пример  
 В следующем примере кода для возвращения данных из запроса на страницах предложение `Skip` используется вместе с предложением `Take`.  Функция `GetCustomers` использует предложение `Skip` для пропуска в списке всех клиентов до предоставленного начального значения индекса и предложение `Take` для возвращения страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#1)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)