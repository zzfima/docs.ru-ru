---
title: Арифметические операторы
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
ms.openlocfilehash: 8ded8d7111bd37cf8762a202b728e814aa5a082b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352660"
---
# <a name="arithmetic-operators-in-visual-basic"></a>Арифметические операторы в Visual Basic
Арифметические операторы используются для выполнения многих знакомых арифметических операций, использующих вычисление числовых значений, представленных литералами, переменными, другими выражениями, вызовами функций и свойств и констант. Кроме того, классификация с помощью арифметических операторов — это операторы сдвига в битах, которые действуют на уровне отдельных битов операндов и сдвигаются их битовые шаблоны влево или вправо.  
  
## <a name="arithmetic-operations"></a>Арифметические операции  
 Можно добавить два значения в выражение вместе с [оператором +](../../../../visual-basic/language-reference/operators/addition-operator.md)или вычесть одно из другого с помощью [оператора-operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 Отрицание также использует [оператор-operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), но только с одним операндом, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 При умножении и разделении используются [оператор *](../../../../visual-basic/language-reference/operators/multiplication-operator.md) и [оператор (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)соответственно, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 В возведение в степень используется [оператор ^](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 Целочисленное деление выполняется с помощью [оператора \ (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). Целочисленное деление Возвращает частное, то есть целое число, представляющее количество, которое делитель может разделить на делимое, без учета остатка. Делитель и делимое должны быть целочисленными типами (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`и `ULong`) для этого оператора. Сначала необходимо преобразовать все остальные типы в целочисленный тип. В следующем примере показано целочисленное деление.  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 Арифметическая операция деления выполняется с помощью [оператора MOD](../../../../visual-basic/language-reference/operators/mod-operator.md). Этот оператор возвращает остаток от деления делителя на делимое на целое число раз. Если и делитель, и делим являются целочисленными типами, возвращаемое значение является целочисленным. Если делитель и делимые являются типами с плавающей запятой, возвращаемое значение также будет плавающей запятой. Следующий пример демонстрирует эту ситуацию.  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a>Попыток деления на ноль  
 Деление на ноль приводит к различным результатам в зависимости от используемых типов данных. В целочисленных подразделениях (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`) .NET Framework выдает исключение <xref:System.DivideByZeroException>. В операциях деления с типом данных `Decimal` или `Single` .NET Framework также вызывает исключение <xref:System.DivideByZeroException>.  
  
 В подразделениях с плавающей запятой, включающих тип данных `Double`, исключение не создается, а результатом является член класса, представляющий <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>или <xref:System.Double.NegativeInfinity>в зависимости от делимого. В следующей таблице перечислены различные результаты попытки деления `Double`ного значения на ноль.  
  
|Тип данных делимого|Тип данных делителя|Делимое значение|Результат|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> (не является математически определенным числом)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 При перехвате исключения <xref:System.DivideByZeroException> можно использовать его члены, чтобы помочь в его обработке. Например, свойство <xref:System.Exception.Message%2A> содержит текст сообщения для исключения. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Операции сдвига битов  
 Операция сдвига в битах выполняет арифметический сдвиг для битового шаблона. Шаблон содержится в операнде слева, а операнд справа указывает количество позиций для сдвига шаблона. Можно сдвинуть шаблон вправо с помощью [оператора > >](../../../../visual-basic/language-reference/operators/right-shift-operator.md) или слева с помощью [оператора < <](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 Тип данных операнда шаблона должен быть `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`или `ULong`. Тип данных операнда суммы сдвига должен быть `Integer` или должен расширяться для `Integer`.  
  
 Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец. Позиции битов, освобожденные сдвигом, устанавливаются следующим образом:  
  
- 0 для арифметического сдвига влево  
  
- 0 для арифметического сдвига вправо положительного числа  
  
- 0 для арифметического сдвига вправо неподписанного типа данных (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
- 1 для арифметического сдвига вправо отрицательного числа (`SByte`, `Short`, `Integer`или `Long`)  
  
 В следующем примере значение `Integer` сдвигается влево и вправо.  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 Арифметические сдвиги никогда не создают исключений переполнения.  
  
## <a name="bitwise-operations"></a>Битовые операции  
 Помимо логических операторов, `Not`, `Or`, `And`и `Xor` также выполняют побитовую арифметическую операцию при использовании числовых значений. Дополнительные сведения см. в разделе "битовые операции" в [логических и побитовых операторах в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Безопасность типов  
 Обычно операнды должны иметь один и тот же тип. Например, если вы делаете сложение с переменной `Integer`, то следует добавить ее в другую переменную `Integer`, а также следует присвоить результат переменной типа `Integer`.  
  
 Одним из способов обеспечения хорошей строгой типизации кода является использование [оператора Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Если задано `Option Strict On`, Visual Basic автоматически выполняет преобразования, строго *типизированные* . Например, при попытке добавить переменную `Integer` в переменную `Double` и присвоить значение переменной `Double`, операция будет выполняться обычным образом, так как значение `Integer` может быть преобразовано в `Double` без потери данных. Типы-ненадежные преобразования, с другой стороны, приводят к ошибке компилятора с `Option Strict On`. Например, при попытке добавить переменную `Integer` в переменную `Double` и присвоить значение переменной `Integer`, возникает ошибка компилятора, так как переменная `Double` не может быть неявно преобразована в `Integer`типа.  
  
 Однако если задать `Option Strict Off`, Visual Basic допускает неявные сужающие преобразования, хотя они могут привести к непредвиденной утрате данных или точности. По этой причине рекомендуется использовать `Option Strict On` при написании рабочего кода. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>См. также

- [Арифметические операторы](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Операторы сдвига битов](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
