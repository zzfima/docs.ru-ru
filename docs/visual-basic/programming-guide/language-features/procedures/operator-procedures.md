---
title: "Процедуры операторов (Visual Basic) | Microsoft Docs"
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
  - "перегрузка операторов"
  - "процедуры операторов"
  - "операторы [Visual Basic], перегрузка"
  - "перегруженные операторы"
  - "процедуры, оператор"
  - "синтаксис, Процедуры операторов"
  - "код Visual Basic, операторы"
  - "код Visual Basic, процедуры"
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Процедуры операторов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Процедура оператора — это последовательность операторов [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], определяющих поведение стандартного оператора \(такого как `*`, `<>` или `And`\) в классе или структуре, определенных вами.  Это также называется *перегрузкой оператора*.  
  
## Когда определять процедуры оператора:  
 После определения класса или структуры, можно объявлять переменные типа этого класса или структуры.  Иногда такая переменная должна участвовать в операции как часть выражения.  Чтобы сделать это, она должна быть операндом оператора.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] определяет операторы только на его основных типах данных.  Можно определить поведение оператора, если один или оба операнда имеют тип класса или структуры.  
  
 Дополнительные сведения см. в разделе [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## Типы процедур оператора  
 Процедура оператора может быть одним из следующих типов:  
  
-   Определение унарного оператора, где аргумент имеет тип класса или структуры.  
  
-   Определение бинарного оператора, в котором по крайней мере один из аргументов имеет тип класса или структуры.  
  
-   Определение оператора преобразования, где аргумент имеет тип класса или структуры.  
  
-   Определение оператора преобразования, который возвращает тип класса или структуры.  
  
 Операторы преобразования всегда унарные, поэтому всегда используйте `CType` как оператор, который вы определяете.  
  
## Синтаксис объявления  
 Для объявления процедуры оператора используется следующий синтаксис:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`   ``  *символ\_оператора*  `(` *операнд\_1*  `[,`  *операнд\_2* `]) As`  *тип\_данных*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Используйте `Widening` или ключевое слово `Narrowing` только в операторе преобразования типа.  Символ оператора является всегда [Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для оператора преобразования типа.  
  
 Объявите два операнда, чтобы определить бинарный оператор, и объявите один операнд, чтобы определить унарный оператор, включая оператор преобразования типа.  Все операнды должны быть объявлены `ByVal`.  
  
 Объявите каждый операнд таким же образом, как вы объявили параметры для [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md).  
  
### Тип данных  
 Поскольку определяется оператор на классе или структуре, определенных вами, по крайней мере один из операндов должен иметь тип данных класса или структуры.  Для оператора преобразования типа операнд или возвращаемый тип должен иметь тип данных класса или структуры.  
  
 Дополнительные сведения см. в разделе [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## Синтаксис вызова  
 Вызовите процедуру оператора неявно с помощью символа оператора в выражении.  Укажите операнды таким же образом, как и для предварительно определенных операторов.  
  
 При неявном вызове процедуры оператора используется следующий синтаксис:  
  
 `Dim testStruct As`  *structurename*  
  
 `Dim testNewStruct As`  *имя\_структуры*  `= testStruct`  *символ\_оператора*  `10`  
  
### Пример объявления и вызова  
 Следующая структура сохраняет значение 128\-разрядного целочисленного значения со знаком, как составные части младшего и старшего порядка.  Она определяет оператор `+` для добавления двух значений `veryLong`  и создания результирующего значения `veryLong` .  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 В следующем примере показан типичный вызов оператора `+`, определенного для `veryLong`.  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 Дополнительные сведения и примеры содержатся в [Перегрузка операторов в Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Практическое руководство. Определение оператора](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Практическое руководство. Определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Практическое руководство. Вызов процедуры оператора](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [Практическое руководство. Использование класса, в котором определяются операторы](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)