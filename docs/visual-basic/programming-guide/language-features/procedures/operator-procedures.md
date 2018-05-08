---
title: Процедуры операторов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 63a16163900f1b4dc7dadef6a227f56b89f4e820
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="operator-procedures-visual-basic"></a>Процедуры операторов (Visual Basic)
Процедура оператора — это последовательность операторов Visual Basic, определяющих поведение стандартного оператора (например, `*`, `<>`, или `And`) в классе или структуре, определенных вами. Это также называется *перегрузка операторов*.  
  
## <a name="when-to-define-operator-procedures"></a>Когда определять процедуры оператора  
 После определения класса или структуры, можно объявлять переменные типа этого класса или структуры. Иногда такая переменная должна участвовать в операции как часть выражения. Сделать это, он должен быть операндом оператора.  
  
 Visual Basic определяет операторы только на его основных типах данных. Можно определить поведение оператора, если один или оба операнда имеют тип класса или структуры.  
  
 Дополнительные сведения см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="types-of-operator-procedure"></a>Типы процедур оператора  
 Процедура оператора может принимать одно из следующих типов:  
  
-   Определение унарного оператора, где аргумент имеет тип класса или структуры.  
  
-   Определение бинарного оператора, где по крайней мере один из аргументов имеет тип класса или структуры.  
  
-   Определение оператора преобразования, где аргумент имеет тип класса или структуры.  
  
-   Определение оператора преобразования, который возвращает тип класса или структуры.  
  
 Операторы преобразования всегда являются унарными и всегда использовать `CType` как оператор вы определяете.  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Ниже приведен синтаксис объявления процедуры оператора:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *символ_оператора* `(` *операнд_1*`[,`*операнд_2* `]) As` *тип данных*   
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Вы используете `Widening` или `Narrowing` ключевое слово только в операторе преобразования типа. Символ оператора является всегда [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для оператора преобразования типа.  
  
 Объявите два операнда, чтобы определить бинарный оператор и объявить один операнд, чтобы определить унарный оператор, включая оператор преобразования типа. Все операнды должны быть объявлены `ByVal`.  
  
 Объявите каждый операнд так же, как объявлять параметры для [Sub-процедуры](./sub-procedures.md).  
  
### <a name="data-type"></a>Тип данных  
 Поскольку в определении оператора в классе или структуре, определенных вами по крайней мере один из операндов должны иметь тип данных этого класса или структуры. Для оператора преобразования типа операнд или возвращаемый тип должен иметь тип данных класса или структуры.  
  
 Дополнительные сведения см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Вызовите процедуру оператора неявно с помощью символа оператора в выражении. Укажите операнды так же, как для стандартных операторов.  
  
 Ниже приведен синтаксис для неявный вызов процедуры оператора:  
  
 `Dim testStruct As`  *Имя структуры*  
  
 `Dim testNewStruct As`  *Имя структуры*`= testStruct`*символ_оператора*   `10`  
  
### <a name="illustration-of-declaration-and-call"></a>Пример объявления и вызова  
 Следующая структура сохраняет значение 128-разрядное целое число со знаком, как составные части старших и младших. Он определяет `+` оператор для добавления двух `veryLong` значения и сформировать результирующий `veryLong` значение.  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 В примере показан типичный вызов `+` оператора, определенного в `veryLong`.  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 Дополнительные сведения и примеры см. в разделе [Перегрузка операторов в Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Подпрограммы](./sub-procedures.md)  
 [Процедуры функций](./function-procedures.md)  
 [Процедуры свойств](./property-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Оператор Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)  
 [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)  
 [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)  
 [Практическое руководство. Использование класса, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md)
