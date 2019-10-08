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
ms.openlocfilehash: e8d3e38261a04c4d29faab351d24d6710413b09a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004790"
---
# <a name="distinct-clause-visual-basic"></a>Предложение Distinct (Visual Basic)
Ограничивают значения текущей переменной диапазона, чтобы исключить дублирующиеся значения в последующих предложениях запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>Примечания  
 Чтобы получить список уникальных элементов, можно использовать предложение `Distinct`. Предложение `Distinct` приводит к тому, что запрос пропускает дублирующиеся результаты запроса. Предложение `Distinct` применяется к повторяющимися значениям для всех полей возврата, указанных в предложении `Select`. Если не указано предложение `Select`, предложение `Distinct` применяется к переменной диапазона для запроса, указанного в предложении `From`. Если переменная диапазона не является неизменяемым типом, запрос будет игнорировать только результат запроса, если все элементы типа соответствуют существующему результату запроса.  
  
## <a name="example"></a>Пример  
 Следующее выражение запроса соединяет список клиентов и список заказов клиентов. Предложение `Distinct` включено для возврата списка уникальных имен клиентов и дат заказов.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
