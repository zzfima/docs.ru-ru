---
title: "Предложение From (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryFrom"
  - "vb.QueryFromIn"
  - "vb.QueryFromLet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "From - предложение"
  - "From - оператор"
  - "запросы [Visual Basic], От"
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Предложение From (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает один или несколько переменных диапазонов и коллекцию для выполнения запроса.  
  
## Синтаксис  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`element`|Обязательный.  *range variable* используется для циклического просмотра элементов коллекции.  Переменная диапазона используется для ссылки на каждый член `collection`, когда запрос циклически просматривает `collection`.  Должно быть перечислимым типом.|  
|`type`|Необязательный.  Тип `element`.  Если не указан `type`, тип `element` получается из `collection`.|  
|`collection`|Обязательный.  Ссылка на коллекцию, которая будет запрашиваться.  Должно быть перечислимым типом.|  
  
## Заметки  
 Предложение `From` используется для определения источника данных для запроса и переменных, которые используются для ссылок на элементы из исходной коллекции.  Эти переменные называются *range variables*.  Предложение `From` необходимо для запроса, за исключением случая, когда предложение `Aggregate` используется для идентификации запроса, возвращающего только сгруппированные результаты.  Дополнительные сведения см. в разделе [Предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Можно указать несколько предложений `From` в запросе для идентификации нескольких коллекций для объединения.  При указании нескольких коллекций, они воспринимаются, как независимые друг от друга, или можно объединить их, если они связаны.  Можно объединить коллекции неявно, с помощью предложения `Select` или явно используя предложения `Join` или `Group Join`.  В качестве альтернативы можно указать несколько переменных диапазонов и коллекций в одном предложении `From` с каждой связанной переменной диапазона и коллекции, разделенных между собой запятыми.  В следующем примере показаны оба параметра синтаксиса для предложения `From`.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 Предложение `From` определяет область запроса, которая аналогична области цикла `For`.  Таким образом, каждая переменная диапазона `element` в области запроса должна иметь уникальное имя.  Поскольку можно указать несколько предложений `From` для запроса, последующие предложения `From` могут обратиться к переменным диапазона в предложении `From` или они могут ссылаться на переменную диапазона в предыдущем предложении `From`.  Например, в следующем примере показано вложенное предложение `From`, где коллекция во втором предложении основана на свойстве переменной диапазона в первом предложении.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 После каждого предложения `From` может следовать любая комбинация предложений дополнительных запросов для уточнения запроса.  Можно уточнить запрос следующими способами:  
  
-   Объединить несколько коллекций неявно с помощью предложений `From` и `Select` или явно с помощью предложений `Join` и `Group Join`.  
  
-   Используйте предложение `Where` для фильтрации результатов запроса.  
  
-   Отсортируйте результат с помощью предложения `Order By`.  
  
-   Группирование аналогичных результатов с помощью предложения `Group By`.  
  
-   Используйте предложение `Aggregate` для идентификации агрегатных функций для вычисления результата всего запроса.  
  
-   Используйте предложение `Let` для представления переменной итерации, значение которой определяется вместо выражения коллекции.  
  
-   Чтобы игнорировать повторяющиеся результаты, используйте предложение `Distinct`.  
  
-   Укажите часть результата для возврата с помощью предложений `Skip`, `Take`, `Skip While` и `Take While`.  
  
## Пример  
 Следующее выражение запроса использует предложение `From` для объявления диапазона переменной `cust` для каждого объекта `Customer` в коллекции `customers`.  Предложение `Where` использует переменную диапазона для ограничения вывода для заказчиков из указанной области.  В результате запроса цикл `For Each` отображает имя компании для каждого заказчика.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## См. также  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение Where](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Предложение Distinct](../../../visual-basic/language-reference/queries/distinct-clause.md)   
 [Предложение Join](../../../visual-basic/language-reference/queries/join-clause.md)   
 [Предложение Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Предложение Let](../../../visual-basic/language-reference/queries/let-clause.md)   
 [Предложение Skip](../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)   
 [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)