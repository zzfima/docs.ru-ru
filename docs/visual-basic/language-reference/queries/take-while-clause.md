---
title: Предложение Take While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 3dfb70066d88683e60f3bf4199441ab3024ef36c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565115"
---
# <a name="take-while-clause-visual-basic"></a>Предложение Take While (Visual Basic)
Включает элементы в коллекцию, если заданное условие имеет значение `true`, и пропускает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Take While expression  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`expression`|Обязательный. Выражение, которое представляет условие для проверки элементов. Выражение должно возвращать `Boolean` значение или функциональный эквивалент, например `Integer` для оценки в качестве `Boolean`.|  
  
## <a name="remarks"></a>Примечания  
 `Take While` Предложение включает элементы от начала результата запроса до предоставленного `expression` возвращает `false`. После `expression` возвращает `false`, запрос будет выполнять все оставшиеся элементы. `expression` Игнорируется для оставшихся результатов.  
  
 `Take While` Предложение отличается от `Where` предложение, в который `Where` предложение может использоваться для включения всех элементов из запроса, которые удовлетворяют определенному условию. `Take While` Предложение включает элементы только до момента первого, условие не выполняется. `Take While` Предложение наиболее полезно при работе с упорядоченным результатом запроса.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется `Take While` предложение для получения результатов, пока не будет найден первый клиент без заказов.  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a>См. также
- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)
- [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
