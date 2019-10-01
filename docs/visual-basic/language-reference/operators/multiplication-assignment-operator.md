---
title: Оператор *= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 47d3239af6ff24501e6babc23c0db4103c477796
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701069"
---
# <a name="-operator-visual-basic"></a>Оператор *= (Visual Basic)
Умножает значение переменной или свойства на значение выражения и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательный. Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент в левой части оператора `*=` может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `*=` вначале умножает значение выражения (в правой части оператора) на значение переменной или свойства (в левой части оператора) (слева). Затем оператор присваивает результат этой операции переменной или свойству.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор *](../../../visual-basic/language-reference/operators/multiplication-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка оператора `*` влияет на поведение оператора `*=`. Если в коде используется `*=` для класса или структуры, которая перегружает `*`, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `*=` используется для умножения одной переменной `Integer` на вторую и присваивания результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Оператор *](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
