---
title: Процедуры функций
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: b62a730e8ade211821826afbb55fa8858ea311a3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341091"
---
# <a name="function-procedures-visual-basic"></a>Процедуры Function (Visual Basic)
`Function` процедура — это последовательность Visual Basic инструкций, заключенных в операторы `Function` и `End Function`. `Function` процедура выполняет задачу, а затем возвращает управление вызывающему коду. Когда он возвращает управление, он также возвращает значение в вызывающий код.  
  
 При каждом вызове процедуры ее инструкции выполняются, начиная с первого исполняемого оператора после оператора `Function` и заканчивая первой инструкцией `End Function`, `Exit Function`или `Return`.  
  
 Процедуру `Function` можно определить в модуле, классе или структуре. Он `Public` по умолчанию, что означает, что его можно вызывать из любого места в приложении, которое имеет доступ к модулю, классу или структуре, в которой он определен.  
  
 `Function` процедура может принимать аргументы, такие как константы, переменные или выражения, которые передаются в него вызывающим кодом.  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Синтаксис для объявления `Function` процедуры выглядит следующим образом:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 *Модификаторы* могут указывать уровень доступа и сведения о перегрузке, переопределении, совместном использовании и затенении. Дополнительные сведения см. в разделе [оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Каждый параметр объявляется так же, как и для [процедур подраздела](./sub-procedures.md).  
  
### <a name="data-type"></a>Тип данных  
 Каждая `Function` процедура имеет тип данных, точно так же, как и каждая переменная. Этот тип данных указывается предложением `As` в инструкции `Function` и определяет тип данных значения, возвращаемого функцией в вызывающий код. Это показано в приведенных ниже примерах объявлений.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Дополнительные сведения см. в разделе "части" в [операторе Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Возвращаемые значения  
 Значение, `Function` процедура, отправляется обратно вызывающему коду, называется возвращаемым значением. Процедура возвращает это значение одним из двух способов:  
  
- Он использует оператор `Return` для указания возвращаемого значения и немедленно возвращает управление вызывающей программе. Это показано в следующем примере.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
- Он присваивает значение имени своей функции в одной или нескольких инструкциях процедуры. Управление не возвращается вызывающей программе до тех пор, пока не будет выполнен оператор `Exit Function` или `End Function`. Это показано в следующем примере.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 Преимуществом присвоения возвращаемого значения имени функции является то, что Управление не возвращается из процедуры до тех пор, пока не встретится оператор `Exit Function` или `End Function`. Это позволяет назначить предварительное значение и позже при необходимости изменить его.  
  
 Дополнительные сведения о возвращаемых значениях см. в разделе [оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md). Дополнительные сведения о возврате массивов см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Процедура `Function` вызывается путем включения ее имени и аргументов в правой части оператора присваивания или в выражении. Необходимо указать значения для всех аргументов, которые не являются необязательными, и необходимо заключить список аргументов в круглые скобки. Если аргументы не указаны, можно дополнительно опустить круглые скобки.  
  
 Синтаксис вызова `Function` процедуры выглядит следующим образом:  
  
 *lvalue*`=`*functionname* `[(` *ArgumentList* `)]`  
  
 `If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`*Expression* `) Then`  
  
 При вызове `Function` процедуры не нужно использовать ее возвращаемое значение. В противном случае выполняются все действия функции, но возвращаемое значение игнорируется. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> часто вызывается таким образом.  
  
### <a name="illustration-of-declaration-and-call"></a>Иллюстрация объявления и вызова  
 Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника, учитывая значения двух других сторон.  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 В следующем примере показан типичный вызов `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Практическое руководство. Создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)
- [Практическое руководство. Возврат значения из процедуры](./how-to-return-a-value-from-a-procedure.md)
- [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
