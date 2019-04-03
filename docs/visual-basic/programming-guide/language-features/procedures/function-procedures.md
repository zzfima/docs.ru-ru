---
title: Процедуры Function (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 568489d6034316e895cd999801241fa995aadefa
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834248"
---
# <a name="function-procedures-visual-basic"></a>Процедуры Function (Visual Basic)
Объект `Function` процедура — это последовательность операторов Visual Basic, заключенным `Function` и `End Function` инструкций. `Function` Процедура выполняет задачи и возвращает управление вызывающему коду. При возвращении управления также возвращает значение вызывающему коду.  
  
 Каждый раз при вызове процедуры, его операторы выполнения, начиная с первого выполняемого оператора после `Function` инструкции и заканчивая первым `End Function`, `Exit Function`, или `Return` обнаружен оператор.  
  
 Вы можете определить `Function` процедуры в модуля, класса или структуры. Это `Public` по умолчанию, означающее, его можно вызвать из любого места в приложении, которое имеет доступ к модуля, класса или структуры, в котором она определена.  
  
 Объект `Function` процедура может принимать аргументы, такие как константы, переменные или выражения, которые передаются в него в вызывающем коде.  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Синтаксис объявления `Function` процедура выглядит следующим образом:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 *Модификаторы* можно указать уровень доступа и сведения о перегрузка, переопределение, совместного использования и затенении. Дополнительные сведения см. в разделе [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Каждый параметр объявляется так же, как и для [подпрограммы](./sub-procedures.md).  
  
### <a name="data-type"></a>Тип данных  
 Каждый `Function` процедуры имеет тип данных, так же, как любой переменной. Этот тип данных определяется `As` предложение в `Function` инструкции и определяет тип данных значения, функция возвращает в вызывающий код. Следующий пример демонстрирует объявление, иллюстрируют это.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Дополнительные сведения см. в разделе «Компоненты» в [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Получение возвращаемых значений  
 Значение `Function` процедура отправляет обратно в вызывающий код вызывается его возвращаемое значение. Процедура возвращает это значение в одном из двух способов:  
  
-   Она использует `Return` инструкцию, чтобы указать возвращаемое значение и возвращает управление вызывающей программе немедленно. Это показано в следующем примере.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   Он присваивает значение собственное имя функции в одной или нескольких инструкций процедуры. Управление не возвращается вызывающей программе до `Exit Function` или `End Function` выполняется инструкция. Это показано в следующем примере.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 Присвоение имени функции возвращаемое значение удобен, управление не возвращается из процедуры, пока встретится `Exit Function` или `End Function` инструкции. Это позволяет назначить предварительное значение и изменить позже при необходимости.  
  
 Дополнительные сведения о возврате значения см. в разделе [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md). Сведения о возврате массивов см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Вы вызываете `Function` процедуры, включая ее имя и аргументы в правой части оператора присваивания или в выражении. Необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргументов необходимо заключить в круглые скобки. Если не указано никаких аргументов, скобки можно опустить.  
  
 Синтаксис для вызова `Function` процедура выглядит следующим образом:  
  
 *lvalue*`=`*functionname* `[(` *argumentlist* `)]`  
  
 `If ((` *FunctionName* `[(` *argumentlist* `)] / 3) <=` *выражение* `) Then`  
  
 При вызове `Function` процедуры, не нужно использовать ее возвращаемое значение. Если этого не сделать, выполняются все действия, функции, но возвращаемое значение игнорируется. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> часто называется таким образом.  
  
### <a name="illustration-of-declaration-and-call"></a>Пример объявления и вызова  
 Следующие `Function` процедура вычисляет самая длинная сторона гипотенузы прямоугольного треугольника, значения для двух других сторон.  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 В следующем примере показано типичный вызов `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Практическое руководство. Создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)
- [Практическое руководство. Возвращение значения из процедуры](./how-to-return-a-value-from-a-procedure.md)
- [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
