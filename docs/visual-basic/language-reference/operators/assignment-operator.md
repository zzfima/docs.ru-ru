---
title: Оператор =
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 75f303219b9bf32613989f65f90a9096ef70e02e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350204"
---
# <a name="-operator-visual-basic"></a>Оператор = (Visual Basic)
Присваивает значение переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Любая изменяемая переменная или любое свойство.  
  
 `value`  
 Любой литерал, константа или выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент в левой части знака равенства (`=`) может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). Оператор `=` присваивает значение справа переменной или свойству слева.  
  
> [!NOTE]
> Оператор `=` также используется в качестве оператора сравнения. Дополнительные сведения см. в разделе [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `=` можно перегрузить только как оператор реляционного сравнения, а не как оператор присваивания. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показан оператор присваивания. Значение справа присваивается переменной слева.  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>См. также

- [Оператор &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Оператор *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [Оператор +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [Оператор-= (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [Оператор/= (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Оператор \\=](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Оператор ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
- [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
