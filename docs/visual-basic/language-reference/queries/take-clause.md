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
ms.openlocfilehash: bfaccf470d93a6a72451e7ad8b41e8dbb1171c71
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932474"
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
 `Take` Предложение вызывает запрос, чтобы включить указанное число идущих подряд элементов с начала списка результатов. Число элементов для включения задается `count` параметра.  
  
 Можно использовать `Take` предложение with `Skip` предложение можно получить диапазон данных из любого фрагмента запроса. Для этого передайте индекс первого элемента диапазона `Skip` предложение и размер диапазона `Take` предложение. В этом случае `Take` предложение должно быть указано после `Skip` предложение.  
  
 При использовании `Take` предложением запроса, также необходимо убедиться, что результаты возвращаются в порядке, который позволит `Take` предложение для включения нужных результатов. Дополнительные сведения о сортировке результатов запроса, см. в разделе [предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Можно использовать `TakeWhile` предложение, чтобы указать, что возвращаться только определенные элементы, в зависимости от предоставленного условия.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется `Take` предложение вместе с `Skip` предложение, чтобы вернуть данные из запроса на страницах. GetCustomers функция использует `Skip` предложение для пропуска всех клиентов, в списке, пока не указанного начального индекса значение, а также используется `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/index.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Предложение Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
