---
title: Арифметические операторы в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
ms.openlocfilehash: cd66d08eba973a796472fcbd40a6a84edbbb62ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="arithmetic-operators-in-visual-basic"></a>Арифметические операторы в Visual Basic
Арифметические операторы используются для выполнения многих известных арифметических операций, включая вычисление числовых значений, представленных литералы, переменные, другие выражения, функции и вызовы свойств и константы. Также классифицируются с арифметическими операторами являются операторов сдвига, которые работают на уровне отдельных битов операндов и перетаскивать их битовых шаблонов влево или вправо.  
  
## <a name="arithmetic-operations"></a>Арифметические операции  
 Можно добавить два значения в выражении вместе с [оператор +](../../../../visual-basic/language-reference/operators/addition-operator.md), или вычесть друг от друга с [-оператор (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 Отрицание также использует [-оператор (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), но только с одним операндом, как приведенный ниже пример демонстрирует.  
  
 [!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 Умножение и деление используют [* оператор](../../../../visual-basic/language-reference/operators/multiplication-operator.md) и [-оператор (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)соответственно, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 Используется для возведения в степень [^ оператор](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 Целочисленное деление выполняется с помощью [\ оператора (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). Целочисленное деление возвращает частное, то есть, целое число, представляющее число раз делитель можно разделить на делимое без остатка. Делитель и делимое должны быть целочисленными типами (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, и `ULong`) для этого оператора. Все остальные типы необходимо сначала преобразовать в целочисленный тип. В следующем примере показано целочисленного деления.  
  
 [!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 Арифметический модуль выполняется с помощью [оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md). Этот оператор возвращает остаток после деления делимого целое количество раз. Если делитель и делимое являются целыми типами, возвращенное значение является неотъемлемой частью. Если делитель и делимое являются типами с плавающей запятой, возвращаемое значение также является с плавающей запятой. В следующем примере показано такое поведение.  
  
 [!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### <a name="attempted-division-by-zero"></a>Попытка деления на ноль  
 Деление на ноль приводит к разным результатам, в зависимости от используемых типов данных. В виде раздельных целочисленных значений (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] вызывает <xref:System.DivideByZeroException> исключение. В операции деления на `Decimal` или `Single` тип данных [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] также создает исключение <xref:System.DivideByZeroException> исключение.  
  
 В числе с плавающей запятой разделах `Double` тип данных без вызова исключения, а результатом является член класса, представляющий <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, или <xref:System.Double.NegativeInfinity>, в зависимости от делимого. В следующей таблице перечислены различные результаты попытки деления `Double` значения на ноль.  
  
|Тип данных делимого|Тип данных делителя|Значение делимого|Результат|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> (математически число)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 После перехвата <xref:System.DivideByZeroException> исключения, можно использовать его члены для его обработки. Например <xref:System.Exception.Message%2A> свойство содержит текст сообщения для исключения. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Операции поразрядного сдвига  
 Операция сдвига выполняет арифметический сдвиг битового шаблона. Шаблон содержится в операнд слева, а операнд справа указывает число позиций для сдвига структуры. Можно сдвинуть биты вправо с [>> оператор](../../../../visual-basic/language-reference/operators/right-shift-operator.md) или влево с [<< оператор](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 Тип данных операнда шаблон должен быть `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`. Тип данных операнда количества разрядов сдвига должен быть `Integer` или должен расширяться к `Integer`.  
  
 Арифметический сдвиг не циклической, это означает, что биты, сдвигаемые результата, не подставляются с другой стороны. Позиции битов, освобожденные сдвигом задаются следующим образом:  
  
-   0 для арифметического сдвига влево  
  
-   0 для арифметического сдвига вправо положительного числа  
  
-   0 для арифметического сдвига вправо беззнакового типа данных (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 для арифметического сдвига вправо отрицательного числа (`SByte`, `Short`, `Integer`, или `Long`)  
  
 Приведенный ниже сдвигает `Integer` значение влево и вправо.  
  
 [!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 Арифметические сдвиги никогда не создаются исключения переполнения.  
  
## <a name="bitwise-operations"></a>Поразрядные операции  
 Логические операторы `Not`, `Or`, `And`, и `Xor` также выполняют поразрядные арифметические операции при использовании числовых значений. Дополнительные сведения см. в разделе «Побитовое операции» в [логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Безопасность типа  
 Операнды обычно должен быть того же типа. Например, если сложение с `Integer` переменной, добавьте ее в другой `Integer` переменной и следует назначить результат переменной типа `Integer` также.  
  
 Один из способов обеспечения типобезопасного кода является использование [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Если задать `Option Strict On`, Visual Basic автоматически выполняет *типобезопасный* преобразования. Например, при попытке добавить `Integer` переменной `Double` переменной и присвойте значение `Double` переменных, операция проходит нормально, так как `Integer` значение можно преобразовать в `Double` без потери данных. Небезопасный тип преобразования, с другой стороны, вызывают ошибку компилятора с `Option Strict On`. Например, при попытке добавить `Integer` переменной `Double` переменную и присвойте значение `Integer` переменной, компилятор выдает ошибку, так как `Double` переменной не может быть неявно преобразован к типу `Integer`.  
  
 Если задать `Option Strict Off`, однако позволяет Visual Basic неявные сужающие преобразования вступили в силу, хотя они могут привести к потере данных или точности. По этой причине мы рекомендуем использовать `Option Strict On` при написании кода в рабочей среде. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>См. также  
 [Арифметические операторы](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Операторы сдвига битов](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
