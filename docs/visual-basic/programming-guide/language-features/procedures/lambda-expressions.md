---
title: "Лямбда-выражения (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.LambdaFunction
dev_langs:
- VB
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: e50593e76afecfe8807c3cb5bac479245d2feaef
ms.lasthandoff: 03/13/2017

---
# <a name="lambda-expressions-visual-basic"></a>Лямбда-выражения (Visual Basic)
Объект *лямбда-выражение* является функцией или подпрограммой без имени, которую можно использовать везде, где допустим делегат. Лямбда-выражения могут быть функциями или подпрограммами и может быть одной или нескольких строк. Лямбда-выражение можно передавать значения из текущей области.  
  
> [!NOTE]
>  `RemoveHandler` Инструкция является исключением. Невозможно передать лямбда-выражение в параметра делегата для `RemoveHandler`.  
  
 Лямбда-выражения создаются с помощью `Function` или `Sub` ключевое слово, так же как стандартные функции или подпрограммы. Однако лямбда-выражения включаются в оператор.  
  
 Следующий пример является лямбда-выражение, которое увеличивает значение своего аргумента и возвращает значение. В этом примере синтаксис однострочные и многострочные лямбда-выражения для функции.  
  
 [!code-vb[VbVbalrLambdas&#14;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 Следующий пример является лямбда-выражения, записывающего значение на консоль. В этом примере синтаксис однострочные и многострочные лямбда-выражения для подпрограммы.  
  
 [!code-vb[VbVbalrLambdas&#15;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 Обратите внимание, что в предыдущих примерах лямбда-выражения назначены имя переменной. При каждом обращении к переменной вызывается лямбда-выражение. Можно также объявить и вызвать лямбда-выражение, в то же время, как показано в следующем примере.  
  
 [!code-vb[VbVbalrLambdas&#3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 Лямбда-выражения могут возвращаться как значение вызванной функции (как показано в примере в [контекста](#context) позже в этой статье), либо передано в качестве аргумента параметр, который принимает тип делегата, как показано в следующем примере.  
  
 [!code-vb[VbVbalrLambdas №&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## <a name="lambda-expression-syntax"></a>Синтаксис лямбда-выражений  
 Синтаксис лямбда-выражения похож стандартные функции или подпрограммы. Ниже приведены различия.  
  
-   Лямбда-выражение не имеет имени.  
  
-   Лямбда-выражения не могут иметь модификаторы, такие как `Overloads` или `Overrides`.  
  
-   Однострочные лямбда-функции не используют `As` предложения, чтобы указать тип возвращаемого значения. Вместо этого тип выводится из значения, результатом которого является тело лямбда-выражения. Например, если тело лямбда-выражения — `cust.City = "London"`, возвращается тип `Boolean`.  
  
-   В многострочных лямбда-функции, можно указать тип возвращаемого значения с помощью `As` предложение, или пропускать `As` предложение, чтобы вывести тип возвращаемого значения. Когда `As` опущен для многострочных лямбда-функции, возвращаемый тип определяется как главный тип из всех `Return` инструкций в многострочных лямбда-функции. *Главный тип* — это уникальный тип, могут быть расширены все другие типы. Если такой уникальный тип нельзя определить, главным типом будет тип, до которого можно сузить все другие типы массива. Если ни один из указанных уникальных типов нельзя определить, главным типом будет `Object`. В этом случае если `Option Strict` равен `On`, возникает ошибка компилятора.  
  
     Например, если передан выражения `Return` инструкции содержат значения типа `Integer`, `Long`, и `Double`, полученный массив имеет тип `Double`. Оба `Integer` и `Long` расширяются до `Double` и только `Double`. Поэтому `Double` является главным типом. Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   Тело функции однострочный должно быть выражение, возвращающее значение, а не оператором. Существует не `Return` инструкции для однострочных функций. Значение, возвращаемое функцией однострочный значение выражения в теле функции.  
  
-   Тело подпрограммы однострочный должно быть одностроковый оператор.  
  
-   Не включайте однострочных функций и подпрограмм `End Function` или `End Sub` инструкции.  
  
-   Тип данных параметра лямбда-выражения можно указать с помощью `As` ключевое слово или тип данных параметра может быть выведен. Все параметры должно было быть задано, что необходимо определить типы данных или все.  
  
-   `Optional`и `Paramarray` параметры не допускаются.  
  
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
  
 Можно добавить тот же обработчик событий с помощью асинхронного лямбда-выражения в [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Чтобы добавить этот обработчик, поставьте модификатор `Async` перед списком параметров лямбда-выражения, как показано в следующем примере.  
  
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
  
 Дополнительные сведения о том, как создавать и использовать асинхронные методы см. в разделе [асинхронное программирование с использованием Async и Await](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
##  <a name="context"></a>Контекст  
 Лямбда-выражение использует общий контекст с областью, в которой он определен. Он имеет те же права доступа, что любой код, написанный в содержащей области. Это включает доступ к переменным-членам, функции и подпрограммы, `Me`и параметры, так и локальные переменные в содержащей области.  
  
 Доступ к локальным переменным и параметрам в содержащей области можно продлить сверх времени существования этой области. При условии, что делегат, относящийся к лямбда-выражение не доступен для сборки мусора, доступ к переменным среды исходного кода сохраняется. В следующем примере переменная `target` является локальным для `makeTheGame`, метод которого лямбда-выражение `playTheGame` определен. Обратите внимание, что возвращаемое лямбда-выражения, назначенные `takeAGuess` в `Main`, по-прежнему есть доступ к локальной переменной `target`.  
  
 [!code-vb[VbVbalrLambdas&#12;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 В следующем примере показано широкий спектр прав доступа вложенных лямбда-выражения. При выполнении возвращаемого лямбда-выражения из `Main` как `aDel`, он обращается к следующим элементам:  
  
-   Поле класса, в котором он определен:`aField`  
  
-   Свойство класса, в котором он определен:`aProp`  
  
-   Параметр метода `functionWithNestedLambda`, в котором он определен:`level1`  
  
-   Локальная переменная `functionWithNestedLambda`:`localVar`  
  
-   Параметр лямбда-выражения, в котором он является вложенным:`level2`  
  
 [!code-vb[VbVbalrLambdas №&9;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## <a name="converting-to-a-delegate-type"></a>Преобразование к типу делегата  
 Лямбда-выражения могут быть неявно преобразованы к совместимому типу делегата. Сведения об общих требованиях для совместимости см. в разделе [неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Например, в следующем примере кода показано лямбда-выражение, которое неявно преобразуется к `Func(Of Integer, Boolean)` или соответствующей сигнатуре делегата.  
  
 [!code-vb[VbVbalrLambdas №&16;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 В следующем примере кода показано лямбда-выражение, которое неявно преобразуется к `Sub(Of Double, String, Double)` или соответствующей сигнатуре делегата.  
  
 [!code-vb[VbVbalrLambdas&#23;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 При присваивании лямбда-выражений делегатам или передавать их в качестве аргументов для процедуры, можно указать имена параметров, но опустить их типы, позволяя принимать типы из делегата.  
  
## <a name="examples"></a>Примеры  
  
-   В следующем примере определяется лямбда-выражение, возвращающее `True` Если аргументу типа nullable было присвоено значение, и `False` имеет значение `Nothing`.  
  
     [!code-vb[VbVbalrLambdas&#4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   В следующем примере определяется лямбда-выражение, возвращающее индекс последнего элемента в массиве.  
  
     [!code-vb[VbVbalrLambdas&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Обнуляемые типы значений](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Практическое руководство: передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Практическое руководство: создание лямбда-выражения](./how-to-create-a-lambda-expression.md)   
 [Неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
