---
title: Предложение Distinct (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 4b0ce12f6361d3dc6e5cc3601e96fc3a9bcf3841
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="distinct-clause-visual-basic"></a>Предложение Distinct (Visual Basic)
Ограничивает значения текущей переменной диапазона, чтобы исключить повторяющиеся значения в предложениях последующих запросов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Distinct` предложение, чтобы получить список уникальных элементов. `Distinct` Предложение вызывает запрос, чтобы игнорировать повторяющиеся результаты запроса. `Distinct` Предложение распространяется на повторяющиеся значения все возвращаемые поля, заданные параметром `Select` предложения. Если не `Select` указано предложение `Distinct` предложение применяется к переменной диапазона для запроса, указанного в `From` предложения. Если переменная диапазона не является неизменяемым типом, запрос только игнорировать результата запроса, если все члены типа соответствуют существующим результатам запроса.  
  
## <a name="example"></a>Пример  
 Следующее выражение запроса соединяет список клиентов и список заказов клиента. `Distinct` Предложение включена, чтобы получить список уникальных имен клиентов и порядок даты.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
