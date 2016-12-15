---
title: "Лямбда-выражения (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.LambdaFunction"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "выражения [Visual Basic], лямбда-оператор"
  - "функции [Visual Basic], лямбда-выражения"
  - "встроенные функции [Visual Basic]"
  - "лямбда-выражения [Visual Basic]"
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
caps.handback.revision: 52
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Лямбда-выражения (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*Лямбда\-выражение* является функцией или подпрограммой без имени, которую можно использовать везде, где допустим делегат.  Лямбда\-выражения могут быть функциями или подпрограммами и содержать одну или несколько строк.  Можно передавать значения из текущей области в лямбда\-выражение.  
  
> [!NOTE]
>  Исключением является оператор `RemoveHandler`.  Невозможно передать лямбда\-выражение в качестве параметра делегата `RemoveHandler`.  
  
 Лямбда\-выражения можно создавать с помощью ключевых слов `Function` или `Sub`, так же как стандартные функции или подпрограммы.  Однако лямбда\-выражения включаются в оператор.  
  
 В следующем примере лямбда\-выражение увеличивает значение своего аргумента и возвращает его.  В примере показан синтаксис однострокового и многострокового лямбда\-выражения для функции.  
  
 [!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 Ниже приведен пример лямбда\-выражения, записывающего значение на консоль.  В примере показан синтаксис однострокового и многострокового лямбда\-выражения для подпрограммы.  
  
 [!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 Обратите внимание, что в предыдущих примерах лямбда\-выражения присваиваются имени переменной.  При каждом обращении к переменной вызывается лямбда\-выражение.  Можно также объявить и вызвать лямбда\-выражение одновременно, как показано в следующем примере.  
  
 [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 Лямбда\-выражения могут возвращаться как значение вызванной функции \(как показано в примере подраздела [Контекст](#context) ниже в этом разделе\) или могут передаваться в качестве аргумента в параметр, который принимает тип делегата, как показано в следующем примере.  
  
 [!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## Синтаксис лямбда\-выражений  
 Синтаксис лямбда\-выражения похож на синтаксис стандартной функции или подпрограммы.  Различия заключаются в следующем:  
  
-   Лямбда\-выражение не имеет имени.  
  
-   Лямбда\-выражения не могут включать модификаторы, такие как `Overloads` или `Overrides`.  
  
-   Одностроковые лямбда\-функции не используют предложение `As` для обозначения типа возвращаемого значения.  Вместо этого тип выводится из значения, которое вычисляется в теле лямбда\-выражения.  Например, если тело лямбда\-выражения — `cust.City = "London"`, возвращается тип `Boolean`.  
  
-   В многостроковых лямбда\-функциях можно либо задать возвращаемый тип с помощью предложения `As`, либо опустить предложение `As`, тогда возвращаемый тип будет выведен.  Когда предложение `As` опускается в многостроковой лямбда\-функции, возвращаемый тип выводится как главный тип из всех операторов `Return` в многостроковой лямбда\-функции.  *Преобладающий тип* других типов можно расширить на уникальный тип.  Если такой уникальный тип нельзя определить, то главным типом будет тип, до которого можно сузить все другие типы массива.  Если ни один из указанных уникальных типов нельзя определить, главным типом будет `Object`.  В этом случае, если для `Option Strict` установлено значение `On`, возникает ошибка компилятора.  
  
     Например, если предоставленный выражения `Return` инструкции содержат значения типа `Integer`, `Long`, и `Double`, результирующий массив имеет тип `Double`.  Типы `Integer` и `Long` расширяются до типа `Double` и только `Double`.  Поэтому `Double` является главным типом.  Дополнительные сведения см. в разделе [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   Телом одностроковой функции должно быть выражение, которое возвращает значение, а не оператор.  Для одностроковых функций нет оператора `Return`.  Значение, возвращаемое одностроковой функцией, является значением выражения в теле функции.  
  
-   Телом одностроковой подпрограммы должен быть одностроковый оператор.  
  
-   Одностроковые функции и подпрограммы не включают операторы `End Function` или `End Sub`.  
  
-   Можно задать тип данных параметра лямбда\-выражения с помощью ключевого слова `As`, либо тип данных параметра может быть выведен.  Все параметры должны иметь определенный или выводимый тип данных.  
  
-   Параметры `Optional` и `Paramarray` не разрешены.  
  
-   Универсальные параметры не разрешены.  
  
## Асинхронный лямбда\-выражения  
 Можно легко создавать лямбда\-выражения и операторы, которые включают асинхронной обработки с помощью [Async](../../../../visual-basic/language-reference/modifiers/async.md) и [Оператор Await](../../../../visual-basic/language-reference/operators/await-operator.md) ключевые слова.  Например, в следующем примере Windows Forms содержит обработчик событий, вызывающий и awaits метод асинхронного `ExampleMethodAsync`.  
  
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
  
 Можно добавить один и тот же обработчик событий с помощью асинхронных лямбда в [Оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md).  Чтобы добавить этот обработчик `Async` модификатор перед списке параметров лямбда, как показано в следующем примере.  
  
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
  
 Дополнительные сведения о том, как создать и использовать асинхронные методы, см. [Асинхронное программирование с использованием ключевых слов Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
##  <a name="context"></a> Контекст  
 Лямбда\-выражение использует общий контекст с областью, внутри которой оно определено.  Оно имеет те же права доступа, что и любой код, написанный в содержащей области.  Это включает доступ к переменным членов, функциям, процедурам, `Me`, а также параметрам и локальным переменным в содержащей области.  
  
 Доступ к локальным переменным и параметрам в содержащей области можно продлить сверх времени существования этой области.  До тех пор, пока делегат, ссылающийся на делегат лямбда\-выражения, недоступен сборщику мусора, доступ к переменным среды исходного кода сохраняется.  В следующем примере переменная `target` является локальной для метода `makeTheGame`, в котором определено лямбда\-выражение `playTheGame`.  Обратите внимание, что возвращаемое лямбда\-выражение, присваивается `takeAGuess` в `Main`, который по\-прежнему сохраняет доступ к локальной переменной `target`.  
  
 [!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 В следующем примере показан широкий спектр прав доступа вложенных лямбда\-выражений.  При выполнении возвращаемого лямбда\-выражения из `Main` как `aDel`, он обращается к следующим элементам:  
  
-   Поле класса, в котором он определен: `aField`.  
  
-   Свойство класса, в котором он определен: `aProp`.  
  
-   Параметр метода `functionWithNestedLambda`, в котором он определен: `level1`.  
  
-   Локальная переменная `functionWithNestedLambda`: `localVar`.  
  
-   Параметр лямбда\-выражения, в котором он является вложенным: `level2`.  
  
 [!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## Преобразование к типу делегата  
 Лямбда\-выражения могут быть неявно преобразованы к совместимому типу делегата.  Сведения об общих требованиях для совместимости см. в разделе [Неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  Например, следующий пример кода показывает лямбда\-выражение, которое неявно преобразуется к типу `Func(Of Integer, Boolean)` или соответствующей сигнатуре делегата.  
  
 [!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 В следующем примере кода показано лямбда\-выражение, которое неявно преобразуется к типу `Sub(Of Double, String, Double)` или соответствующей сигнатуре делегата.  
  
 [!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 При присваивании лямбда\-выражений делегатам или передаче их в качестве аргументов процедурам можно указать имена параметров, но опустить их типы, позволяя принимать типы из делегата.  
  
## Примеры  
  
-   В следующем примере определяется лямбда\-выражение, которое возвращает `True`, если аргументу типа nullable было присвоено значение, и `False`, если аргумент имеет значение `Nothing`.  
  
     [!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   В следующем примере определяется лямбда\-выражение, возвращающее индекс последнего элемента в массиве.  
  
     [!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Типы значения, допускающие Null](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Практическое руководство. Передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Практическое руководство. Создание лямбда\-выражения](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-lambda-expression.md)   
 [Неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)