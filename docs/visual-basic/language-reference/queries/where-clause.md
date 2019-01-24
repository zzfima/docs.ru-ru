---
title: Предложение Where (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 5ecfc523573a6ab8142a04557156a3819eed440e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662300"
---
# <a name="where-clause-visual-basic"></a>Предложение Where (Visual Basic)
Определяет условия фильтрации запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Where condition  
```  
  
## <a name="parts"></a>Части  
 `condition`  
 Обязательный. Выражение, определяющее, включаются ли в коллекции выходных значений для текущего элемента в коллекции. Выражение должно возвращать `Boolean` значение или его эквивалент `Boolean` значение. Если условие принимает значение `True`, элемент включается в результат запроса; в противном случае, элемент исключается из результата запроса.  
  
## <a name="remarks"></a>Примечания  
 `Where` Предложение позволяет фильтровать запросы к данным, выбрав только элементы, которые соответствуют определенным критериям. Элементы, значения которых вызвать `Where` предложение для вычисления `True` включены в результат запроса; другие элементы исключаются. Выражение, которое используется в `Where` должны иметь предложение `Boolean` или его эквивалент `Boolean`, такие как целое число, результатом которого является `False` если его значение равно нулю. Можно объединить несколько выражений в `Where` предложение с помощью логических операторов, таких как `And`, `Or`, `AndAlso`, `OrElse`, `Is`, и `IsNot`.  
  
 По умолчанию, выражения запроса не вычисляются до к ним осуществляется доступ, например, когда они находятся привязкой к данным или прошедших итерацию через в `For` цикла. В результате `Where` предложение вычисляется только в том случае, пока не осуществляется доступ к запросу. Если у вас есть значения, внешним по отношению к запроса, которые используются в `Where` предложение, убедитесь, что соответствующее значение используется в `Where` предложение во время выполнения запроса. Дополнительные сведения о выполнении запросов см. в разделе [Your первого запроса LINQ записи](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Можно вызывать функции в `Where` предложение, чтобы выполнить расчет или операцию над значением из текущего элемента в коллекции. Вызов функции в `Where` предложение может вызвать запрос для выполнения сразу же при определении, а не при доступе. Дополнительные сведения о выполнении запросов см. в разделе [Your первого запроса LINQ записи](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Пример  
 В следующем запросе используется выражение `From` предложение для объявления переменной диапазона `cust` для каждого `Customer` объекта в `customers` коллекции. `Where` Предложение использует переменную диапазона для ограничения выходных данных клиентов из заданной области. `For Each` Цикл имя компании для каждого клиента в результатах запроса.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `And` и `Or` логические операторы в `Where` предложение.  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## <a name="see-also"></a>См. также
- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
