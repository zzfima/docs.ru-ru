---
title: "Предложение Skip While (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f447a6d9b2eb58fa546ced6c96b987caf68fb3e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="skip-while-clause-visual-basic"></a>Предложение Skip While (Visual Basic)
Пропускает элементы в коллекции, если заданное условие имеет значение `true`, и возвращает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`expression`|Обязательный. Выражение, представляющее условие для проверки элементов. Выражение должно возвращать `Boolean` значение или функциональный эквивалент, таких как `Integer` будут вычисляться как `Boolean`.|  
  
## <a name="remarks"></a>Примечания  
 `Skip While` Предложение пропускает элементы от начала результата запроса до предоставленного `expression` возвращает `false`. После `expression` возвращает `false`, запрос возвращает все оставшиеся элементы. `expression` Игнорируется для оставшихся результатов.  
  
 `Skip While` Предложение отличается от `Where` предложение в том, что `Where` предложение может использоваться, чтобы исключить все элементы из запроса, который не удовлетворяют определенному условию. `Skip While` Предложение исключает элементы только до момента первого, условие не выполняется. `Skip While` Предложение наиболее полезно при работе с упорядоченным результатом запроса.  
  
 Можно пропустить определенное количество результатов в начале результата запроса с помощью `Skip` предложения.  
  
## <a name="example"></a>Пример  
 Следующий пример кода использует `Skip While` предложение для обхода результатов, пока не будет найден первого заказчика из США.  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложение Skip](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
