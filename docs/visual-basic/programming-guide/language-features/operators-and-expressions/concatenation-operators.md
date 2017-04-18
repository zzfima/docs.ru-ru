---
title: "Операторы объединения в Visual Basic | Документы Microsoft"
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
- '& operator [Visual Basic], concatenation'
- concatenation operators
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators, Visual Basic strings
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: fa11f1dcff2c333861596cbac03391403cf962c1
ms.lasthandoff: 03/13/2017

---
# <a name="concatenation-operators-in-visual-basic"></a>Операторы объединения в Visual Basic
Операторы объединения объединяют несколько строк в одну. Существует два оператора объединения: `+` и `&`. Оба они выполняют базовую операцию объединения, как показано в следующем примере.  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 Эти операторы также могут объединять переменные `String`, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators&#76;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a>Различия между двумя операторами объединения  
 [Оператор +](../../../../visual-basic/language-reference/operators/addition-operator.md) имеет основной целью сложения двух чисел. Однако он также может объединять числовые операнды со строковыми. `+` Оператор имеет сложный набор правил, определяющих, следует ли добавлять, объединять, сообщить об ошибке компилятора или исключение времени выполнения <xref:System.InvalidCastException>исключение.</xref:System.InvalidCastException>  
  
 [& Оператор](../../../../visual-basic/language-reference/operators/concatenation-operator.md) определяется только для `String` операнда и всегда расширяет свои операнды до `String`, независимо от параметра `Option Strict`. Оператор `&` рекомендуется использовать для объединения строк, так как он определен исключительно для строк и снижает шансы создания непреднамеренного преобразования.  
  
## <a name="performance-string-and-stringbuilder"></a>Производительность: String и StringBuilder  
 Если вы выполняете множество манипуляций со строками, как объединения, удаления и замены, производительность можно увеличить с <xref:System.Text.StringBuilder>класса в <xref:System.Text>имен.</xref:System.Text> </xref:System.Text.StringBuilder> Требуется дополнительная инструкция для создания и инициализации <xref:System.Text.StringBuilder>объекта и еще один оператор для преобразования итогового значения для `String`, но на этот раз можно восстановить, так как <xref:System.Text.StringBuilder>может работать быстрее.</xref:System.Text.StringBuilder> </xref:System.Text.StringBuilder>  
  
## <a name="see-also"></a>См. также  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Типы методов для обработки в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)   
 [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
