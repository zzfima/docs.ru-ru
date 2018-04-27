---
title: Процедуры Function (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ad4f55a9dd9fbd68c36dd53a01f97ddb03c2bb9b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="function-procedures-visual-basic"></a>Процедуры Function (Visual Basic)
Объект `Function` процедура — это последовательность операторов Visual Basic, заключенным в `Function` и `End Function` инструкции. `Function` Процедура выполняет задачу и возвращает управление вызывающему коду. При возвращении элемента управления также возвращает значение вызывающему коду.  
  
 При каждом вызове процедуры ее инструкции выполняются, начиная с первого исполняемого оператора после `Function` инструкции и заканчивая первым `End Function`, `Exit Function`, или `Return` обнаружен оператор.  
  
 Можно определить `Function` процедуру в модуля, класса или структуры. Это `Public` по умолчанию, означающее, который можно вызвать из любого места в приложении, которое имеет доступ к модуля, класса или структуры, в котором она определена.  
  
 Объект `Function` процедура может принимать аргументы, например константы, переменные или выражения, которые передаются вызывающим кодом.  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Синтаксис объявления `Function` процедура является следующим образом:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 *Модификаторы* можно указать уровень доступа и сведения о перегрузке, переопределении, общем доступе и затенение. Дополнительные сведения см. в разделе [Function, инструкция](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Каждый параметр объявляется так же, как для [Sub-процедуры](./sub-procedures.md).  
  
### <a name="data-type"></a>Тип данных  
 Каждый `Function` процедуры имеет тип данных, просто любой переменной. Этот тип данных определяется `As` предложения в `Function` оператор, который определяет тип данных значения, функция возвращает в вызывающий код. Следующий пример демонстрирует объявление проиллюстрировать это.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Дополнительные сведения см. в разделе «Компоненты» в [Function, инструкция](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Получение возвращаемых значений  
 Значение `Function` процедура отправляет обратно в вызывающий код вызывается возвращаемого значения. Процедура возвращает это значение в одном из двух способов:  
  
-   Она использует `Return` инструкцию, чтобы задать возвращаемое значение и возвращает управление немедленно вызываемой программе. Это показано в следующем примере.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   Значение присваивается собственному имени функции в одной или нескольких инструкций процедуры. Управление не возвращается вызывающей программе до `Exit Function` или `End Function` выполняется инструкция. Это показано в следующем примере.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 Преимуществом присвоение имени функции возвращаемое значение является, управление не возвращается из процедуры, пока встретится `Exit Function` или `End Function` инструкции. Это позволяет определить предварительное значение и изменять его впоследствии при необходимости.  
  
 Дополнительные сведения о возврате значения см. в разделе [Function, инструкция](../../../../visual-basic/language-reference/statements/function-statement.md). Сведения о возврате массивов см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Вызвать `Function` процедуры, включая ее имя и аргументы справа от оператора присваивания или в составе выражения. Необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргумент должен быть заключен в круглые скобки. Если не указано никаких аргументов, скобки можно опустить.  
  
 Синтаксис для вызова `Function` процедура является следующим образом:  
  
 *lvalue*`=`*functionname* `[(` *argumentlist*  `)]`  
  
 `If ((` *FunctionName* `[(` *argumentlist* `)] / 3) <=` *выражение*  `) Then`  
  
 При вызове `Function` процедуры, не нужно использовать ее возвращаемое значение. Если этого не сделать, выполняются все действия функции, но возвращаемое значение игнорируется. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> часто называют таким образом.  
  
### <a name="illustration-of-declaration-and-call"></a>Пример объявления и вызова  
 Следующие `Function` процедуры рассчитывается длинной стороны, гипотенуза прямоугольного треугольника, заданы значения для двух других сторон.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 В примере показан типичный вызов `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Подпрограммы](./sub-procedures.md)  
 [Процедуры свойств](./property-procedures.md)  
 [Процедуры операторов](./operator-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Практическое руководство. Создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Практическое руководство. Возврат значения из процедуры](./how-to-return-a-value-from-a-procedure.md)  
 [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
