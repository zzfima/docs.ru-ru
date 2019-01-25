---
title: Лямбда-выражения (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: 3d2cab1c40b1a84e9a3b6bed885b2a0020e53f01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529480"
---
# <a name="lambda-expressions-visual-basic"></a>Лямбда-выражения (Visual Basic)
Объект *лямбда-выражение* является функцией или подпрограммой без имени, который может использоваться везде, где допустим делегат. Лямбда-выражения могут быть функции или подпрограммы и может быть одной или нескольких линий. Можно передавать значения из текущей области в лямбда-выражение.  
  
> [!NOTE]
>  `RemoveHandler` Инструкция является исключением. Невозможно передать лямбда-выражение в для параметра делегата `RemoveHandler`.  
  
 Лямбда-выражения можно создавать с помощью `Function` или `Sub` ключевое слово, точно так же, как стандартные функции или подпрограммы. Тем не менее лямбда-выражения включаются в инструкции.  
  
 Следующий пример является лямбда-выражения и увеличивает значение своего аргумента и возвращает значение. В этом примере синтаксис однострочные и многострочные лямбда-выражений для функции.  
  
 [!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 Следующий пример является лямбда-выражения и записывает значение в консоль. В примере синтаксиса однострочные и многострочные лямбда-выражения для подпрограммы.  
  
 [!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 Обратите внимание на то, что в предыдущих примерах лямбда-выражения относятся к имени переменной. При ссылке на эту переменную, можно вызвать лямбда-выражения. Можно также объявить и вызвать лямбда-выражение, в то же время, как показано в следующем примере.  
  
 [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 Лямбда-выражения могут быть возвращены для параметра вызов функции (как показано в примере в [контекст](#context) разделе этой статьи), или передаваться в качестве аргумента параметр, принимающий тип делегата, как показано ниже Пример.  
  
 [!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## <a name="lambda-expression-syntax"></a>Синтаксис лямбда-выражений  
 Синтаксис лямбда-выражения похож стандартные функции или подпрограммы. Ниже приведены различия.  
  
-   Лямбда-выражение не имеет имени.  
  
-   Лямбда-выражения не может иметь модификаторы, такие как `Overloads` или `Overrides`.  
  
-   Не используйте однострочное лямбда-функции `As` предложение, чтобы указать тип возвращаемого значения. Вместо этого тип выводится из значения, тело лямбда-выражение, результатом которого является. Например, если тело лямбда-выражения — `cust.City = "London"`, его возвращаемый тип — `Boolean`.  
  
-   В функциях многострочные лямбда-выражения, можно указать тип возвращаемого значения с помощью `As` предложения, или пропустите `As` предложение, чтобы вывести тип возвращаемого значения. Когда `As` предложение опущено для многострочного лямбда-функцию, тип возвращаемого значения определяется как главный тип из всех `Return` инструкций в многострочные лямбда-функции. *Главным типом* — это уникальный тип, могут быть расширены все другие типы. Если такой уникальный тип нельзя определить, главным типом является тип, до которого можно сузить все другие типы массива. Если ни один из указанных уникальных типов нельзя определить, главным типом будет `Object`. В этом случае если `Option Strict` присваивается `On`, возникает ошибка компилятора.  
  
     Например, если выражения `Return` инструкция содержит значения типа `Integer`, `Long`, и `Double`, результирующий массив будет иметь тип `Double`. Оба `Integer` и `Long` расширяющего преобразования к `Double` и только `Double`. Поэтому `Double` является главным типом. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   Тело функции однострочный должно быть выражение, возвращающее значение, не являющийся оператором. Существует не `Return` инструкции для однострочных функций. Значение, возвращаемое функцией однострочный значение выражения в теле функции.  
  
-   Подпрограммы однострочный текст должен быть одинарная оператором.  
  
-   Не используйте однострочных функций и подпрограмм `End Function` или `End Sub` инструкции.  
  
-   Можно указать тип данных параметра лямбда-выражения с помощью `As` ключевое слово или тип данных параметра может быть выведен. Необходимо заранее указать все параметры, что необходимо определить типы данных или все.  
  
-   `Optional` и `Paramarray` параметров не разрешены.  
  
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
  
 Дополнительные сведения о том, как создать и использовать асинхронные методы, см. в разделе [асинхронное программирование с использованием Async и Await](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
##  <a name="context"></a> Контекст  
 Лямбда-выражение использует общий контекст с областью, в котором он определен. Он имеет те же права доступа, что любой код, написанный в содержащей области. Это включает доступ к переменным-членам, функции и подпрограммы, `Me`и параметры, так и локальные переменные в содержащей области.  
  
 Доступ к локальным переменным и параметрам в содержащей области можно расширить за время существования этой области. До тех пор, пока делегат, ссылающийся на лямбда-выражение не доступен в сборку мусора, можно сохранить доступ к переменным в исходной среде. В следующем примере переменной `target` является локальным для `makeTheGame`, метод, в котором лямбда-выражение `playTheGame` определен. Обратите внимание, что возвращенный лямбда-выражения, назначенный `takeAGuess` в `Main`, по-прежнему имеет доступ к локальной переменной `target`.  
  
 [!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 В следующем примере показано широкий спектр прав доступа вложенных лямбда-выражения. При выполнении возвращаемого лямбда-выражения из `Main` как `aDel`, он обращается к следующим элементам:  
  
-   Поле класса, в котором он определен: `aField`  
  
-   Свойство класса, в котором он определен: `aProp`  
  
-   Параметр метода `functionWithNestedLambda`, в котором она была определена: `level1`  
  
-   Локальная переменная `functionWithNestedLambda`: `localVar`  
  
-   Параметр лямбда-выражения, в который он вложен: `level2`  
  
 [!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## <a name="converting-to-a-delegate-type"></a>Преобразование в тип делегата  
 Лямбда-выражения могут быть неявно преобразованы совместимого типа делегата. Сведения об общих требованиях для обеспечения совместимости, см. в разделе [неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Например, в следующем примере кода показано лямбда-выражение, которое неявно преобразуется к `Func(Of Integer, Boolean)` или соответствующий сигнатуре делегата.  
  
 [!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 В следующем примере кода показано лямбда-выражение, которое неявно преобразуется к `Sub(Of Double, String, Double)` или соответствующий сигнатуре делегата.  
  
 [!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 Когда назначать делегатам лямбда-выражения или передавать их в качестве аргументов для процедуры, можно указать имена параметров, но опустить их типы, позволяя принимать типы из делегата.  
  
## <a name="examples"></a>Примеры  
  
-   В следующем примере определяется лямбда-выражение, возвращающее `True` Если присвоено значение, допускающее значение NULL аргумент и `False` имеет значение `Nothing`.  
  
     [!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   В следующем примере определяется лямбда-выражение, которое возвращает индекс последнего элемента в массиве.  
  
     [!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## <a name="see-also"></a>См. также
- [Процедуры](./index.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Типы значений, допускающие значение NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Практическое руководство. Передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Практическое руководство. Создать лямбда-выражение](./how-to-create-a-lambda-expression.md)
- [Неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
