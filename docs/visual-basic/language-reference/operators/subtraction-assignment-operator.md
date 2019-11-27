---
title: Оператор -=
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: 44cb226d64e9f0b86c6566eb25fbafd6323a6d4c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347812"
---
# <a name="--operator-visual-basic"></a>Оператор -= (Visual Basic)
Вычитает значение выражения из значения переменной или свойства и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательно. Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательно. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент в левой части оператора `-=` может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `-=` вначале вычитает значение выражения (в правой части оператора) из значения переменной или свойства (в левой части оператора) (). Затем оператор присваивает результат этой операции переменной или свойству.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор-operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка оператора `-` влияет на поведение оператора `-=`. Если в коде используется `-=` в классе или структуре, которая перегружает `-`, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `-=` используется для вычитания одной `Integer`ной переменной из другой и присвоить результат второй переменной.  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>См. также

- [Оператор-operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
