---
title: "Арифметические операторы в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators
- bit-shift operators
- zero, division by zero
- operators [Visual Basic], arithmetic
- division, by zero
- Visual Basic code, operators
- arithmetic operators, about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c724bf8b6794e71d49b32c7d3ce9e010f541f68f
ms.lasthandoff: 03/13/2017

---
# <a name="arithmetic-operators-in-visual-basic"></a>Арифметические операторы в Visual Basic
Арифметические операторы используются для выполнения многих известных арифметических операций, включая вычисление числовых значений, представленных литералы, переменные, другие выражения, функции и вызовы свойств и константы. Также относятся к с арифметическими операторами являются операторы поразрядного сдвига, которые работают на уровне отдельных битов операндов и перетаскивать их битовых шаблонов влево или вправо.  
  
## <a name="arithmetic-operations"></a>Арифметические операции  
 Можно добавить два значения в выражении вместе с [оператор +](../../../../visual-basic/language-reference/operators/addition-operator.md), или вычесть одно из другого с [-оператор (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators&#57;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 Отрицание также использует [-оператор (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), но только с одним операндом, как приведенный ниже пример демонстрирует.  
  
 [!code-vb[VbVbalrOperators&#58;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 Умножение и деление используют [* оператор](../../../../visual-basic/language-reference/operators/multiplication-operator.md) и [-оператор (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)соответственно, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators&#59;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 Используется для возведения в степень [^ оператор](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators&#60;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 Целочисленное деление выполняется с помощью [\ Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). Целочисленное деление возвращает частное, то есть целое число, представляющее число раз делитель можно разделить делимое без остатка. Делитель и делимое должны быть целочисленными типами (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, и `ULong`) для данного оператора. Все остальные типы должны сначала преобразованы в целочисленный тип. В следующем примере показано целочисленного деления.  
  
 [!code-vb[VbVbalrOperators&#61;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 Арифметический модуль выполняется с помощью [оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md). Этот оператор возвращает остаток после деления делимого целое количество раз. Если делитель и делимое являются целыми типами, возвращенное значение является неотъемлемой частью. Если делитель и делимое являются типами с плавающей запятой, возвращенное значение также является с плавающей запятой. В следующем примере показано такое поведение.  
  
 [!code-vb[VbVbalrOperators&#62;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators&#63;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### <a name="attempted-division-by-zero"></a>Попытка деления на ноль  
 Деление на ноль приводит к разным результатам, в зависимости от используемых типов данных. In integral divisions (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] throws a <xref:System.DivideByZeroException> exception.</xref:System.DivideByZeroException> В операции деления на `Decimal` или `Single` тип данных [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] также создает <xref:System.DivideByZeroException>исключение.</xref:System.DivideByZeroException>  
  
 В с плавающей запятой подразделений с использованием `Double` типа данных, исключение не создается, а результатом является член класса, представляющий <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, или <xref:System.Double.NegativeInfinity>, в зависимости от делимого.</xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity> </xref:System.Double.NaN> В следующей таблице перечислены различные результаты попытки деления `Double` значение на ноль.  
  
|Тип данных делимого|Тип данных делителя|Значение делимого|Результат|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN>(математически число)</xref:System.Double.NaN>|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity></xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity></xref:System.Double.NegativeInfinity>|  
  
 После перехвата <xref:System.DivideByZeroException>исключения, можно использовать его члены при обработке его.</xref:System.DivideByZeroException> Например <xref:System.Exception.Message%2A>свойство содержит текст сообщения для исключения.</xref:System.Exception.Message%2A> Дополнительные сведения см. в разделе [Try... CATCH... Оператор Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Операции поразрядного сдвига  
 Операция сдвига разряда выполняет арифметический сдвиг битового шаблона. Шаблон содержится в операнде слева, а операнд справа указывает число позиций для сдвига структуры. Можно сдвинуть биты вправо с [>> оператор](../../../../visual-basic/language-reference/operators/right-shift-operator.md) или влево с [ <> </> ](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 Тип данных операнда шаблон должен быть `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`. Тип данных операнда количества разрядов сдвига должен быть `Integer` или его необходимо расширить до `Integer`.  
  
 Арифметический сдвиг не цикличен, это означает, что биты, сдвигаемые результата, не подставляются в конце. Позиции битов, освобожденные сдвигом, устанавливаются следующим образом:  
  
-   0 для арифметического сдвига влево  
  
-   0 для арифметического сдвига вправо положительного числа  
  
-   0 для арифметического сдвига вправо беззнакового типа данных (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 для арифметического сдвига вправо отрицательного числа (`SByte`, `Short`, `Integer`, или `Long`)  
  
 Следующий пример перемещает `Integer` значение слева и справа.  
  
 [!code-vb[VbVbalrOperators&#64;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 Арифметические сдвиги никогда не генерируют исключения переполнения.  
  
## <a name="bitwise-operations"></a>Поразрядные операции  
 Логические операторы `Not`, `Or`, `And`, и `Xor` также выполняют поразрядные арифметические операции, когда применяются для числовых значений. Дополнительные сведения см. в разделе «Битовые операции» в [логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Строгая типизация  
 Операнды обычно должен быть того же типа. Например, если вы сложение с `Integer` переменных, его следует добавить в другой `Integer` переменной и следует присвоить результат переменной типа `Integer` также.  
  
 Один из способов обеспечить типобезопасного кода является использование [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Если задать `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически выполняет *строго типизированным* преобразования. Например, при попытке добавить `Integer` переменной `Double` переменной и присвойте значение `Double` переменных, операция проходит нормально, поскольку `Integer` значение может быть преобразовано в `Double` без потери данных. Небезопасный тип преобразования, с другой стороны, вызывают ошибку компилятора с `Option Strict On`. Например, при попытке добавить `Integer` переменной `Double` переменной и присвойте значение `Integer` переменной, компилятор выдает ошибку, поскольку `Double` переменной нельзя неявно преобразовать в тип `Integer`.  
  
 Если задать `Option Strict Off`, однако [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] разрешает неявные сужающие преобразования вступили в силу, хотя они могут привести к потере данных или точности. По этой причине мы рекомендуем использовать `Option Strict On` при написании конечного кода. Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>См. также  
 [Арифметические операторы](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Операторы поразрядного сдвига](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
