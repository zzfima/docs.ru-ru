---
title: "Предложение Let (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70e47517a62f58dcababd31c26277417b62eab66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-visual-basic"></a>Предложение Let (Visual Basic)
Вычисляет значение и присваивает его новой переменной в запросе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`variable`|Обязательный. Псевдоним, который может использоваться для ссылки на результаты предоставленного выражения.|  
|`expression`|Обязательный. Выражение, оценивается и назначен переменной.|  
  
## <a name="remarks"></a>Примечания  
 `Let` Предложение позволяет вычислить значения для каждого результата запроса и ссылаться на них с помощью псевдонима. Псевдоним может использоваться в других предложениях, таких как `Where` предложения. `Let` Предложение позволяет создавать инструкции запроса, который является более удобным для чтения, поскольку можно указать псевдоним для условия выражения, включенного в запрос и заменять этот псевдоним при каждом условия выражения.  
  
 Можно включить любое количество `variable` и `expression` назначения в `Let` предложения. Каждое назначение разделяются точкой с запятой (,).  
  
## <a name="example"></a>Пример  
 Следующий пример кода использует `Let` предложение для вычисления 10% скидки на продукты.  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
