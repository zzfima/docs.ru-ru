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
ms.openlocfilehash: 19eba101e2a91d1b0549e9e3eb86d0af94f2d1b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619754"
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
|`element`|Обязательный. Переменная управления для присоединяемой коллекции.|  
|`type`|Необязательный параметр. Тип параметра `element`. Если не `type` указан, тип `element` выводится из `collection`.|  
|`collection`|Обязательный. Коллекция для объединения с коллекцией, которая находится в левой части `Group Join` оператор. Объект `Group Join` предложения могут быть вложенными в `Join` предложение или в другом `Group Join` предложение.|  
|`key1` `Equals` `key2`|Обязательный. Определяет ключи для соединяемых коллекций. Необходимо использовать `Equals` оператор для сравнения ключей из соединяемых коллекций. Можно комбинировать условия соединения с помощью `And` оператор для идентификации нескольких ключей. `key1` Параметр должен быть из коллекции в левой части `Join` оператор. `key2` Параметр должен быть из коллекции в правой части `Join` оператор.<br /><br /> Ключи, используемые в условии соединения может быть выражений, содержащих более одного элемента из коллекции. Тем не менее каждое ключевое выражение может содержать только элементы из соответствующей коллекции.|  
|`expressionList`|Обязательный. Одно или несколько выражений, определяющих способ создания групп элементов из коллекции. Чтобы определить имя элемента для результатов группирования, используйте `Group` ключевое слово (`<alias> = Group`). Вы также можете включать агрегатные функции для применения к группе.|  
  
## <a name="remarks"></a>Примечания  
 `Group Join` Предложение объединяет две коллекции, на основе сопоставления значений ключа из соединяемых коллекций. Полученная в результате коллекция может содержать член, который ссылается на коллекцию элементов из второй коллекции, соответствующих значению ключа из первой коллекции. Можно также указать агрегатные функции для применения к сгруппированным элементам из второй коллекции. Сведения об агрегатных функциях см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Рассмотрим, например, коллекция менеджеров и коллекции сотрудников. Элементы из обеих коллекций имеют свойство ManagerID, идентифицирующее подотчетных конкретному руководителю. Результаты операции соединения будут содержать результат для каждого руководителя и сотрудника с соответствующим значением ManagerID. В результате `Group Join` операции будет содержать полный список руководителей. Каждый результат manager будет иметь член, на который ссылка списка сотрудников, которые были совпадение для конкретного диспетчера.  
  
 Коллекции, полученный в результате `Group Join` операция может содержать любое сочетание значений из коллекции, указанной в `From` предложения и выражений, указанных в `Into` предложении `Group Join` предложение. Дополнительные сведения о допустимых выражениях для `Into` предложение, см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Объект `Group Join` операция возвращает все результаты из коллекции в левой части `Group Join` оператор. Это справедливо, даже если нет совпадений в присоединяемой коллекции. Это аналогично `LEFT OUTER JOIN` в SQL.  
  
 Можно использовать `Join` предложение для объединения коллекции в одну коллекцию. Это эквивалентно `INNER JOIN` в SQL.  
  
## <a name="example"></a>Пример  
 В следующем примере объединяются две коллекции с помощью `Group Join` предложение.  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-join-clause_1.vb)]  
  
## <a name="see-also"></a>См. также
- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Join](../../../visual-basic/language-reference/queries/join-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Предложение Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)
