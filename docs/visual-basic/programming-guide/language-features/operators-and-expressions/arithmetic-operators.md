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
ms.openlocfilehash: 2bd88b2df91c38d658e46157a9a83ce44ab9f25c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981274"
---
# <a name="arithmetic-operators-in-visual-basic"></a>Арифметические операторы в Visual Basic
Арифметические операторы используются для выполнения многих известных арифметических операций, включая вычисление числовых значений, представленных литералы, переменные, другие выражения, функции и вызовы свойства и константы. Также классифицируются с арифметическими операторами являются операторы поразрядного сдвига, которые работают на уровне отдельных битов операндов и сдвиг их битовых шаблонов влево или вправо.  
  
## <a name="arithmetic-operations"></a>Арифметические операции  
 Вы можете добавить два значения в выражении вместе с [оператором "+"](../../../../visual-basic/language-reference/operators/addition-operator.md), или вычесть единицу из другого и [-оператор (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 Отрицание также использует [-оператор (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), но только с одним операндом, как показано следующем примере.  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 Умножение и деление используйте [* оператор](../../../../visual-basic/language-reference/operators/multiplication-operator.md) и [/ Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md), соответственно, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 Используется для возведения в степень [^ оператор](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 Целочисленное деление выполняется с помощью [\ оператора (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). Целочисленное деление возвращает частное, т. е целое число, представляющее число раз делитель можно разделить без остатка делится делимое. Как делитель, так и делимое должны быть целочисленными типами (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, и `ULong`) для этого оператора. Все другие типы необходимо сначала преобразовать в целочисленный тип. В следующем примере показано целочисленное деление.  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 Арифметический модуль выполняется с помощью [оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md). Этот оператор возвращает остаток после деления делимого целое количество раз. Если как делитель, так и делимое целочисленных типов, возвращаемое значение является неотъемлемой частью. Если делитель и делимое являются типами с плавающей запятой, возвращаемое значение также является с плавающей запятой. В следующем примере показано такое поведение.  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a>Попытка деления на ноль  
 Деление на ноль приводит к разным результатам в зависимости от используемых типов данных. В виде раздельных целочисленных значений (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] вызывает <xref:System.DivideByZeroException> исключение. В операции деления с `Decimal` или `Single` тип данных, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] также выдает <xref:System.DivideByZeroException> исключение.  
  
 В с плавающей запятой виде раздельных значений с использованием `Double` тип данных, исключение не создается, и результатом является член класса, представляющий <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, или <xref:System.Double.NegativeInfinity>в зависимости от делимое. В следующей таблице перечислены различные результаты попытки деления `Double` значение деления на ноль.  
  
|Тип данных делимое|Тип данных делитель|Делимое значение|Результат|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> (не математически число)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 После перехвата <xref:System.DivideByZeroException> исключения, можно использовать его члены для его обработки. Например <xref:System.Exception.Message%2A> свойство содержит текст сообщения для исключения. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Операции сдвига разряда  
 Операция сдвига выполняет арифметический сдвиг битового шаблона. Шаблон содержится в операнде слева, а операнд справа указывает количество позиций для сдвига структуры. Можно сдвинуть биты вправо с [>> оператор](../../../../visual-basic/language-reference/operators/right-shift-operator.md) или влево с [<< оператор](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 Тип данных операнда шаблон должен быть `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`. Тип данных операнда количества shift должен быть `Integer` или должны расширяться до `Integer`.  
  
 Арифметические сдвиги не являются циклическими, это означает, что биты, сдвигаемые результата, не подставляются на другом конце. Позиции битов, освобожденные сдвигом заданы следующим образом:  
  
-   0 для арифметического сдвига влево  
  
-   0 для арифметического сдвига вправо положительного числа  
  
-   0 для арифметического сдвига вправо беззнакового типа данных (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 для арифметического сдвига вправо отрицательного числа (`SByte`, `Short`, `Integer`, или `Long`)  
  
 Следующий пример сдвигает `Integer` значение влево и вправо.  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 Арифметические сдвиги никогда не создают исключения переполнения.  
  
## <a name="bitwise-operations"></a>Поразрядные операции  
 Логические операторы `Not`, `Or`, `And`, и `Xor` выполнять Побитовая арифметика при использовании с числовыми значениями. Дополнительные сведения см. в разделе «Битовые операции» в [логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Безопасность типа  
 Операнды обычно должен быть того же типа. Например, если сложение с `Integer` переменной, добавьте ее в другой `Integer` переменной и следует присвоить результат переменной типа `Integer` также.  
  
 Один из способов обеспечить типобезопасного кода является использование [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Если задать `Option Strict On`, Visual Basic автоматически выполняет *типобезопасный* преобразования. Например, если попытаться добавить `Integer` переменной `Double` переменную и присвоить значение `Double` переменных, операция выполняется нормально, так как `Integer` значение можно преобразовать в `Double` без потери данных. Небезопасные преобразования, с другой стороны, вызывают ошибку компилятора с `Option Strict On`. Например, если попытаться добавить `Integer` переменной `Double` переменную и присвоить значение `Integer` переменной, компилятор выдает ошибку, так как `Double` переменной не может неявно преобразовать в тип `Integer`.  
  
 Если задать `Option Strict Off`, однако Visual Basic позволяет неявные сужающие преобразования вступили в силу, несмотря на то, что они могут привести к потере данных или точности. По этой причине мы рекомендуем использовать `Option Strict On` при написании кода в рабочей среде. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>См. также
- [Арифметические операторы](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Операторы сдвига битов](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
