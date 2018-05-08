---
title: Операторы объединения в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: ab268e513e6f019ed651c94deb5e423cfcca7587
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="concatenation-operators-in-visual-basic"></a>Операторы объединения в Visual Basic
Операторы объединения объединяют несколько строк в одну. Существует два оператора объединения: `+` и `&`. Оба они выполняют базовую операцию объединения, как показано в следующем примере.  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 Эти операторы также могут объединять переменные `String`, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a>Различия между двумя операторами объединения  
 [Оператор +](../../../../visual-basic/language-reference/operators/addition-operator.md) имеет основной целью сложения двух чисел. Однако он также может объединять числовые операнды со строковыми. Оператор `+` имеет сложный набор правил, определяющий, следует ли выполнять добавление, объединение, сигнализировать об ошибке компилятора или выдавать исключение времени выполнения <xref:System.InvalidCastException>.  
  
 [& Оператор](../../../../visual-basic/language-reference/operators/concatenation-operator.md) определяется только для `String` операнда и он всегда расширяет свои операнды до `String`, независимо от значения `Option Strict`. Оператор `&` рекомендуется использовать для объединения строк, так как он определен исключительно для строк и снижает шансы создания непреднамеренного преобразования.  
  
## <a name="performance-string-and-stringbuilder"></a>Производительность: String и StringBuilder  
 Если вы выполняете множество операций со строкой, таких как объединения, удаления и замены, использование класса <xref:System.Text.StringBuilder> из пространства имен <xref:System.Text> может оказать положительное влияние на производительность. Для создания и инициализации объекта <xref:System.Text.StringBuilder> требуется дополнительная инструкция, кроме того, еще одна инструкция необходима для преобразования итогового значения в `String`, однако это время можно скомпенсировать высокой скоростью выполнения <xref:System.Text.StringBuilder>.  
  
## <a name="see-also"></a>См. также  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Типы методов обработки строки в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)  
 [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
