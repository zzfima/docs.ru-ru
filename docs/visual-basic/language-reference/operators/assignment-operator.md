---
title: "Оператор = (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 230005640b2b494e5413b14ba13a7cb82ee9f22b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>Оператор = (Visual Basic)
Присваивает значение переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Любой доступный для записи переменная или свойство.  
  
 `value`  
 Любой литерал, константу или выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент слева от знака равенства (`=`) может быть простой скалярной переменной, свойством или элемент массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). `=` Оператор присваивает значение справа переменной или свойству слева от него.  
  
> [!NOTE]
>  `=` Оператор также используется в качестве оператора сравнения. Дополнительные сведения см. в разделе [операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Перегрузка  
 `=` Оператор может быть перегружен только как оператор сравнения, а не как оператор присваивания. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 Ниже приведен пример оператора присваивания. Присваивается значение справа переменной слева.  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Оператор *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [Оператор +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [-= Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [/ =-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\\= Оператор](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [Оператор ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
