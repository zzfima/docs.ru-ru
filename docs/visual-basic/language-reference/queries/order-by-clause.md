---
title: "Предложение Order By (Visual Basic) | Microsoft Docs"
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
  - "vb.QueryOrderBy"
  - "vb.QueryAscending"
  - "vb.QueryDescending"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Order By - предложение"
  - "Order By - оператор"
  - "запросы [Visual Basic], Order By"
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Предложение Order By (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает порядок сортировки для результата запроса.  
  
## Синтаксис  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## Части  
 `orderExp1`  
 Обязательный.  Одно или несколько полей из текущего результата запроса, определяющие порядок возвращаемых значений.  Имена полей должны быть разделены запятыми \(,\).  Можно определить каждое поле как отсортированное в возрастающем или убывающем порядке с помощью ключевых слов `Ascending` и `Descending`.  Если не указаны ключевые слова `Ascending` или `Descending`, сортировка по умолчанию происходит по возрастанию.  Поля порядка сортировки получают приоритет слева направо.  
  
## Заметки  
 Чтобы отсортировать результаты запроса, используйте предложение `Order By`.  Предложение `Order By` может сортировать результаты, основанные только на переменной диапазона для текущей области.  Например, предложение `Select` представляет новую область в выражении запроса с новыми переменными итерации для этой области.  Диапазон переменных, определенные до предложения `Select` в запросе, будут недоступны после предложения `Select`.  Таким образом, если требуется упорядочить результаты по полю, не доступному в предложении `Select`, необходимо поместить предложение `Order By` перед предложением `Select`.  Например, это может понадобиться для сортировки запроса по полям, которые не возвращаются как часть результата.  
  
 Порядок по возрастанию и убыванию для поля определяется реализацией интерфейса <xref:System.IComparable> для типа данных поля.  Если тип данных не реализует интерфейс <xref:System.IComparable>, порядок сортировки игнорируется.  
  
## Пример  
 Следующее выражение запроса использует предложение `From` для объявления диапазона переменной `book` для коллекции `books`.  Предложение `Order By` сортирует результаты запроса по цене в возрастающем порядке \(по умолчанию\).  Книги с одной и той же ценой сортируются по названию в возрастающем порядке.  Предложение `Select` выбирает свойства `Title` и `Price` в качестве значений, возвращаемых по запросу.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## Пример  
 Следующее выражение запроса использует предложение `Order By` для сортировки результатов запроса по цене в убывающем порядке.  Книги с одной и той же ценой сортируются по названию в возрастающем порядке.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## Пример  
 Следующее выражение запроса использует предложение `Select` для выбора названия книги, цены, даты издания и автора.  Затем заполняются поля `Title`, `Price`, `PublishDate` и `Author` переменной диапазона для новой области.   Предложение `Order By` упорядочивает новую переменную диапазона по имени автора, названию книги и затем по цене.  Каждый столбец сортируется в порядке по умолчанию \(по возрастанию\).  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)