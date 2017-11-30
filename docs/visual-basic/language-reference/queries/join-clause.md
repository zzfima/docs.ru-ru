---
title: "Предложение Join (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bb25c9dac8994e7f975539c1d036f0f0d9d239e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="join-clause-visual-basic"></a>Предложение Join (Visual Basic)
Объединяет две коллекции в одну. Операция соединения основана на сопоставлении ключей и использует `Equals` оператор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a>Части  
 `element`  
 Обязательный. Переменная управления для присоединяемой коллекции.  
  
 `collection`  
 Обязательный. Коллекция для объединения с коллекцией, определенной в левой части `Join` оператор. Объект `Join` предложение может быть вложенным в другой `Join` предложения, либо в `Group Join` предложения.  
  
 `joinClause`  
 Необязательно. Один или более дополнительных `Join` предложения для дальнейшего уточнения запроса.  
  
 `groupJoinClause`  
 Необязательно. Один или более дополнительных `Group Join` предложения для дальнейшего уточнения запроса.  
  
 `key1` `Equals` `key2`  
 Обязательный. Определяет ключи для соединяемых коллекций. Необходимо использовать `Equals` оператор для сравнения ключей из соединяемых коллекций. Можно комбинировать условия соединения с помощью `And` оператор для идентификации нескольких ключей. `key1`должен быть из коллекции в левой части `Join` оператор. `key2`должен быть из коллекции в правой части `Join` оператор.  
  
 Ключи, используемые в условии соединения может быть выражений, содержащих более одного элемента из коллекции. Однако каждое ключевое выражение может содержать только элементы из соответствующей ему коллекции.  
  
## <a name="remarks"></a>Примечания  
 `Join` Предложение объединяет две коллекции на основании совпадающих значений ключей из соединяемых коллекций. Полученная в результате коллекция может содержать любую комбинацию значений из коллекции в левой части `Join` оператор и коллекции, указанной в `Join` предложения. Запрос будет возвращать только те результаты, для которых условие, заданное `Equals` выполняется оператор. Это эквивалентно `INNER JOIN` в SQL.  
  
 Можно использовать несколько `Join` предложения в запросе, для соединения двух или нескольких коллекций в одну коллекцию.  
  
 Можно выполнять неявные соединения для объединения коллекций без `Join` предложения. Чтобы сделать это, включать несколько `In` предложения в вашей `From` предложения и укажите `Where` предложение, определяющее ключи, которые вы хотите использовать для соединения.  
  
 Можно использовать `Group Join` предложение для объединения коллекции в одну иерархическую коллекцию. Это аналогично `LEFT OUTER JOIN` в SQL.  
  
## <a name="example"></a>Пример  
 В следующем примере кода выполняется неявное соединение для объединения списка клиентов и их заказов.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода две коллекции объединяются с помощью `Join` предложения.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 В этом примере будет создавать выходные данные, аналогичные следующим:  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>Пример  
 В следующем примере кода две коллекции объединяются с помощью `Join` предложение, содержащее два ключевых столбцов.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 Пример вывода следующего вида:  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложение Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
