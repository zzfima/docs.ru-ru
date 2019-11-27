---
title: Оператор /=
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
ms.openlocfilehash: a8a031e968df90496a4e263ae78d47045ccdc923
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331038"
---
# <a name="-operator-visual-basic"></a>Оператор /= (Visual Basic)
Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей запятой переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательно. Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательно. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент в левой части оператора `/=` может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `/=` сначала делит значение переменной или свойства (в левой части оператора) на значение выражения (в правой части оператора). в противном случае. Затем оператор присваивает результат операции с плавающей запятой переменной или свойству.  
  
 Эта инструкция присваивает значение `Double` переменной или свойству слева. Если `Option Strict` `On`, `variableorproperty` должен быть `Double`. Если `Option Strict` имеет `Off`, Visual Basic выполняет неявное преобразование и присваивает результирующее значение `variableorproperty`, возкак возможную ошибку во время выполнения. Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [Option](../../../visual-basic/language-reference/statements/option-strict-statement.md)parallelism.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Перегрузка оператора `/` влияет на поведение оператора `/=`. Если в коде используется `/=` в классе или структуре, которая перегружает `/`, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `/=` используется для деления одной `Integer` переменной на вторую и присваивания значения частного для первой переменной.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также

- [Оператор/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [Оператор \\=](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
