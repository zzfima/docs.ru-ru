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
ms.openlocfilehash: 88166a040823cfefe623f672e556c364d652a7fc
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004729"
---
# <a name="let-clause-visual-basic"></a>Предложение Let (Visual Basic)
Выполняет вычисление значения и присваивает его новой переменной в запросе.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`variable`|Обязательное. Псевдоним, который может использоваться для ссылки на результаты предоставляемого выражения.|  
|`expression`|Обязательное. Выражение, которое будет вычислено и назначено указанной переменной.|  
  
## <a name="remarks"></a>Примечания  
 Предложение `Let` позволяет вычислять значения для каждого результата запроса и ссылаться на них с помощью псевдонима. Псевдоним можно использовать в других предложениях, например в предложении `Where`. Предложение `Let` позволяет создать инструкцию запроса, которая будет удобна для чтения, поскольку можно указать псевдоним для предложения выражения, включенного в запрос, и заменить его при каждом использовании предложения Expression.  
  
 В предложение `Let` можно включить любое количество `variable` и `expression` назначений. Разделяйте каждое назначение запятой (,).  
  
## <a name="example"></a>Пример  
 В следующем примере кода предложение `Let` используется для расчета скидки на 10% для продуктов.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>См. также:

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
