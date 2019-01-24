---
title: Предложение From (Visual Basic)
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
ms.openlocfilehash: fd11d00ebfa42eda272db39965d25b905bd5c841
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678789"
---
# <a name="from-clause-visual-basic"></a>Предложение From (Visual Basic)
Указывает один или несколько переменных диапазона и набор для запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`element`|Обязательный. Объект *переменная диапазона* используется для итерации по элементам коллекции. Переменная диапазона используется для обращения к каждому элементу `collection` как запрос проходит по `collection`. Должен быть перечислимым типом.|  
|`type`|Необязательный параметр. Тип параметра `element`. Если не `type` указан, тип `element` выводится из `collection`.|  
|`collection`|Обязательный. Относится к коллекции, должны запрашиваться. Должен быть перечислимым типом.|  
  
## <a name="remarks"></a>Примечания  
 `From` Предложение используется для определения источника данных для запроса и переменные, которые используются для ссылки на элемент в исходной коллекции. Эти переменные называются *переменные диапазона*. `From` Предложение является обязательным для запроса, за исключением случаев `Aggregate` предложение используется для определения запросов, что возвращает только агрегированные результаты. Дополнительные сведения см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Можно указать несколько `From` предложения в запросе для идентификации нескольких коллекций для объединения. При указании нескольких коллекций, они воспринимаются независимо друг от друга, или вы можете объединить их, если они связаны. Объединение коллекций неявно с помощью `Select` предложения, или явно с помощью `Join` или `Group Join` предложения. Кроме того, можно указать несколько переменных диапазона и коллекций в одном `From` предложение, с каждой связанной переменной диапазона и коллекций, разделенных запятыми от других. В следующем примере кода показаны оба варианта синтаксиса для `From` предложение.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 `From` Предложение определяет область запроса, который аналогичен рамки `For` цикла. Таким образом, каждый `element` переменной диапазона в области запроса должен иметь уникальное имя. Поскольку можно указать несколько `From` предложения запроса, последующие `From` предложения могут ссылаться на переменные диапазона в `From` предложения, или они могут ссылаться на переменную диапазона в предыдущем `From` предложение. Например, в следующем примере показано вложенный `From` предложение, где коллекция во втором предложении основана на свойстве переменной диапазона в первом предложении.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 Каждый `From` предложение может следовать любое сочетание дополнительных предложений запроса для уточнения запроса. Можно уточнить запрос следующим образом:  
  
-   Объединить несколько коллекций неявно с помощью `From` и `Select` предложения, или явно с помощью `Join` или `Group Join` предложения.  
  
-   Используйте `Where` предложение для фильтрации результатов запроса.  
  
-   Отсортировать результаты с помощью `Order By` предложение.  
  
-   Группировать аналогичные результаты с помощью `Group By` предложение.  
  
-   Используйте `Aggregate` предложение для идентификации агрегатных функций для вычисления результата всего запроса.  
  
-   Используйте `Let` предложение для представления переменной итерации, значение которого определяется с помощью выражения, а не коллекция.  
  
-   Используйте `Distinct` предложение, чтобы игнорировать повторяющиеся результаты запроса.  
  
-   Определения частей результат для возврата с помощью `Skip`, `Take`, `Skip While`, и `Take While` предложения.  
  
## <a name="example"></a>Пример  
 В следующем запросе используется выражение `From` предложение для объявления переменной диапазона `cust` для каждого `Customer` объекта в `customers` коллекции. `Where` Предложение использует переменную диапазона для ограничения выходных данных клиентов из заданной области. `For Each` Цикл имя компании для каждого клиента в результатах запроса.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
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
