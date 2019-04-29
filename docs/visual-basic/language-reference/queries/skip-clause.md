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
ms.openlocfilehash: db2d79596895505ddaa7778e831082a94c7ad44e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945253"
---
# <a name="skip-clause-visual-basic"></a>Предложение Skip (Visual Basic)
Пропускает заданное число элементов в коллекции и возвращает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Skip count  
```  
  
## <a name="parts"></a>Части  
 `count`  
 Обязательный. Значение или выражение, результатом является число элементов последовательности, чтобы пропустить.  
  
## <a name="remarks"></a>Примечания  
 `Skip` Предложение вызывает запрос для пропуска элементов в начале списка результатов и возвращает остальные элементы. Количество пропускаемых элементов определяется `count` параметра.  
  
 Можно использовать `Skip` предложение with `Take` предложение можно получить диапазон данных из любого фрагмента запроса. Для этого передайте индекс первого элемента диапазона `Skip` предложение и размер диапазона `Take` предложение.  
  
 При использовании `Skip` предложением запроса, также необходимо убедиться, что результаты возвращаются в порядке, который позволит `Skip` предложение для обхода желаемых результатов. Дополнительные сведения о сортировке результатов запроса, см. в разделе [предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Можно использовать `SkipWhile` предложение, чтобы указать, что только определенные элементы игнорируются, в зависимости от предоставленного условия.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется `Skip` предложение вместе с `Take` предложение, чтобы вернуть данные из запроса на страницах. `GetCustomers` Функция использует `Skip` предложение для пропуска всех клиентов, в списке, пока не указанного начального индекса значение, а также используется `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)
