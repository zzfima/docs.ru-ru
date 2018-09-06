---
title: Тип данных Decimal (Visual Basic)
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
ms.openlocfilehash: ffc1cd141ba624d2ce26e4b1c070431ff0ddd6fe
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44036198"
---
# <a name="decimal-data-type-visual-basic"></a>Тип данных Decimal (Visual Basic)
Содержит знаком, 128 бит (16-байтные) значения, представляющие 96-разрядного (12-байтные) целые числа с переменной степенью 10. Коэффициент масштабирования указывает число цифр справа от десятичного разделителя; она в диапазоне от 0 до 28. С масштабом 0 (без десятичных разрядов), наибольшее возможное значение равно +/-79,228,162,514,264,337,593,543,950,335 (+/-7 .9228162514264337593543950335E + 28). Наибольшее значение равно +/-7,9228162514264337593543950335 с 28 десятичных разрядов и наименьшее ненулевое значение равно +/-0,0000000000000000000000000001, элемента (+/-1E-28).  
  
## <a name="remarks"></a>Примечания  
 `Decimal` Тип данных предоставляет наибольшее количество значащих цифр для числа. Он поддерживает до 29 значащих цифр и может представлять значения, превышающие 7,9 228 x 10 ^ 28. Это особенно хорошо подходит для вычислений, такие как финансовые, который требуется большое количество цифр, но не допускает ошибки округления.  
  
 Значение по умолчанию для типа `Decimal` — 0.  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Точность.** `Decimal` не является типом данных с плавающей запятой. `Decimal` Структура содержит значение двоичное целое число, а также бита знака и целое число, указывающее, какая часть значения является десятичной дробью коэффициент масштабирования. По этой причине `Decimal` числа имеют более точное представление в памяти, чем типы с плавающей запятой (`Single` и `Double`).  
  
-   **Производительность.** `Decimal` Тип данных является самым медленным всех числовых типов. Следует взвесить важность точности с производительностью, прежде чем выбрать тип данных.  
  
-   **Расширяющие.** `Decimal` Тип данных можно расширить до `Single` или `Double`. Это означает, что вы можете преобразовать `Decimal` ни с одной из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
-   **Замыкающие нули.** Visual Basic не хранит конечные нули в `Decimal` литерала. Тем не менее `Decimal` переменная сохраняет любые конечные нули, полученные в результате вычислений. Это показано в следующем примере.  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     Выходные данные `MsgBox` в предыдущем примере выглядит следующим образом:  
  
     D1 = 2.375, d2 = 1.625 d3 = 4.000 d4 = 4  
  
-   **Символы типа.** При добавлении к литералу символа типа литерала `D` производится принудительное приведение литерала к типу данных `Decimal`. При добавлении символа идентификатора типа `@` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Decimal`.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Decimal?displayProperty=nameWithType>.  
  
## <a name="range"></a>Диапазон  
 Может потребоваться использовать `D` символ, чтобы назначить большое значение для типа `Decimal` переменная или константа. Это требование обусловлено тем, компилятор интерпретирует литерал как `Long` Если знак типа литерала следует литерал, как показано в следующем примере.  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 Объявление `bigDec1` не приводит к переполнению, так как значение, которое ему присваивается попадает в диапазон для `Long`. `Long` Значения могут быть назначены `Decimal` переменной.  
  
 Объявление `bigDec2` возникает ошибка переполнения, поскольку, ему присваивается значение слишком велико для `Long`. Так как сначала числовой литерал не может интерпретироваться как `Long`, он не может быть назначен `Decimal` переменной.  
  
 Для `bigDec3`, знак типа литерала `D` решает проблему, заставив компилятор литерал как `Decimal` вместо как `Long`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Decimal?displayProperty=nameWithType>  
 <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>  
 <xref:System.Math.Round%2A?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/index.md)  
 [Тип данных Single](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
