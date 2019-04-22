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
ms.openlocfilehash: b127c50f3319d4fe7c4890fc3bffb295baa37466
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840176"
---
# <a name="mod-operator-visual-basic"></a>Оператор Mod (Visual Basic)
Делит два числа и возвращает только остаток.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a>Части  
 `number1`  
 Обязательный. Произвольное числовое выражение.  
  
 `number2`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 все числовые типы. Сюда входят типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="result"></a>Результат

Результатом является остаток `number1` делится `number2`. Например, выражение `14 Mod 4` равно 2.  

> [!NOTE]
> Есть разница между *остаток* и *модуля* в математике дает различные результаты для отрицательных чисел. `Mod` Оператор в Visual Basic .NET Framework `op_Modulus` оператор и базовым [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) инструкции IL, все операции остатка.

Результат `Mod` операция сохраняет со знаком делимого, `number1`, и поэтому он может быть положительным или отрицательным. Результат всегда находится в диапазоне (-`number2`, `number2`), монопольная. Пример:

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
 Если параметр `number1` или `number2` — это значение с плавающей запятой с плавающей запятой остаток от деления возвращается. Тип данных результата — это наименьший тип данных, который может содержать все возможные значения, возникающие в результате деления с типами данных `number1` и `number2`.  
  
 Если `number1` или `number2` принимает значение [ничего не](../../../visual-basic/language-reference/nothing.md), он интерпретируется как ноль.  
  
 Связанные операторы включают в себя следующее:  
  
-   [\ Оператора (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) возвращает целочисленное частное от деления. Например, выражение `14 \ 4` равен 3.  
  
-   [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) возвращает полное частное, включая остаток, как число с плавающей запятой. Например, выражение `14 / 4` принимает значение 3.5.  
  
## <a name="attempted-division-by-zero"></a>Попытка деления на ноль  
 Если `number2` оказался равным нулю, поведение `Mod` оператора зависит от типа данных операндов. Создает целочисленного деления <xref:System.DivideByZeroException> исключение. Возвращает деления с плавающей запятой <xref:System.Double.NaN>.  
  
## <a name="equivalent-formula"></a>Аналогичной формулы  
 Выражение `a Mod b` является эквивалентом для любой из следующих формул:  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a>С плавающей запятой неточности  
 При работе с числами с плавающей запятой, помните, что они не всегда имеют точное десятичное представление в памяти. Это может привести к непредвиденным результатам определенных операций, таких как сравнения значений и `Mod` оператор. Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="overloading"></a>Перегрузка  
 `Mod` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение. Если код применяет `Mod` к экземпляру класса или структуры, которая включает в себя такие перегрузки, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Mod` оператор деления двух чисел и возвращает только остаток. Если оба числа число с плавающей запятой, результатом является числом с плавающей запятой, представляющее остаток.  
  
 [!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано возможная неточность операндов с плавающей запятой. В первой инструкции, операнды имеют `Double`, и 0,2 является периодической бесконечной двоичной дробью, сохраненное значение 0,20000000000000001. Во втором операторе символа типа литерала `D` приводит оба операнда для `Decimal`, и 0,2 имеет точное представление.  
  
 [!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [\ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
