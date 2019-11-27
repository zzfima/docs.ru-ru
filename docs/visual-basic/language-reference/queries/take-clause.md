---
title: Предложение Take
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 3082954ef84560ccb70f7a47cd3532f622829392
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349637"
---
# <a name="take-clause-visual-basic"></a>Предложение Take (Visual Basic)
Возвращает указанное число идущих подряд элементов с начала коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>Части  
 `count`  
 Обязательно. Значение или выражение, результатом которого является число возвращаемых элементов последовательности.  
  
## <a name="remarks"></a>Примечания  
 Предложение `Take` вызывает включение в запрос указанного числа смежных элементов из начала списка результатов. Число включаемых элементов задается параметром `count`.  
  
 Можно использовать предложение `Take` с предложением `Skip`, чтобы получить диапазон данных из любого сегмента запроса. Для этого передайте индекс первого элемента диапазона в предложение `Skip` и размер диапазона в предложение `Take`. В этом случае предложение `Take` должно быть указано после предложения `Skip`.  
  
 При использовании предложения `Take` в запросе может также потребоваться убедиться, что результаты возвращены в порядке, который позволит предложению `Take` включить предполагаемые результаты. Дополнительные сведения о упорядочении результатов запроса см. в разделе [предложение ORDER BY](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Можно использовать предложение `TakeWhile`, чтобы указать, что возвращаются только определенные элементы, в зависимости от указанного условия.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется предложение `Take` вместе с предложением `Skip` для возврата данных из запроса на страницах. Функция "клиенты" использует предложение `Skip` для обхода клиентов в списке до получения значения начального индекса и использует предложение `Take` для возврата страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Предложение Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
