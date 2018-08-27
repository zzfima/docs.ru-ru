---
title: Предложение Skip (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 615f98bf36d29c1f269d6866b1232ad33a5ae2f2
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925441"
---
# <a name="skip-clause-visual-basic"></a>Предложение Skip (Visual Basic)
Пропускает заданное число элементов в коллекции и возвращает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Skip count  
```  
  
## <a name="parts"></a>Части  
 `count`  
 Обязательно. Значение или выражение, результатом является число элементов последовательности, чтобы пропустить.  
  
## <a name="remarks"></a>Примечания  
 `Skip` Предложение вызывает запрос для пропуска элементов в начале списка результатов и возвращает остальные элементы. Количество пропускаемых элементов определяется `count` параметра.  
  
 Можно использовать `Skip` предложение with `Take` предложение можно получить диапазон данных из любого фрагмента запроса. Для этого передайте индекс первого элемента диапазона `Skip` предложение и размер диапазона `Take` предложение.  
  
 При использовании `Skip` предложением запроса, также необходимо убедиться, что результаты возвращаются в порядке, который позволит `Skip` предложение для обхода желаемых результатов. Дополнительные сведения о сортировке результатов запроса, см. в разделе [предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Можно использовать `SkipWhile` предложение, чтобы указать, что только определенные элементы игнорируются, в зависимости от предоставленного условия.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется `Skip` предложение вместе с `Take` предложение, чтобы вернуть данные из запроса на страницах. `GetCustomers` Функция использует `Skip` предложение для пропуска всех клиентов, в списке, пока не указанного начального индекса значение, а также используется `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/index.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)
