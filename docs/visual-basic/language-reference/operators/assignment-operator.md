---
title: "= Оператор (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
dev_langs:
- VB
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 47b69a908f12ec36daf2848da6ee4b04895fd3a4
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-visual-basic"></a>Оператор = (Visual Basic)
Присваивает значение переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
variableorproperty = value  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Любой доступный для записи переменная или любое свойство.  
  
 `value`  
 Любой литерал, константа или выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент слева от знака равенства (`=`) может быть простой скалярной переменной, свойства или элемента массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). `=` Оператор присваивает значение справа переменной или свойству, расположенному слева.  
  
> [!NOTE]
>  `=` Оператор также используется как оператор сравнения. Дополнительные сведения см. в разделе [операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Перегрузка  
 `=` Оператор может быть перегружен только как оператор сравнения, а не как оператор присваивания. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор присваивания. Присваивается значение справа переменной слева.  
  
 [!code-vb[VbVbalrOperators №&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [& =-Оператор](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [* =-Оператор](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)   
 [+= Оператор](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)   
 [-= Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [/ =-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [\\= Оператор](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [^ =-Оператор](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)   
 [Инструкции](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Только для чтения](../../../visual-basic/language-reference/modifiers/readonly.md)   
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

