---
title: Предложение Group Join (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupJoinIn
- vb.QueryGroupJoinOn
- vb.QueryGroupJoin
- vb.QueryGroupJoinInto
helpviewer_keywords:
- Group Join clause [Visual Basic]
- Group Join statement [Visual Basic]
- queries [Visual Basic], Group Join
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
ms.openlocfilehash: 094281b0afb34451ae8539e4eb967043b21d379c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604761"
---
# <a name="group-join-clause-visual-basic"></a>Предложение Group Join (Visual Basic)
Объединяет две коллекции в одну иерархическую коллекцию. Операция соединения основана на сопоставлении ключей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`element`|Обязательно. Переменная управления для присоединяемой коллекции.|  
|`type`|Необязательный. Тип параметра `element`. Если не `type` указан, тип `element` выводится из `collection`.|  
|`collection`|Обязательно. Коллекция для объединения с коллекцией, которая находится слева от `Group Join` оператор. Объект `Group Join` предложения, которые могут быть вложены в `Join` предложения или в другом `Group Join` предложения.|  
|`key1` `Equals` `key2`|Обязательно. Определяет ключи для соединяемых коллекций. Необходимо использовать `Equals` оператор для сравнения ключей из соединяемых коллекций. Можно комбинировать условия соединения с помощью `And` оператор для идентификации нескольких ключей. `key1` Параметр должен быть из коллекции в левой части `Join` оператор. `key2` Параметр должен быть из коллекции в правой части `Join` оператор.<br /><br /> Ключи, используемые в условии соединения может быть выражений, содержащих более одного элемента из коллекции. Однако каждое ключевое выражение может содержать только элементы из соответствующей ему коллекции.|  
|`expressionList`|Обязательно. Одно или несколько выражений, определяющих способ создания групп элементов из коллекции. Чтобы определить имя элемента для результатов группирования, используйте `Group` ключевое слово (`<alias> = Group`). Вы также можете включать агрегатные функции для применения к группе.|  
  
## <a name="remarks"></a>Примечания  
 `Group Join` Предложение объединяет две коллекции на основании совпадающих значений ключей из соединяемых коллекций. Полученная в результате коллекция может содержать член, который ссылается на коллекцию элементов из второй коллекции, соответствующих значению ключа из первой коллекции. Можно также указать агрегатные функции для применения к сгруппированным элементам из второй коллекции. Сведения об агрегатных функциях см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Рассмотрим, например, коллекция менеджеров и коллекции сотрудников. Элементы из обеих коллекций имеют свойство ManagerID, определяющее сотрудников, подчиняющихся тому конкретному руководителю. Результаты операции соединения будут содержать результат для каждого руководителя и сотрудника с соответствующим значением ManagerID. В результате `Group Join` операции будет содержать полный список руководителей. Каждый диспетчер результат будет иметь член, ссылающийся на список сотрудников, которые были соответствия для конкретного диспетчера.  
  
 Коллекция, возникающие в результате `Group Join` операция может содержать любую комбинацию значений из коллекции, указанной в `From` предложения и выражений, указанных в `Into` предложения `Group Join` предложения. Дополнительные сведения о допустимых выражениях для `Into` предложение, в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Объект `Group Join` операция вернет все результаты из коллекции в левой части `Group Join` оператор. Это верно, даже если не найдено совпадений в присоединяемой коллекции. Это аналогично `LEFT OUTER JOIN` в SQL.  
  
 Можно использовать `Join` предложение для объединения коллекции в одну коллекцию. Это эквивалентно `INNER JOIN` в SQL.  
  
## <a name="example"></a>Пример  
 В следующем примере кода две коллекции объединяются с помощью `Group Join` предложения.  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-join-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложение Join](../../../visual-basic/language-reference/queries/join-clause.md)  
 [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Предложение Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)
