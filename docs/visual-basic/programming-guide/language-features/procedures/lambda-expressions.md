---
title: "Лямбда-выражения (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: "52"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69ac88d295420277e99058d0f80a5ae1c2ce2e39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-visual-basic"></a>Лямбда-выражения (Visual Basic)
Объект *лямбда-выражение* — это функция или подпрограмма без имени, которую можно использовать везде, где допустим делегат. Лямбда-выражения могут быть функции или подпрограммы и может быть одной или нескольких строк. Лямбда-выражение можно передавать значения из текущей области.  
  
> [!NOTE]
>  `RemoveHandler` Инструкция является исключением. Невозможно передать лямбда-выражение в для делегирования параметра `RemoveHandler`.  
  
 Лямбда-выражения можно создавать с помощью `Function` или `Sub` ключевое слово, так же как стандартные функции или подпрограммы. Однако лямбда-выражения включаются в инструкции.  
  
 Следующий пример является лямбда-выражение, которое увеличивает значение своего аргумента и возвращает значение. В примере синтаксиса однострочный и многострочный лямбда-выражения для функции.  
  
 [!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 Следующий пример является лямбда-выражение, выводит на консоль значение. В примере синтаксиса однострочный и многострочный лямбда-выражения для подпрограммы.  
  
 [!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 Обратите внимание, что в предыдущих примерах лямбда-выражения назначены имя переменной. При каждом обращении к переменной вызывается лямбда-выражения. Можно также объявить и вызвать лямбда-выражение, в то же время, как показано в следующем примере.  
  
 [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 Лямбда-выражения могут возвращаться как значение вызванной функции (как показано в примере в [контекста](#context) далее в этом разделе), или передаваться в качестве аргумента параметр, принимающий тип делегата, как показано в следующем примере Пример.  
  
 [!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## <a name="lambda-expression-syntax"></a>Синтаксис лямбда-выражений  
 Синтаксис лямбда-выражения похож стандартные функции или подпрограммы. Существуют следующие различия.  
  
-   Лямбда-выражение не имеет имени.  
  
-   Лямбда-выражения не может содержать модификаторы, такие как `Overloads` или `Overrides`.  
  
-   Не используйте однострочный лямбда-функции `As` предложений, чтобы указать тип возвращаемого значения. Вместо этого тип выводится из значения, результатом которого является тело лямбда-выражения. Например, если тело лямбда-выражения — `cust.City = "London"`, его возвращаемый тип является `Boolean`.  
  
-   В многострочном лямбда-функции, либо можно указать тип возвращаемого значения с помощью `As` предложение, или пропускать `As` предложение, чтобы вывести тип возвращаемого значения. Когда `As` предложение опущено для многострочного лямбда-функции, возвращаемый тип определяется как главный тип из всех `Return` инструкций в многострочном лямбда-функции. *Главным типом* — это уникальный тип, могут быть расширены все другие типы. Если такой уникальный тип нельзя определить, главным типом будет тип, до которого можно сузить все другие типы массива. Если ни один из указанных уникальных типов нельзя определить, главным типом будет `Object`. В этом случае если `Option Strict` равно `On`, возникает ошибка компилятора.  
  
     Например, если предоставленный выражения `Return` инструкции содержат значения типа `Integer`, `Long`, и `Double`, результирующий массив будет иметь тип `Double`. Оба `Integer` и `Long` расширяются до `Double` и только `Double`. Поэтому `Double` является главным типом. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   Тело функции однострочный должен быть выражением, возвращающим значение, не являющийся оператором. Имеется не `Return` инструкции для функций одной строки. Значение, возвращаемое функцией однострочный значение выражения в теле функции.  
  
-   Тело подпрограммы однострочный должно быть однострочного оператора.  
  
-   Не включать одну строку функции и подпрограммы `End Function` или `End Sub` инструкции.  
  
-   Можно указать тип данных параметра лямбда-выражения с помощью `As` ключевое слово или тип данных параметра может быть выведен. Все параметры необходимо задать, необходимо определить типы данных или все.  
  
-   `Optional`и `Paramarray` параметры не разрешены.  
  
-   Универсальные параметры не допускаются.  
  
## <a name="async-lambdas"></a>Асинхронные лямбда-выражения  
 Можно легко создавать лямбда-выражения и операторы, включающие асинхронную обработку с помощью [Async](../../../../visual-basic/language-reference/modifiers/async.md) и [оператор Await](../../../../visual-basic/language-reference/operators/await-operator.md) ключевые слова. Например, в следующем примере Windows Forms содержится обработчик событий, который вызывает асинхронный метод `ExampleMethodAsync`и ожидает его.  
  
```vb  
Public Class Form1  
  
    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' ExampleMethodAsync returns a Task.  
        Await ExampleMethodAsync()  
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 Можно добавить один и тот же обработчик событий с помощью асинхронного лямбда-выражения в [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Чтобы добавить этот обработчик, поставьте модификатор `Async` перед списком параметров лямбда-выражения, как показано в следующем примере.  
  
```vb  
Public Class Form1  
  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AddHandler Button1.Click,   
            Async Sub(sender1, e1)  
                ' ExampleMethodAsync returns a Task.  
                Await ExampleMethodAsync()  
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."  
            End Sub  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 Дополнительные сведения о способах создания и использования асинхронных методах см. в разделе [асинхронное программирование с использованием ключевых слов Async и Await](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
##  <a name="context"></a>Контекст  
 Лямбда-выражение использует общий контекст с областью видимости, в которой он определен. Он имеет те же права доступа, что любой код, написанный в содержащей области. Это включает доступ к переменным-членам, функции и процедурам, `Me`и параметры и локальные переменные в содержащей области.  
  
 Доступ к локальным переменным и параметрам в содержащей области можно продлить сверх времени существования этой области. При условии, что делегат, относящийся к лямбда-выражение не доступен для сборки мусора, сохраняется доступ к переменным в исходной среде. В следующем примере переменная `target` является локальным для `makeTheGame`, метод, в котором лямбда-выражение `playTheGame` определен. Обратите внимание, что возвращенный лямбда-выражения, назначенный `takeAGuess` в `Main`, по-прежнему имеет доступ к локальной переменной `target`.  
  
 [!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 В следующем примере показано широкий спектр прав доступа вложенных лямбда-выражения. При выполнении возвращаемого лямбда-выражения из `Main` как `aDel`, он обращается к следующим элементам:  
  
-   Поле класса, в котором он определен:`aField`  
  
-   Свойство класса, в котором он определен:`aProp`  
  
-   Параметр метода `functionWithNestedLambda`, в котором он определен:`level1`  
  
-   Локальную переменную `functionWithNestedLambda`:`localVar`  
  
-   Параметр лямбда-выражения, в котором он является вложенным:`level2`  
  
 [!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## <a name="converting-to-a-delegate-type"></a>Преобразование в тип делегата  
 Лямбда-выражения могут быть неявно преобразованы к совместимому типу делегата. Сведения об общих требованиях для совместимости см. в разделе [неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Например, в следующем примере кода показано лямбда-выражение, которое неявно преобразуется к `Func(Of Integer, Boolean)` или соответствующей сигнатуре делегата.  
  
 [!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 В следующем примере кода показано лямбда-выражение, которое неявно преобразуется к `Sub(Of Double, String, Double)` или соответствующей сигнатуре делегата.  
  
 [!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 При присваивании лямбда-выражения делегатам или передавать их в качестве аргументов для процедуры, можно указать имена параметров, но опустить их типы, позволяя принимать типы из делегата.  
  
## <a name="examples"></a>Примеры  
  
-   В следующем примере определяется лямбда-выражение, возвращающее `True` Если аргументу типа nullable было присвоено значение, и `False` имеет значение `Nothing`.  
  
     [!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   В следующем примере определяется лямбда-выражение, возвращающее индекс последнего элемента в массиве.  
  
     [!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Типы значений, допускающие значение NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) (Практическое руководство. Передача процедур другой процедуре в Visual Basic)  
 [Практическое руководство. Создание лямбда-выражения](./how-to-create-a-lambda-expression.md)  
 [Неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
