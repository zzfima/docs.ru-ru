---
title: Предложение Skip (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 508f3c094df4c834305bcb4a78223c1cee82b1c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 `Skip` Предложение вызывает запрос для пропуска элементов в начале списка результатов и возвращает остальные элементы. Число пропускаемых элементов определяется `count` параметра.  
  
 Можно использовать `Skip` предложение with `Take` предложение для возврата диапазона данных из любого сегмента запроса. Для этого передайте индекс первого элемента диапазона `Skip` предложение и размер диапазона `Take` предложения.  
  
 При использовании `Skip` предложения в запросе могут также необходимо убедиться, что результаты возвращаются в порядке, который позволит `Skip` предложение для обхода желаемых результатов. Дополнительные сведения о сортировке результатов запроса см. в разделе [предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Можно использовать `SkipWhile` предложений, чтобы указать, что только определенные элементы игнорируются в зависимости от предоставленного условия.  
  
## <a name="example"></a>Пример  
 Следующий пример кода использует `Skip` предложение вместе с `Take` предложение для возврата данных из запроса на страницах. `GetCustomers` Функция использует `Skip` предложение для пропуска всех клиентов в списке, пока указанного начального индекса значение, а также используется `Take` предложение для возвращения страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)
