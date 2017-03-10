---
title: "Предложение Group Join (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryGroupJoinIn"
  - "vb.QueryGroupJoinOn"
  - "vb.QueryGroupJoin"
  - "vb.QueryGroupJoinInto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Group Join - предложение"
  - "Group Join - оператор"
  - "запросы [Visual Basic], Group Join"
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Предложение Group Join (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Объединяет две коллекции в одну иерархическую.  Операция объединения основана на совпадении ключей.  
  
## Синтаксис  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`element`|Обязательный.  Переменная управления для присоединяемой коллекции.|  
|`type`|Необязательный.  Тип `element`.  Если не указан `type`, тип `element` получается из `collection`.|  
|`collection`|Обязательный.  Коллекция для объединения с коллекцией, находящейся в левой части оператора `Group Join`.  Предложение `Group Join` может быть вложено в предложение `Join` или в другое предложение `Group Join`.|  
|`key1` `Equals` `key2`|Обязательный.  Определяет ключи для объединяемых коллекций.  Необходимо использовать оператор `Equals` для сравнения ключей из объединяемых коллекций.  Можно комбинировать условия соединения с помощью оператора `And` для идентификации нескольких ключей.  Параметр `key1` должен быть из коллекции, которая находится в левой части оператора `Join`.  Параметр `key2` должен быть из коллекции, которая находится в правой части оператора `Join`.<br /><br /> Ключи, используемые в условии объединения, могут быть выражениями, включающими несколько элементов из коллекции.  Однако каждое ключевое выражение может содержать только элементы из соответствующей ему коллекции.|  
|`expressionList`|Обязательный.  Одно или несколько выражений, определяющих способ создания групп элементов из коллекции.  Для определения имени члена для сгруппированных результатов используйте ключевое слово `Group` \(`<alias> = Group`\).  Можно также включить агрегатные функции, применимые к группе.|  
  
## Заметки  
 Предложение `Group Join` объединяет две коллекции, на основании совпадающих значений ключей из соединяемых коллекций.  Результирующая коллекция может содержать член, который ссылается на коллекцию элементов из второй коллекции, соответствующих значению ключа из первой коллекции.  Можно также указать агрегатные функции для применения к сгруппированным элементам из второй коллекции.  Дополнительные сведения об агрегатных функциях см. в разделе [Предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Рассмотрим, например, коллекцию руководителей и коллекцию сотрудников.  Элементы из обеих коллекций имеют свойство ManagerID, определяющее сотрудников, подотчетных конкретному руководителю.  Результаты операции соединения будут содержать результат для каждого руководителя и сотрудника с совпадением по значению ManagerID.  Результаты операции `Group Join` будут содержать полный список руководителей.  Результат для каждого руководителя будет иметь член, ссылающийся на список соответствующих ему сотрудников.  
  
 Получаемая коллекция после операции `Group Join` может содержать любую комбинацию значений из коллекции, определенной в предложении `From`, и выражений, указанных в предложении `Into` предложения `Group Join`.  Дополнительные сведения о допустимых выражениях для предложения `Into` см. в разделе [Предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Операция `Group Join` возвратит все результаты из коллекции, определенной на левой стороне оператора `Group Join`.  Это верно, даже если не найдено совпадений в присоединяемой коллекции.  Это аналогично `LEFT OUTER JOIN` в SQL.  
  
 Можно использовать предложение `Join` для объединения коллекций в одну коллекцию.  Это эквивалентно `INNER JOIN` в SQL.  
  
## Пример  
 В следующем примере кода две коллекции объединяются с помощью предложения `Group Join`.  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#14)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Join](../../../visual-basic/language-reference/queries/join-clause.md)   
 [Предложение Where](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Предложение Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)