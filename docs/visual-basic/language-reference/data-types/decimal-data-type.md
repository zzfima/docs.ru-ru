---
title: Тип данных Decimal
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: 6d62bcc1d043b45c0fc30154d9dc633b998f97b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344035"
---
# <a name="decimal-data-type-visual-basic"></a>Тип данных Decimal (Visual Basic)

Содержит 128-разрядные (16-байтные) значения со знаком, представляющие 96-разрядные (12-байтные) целые числа с переменной степенью, кратной 10. Коэффициент масштабирования определяет количество цифр справа от десятичной запятой. Он находится в диапазоне от 0 до 28. С масштабом 0 (без десятичных знаков) максимально возможное значение — +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E + 28). С 28 десятичными разрядами максимальное значение — +/-7.9228162514264337593543950335, а наименьшее ненулевое значение — +/-0,0000000000000000000000000001 (+/-1E-28).

## <a name="remarks"></a>Примечания

Тип данных `Decimal` предоставляет наибольшее количество значащих цифр для числа. Он поддерживает до 29 значащих цифр и может представлять значения, превышающие 7,9228 x 10 ^ 28. Он особенно подходит для вычислений, например финансовых, которые нуждаются в большом количестве цифр, но не могут допускать ошибки округления.

Значение по умолчанию для типа `Decimal` — 0.

## <a name="programming-tips"></a>Советы по программированию

- **Обеспечивают.** `Decimal` не является типом данных с плавающей запятой. Структура `Decimal` содержит двоичное целочисленное значение, а также бит знака и целочисленный коэффициент масштабирования, указывающий, какая часть значения является десятичной дробью. По этой причине `Decimal` числа имеют более точное представление в памяти, чем типы с плавающей запятой (`Single` и `Double`).

- **Производительность.** Тип данных `Decimal` является самым медленным из всех числовых типов. Перед выбором типа данных следует оценить важность точности в соответствии с производительностью.

- **Расширяющие.** Тип данных `Decimal` расширяется до `Single` или `Double`. Это означает, что можно преобразовать `Decimal` в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.

- **Нули в конце.** Visual Basic не сохраняет конечные нули в литерале `Decimal`. Однако `Decimal` переменная сохраняет все конечные нули, полученные при вычислении. Это показано в следующем примере.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  Выходные данные `MsgBox` в предыдущем примере имеют следующий вид:

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **Символы типа.** При добавлении к литералу символа типа литерала `D` производится принудительное приведение литерала к типу данных `Decimal`. При добавлении символа идентификатора типа `@` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Decimal`.

- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="range"></a>Диапазон

 Может потребоваться использовать символ типа `D`, чтобы присвоить большое значение переменной `Decimal` или константе. Это требование обусловлено тем, что компилятор интерпретирует литерал как `Long`, если только символ типа литерала не соответствует литералу, как показано в следующем примере.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

Объявление `bigDec1` не создает переполнение, так как присваиваемое ему значение попадает в диапазон для `Long`. Значение `Long` можно присвоить переменной `Decimal`.

Объявление `bigDec2` создает ошибку переполнения, так как присвоенное ей значение слишком велико для `Long`. Поскольку числовой литерал не может быть интерпретирован в качестве `Long`, его нельзя присвоить переменной `Decimal`.

Для `bigDec3`символьный тип литерала `D` решает проблему, заставляя компилятор интерпретировать литерал как `Decimal`, а не как `Long`.

## <a name="see-also"></a>См. также

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Тип данных Single](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
