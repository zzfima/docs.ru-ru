---
title: "Предложение From (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0ecdc8b70fb1ae164a6c78998ce11db9938fbb56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="from-clause-visual-basic"></a>Предложение From (Visual Basic)
Указывает один или несколько переменных диапазона и коллекции для запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`element`|Обязательный. Объект *переменной диапазона* используется для итерации элементов коллекции. Переменная диапазона используется для ссылки на каждый член `collection` как запрос осуществляет итерацию по `collection`. Должно быть перечислимым типом.|  
|`type`|Необязательно. Тип параметра `element`. Если не `type` указан, тип `element` выводится из `collection`.|  
|`collection`|Обязательный. Ссылается на коллекцию, которой будет отправлен запрос. Должно быть перечислимым типом.|  
  
## <a name="remarks"></a>Примечания  
 `From` Предложение используется для определения источника данных для запроса и переменные, которые используются для ссылки на элемент исходной коллекции. Эти переменные называются *переменные диапазона*. `From` Предложение является обязательным для запроса, за исключением случаев `Aggregate` предложение используется для обнаружения, возвращает только агрегированными результаты запроса. Дополнительные сведения см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Можно указать несколько `From` предложения в запросе, чтобы определить несколько коллекций для объединения. При указании нескольких коллекций, они воспринимаются независимо друг от друга, или можно объединить их, если они относятся. Объединение коллекций неявно с помощью `Select` предложение, или явно с использованием `Join` или `Group Join` предложения. В качестве альтернативы можно указать несколько переменных диапазонов и коллекций в одном `From` вместе с каждой связанной переменной диапазона и коллекций, разделенных запятой от остальных. В следующем примере кода показано, как параметры синтаксиса для `From` предложения.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 `From` Предложение определяет область запроса, что похоже на область `For` цикла. Таким образом, каждый `element` переменная диапазона в область запроса должен иметь уникальное имя. Поскольку можно указать несколько `From` предложения запроса, последующие `From` предложений можно ссылаться на переменные диапазона в `From` предложения или они могут ссылаться на переменные диапазона при выполнении предыдущего `From` предложения. Например, в следующем примере показано во вложенной `From` предложение, где коллекция во втором предложении основана на свойстве переменной диапазона в первом предложении.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 Каждый `From` предложение может следовать любое сочетание предложений дополнительных запросов для уточнения запроса. Можно уточнить запрос следующими способами:  
  
-   Объединить несколько коллекций неявно с помощью `From` и `Select` предложений, или явно с использованием `Join` или `Group Join` предложения.  
  
-   Используйте `Where` предложение для фильтрации результатов запроса.  
  
-   Отсортировать результаты с помощью `Order By` предложения.  
  
-   Сгруппировать аналогичные результаты с помощью `Group By` предложения.  
  
-   Используйте `Aggregate` предложение для идентификации агрегатных функций для вычисления результата всего запроса.  
  
-   Используйте `Let` предложение для представления переменной итерации, значение которого определяется выражения, а не коллекцию.  
  
-   Используйте `Distinct` предложений, чтобы игнорировать повторяющиеся результаты запроса.  
  
-   Определения частей результат, возвращаемый с помощью `Skip`, `Take`, `Skip While`, и `Take While` предложения.  
  
## <a name="example"></a>Пример  
 В следующем запросе используется выражение `From` предложение для объявления переменной диапазона `cust` для каждого `Customer` объекта в `customers` коллекции. `Where` Предложение использует переменную диапазона для ограничения выходных данных для клиентов из заданной области. `For Each` Цикл имя компании для каждого клиента в результатах запроса.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a>См. также  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)  
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
