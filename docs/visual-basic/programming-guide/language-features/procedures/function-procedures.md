---
title: "Процедуры (Visual Basic) функции | Документы Microsoft"
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
- Function procedures
- return values, function procedures
- Visual Basic code, procedures
- procedures, calling
- procedures, Function procedures
- syntax, function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 11baaa6985f0681aa9c67c4f2470fb9917db5b78
ms.lasthandoff: 03/13/2017

---
# <a name="function-procedures-visual-basic"></a>Процедуры Function (Visual Basic)
Объект `Function` процедура представляет собой ряд [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] операторы заключены в `Function` и `End Function` инструкции. `Function` Процедура выполняет задачу и возвращает управление вызывающему коду. При возвращении управления также возвращает значение в вызывающий код.  
  
 При каждом вызове процедуры ее запуска, инструкции, начиная с первого исполняемого оператора после `Function` инструкции и заканчивая первым `End Function`, `Exit Function`, или `Return` обнаружен оператор.  
  
 Можно определить `Function` процедуру в модуля, класса или структуры. Это `Public` по умолчанию, означающее, его можно вызвать из любого места в приложении, которое имеет доступ к модуля, класса или структуры, в котором она определена.  
  
 A `Function` процедура может принимать аргументы, например константы, переменные или выражения, которые передаются ей вызывающим кодом.  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Синтаксис объявления `Function` используется следующая процедура:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 *Модификаторы* можно указать уровень доступа и сведения о перегрузке, переопределении, общем доступе и затенение. Дополнительные сведения см. в разделе [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Каждый параметр объявляется так же, как для [Sub-процедуры](./sub-procedures.md).  
  
### <a name="data-type"></a>Тип данных  
 Каждый `Function` процедуры имеет тип данных, просто любой переменной. Этот тип данных определяется `As` предложения в `Function` оператор, который определяет тип данных значения, функция возвращает управление вызывающему коду. Следующий пример демонстрирует объявление проиллюстрировать это.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Дополнительные сведения см. в разделе «Компоненты» в [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Получение возвращаемых значений  
 Значение `Function` процедура отправляет обратно в вызывающий код вызывается возвращаемого значения. Процедура возвращает значение одним из двух способов:  
  
-   Он использует `Return` инструкцию, чтобы указать возвращаемое значение и возвращает управление немедленно вызывающей программе. Это показано в следующем примере.  
  
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
  
 Преимуществом присвоением имени функции возвращаемого значения является то, что управление не возвращается из процедуры, пока встретится `Exit Function` или `End Function` инструкции. Это позволяет определить предварительное значение и изменять его впоследствии при необходимости.  
  
 Дополнительные сведения о возврате значения см. в разделе [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md). Сведения о возврате массивов в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Вызвать `Function` процедуры, включая ее имя и аргументы справа от оператора присваивания или в составе выражения. Необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргументов должен быть заключен в круглые скобки. Если не указано никаких аргументов, скобки можно опустить.  
  
 Синтаксис для вызова `Function` используется следующая процедура:  
  
 *lvalue*`=`*functionname* `[(` *argumentlist*    `)]`  
  
 `If ((`*functionname* `[(` *argumentlist* `)] / 3) <=` *выражений*  `) Then`  
  
 При вызове `Function` процедуры, не нужно использовать ее возвращаемое значение. Если этого не сделать, выполняются все действия функции, но возвращаемое значение игнорируется. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>часто называется таким образом.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
### <a name="illustration-of-declaration-and-call"></a>Пример объявления и вызова  
 Следующие `Function` процедура вычисляет длину самой длинной сторона, гипотенуза прямоугольного треугольника, учитывая значения для двух других сторон.  
  
 [!code-vb[VbVbcnProcedures&#1;](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 В следующем примере показано типичный вызов `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures №&6;](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Sub-процедуры](./sub-procedures.md)   
 [Процедуры свойств](./property-procedures.md)   
 [Процедуры операторов](./operator-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Практическое руководство: создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)   
 [Практическое руководство: возвращаемое значение из процедуры](./how-to-return-a-value-from-a-procedure.md)   
 [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
