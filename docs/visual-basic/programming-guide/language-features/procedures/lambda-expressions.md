---
title: Лямбда-выражения
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: f3f963167e1b3633cc5fe6e1f435e374cd272cce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345977"
---
# <a name="lambda-expressions-visual-basic"></a>Лямбда-выражения (Visual Basic)

*Лямбда-выражение* — это функция или подпрограммы без имени, которую можно использовать везде, где действует делегат. Лямбда-выражения могут быть функциями или подподпрограммами и могут быть однострочными или многострочными. Можно передать значения из текущей области в лямбда-выражение.

> [!NOTE]
> Оператор `RemoveHandler` является исключением. Невозможно передать лямбда-выражение в для параметра делегата `RemoveHandler`.

Лямбда-выражения создаются с помощью ключевого слова `Function` или `Sub`, как при создании стандартной функции или подпрограммы. Однако лямбда-выражения включаются в оператор.

Следующий пример представляет собой лямбда-выражение, которое увеличивает свой аргумент и возвращает значение. В примере показан синтаксис однострочного и многострочного лямбда-выражения для функции.

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

Следующий пример представляет собой лямбда-выражение, которое записывает значение в консоль. В примере показан синтаксис однострочного и многострочного лямбда-выражения для подпрограммы.

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

Обратите внимание, что в предыдущих примерах лямбда-выражения присваиваются имени переменной. При каждом обращении к переменной вызывается лямбда-выражение. Можно также объявить и вызвать лямбда-выражение одновременно, как показано в следующем примере.

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

Лямбда-выражение может быть возвращено как значение вызова функции (как показано в примере в разделе " [контекст](#context) " Далее в этом разделе) или передано в качестве аргумента в параметр, принимающий тип делегата, как показано в следующем примере.

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a>Синтаксис лямбда-выражений

Синтаксис лямбда-выражения напоминает стандартную функцию или подпрограммы. Различия заключаются в следующем.

- Лямбда-выражение не имеет имени.

- Лямбда-выражения не могут иметь модификаторы, такие как `Overloads` или `Overrides`.

- Однострочные лямбда-функции не используют предложение `As` для обозначения возвращаемого типа. Вместо этого тип выводится из значения, которое вычисляется телом лямбда-выражения. Например, если тело лямбда-выражения имеет `cust.City = "London"`, его возвращаемый тип — `Boolean`.

- В многострочных лямбда-функциях можно либо указать тип возвращаемого значения с помощью предложения `As`, либо опустить предложение `As`, чтобы тип возвращаемого значения был выведен. Если в многострочной лямбда-функции пропущено предложение `As`, возвращаемый тип определяется как главный тип от всех инструкций `Return` в многострочной лямбда-функции. *Главный тип* — это уникальный тип, к которому могут расширяться все другие типы. Если невозможно определить этот уникальный тип, главным типом является уникальный тип, до которого могут быть ограничены все другие типы в массиве. Если ни один из указанных уникальных типов нельзя определить, главным типом будет `Object`. В этом случае, если `Option Strict` имеет значение `On`, возникает ошибка компилятора.

     Например, если выражения, передаваемые в оператор `Return`, содержат значения типа `Integer`, `Long`и `Double`, полученный массив имеет тип `Double`. Как `Integer`, так `Long` расширяются до `Double` и только `Double`. Поэтому `Double` является главным типом. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

- Тело однострочной функции должно быть выражением, возвращающим значение, а не оператором. Для однострочных функций отсутствует `Return`ная инструкция. Значение, возвращаемое однострочной функцией, является значением выражения в теле функции.

- Тело однострочной подпрограммы должно быть однострочным оператором.

- Однострочные функции и подпрограммы не включают `End Function` или `End Sub` инструкции.

- Можно указать тип данных параметра лямбда-выражения с помощью ключевого слова `As`, или же тип данных параметра может быть определен. Либо все параметры должны иметь указанные типы данных, либо все должны быть выведены.

- Параметры `Optional` и `Paramarray` не разрешены.

- Универсальные параметры не допускаются.

## <a name="async-lambdas"></a>Асинхронные лямбда-выражения

Можно легко создавать лямбда-выражения и инструкции, включающие асинхронную обработку с помощью ключевых слов оператора [Async](../../../../visual-basic/language-reference/modifiers/async.md) и [await](../../../../visual-basic/language-reference/operators/await-operator.md) . Например, в следующем примере Windows Forms содержится обработчик событий, который вызывает асинхронный метод `ExampleMethodAsync`и ожидает его.

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

Вы можете добавить тот же обработчик событий с помощью асинхронного лямбда-выражения в [операторе AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Чтобы добавить этот обработчик, поставьте модификатор `Async` перед списком параметров лямбда-выражения, как показано в следующем примере.

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

Дополнительные сведения о создании и использовании асинхронных методов см. в разделе [Асинхронное программирование с использованием Async и await](../../../../visual-basic/programming-guide/concepts/async/index.md).

## <a name="context"></a>Контекст

Лямбда-выражение использует свой контекст с областью, в которой он определен. Он имеет те же права доступа, что и любой код, написанный в содержащей его области. Это включает доступ к переменным элементов, функциям и процедурам, `Me`, а также параметрам и локальным переменным в содержащей их области.

Доступ к локальным переменным и параметрам в содержащей области может дополняться за время существования этой области. Пока делегат, ссылающийся на лямбда-выражение, недоступен для сборки мусора, доступ к переменным в исходной среде сохраняется. В следующем примере переменная `target` локальная для `makeTheGame`, метод, в котором определяется лямбда-выражение `playTheGame`. Обратите внимание, что возвращенное лямбда-выражение, назначенное `takeAGuess` в `Main`, по-прежнему имеет доступ к локальной переменной `target`.

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

В следующем примере показан широкий спектр прав доступа вложенного лямбда-выражения. Когда возвращаемое лямбда-выражение выполняется из `Main` как `aDel`, оно обращается к следующим элементам:

- Поле класса, в котором оно определено: `aField`

- Свойство класса, в котором оно определено: `aProp`

- Параметр метода `functionWithNestedLambda`, в котором он определен: `level1`

- Локальная переменная `functionWithNestedLambda`: `localVar`

- Параметр лямбда-выражения, в котором он вложен: `level2`

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a>Преобразование в тип делегата

Лямбда-выражение может быть неявно преобразовано в совместимый тип делегата. Сведения о общих требованиях к совместимости см. в разделе [неявное преобразование делегатов](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Например, в следующем примере кода показано лямбда-выражение, которое неявно преобразуется в `Func(Of Integer, Boolean)` или соответствующую сигнатуру делегата.

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

В следующем примере кода показано лямбда-выражение, которое неявно преобразуется в `Sub(Of Double, String, Double)` или соответствующую сигнатуру делегата.

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

При назначении лямбда-выражений делегатам или передаче их в качестве аргументов в процедуры можно указать имена параметров, но не указывать их типы данных, позволяя принимать типы из делегата.

## <a name="examples"></a>Примеры

- В следующем примере определяется лямбда-выражение, которое возвращает `True`, если аргументу, допускающему значение null, присвоено значение, и `False`, если его значение равно `Nothing`.

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- В следующем примере определяется лямбда-выражение, возвращающее индекс последнего элемента в массиве.

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Типы значений, допускающие значение NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) (Практическое руководство. Передача процедур другой процедуре в Visual Basic)
- [Практическое руководство. Создание лямбда-выражения](./how-to-create-a-lambda-expression.md)
- [Неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
