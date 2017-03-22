---
title: "Процедуры операторов (Visual Basic) | Документы Microsoft"
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
- Visual Basic code, procedures
- procedures, operator
- Visual Basic code, operators
- syntax, Operator procedures
- operators [Visual Basic], overloading
- overloaded operators
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
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
ms.openlocfilehash: a9e86c9c466ba236cc33153f2f341af35c622de6
ms.lasthandoff: 03/13/2017

---
# <a name="operator-procedures-visual-basic"></a>Процедуры операторов (Visual Basic)
Процедура оператора — это последовательность [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] инструкции, определяющие поведение стандартного оператора (такие как `*`, `<>`, или `And`) в классе или структуре, определенных вами. Это также называется *перегрузка операторов*.  
  
## <a name="when-to-define-operator-procedures"></a>Когда определять процедуры оператора  
 После определения класса или структуры, можно объявлять переменные типа этого класса или структуры. Иногда такая переменная должна участвовать в операции как часть выражения. Чтобы сделать это, ее необходимо операнд оператора.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Определяет операторы только на его основных типах данных. Можно определить поведение оператора, если один или оба операнда имеют тип класса или структуры.  
  
 Дополнительные сведения см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="types-of-operator-procedure"></a>Типы процедур оператора  
 Процедура оператора может быть одним из следующих типов:  
  
-   Определение унарного оператора, где аргумент имеет тип класса или структуры.  
  
-   Определение бинарного оператора, где по крайней мере один из аргументов имеет тип класса или структуры.  
  
-   Определение оператора преобразования, где аргумент имеет тип класса или структуры.  
  
-   Определение оператора преобразования, который возвращает тип класса или структуры.  
  
 Операторы преобразования всегда унарные, поэтому всегда использовать `CType` как оператор, который вы определяете.  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Синтаксис объявления процедуры оператора выглядит следующим образом:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Использовать `Widening` или `Narrowing` ключевое слово только в операторе преобразования типа. Символ оператора является всегда [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для оператора преобразования типа.  
  
 Объявите два операнда, чтобы определить бинарный оператор, и объявите один операнд, чтобы определить унарный оператор, включая оператор преобразования типа. Все операнды должны быть объявлены `ByVal`.  
  
 Объявите каждый операнд так же, как вы объявили параметры для [Sub-процедуры](./sub-procedures.md).  
  
### <a name="data-type"></a>Тип данных  
 Поскольку вы определяете оператора для класса или структуры, которые были определены, по крайней мере один из операндов должны иметь тип данных класса или структуры. Для оператора преобразования типа операнд или возвращаемый тип должен быть типа данных класса или структуры.  
  
 Дополнительные сведения см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Вызовите процедуру оператора неявно с помощью символа оператора в выражении. Укажите операнды так же, как для стандартных операторов.  
  
 Неявный вызов процедуры оператора синтаксис выглядит следующим образом:  
  
 `Dim testStruct As`  *Имя структуры*  
  
 `Dim testNewStruct As`  *Имя структуры*`= testStruct`*operatorsymbol    *  `10`  
  
### <a name="illustration-of-declaration-and-call"></a>Пример объявления и вызова  
 Следующая структура сохраняет значение 128-разрядное целое число со знаком, как составные части старший и младший. Он определяет `+` оператор для добавления двух `veryLong` значения и сформировать сканером `veryLong` значение.  
  
 [!code-vb[VbVbcnProcedures&#23;](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 В следующем примере показано типичный вызов `+` оператора, определенного в `veryLong`.  
  
 [!code-vb[VbVbcnProcedures&#24;](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 Дополнительные сведения и примеры см. в разделе [перегрузки операторов в Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Sub-процедуры](./sub-procedures.md)   
 [Процедуры функций](./function-procedures.md)   
 [Процедуры свойств](./property-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Практическое руководство: определение оператора](./how-to-define-an-operator.md)   
 [Практическое руководство: определение оператора преобразования](./how-to-define-a-conversion-operator.md)   
 [Практическое руководство: вызов процедуры оператора](./how-to-call-an-operator-procedure.md)   
 [Практическое руководство. Использование класса, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md)
