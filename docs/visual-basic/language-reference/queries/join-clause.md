---
title: "Предложение Join (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryJoinIn"
  - "vb.QueryJoin"
  - "vb.QueryJoinOn"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Join - предложение"
  - "Join - оператор"
  - "запросы [Visual Basic], предложение Join"
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Предложение Join (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Объединяет две коллекции в одну.  Операция Join \(объединение\) основана на сопоставлении ключей и использует оператор `Equals`.  
  
## Синтаксис  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## Части  
 `element`  
 Обязательное.  Переменная управления для присоединяемой коллекции.  
  
 `collection`  
 Обязательное.  Коллекция для объединения с коллекцией, определенной в левой части оператора `Join`.  Предложения `Join` могут быть вложены в другие предложения `Join` или в предложение `Group Join`.  
  
 `joinClause`  
 Необязательный параметр.  Одно или несколько дополнительных предложений `Join` для дальнейшего уточнения запроса.  
  
 `groupJoinClause`  
 Необязательный параметр.  Одно или несколько дополнительных предложений `Group Join` для дальнейшего уточнения запроса.  
  
 `key1` `Equals` `key2`  
 Обязательное.  Определяет ключи для объединяемых коллекций.  Необходимо использовать оператор `Equals` для сравнения ключей из объединяемых коллекций.  Можно комбинировать условия соединения с помощью оператора `And` для идентификации нескольких ключей.  Параметр `key1` должен быть из коллекции, которая находится в левой части оператора `Join`.  Параметр `key2` должен быть из коллекции, которая находится в правой части оператора `Join`.  
  
 Ключи, используемые в условии объединения, могут быть выражениями, включающими несколько элементов из коллекции.  Однако каждое ключевое выражение может содержать только элементы из соответствующей ему коллекции.  
  
## Заметки  
 Предложение `Join` объединяет две коллекции на основании совпадающих значений ключей из соединяемых коллекций.  Результирующая коллекция может содержать любую комбинацию значений из коллекции в левой части оператора `Join` и коллекции указанной в предложении `Join`.  Запрос будет возвращать только те результаты, для которых соблюдается условие, заданное оператором `Equals`.  Это эквивалентно `INNER JOIN` в SQL.  
  
 Можно использовать несколько предложений `Join` в запросе для объединения двух или более коллекций в одну.  
  
 Можно выполнять неявные соединения для объединения коллекций без предложения `Join`.  Для этого включите несколько предложений `In` в предложение `From` и укажите предложение `Where`, определяющее ключи, которые необходимо использовать для соединения.  
  
 Можно использовать предложение `Group Join` для объединения коллекций в одну иерархическую коллекцию.  Это аналогично `LEFT OUTER JOIN` в SQL.  
  
## Пример  
 В следующем примере кода выполняется неявное соединение для объединения списка заказчиков и их заказов.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## Пример  
 В следующем примере кода две коллекции объединяются с помощью предложения `Join`.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 В этом примере вывод совпадает с приведенным ниже:  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## Пример  
 В следующем примере кода объединяются две коллекции с помощью предложения `Join` с двумя столбцами ключей.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 В этом примере вывод совпадает с приведенным ниже:  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [Предложение Where](../../../visual-basic/language-reference/queries/where-clause.md)