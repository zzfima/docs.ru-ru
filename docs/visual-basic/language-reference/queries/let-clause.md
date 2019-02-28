---
title: Предложение Let (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 545eefc67d52428470c19b62085fd87927505c7e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972707"
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
|`expression`|Обязательный. Выражение, будут вычисляются и присваиваются переменной.|  
  
## <a name="remarks"></a>Примечания  
 `Let` Предложение позволяет вычислить значения для каждого результат запроса и ссылаться на них с помощью псевдонима. Псевдоним может использоваться в других предложениях, таких как `Where` предложение. `Let` Предложение позволяет создать оператор запроса, который является более удобным для чтения, поскольку можно указать псевдоним для условия выражения, включенного в запрос и заменять этот псевдоним каждый раз, используется предложение выражения.  
  
 Можно включить любое число `variable` и `expression` назначения в `Let` предложение. После каждого назначения следует разделяйте запятыми (,).  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется `Let` предложение для вычисления скидку 10% на продукты.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>См. также
- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
