---
title: Предложение Skip While
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 47703e445865435f5bf5312c3fe41833ac21aa3f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333145"
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
|`expression`|Обязательно. Выражение, представляющее условие для проверки элементов. Выражение должно возвращать `Boolean` значение или функциональный эквивалент, например `Integer`, который вычисляется как `Boolean`.|  
  
## <a name="remarks"></a>Примечания  
 Предложение `Skip While` обходит элементы из начала результата запроса до тех пор, пока переданный `expression` не возвратит `false`. После того как `expression` возвращает `false`, запрос возвращает все оставшиеся элементы. Для оставшихся результатов `expression` игнорируется.  
  
 Предложение `Skip While` отличается от предложения `Where` в том, что предложение `Where` можно использовать для исключения всех элементов из запроса, которые не соответствуют определенному условию. Предложение `Skip While` исключает элементы только до первого момента, когда условие не будет удовлетворено. Предложение `Skip While` наиболее полезно при работе с упорядоченным результатом запроса.  
  
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
