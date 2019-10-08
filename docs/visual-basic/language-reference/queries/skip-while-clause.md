---
title: Предложение Skip While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 7f37a6fa1c9ba7fdf7978ac6853e4c2985bf72e7
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004708"
---
# <a name="skip-while-clause-visual-basic"></a>Предложение Skip While (Visual Basic)
Пропускает элементы в коллекции, если заданное условие имеет значение `true`, и возвращает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`expression`|Обязательный. Выражение, представляющее условие для проверки элементов. Выражение должно возвращать значение `Boolean` или функциональный эквивалент, например `Integer` для оценки как `Boolean`.|  
  
## <a name="remarks"></a>Примечания  
 Предложение `Skip While` обходит элементы из начала результата запроса до тех пор, пока переданный `expression` возвращает `false`. После `expression` возвращает `false`, запрос возвращает все оставшиеся элементы. @No__t-0 игнорируется для оставшихся результатов.  
  
 Предложение `Skip While` отличается от предложения `Where` тем, что предложение @no__t 2 можно использовать для исключения всех элементов из запроса, которые не соответствуют определенному условию. Предложение `Skip While` исключает элементы только до первого момента, когда условие не будет удовлетворено. Предложение `Skip While` наиболее полезно при работе с упорядоченным результатом запроса.  
  
 Можно обойти определенное количество результатов с начала результата запроса с помощью предложения `Skip`.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется предложение `Skip While` для обхода результатов до тех пор, пока не будет найден первый клиент из США.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
