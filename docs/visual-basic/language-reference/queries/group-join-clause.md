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
ms.openlocfilehash: 184077f2689eb64e4373d407913eefcc03b795c2
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005722"
---
# <a name="group-join-clause-visual-basic"></a>Предложение Group Join (Visual Basic)
Объединяет две коллекции в одну иерархическую коллекцию. Операция Join основана на совпадающих ключах.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`element`|Обязательный. Управляющая переменная для объединяемой коллекции.|  
|`type`|Необязательный параметр. Тип параметра `element`. Если `type` не указан, тип `element` выводится из `collection`.|  
|`collection`|Обязательный. Коллекция для объединения с коллекцией, находящейся в левой части оператора `Group Join`. Предложение `Group Join` может быть вложено в предложение `Join` или в другое предложение `Group Join`.|  
|`key1` `Equals` `key2`|Обязательный. Определяет ключи для соединяемых коллекций. Для сравнения ключей из объединяемых коллекций необходимо использовать оператор `Equals`. Условия JOIN можно комбинировать с помощью оператора `And` для обнаружения нескольких ключей. Параметр `key1` должен быть из коллекции в левой части оператора `Join`. Параметр `key2` должен быть из коллекции в правой части оператора `Join`.<br /><br /> Ключи, используемые в условии объединения, могут быть выражениями, включающими более одного элемента из коллекции. Однако каждое ключевое выражение может содержать только элементы из соответствующей коллекции.|  
|`expressionList`|Обязательный. Одно или несколько выражений, которые определяют, как объединяются группы элементов из коллекции. Чтобы указать имя члена для сгруппированных результатов, используйте ключевое слово `Group` (`<alias> = Group`). Вы также можете включать агрегатные функции для применения к группе.|  
  
## <a name="remarks"></a>Примечания  
 Предложение `Group Join` объединяет две коллекции на основе совпадающих значений ключей из объединяемых коллекций. Результирующая коллекция может содержать член, который ссылается на коллекцию элементов из второй коллекции, которая соответствует значению ключа из первой коллекции. Можно также указать агрегатные функции для применения к сгруппированным элементам из второй коллекции. Дополнительные сведения о агрегатных функциях см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Рассмотрим, например, коллекцию руководителей и коллекцию сотрудников. Элементы обеих коллекций имеют свойство ManagerID, определяющее сотрудников, которые отправляют отчеты определенному менеджеру. Результаты операции объединения будут содержать результат для каждого менеджера и сотрудника с соответствующим значением ManagerID. Результаты операции `Group Join` будут содержать полный список руководителей. Каждый результат менеджера будет иметь член, который ссылался на список сотрудников, которые были соответствующими руководителю.  
  
 Коллекция, полученная в результате операции `Group Join`, может содержать любое сочетание значений из коллекции, определенной в предложении `From`, и выражения, определенные в предложении `Into` предложения `Group Join`. Дополнительные сведения о допустимых выражениях для предложения `Into` см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Операция `Group Join` возвратит все результаты из коллекции, указанной в левой части оператора `Group Join`. Это справедливо, даже если в объединяемой коллекции нет совпадений. Это аналогично `LEFT OUTER JOIN` в SQL.  
  
 Для объединения коллекций в одну коллекцию можно использовать предложение `Join`. Это эквивалентно `INNER JOIN` в SQL.  
  
## <a name="example"></a>Пример  
 В следующем примере кода две коллекции объединяются с помощью предложения `Group Join`.  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Join](../../../visual-basic/language-reference/queries/join-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Предложение Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)
