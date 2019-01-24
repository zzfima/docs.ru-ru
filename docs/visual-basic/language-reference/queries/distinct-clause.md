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
ms.openlocfilehash: 3761f6d6ba97e7f1a824b70b18a50dae820c7e51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710044"
---
# <a name="distinct-clause-visual-basic"></a>Предложение Distinct (Visual Basic)
Ограничивает значения текущей переменной диапазона, чтобы исключить повторяющиеся значения в предложениях последующих запросов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Distinct` предложение, чтобы получить список уникальных элементов. `Distinct` Предложение вызывает игнорировать повторяющиеся результаты запроса. `Distinct` Предложение применяется к повторяющимся значениям для все возвращаемые поля, заданные параметром `Select` предложение. Если не `Select` указано предложение, `Distinct` предложение применяется к переменной диапазона для запроса, указанного в `From` предложение. Если переменной диапазона не является неизменяемым типом, запрос только игнорирует результат запроса, если все члены типа соответствуют существующим результатам запроса.  
  
## <a name="example"></a>Пример  
 Следующее выражение запроса объединяет список клиентов и список заказов клиентов. `Distinct` Предложение включена, чтобы получить список уникальных имен клиентов и порядок даты.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a>См. также
- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
