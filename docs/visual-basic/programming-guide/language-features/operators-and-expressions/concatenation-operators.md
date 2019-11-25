---
title: Операторы объединения
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: f86245c649647be4e040a61083d8b93eee4d7422
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353679"
---
# <a name="concatenation-operators-in-visual-basic"></a>Операторы объединения в Visual Basic

Операторы объединения объединяют несколько строк в одну. Существует два оператора объединения: `+` и `&`. Оба они выполняют базовую операцию объединения, как показано в следующем примере.

```vb
Dim x As String = "Mic" & "ro" & "soft"
Dim y As String = "Mic" + "ro" + "soft"
' The preceding statements set both x and y to "Microsoft".
```

Эти операторы также могут объединять переменные `String`, как показано в следующем примере.

[!code-vb[VbVbalrOperators#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#76)]

## <a name="differences-between-the-two-concatenation-operators"></a>Различия между двумя операторами объединения

The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers. Однако он также может объединять числовые операнды со строковыми. Оператор `+` имеет сложный набор правил, определяющий, следует ли выполнять добавление, объединение, сигнализировать об ошибке компилятора или выдавать исключение времени выполнения <xref:System.InvalidCastException>.

The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`. Оператор `&` рекомендуется использовать для объединения строк, так как он определен исключительно для строк и снижает шансы создания непреднамеренного преобразования.

## <a name="performance-string-and-stringbuilder"></a>Производительность: String и StringBuilder

Если вы выполняете множество операций со строкой, таких как объединения, удаления и замены, использование класса <xref:System.Text.StringBuilder> из пространства имен <xref:System.Text> может оказать положительное влияние на производительность. Для создания и инициализации объекта <xref:System.Text.StringBuilder> требуется дополнительная инструкция, кроме того, еще одна инструкция необходима для преобразования итогового значения в `String`, однако это время можно скомпенсировать высокой скоростью выполнения <xref:System.Text.StringBuilder>.

## <a name="see-also"></a>См. также

- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Types of String Manipulation Methods in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)
- [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
