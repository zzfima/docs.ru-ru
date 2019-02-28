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
ms.openlocfilehash: fe08c855e4dd0adca68d48c3b32cb399033a9d46
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974930"
---
# <a name="operator-procedures-visual-basic"></a>Процедуры операторов (Visual Basic)
Процедура оператора — это последовательность операторов Visual Basic, которые определяют поведение стандартного оператора (такие как `*`, `<>`, или `And`) для класса или структуры, которые вы определили. Это также называется *перегрузка операторов*.  
  
## <a name="when-to-define-operator-procedures"></a>Когда следует определять процедуры оператора  
 После определения класса или структуры, можно объявлять переменные типа этого класса или структуры. Иногда такой переменной необходимо участвовать в операции как часть выражения. Чтобы сделать это, он должен быть операнд оператора.  
  
 Visual Basic определяет операторы только на его основных типах данных. Можно определить поведение оператора, если один или оба операнда имеют тип класса или структуры.  
  
 Дополнительные сведения см. в разделе [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="types-of-operator-procedure"></a>Типы процедур оператора  
 Процедура оператора может принимать одно из следующих типов:  
  
-   Определение унарного оператора, где аргумент имеет тип класса или структуры.  
  
-   Определение бинарного оператора, где по крайней мере один из аргументов имеет тип класса или структуры.  
  
-   Определение оператора преобразования, где аргумент имеет тип класса или структуры.  
  
-   Определение оператора преобразования, который возвращает тип класса или структуры.  
  
 Операторы преобразования всегда являются унарными и всегда использовать `CType` как оператор вы определяете.  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Ниже приведен синтаксис объявления процедуры оператора:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *символ_оператора* `(` *операнд1*`[,`*операнд2* `]) As` *тип данных*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Использовании `Widening` или `Narrowing` ключевое слово только в операторе преобразования типа. Символ оператора является всегда [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для оператора преобразования типа.  
  
 Объявите два операнда, чтобы определить бинарный оператор, и объявите один операнд, чтобы определить унарный оператор, включая оператор преобразования типа. Все операнды должны быть объявлены `ByVal`.  
  
 Объявите каждый операнд так же, как объявлять параметры для [подпрограммы](./sub-procedures.md).  
  
### <a name="data-type"></a>Тип данных  
 Так как при определении оператора для класса или структуры, которые вы определили, по крайней мере один из операндов должен иметь тип данных этого класса или структуры. Для оператора преобразования типа данных типа класса или структуры необходимо операнд или тип возвращаемого значения.  
  
 Дополнительные сведения см. в разделе [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Вызовите процедуру оператора неявно с помощью символа оператора в выражении. Укажите операнды так же, как и для стандартных операторов.  
  
 Ниже приведен синтаксис для неявный вызов процедуры оператора:  
  
 `Dim testStruct As`  *Имя структуры*  
  
 `Dim testNewStruct As`  *Имя структуры*`= testStruct`*символ_оператора*  `10`  
  
### <a name="illustration-of-declaration-and-call"></a>Пример объявления и вызова  
 Следующая структура сохраняет значение 128-битового знакового целого числа в качестве составных частей старшие и младшие. Он определяет `+` оператора для добавления двух `veryLong` значения и сформировать результирующий `veryLong` значение.  
  
 [!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]  
  
 В следующем примере показано типичный вызов `+` оператора, определенного в `veryLong`.  
  
 [!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]  
  
  
## <a name="see-also"></a>См. также
- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры функций](./function-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)
- [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)
- [Практическое руководство. Используйте класс, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md)
