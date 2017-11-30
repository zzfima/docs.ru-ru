---
title: "Предложение Take While (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c8add6c55bb9353bac3489e68f497cb32785aad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
|`expression`|Обязательный. Выражение, представляющее условие для проверки элементов. Выражение должно возвращать `Boolean` значение или функциональный эквивалент, таких как `Integer` будут вычисляться как `Boolean`.|  
  
## <a name="remarks"></a>Примечания  
 `Take While` Предложение включает элементы от начала результата запроса до предоставленного `expression` возвращает `false`. После `expression` возвращает `false`, запрос будет выполнять все оставшиеся элементы. `expression` Игнорируется для оставшихся результатов.  
  
 `Take While` Предложение отличается от `Where` предложение в том, что `Where` предложение может использоваться для включения всех элементов из запроса, которые удовлетворяют определенному условию. `Take While` Предложение включает элементы только до момента первого, условие не выполняется. `Take While` Предложение наиболее полезно при работе с упорядоченным результатом запроса.  
  
## <a name="example"></a>Пример  
 Следующий пример кода использует `Take While` предложение для получения результатов, пока не будет найден первый клиент без заказов.  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)  
 [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
