---
title: "Процедуры Function (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "процедуры функций"
  - "возвращаемые значения, процедуры функций"
  - "код Visual Basic, процедуры"
  - "процедуры, вызов"
  - "процедуры, процедуры функций"
  - "синтаксис, процедуры функций"
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Процедуры Function (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Процедура `Function` — это последовательность операторов [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], заключенных между операторами `Function` и `End Function`.  Процедура `Function` выполняет задачу и возвращает управление вызвавшему ее коду.  Вместе с управлением вызвавшему коду возвращается значение.  
  
 При каждом вызове процедуры ее инструкции выполняются, начиная с первого исполняемого оператора после оператора `Function` и заканчивая первым из операторов `End Function`, `Exit Function` или `Return`.  
  
 Можно определить процедуру `Function` в модуле, классе или структуре.  По умолчанию эта процедура является глобальной \(`Public`\), что позволяет вызывать ее из любого места в приложении, из которого доступны модуль, класс или структура, в которых она определена.  
  
 Процедура `Function` может принимать аргументы, например константы, переменные или выражения, которые передаются ей вызывающим кодом.  
  
## Синтаксис объявления  
 Для объявления процедуры `Function` используется следующий синтаксис:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 В разделе *модификаторы* можно указать уровень доступа и сведения о перегрузке, переопределении, общем доступе и переобъявлении.  Дополнительные сведения см. в разделе [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Параметры объявляются так же, как для [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md).  
  
### Тип данных  
 Каждой процедуре `Function`, как и любой переменной, назначается тип данных.  Этот тип данных указывается предложением `As` оператора `Function` и определяет тип значения, которое функция будет возвращать вызывающему коду.  Например:  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Дополнительные сведения об ограничениях содержатся в подразделе "Компоненты" раздела [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## Возвращаемые значения  
 Значение процедура `Function` отправляет обратно вызывающему коду называется ее возвращаемое значение.  Процедура возвращает значение одним из двух способов:  
  
-   Для определения возвращаемого значения используется оператор `Return`, после которого управление немедленно возвращается вызывающей программе.  Это показано в приведенном ниже примере.  
  
    ```vb  
    Function FunctionName [(ParameterList)] As ReturnType  
        ' The following statement immediately transfers control back  
        ' to the calling code and returns the value of Expression.  
        Return Expression  
    End Function  
    ```  
  
-   Значение присваивается собственному имени функции в одном или нескольких операторах процедуры.  Управление не возвращается вызывающей программе до тех пор, пока не будет выполнен оператор `Exit Function` или `End Function`.  Это показано в приведенном ниже примере.  
  
    ```vb  
    Function FunctionName [(ParameterList)] As ReturnType  
        ‘ The following statement does not transfer control back to the calling code.  
        FunctionName = Expression  
        ' When control returns to the calling code, Expression is the return value.  
    End Function  
    ```  
  
 Преимущество первого способа \(с присвоением имени функции возвращаемого значения\) заключается в том, что управление возвращается в вызывающую программу только после того, как будет выполнен оператор `Exit Function` или `End Function`.  Это позволяет разработчику определить предварительное значение и изменять его впоследствии при необходимости.  
  
 Дополнительные сведения о получении значений см. в разделе [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md).  Дополнительные сведения о возврат массивов см. в разделе [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Синтаксис вызова  
 Для вызова процедуры `Function` следует указать ее имя и аргументы справа от оператора присваивания или в составе выражения.  Необходимо задать значения всех аргументов, которые являются обязательными, причем список аргументов должен быть заключен в скобки.  Если не указано никаких аргументов, скобки можно опустить \(необязательно\).  
  
 Для вызова процедуры `Function` используется следующий синтаксис:  
  
 *значение*  `=` *functionname* `[(` *argumentlist* `)]`  
  
 `If ((` *functionname* `[(` *argumentlist* `)] / 3) <=` *выражение* `) Then`  
  
 При вызове процедуры `Function` не обязательно использовать возвращаемое ею значение.  Если значение не используется, выполняются все действия функции, но возвращаемое значение игнорируется.  Часто таким образом вызывается функция <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.  
  
### Пример объявления и вызова  
 Приведенная ниже процедура `Function` вычисляет длину самой длинной стороны прямоугольного треугольника \(гипотенузы\) по значениям двух других сторон.  
  
 [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 В следующем примере показан типичный вызов `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Практическое руководство. Создание процедуры, возвращающей значение](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [Практическое руководство. Возврат значения из процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [Практическое руководство. Вызов процедуры, возвращающей значение](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)