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
ms.openlocfilehash: 404dd848058f7e5c9bc8a74b6d89df18c6c55fad
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005003"
---
# <a name="where-clause-visual-basic"></a>Предложение Where (Visual Basic)
Задает условие фильтрации для запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a>Части  
 `condition`  
 Обязательный. Выражение, определяющее, включаются ли значения для текущего элемента в коллекции в выходную коллекцию. Выражение должно иметь значение `Boolean` или эквивалент значения `Boolean`. Если условие принимает значение `True`, элемент включается в результат запроса. в противном случае элемент исключается из результата запроса.  
  
## <a name="remarks"></a>Примечания  
 Предложение `Where` позволяет фильтровать данные запроса, выбирая только те элементы, которые соответствуют определенным условиям. Элементы, значения которых приводят к вычислению предложения `Where` для вычисления `True`, включаются в результат запроса; другие элементы исключаются. Выражение, используемое в предложении `Where`, должно возвращать `Boolean` или эквивалент `Boolean`, например целое число, результатом которого является `False`, если его значение равно нулю. В предложении `Where` можно объединить несколько выражений, используя логические операторы, такие как `And`, `Or`, `AndAlso`, `OrElse`, `Is` и `IsNot`.  
  
 По умолчанию выражения запроса не оцениваются до тех пор, пока они не будут доступны, например, когда они привязаны к данным или просматриваются в цикле `For`. В результате предложение `Where` не вычисляется до тех пор, пока не будет осуществлен доступ к запросу. Если имеются внешние значения для запроса, используемые в предложении `Where`, убедитесь, что соответствующее значение используется в предложении `Where` во время выполнения запроса. Дополнительные сведения о выполнении запросов см. [в разделе Написание первого запроса LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Можно вызывать функции в предложении `Where` для выполнения вычисления или операции со значением из текущего элемента в коллекции. Вызов функции в предложении `Where` может привести к немедленному выполнению запроса, если он определен, а не при доступе к нему. Дополнительные сведения о выполнении запросов см. [в разделе Написание первого запроса LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Пример  
 Следующее выражение запроса использует предложение `From` для объявления переменной диапазона `cust` для каждого объекта `Customer` в коллекции `customers`. Предложение `Where` использует переменную диапазона для ограничения выходных данных для клиентов из указанной области. Цикл `For Each` отображает название компании для каждого клиента в результатах запроса.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Пример  
 В следующем примере используются логические операторы `And` и `Or` в предложении `Where`.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
