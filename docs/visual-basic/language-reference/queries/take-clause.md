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
ms.openlocfilehash: 32a4c7fd7f1e2f6fe640f3f53f15579f014759d5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004714"
---
# <a name="take-clause-visual-basic"></a>Предложение Take (Visual Basic)
Возвращает указанное число идущих подряд элементов с начала коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>Части  
 `count`  
 Обязательный. Значение или выражение, результатом которого является число возвращаемых элементов последовательности.  
  
## <a name="remarks"></a>Примечания  
 Предложение `Take` приводит к тому, что запрос включает указанное число смежных элементов из начала списка результатов. Число включаемых элементов задается параметром `count`.  
  
 Предложение `Take` можно использовать с предложением `Skip` для возврата диапазона данных из любого сегмента запроса. Для этого передайте индекс первого элемента диапазона в предложение `Skip` и размер диапазона в предложение `Take`. В этом случае предложение `Take` должно быть указано после предложения `Skip`.  
  
 При использовании предложения `Take` в запросе может также потребоваться убедиться, что результаты возвращены в порядке, который позволит использовать предложение `Take` для включения предполагаемых результатов. Дополнительные сведения о упорядочении результатов запроса см. в разделе [предложение ORDER BY](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
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
