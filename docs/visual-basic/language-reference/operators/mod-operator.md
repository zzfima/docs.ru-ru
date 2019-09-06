---
title: Оператор Mod (Visual Basic)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: dc1e866836bb7420ffe17210b5be7a5e1d4048d0
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374494"
---
# <a name="mod-operator-visual-basic"></a>Оператор Mod (Visual Basic)

Делит два числа и возвращает только остаток.

## <a name="syntax"></a>Синтаксис

```vb
result = number1 Mod number2
```

## <a name="parts"></a>Части

`result` \
Обязательный. Любая числовая переменная или свойство.

`number1` \
Обязательный. Произвольное числовое выражение.

`number2` \
Обязательный. Произвольное числовое выражение.

## <a name="supported-types"></a>Поддерживаемые типы

все числовые типы. К ним относятся типы без знака и тип с плавающей запятой `Decimal`и.

## <a name="result"></a>Результат

Результат — остаток `number1` `number2`от деления на. Например, выражение `14 Mod 4` принимает значение 2.

> [!NOTE]
> Существует разница между *остатком* и *остатком* в математике с различными результатами для отрицательных чисел. Оператор в Visual Basic, оператор .NET Framework `op_Modulus` и базовая инструкция [REM](<xref:System.Reflection.Emit.OpCodes.Rem>) Il выполняют операцию остатка. `Mod`

Результат `Mod` операции удерживает знак делимого, `number1`и поэтому он может быть положительным или отрицательным. Результат всегда находится в диапазоне (-`number2`, `number2`), исключающем. Например:

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a>Примечания

`number1` Если или `number2` является значением с плавающей запятой, то возвращается остаток от деления с плавающей запятой. Тип данных результата является наименьшим типом данных, который может содержать все возможные значения, являющиеся результатом деления с типами `number1` данных и. `number2`

Если `number1` или`number2` имеет значение [Nothing](../../../visual-basic/language-reference/nothing.md), оно считается нулевым.

К связанным операторам относятся следующие.

- [Оператор \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) возвращает целочисленное частное от деления. Например, выражение `14 \ 4` принимает значение 3.

- [Оператор/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) возвращает полное частное, включая остаток, в виде числа с плавающей запятой. Например, результатом вычисления выражения `14 / 4` является 3,5.

## <a name="attempted-division-by-zero"></a>Попыток деления на ноль

Если `number2` значение равно нулю, поведение `Mod` оператора зависит от типа данных операндов:
- Целочисленное деление вызывает исключение <xref:System.DivideByZeroException> , если `number2` не может быть определено во время компиляции и вызывает ошибку `BC30542 Division by zero occurred while evaluating this expression` во время компиляции, `number2` если во время компиляции значение равно нулю.
- Деление с плавающей запятой возвращает <xref:System.Double.NaN?displayProperty=nameWithType>.

## <a name="equivalent-formula"></a>Эквивалентная формула

Выражение `a Mod b` эквивалентно любой из следующих формул:

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a>Точность чисел с плавающей запятой

При работе с числами с плавающей запятой Помните, что они не всегда имеют точное десятичное представление в памяти. Это может привести к непредвиденным результатам некоторых операций, таких как сравнение значений и `Mod` оператор. Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).

## <a name="overloading"></a>Перегрузка

Оператор можно перегрузить, то есть класс или структура может переопределить его поведение. `Mod` Если код применяется `Mod` к экземпляру класса или структуры, включающей такую перегрузку, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Пример

В следующем примере `Mod` оператор используется для деления двух чисел и возврата только остатка. Если любое число является числом с плавающей запятой, результатом является число с плавающей запятой, представляющее остаток.

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a>Пример

В следующем примере показана потенциальная неточность операндов с плавающей запятой. В первой инструкции операнды имеют `Double`значение, а 0,2 — бесконечно повторяющуюся двоичную дробь с хранимым значением 0.20000000000000001. Во второй инструкции символ `D` типа литерала принуждает оба операнда к `Decimal`, и 0,2 имеет точное представление.

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Оператор \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
