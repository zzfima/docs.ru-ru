---
title: "Операторы объединения в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "& - оператор [Visual Basic], объединение"
  - "+ - оператор [Visual Basic], объединение"
  - "операторы объединения"
  - "операторы объединения, строки Visual Basic"
  - "операторы [Visual Basic], объединение"
  - "код Visual Basic, операторы"
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Операторы объединения в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Операторы объединения объединяют несколько строк в одну.  Существует два оператора объединения: `+` и `&`.  Оба они выполняют базовую операцию объединения, как показано в следующем примере.  
  
 [!CODE [Dim x As String = "Mic" & "ro" & "soft" Dim y As String = "Mic" + "ro" + "soft" ' The preceding statements set both x and y to "Microsoft".](Dim x As String = "Mic" & "ro" & "soft" Dim y As String = "Mic" + "ro" + "soft" ' The preceding statements set both x and y to "Microsoft".)]  
  
 Эти операторы также могут объединять переменные `String`, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/concatenation-operators_1.vb)]  
  
## Различия между двумя операторами объединения  
 Основное назначение оператора [Оператор \+](../../../../visual-basic/language-reference/operators/addition-operator.md) заключается в добавлении двух чисел.  Однако он также может объединять числовые операнды со строковыми.  Оператор `+` имеет сложный набор правил, определяющий, следует ли выполнять добавление, объединение, сигнализировать об ошибке компилятора или выдавать исключение времени выполнения <xref:System.InvalidCastException>.  
  
 Оператор [Оператор &](../../../../visual-basic/language-reference/operators/concatenation-operator.md) определяется только для операндов `String` и всегда расширяет свои операнды до `String`, независимо от значения `Option Strict`.  Оператор `&` рекомендуется использовать для объединения строк, так как он определен исключительно для строк и снижает шансы создания непреднамеренного преобразования.  
  
## Производительность: String и StringBuilder  
 Если вы выполняете множество операций со строкой, таких как объединения, удаления и замены, использование класса <xref:System.Text.StringBuilder> из пространства имен <xref:System.Text> может оказать положительное влияние на производительность.  Для создания и инициализации объекта <xref:System.Text.StringBuilder> требуется дополнительная инструкция, кроме того, еще одна инструкция необходима для преобразования итогового значения в `String`, однако это время можно скомпенсировать высокой скоростью выполнения <xref:System.Text.StringBuilder>.  
  
## См. также  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Типы методов для работы со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)   
 [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)