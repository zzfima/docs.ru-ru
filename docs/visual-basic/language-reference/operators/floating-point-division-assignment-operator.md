---
title: Оператор /= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: b4855e8270a329f9345339060a323b5ca9cd9792
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592175"
---
# <a name="-operator-visual-basic"></a>Оператор /= (Visual Basic)
Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей запятой переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательный. Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент в левой части оператора `/=` может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `/=` вначале делит значение переменной или свойства (в левой части оператора) на значение выражения (в правой части оператора), равное. Затем оператор присваивает результат операции с плавающей запятой переменной или свойству.  
  
 Эта инструкция присваивает значение `Double` переменной или свойству слева. Если `Option Strict` равно `On`, `variableorproperty` должно быть `Double`. Если `Option Strict` равно `Off`, Visual Basic выполняет неявное преобразование и присваивает полученное значение `variableorproperty` с возможной ошибкой во время выполнения. Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [Option](../../../visual-basic/language-reference/statements/option-strict-statement.md)parallelism.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Перегрузка оператора `/` влияет на поведение оператора `/=`. Если в коде используется `/=` для класса или структуры, которая перегружает `/`, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `/=` используется для деления одной переменной `Integer` на вторую и присваивания значения частного для первой переменной.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также

- [Оператор/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [\\ = оператор](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
