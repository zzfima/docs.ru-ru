---
title: Предложение Take While
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 23b7c84a9f896161a66059fcb1f30753d3b863d5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347100"
---
# <a name="take-while-clause-visual-basic"></a>Предложение Take While (Visual Basic)
Включает элементы в коллекцию, если заданное условие имеет значение `true`, и пропускает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`expression`|Обязательно. Выражение, представляющее условие для проверки элементов. Выражение должно возвращать `Boolean` значение или функциональный эквивалент, например `Integer`, который вычисляется как `Boolean`.|  
  
## <a name="remarks"></a>Примечания  
 Предложение `Take While` включает элементы из начала результата запроса до тех пор, пока переданный `expression` не возвратит `false`. После того как `expression` возвращает `false`, запрос будет обходить все оставшиеся элементы. Для оставшихся результатов `expression` игнорируется.  
  
 Предложение `Take While` отличается от предложения `Where` в том, что предложение `Where` можно использовать для включения всех элементов из запроса, удовлетворяющего определенному условию. Предложение `Take While` включает элементы только до первого момента, когда условие не будет удовлетворено. Предложение `Take While` наиболее полезно при работе с упорядоченным результатом запроса.  
  
## <a name="example"></a>Пример  
 В следующем примере кода предложение `Take While` используется для получения результатов до тех пор, пока не будет найден первый клиент без заказов.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)
- [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
