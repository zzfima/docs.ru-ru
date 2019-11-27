---
title: Предложение From
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: a63fb41fc2b0ad885acf76ad5d56e446922f5b90
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343780"
---
# <a name="from-clause-visual-basic"></a>Предложение From (Visual Basic)
Указывает одну или несколько переменных диапазона и коллекцию для запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`element`|Обязательно. *Переменная диапазона* , используемая для прохода по элементам коллекции. Переменная диапазона используется для ссылки на каждый элемент `collection`, так как запрос проходит по `collection`. Должен быть перечислимым типом.|  
|`type`|Необязательный элемент. Тип параметра `element`. Если `type` не указано, тип `element` выводится из `collection`.|  
|`collection`|Обязательно. Ссылается на коллекцию, к которой выполняется запрос. Должен быть перечислимым типом.|  
  
## <a name="remarks"></a>Примечания  
 Предложение `From` используется для указания исходных данных для запроса и переменных, которые используются для ссылки на элемент из исходной коллекции. Эти переменные называются *переменными диапазона*. Предложение `From` является обязательным для запроса, за исключением случаев, когда для задания запроса, возвращающего только агрегированные результаты, используется предложение `Aggregate`. Дополнительные сведения см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Можно указать несколько предложений `From` в запросе, чтобы определить несколько коллекций для объединения. Если указано несколько коллекций, они проходят по отдельности или объединяются, если они связаны. Коллекции можно объединять неявным образом с помощью предложения `Select` или явно с помощью предложений `Join` или `Group Join`. В качестве альтернативы можно указать несколько переменных диапазона и коллекций в одном предложении `From`, где каждая связанная переменная диапазона и коллекция отделены друг от друга запятыми. В следующем примере кода показаны оба синтаксических параметра для предложения `From`.  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 Предложение `From` определяет область запроса, которая аналогична области цикла `For`. Таким образом, каждая переменная диапазона `element` в области запроса должна иметь уникальное имя. Поскольку можно указать несколько предложений `From` для запроса, последующие предложения `From` могут ссылаться на переменные диапазона в предложении `From` или они могут ссылаться на переменные диапазона в предыдущем предложении `From`. Например, в следующем примере показано вложенное предложение `From`, где коллекция во втором предложении основана на свойстве переменной диапазона в первом предложении.  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 За каждым предложением `From` может следовать любое сочетание дополнительных предложений запроса для уточнения запроса. Запрос можно уточнить следующими способами.  
  
- Объедините несколько коллекций неявным образом с помощью предложений `From` и `Select` или явно с помощью предложений `Join` или `Group Join`.  
  
- Чтобы отфильтровать результат запроса, используйте предложение `Where`.  
  
- Отсортируйте результат с помощью предложения `Order By`.  
  
- Сгруппируйте аналогичные результаты вместе с помощью предложения `Group By`.  
  
- Используйте предложение `Aggregate`, чтобы определить агрегатные функции для вычисления результата всего запроса.  
  
- Используйте предложение `Let`, чтобы ввести переменную итерации, значение которой определяется выражением, а не коллекцией.  
  
- Используйте предложение `Distinct` для пропуска повторяющихся результатов запроса.  
  
- Выявление частей результата, возвращаемых с помощью предложений `Skip`, `Take`, `Skip While`и `Take While`.  
  
## <a name="example"></a>Пример  
 Следующее выражение запроса использует предложение `From`, чтобы объявить переменную диапазона `cust` для каждого объекта `Customer` в коллекции `customers`. Предложение `Where` использует переменную диапазона для ограничения выходных данных для клиентов из указанной области. Цикл `For Each` отображает название компании для каждого клиента в результатах запроса.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a>См. также

- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Предложение Distinct](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [Предложение Join](../../../visual-basic/language-reference/queries/join-clause.md)
- [Предложение Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Предложение Let](../../../visual-basic/language-reference/queries/let-clause.md)
- [Предложение Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)
- [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)
