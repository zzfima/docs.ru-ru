---
title: Предложение Take (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 0dddb411af1b4ee269e091c07553a94589d90b2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="take-clause-visual-basic"></a>Предложение Take (Visual Basic)
Возвращает указанное число идущих подряд элементов с начала коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Take count  
```  
  
## <a name="parts"></a>Части  
 `count`  
 Обязательно. Значение или выражение, результатом является число элементов последовательности для возврата.  
  
## <a name="remarks"></a>Примечания  
 `Take` Предложение вызывает запрос, чтобы включить заданное число смежных элементов от начала списка результатов. Число элементов для включения определяется `count` параметра.  
  
 Можно использовать `Take` предложение with `Skip` предложение для возврата диапазона данных из любого сегмента запроса. Для этого передайте индекс первого элемента диапазона `Skip` предложение и размер диапазона `Take` предложения. В этом случае `Take` предложение должно быть указано после `Skip` предложения.  
  
 При использовании `Take` предложения в запросе могут также необходимо убедиться, что результаты возвращаются в порядке, который позволит `Take` предложений, чтобы включить нужные результаты. Дополнительные сведения о сортировке результатов запроса см. в разделе [предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Можно использовать `TakeWhile` предложений, чтобы указать, что возвращаться только некоторые элементы, в зависимости от предоставленного условия.  
  
## <a name="example"></a>Пример  
 Следующий пример кода использует `Take` предложение вместе с `Skip` предложение для возврата данных из запроса на страницах. Использует функцию GetCustomers `Skip` предложение для пропуска всех клиентов в списке, пока указанного начального индекса значение, а также используется `Take` предложение для возвращения страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Предложение Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
