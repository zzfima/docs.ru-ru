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
ms.openlocfilehash: 1827eb5630ed217527de25fc9d9c2bb8994b9aff
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249673"
---
# <a name="lambda-expressions-visual-basic"></a>Лямбда-выражения (Visual Basic)

*Выражение lambda* — это функция или подпрограмма без имени, которое может быть использовано там, где делегат действителен. Выражения Lambda могут быть функциями или подпрограммами и могут быть однолинейными или многолинейными. Вы можете передать значения из текущего объема в выражение lambda.

> [!NOTE]
> Заявление `RemoveHandler` является исключением. Вы не можете передать выражение лямбда `RemoveHandler`для делегата параметр .

Вы создаете выражения лямбда, используя `Function` или `Sub` ключевое слово, так же, как вы создаете стандартную функцию или подпрограмму. Тем не менее, выражения лямбда включены в заявление.

Следующим примером является выражение лямбда, которое приращает свой аргумент и возвращает значение. В примере показан синтаксис выражения одностроки, так и многолинейного выражения лямбда для функции.

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

Следующим примером является выражение лямбда, которое записывает значение для консоли. На примере показан синтаксис выражения одностроки, так и многолинейного выражения лямбда для подпрограммы.

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

Обратите внимание, что в предыдущих примерах выражения лямбда присваиваются переменному имени. Всякий раз, когда вы ссылаетесь на переменную, вы ссылаетесь на выражение лямбда. Вы также можете декларировать и вызывать выражение лямбда в то же время, как показано в следующем примере.

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

Выражение лямбда может быть возвращено в качестве значения вызова функции (как показано в примере в разделе [Контекст](#context) позже в этой теме) или передано в качестве аргумента в параметр, который принимает тип делегата, как показано в следующем примере.

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a>Синтаксис лямбда-выражений

Синтаксис выражения лямбда напоминает выражение стандартной функции или подпрограммы. Различия заключаются в следующем.

- Выражение лямбда не имеет названия.

- Выражения Lambda не могут иметь `Overloads` модификаторы, такие как или `Overrides`.

- Функции однолинейной лямбды не используют `As` положение для обозначения типа возврата. Вместо этого, тип выведен из значения, что тело выражения лямбда оценивает. Например, если тело выражения лямбды, `cust.City = "London"`его `Boolean`тип возврата .

- В многолинейных функциях lambda можно либо указать `As` тип возврата, `As` используя оговорку, либо пропустить оговорку, чтобы вывод типа возврата. Когда `As` оговорка опущена для многолинейной функции лямбды, тип возврата выводится как доминирующий тип из всех `Return` утверждений в многолинейной функции лямбды. *Доминирующим типом* является уникальный тип, который все другие типы могут расширитьдок. Если этот уникальный тип не может быть определен, доминирующим типом является уникальный тип, который все другие типы в массиве могут сузиться до. Если ни один из указанных уникальных типов нельзя определить, главным типом будет `Object`. В этом случае, `Option Strict` если `On`установлен, происходит ошибка компилятора.

     Например, если выражения, поставляемые `Return` в оператора, `Long`содержат `Double`значения типа `Integer`и, `Double`то результирующая массивная часть типа. И `Integer` `Long` расширить `Double` и `Double`только . Поэтому `Double` является главным типом. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

- Тело функции одной строки должно быть выражением, которое возвращает значение, а не заявление. Для однолинейных функций не `Return` существует оператора. Значение, возвращаемые однолинейной функцией, является значением выражения в теле функции.

- Тело однолинейного подпрограммы должно быть однолинейным заявлением.

- Функции и подпрограммы одной строки `End Function` `End Sub` не включают в себя или заявление.

- Можно указать тип параметра выражения лямбда `As` с помощью ключевого слова или сделать вывод о типе параметра. Либо все параметры должны иметь указанные типы данных, либо все должны быть выведены.

- `Optional`и `Paramarray` параметры не допускаются.

- Общие параметры не допускаются.

## <a name="async-lambdas"></a>Асинхронные лямбда-выражения

Вы можете легко создавать выражения и заявления lambda, которые включают асинхронную обработку с помощью ключевых слов [Async](../../../../visual-basic/language-reference/modifiers/async.md) и [Await Operator.](../../../../visual-basic/language-reference/operators/await-operator.md) Например, в следующем примере Windows Forms содержится обработчик событий, который вызывает асинхронный метод `ExampleMethodAsync`и ожидает его.

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

Вы можете добавить тот же обработчик событий с помощью async lambda в [отчете AddHandler.](../../../../visual-basic/language-reference/statements/addhandler-statement.md) Чтобы добавить этот обработчик, поставьте модификатор `Async` перед списком параметров лямбда-выражения, как показано в следующем примере.

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

Для получения дополнительной информации о том, как создавать и использовать методы async, [см.](../../../../visual-basic/programming-guide/concepts/async/index.md)

## <a name="context"></a>Контекст

Выражение лямбда разделяет его контекст с областью, в которой оно определено. Он имеет те же права доступа, что и любой код, написанный в содержащем области. Это включает в себя доступ к переменным членов, функциям и подлодкам, `Me`а также параметрам и локальным переменным в области, содержащему область.

Доступ к локальным переменным и параметрам в содержащейся области может выходить за рамки срока службы этой сферы. До тех пор, пока делегат, ссылаясь на выражение лямбды, не доступен для сбора мусора, доступ к переменным в исходной среде сохраняется. В следующем примере `target` переменная `makeTheGame`является локальной для метода, в котором определяется выражение `playTheGame` лямбда. Обратите внимание, что возвращенное выражение `takeAGuess` `Main`lambda, назначенное `target`в, по-прежнему имеет доступ к локальной переменной.

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

Следующий пример демонстрирует широкий спектр прав доступа вложенного выражения лямбда. Когда возвращенное выражение lambda `Main` `aDel`выполняется от как, оно получает доступ к этим элементам:

- Поле класса, в котором он определяется:`aField`

- Свойство класса, в котором он определяется:`aProp`

- Параметр метода, `functionWithNestedLambda`в котором он определен:`level1`

- Локальная `functionWithNestedLambda`переменная:`localVar`

- Параметр выражения лямбда, в котором она вложена:`level2`

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a>Преобразование в тип делегата

Выражение лямбда может быть неявно преобразовано в совместимый тип делегата. Для получения информации об общих требованиях к совместимости [см.](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md) Например, в следующем примере кода показано выражение лямбда, которое неявно преобразуется `Func(Of Integer, Boolean)` в подпись делегата или соответствующую подпись делегата.

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

Следующий пример кода показывает выражение лямбда, `Sub(Of Double, String, Double)` которое неявно преобразуется в или соответствующую подпись делегата.

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

При присвоении выражения мягца делегатам или в качестве аргументов в процедуры можно указать имена параметров, но пропустить их типы данных, позволяя отнять типы данных у делегата.

## <a name="examples"></a>Примеры

- Следующий пример определяет выражение lambda, которое возвращается, `True` если аргумент типа `False` нулевой `Nothing`значения имеет присвоенное значение, и если его значение находится в .

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- Следующий пример определяет выражение лямбда, которое возвращает индекс последнего элемента в массиве.

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Типы значений, допускающие значение NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Практическое руководство. Передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Практическое руководство. Создание лямбда-выражения](./how-to-create-a-lambda-expression.md)
- [Неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
