---
title: Оператор For Each...Next (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
helpviewer_keywords:
- infinite loops
- Next statement [Visual Basic], For Each...Next
- endless loops
- loop structures [Visual Basic], For Each...Next
- loops, endless
- Each keyword [Visual Basic]
- instructions, repeating
- For Each statement [Visual Basic]
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement [Visual Basic], For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
ms.openlocfilehash: f56e5defa2328011d222bfca05334b610e805055
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332785"
---
# <a name="for-eachnext-statement-visual-basic"></a>Оператор For Each...Next (Visual Basic)

Повторяет группу операторов для каждого элемента в коллекции.

## <a name="syntax"></a>Синтаксис

```vb
For Each element [ As datatype ] In group
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ element ]
```

## <a name="parts"></a>Части

|Термин|Определение|
|---|---|
|`element`|Требуется в операторе `For Each`. Необязательный в операторе `Next`. Перемен. Используется для прохода по элементам коллекции.|
|`datatype`|Необязательный параметр, если [`Option Infer`](option-infer-statement.md) имеет значение On (по умолчанию) или `element` уже объявлен; требуется, если `Option Infer` имеет значение OFF и `element` еще не объявлено. Тип данных `element`.|
|`group`|Обязательное. Переменная типа, которая является типом коллекции или объектом. Ссылается на коллекцию, в которой `statements` повторяется.|
|`statements`|Необязательно. Одна или несколько инструкций между `For Each` и `Next`, которые выполняются для каждого элемента в `group`.|
|`Continue For`|Необязательно. Передает управление в начало цикла `For Each`.|
|`Exit For`|Необязательно. Передает управление за пределы цикла `For Each`.|
|`Next`|Обязательное. Завершает определение цикла `For Each`.|

## <a name="simple-example"></a>Простой пример

Используйте цикл `For Each`...`Next`, если необходимо повторить набор инструкций для каждого элемента коллекции или массива.

> [!TIP]
> A [для... Оператор Next](../../../visual-basic/language-reference/statements/for-next-statement.md) работает хорошо, когда можно связать каждую итерацию цикла с управляющей переменной и определить начальные и конечные значения переменной. Однако при работе с коллекцией концепция начальных и конечных значений не имеет смысла, и вам не обязательно быть уверенным, сколько элементов имеет коллекция. В этом случае цикл `For Each`...`Next` часто является лучшим выбором.

В следующем примере `For Each`...`Next` выполняет перебор всех элементов коллекции списков.

[!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]

Дополнительные примеры см. в разделе [коллекции](../../../standard/collections/index.md) и [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).

## <a name="nested-loops"></a>Вложенные циклы

Можно вкладывать `For Each` циклы, помещая один цикл внутрь другого.

В следующем примере демонстрируется вложенная `For Each`...`Next` Сотрудник.

[!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]

При вложении циклов каждый цикл должен иметь уникальную переменную `element`.

Можно также вкладывать различные виды управляющих структур друг в друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).

## <a name="exit-for-and-continue-for"></a>Выход и продолжение для

Оператор [Exit For](../../../visual-basic/language-reference/statements/exit-statement.md) вызывает завершение выполнения `For`...`Next` выполняет цикл и передает управление оператору, который следует за оператором `Next`.

Оператор `Continue For` передает управление сразу в следующую итерацию цикла. Дополнительные сведения см. в разделе [оператор continue](../../../visual-basic/language-reference/statements/continue-statement.md).

В следующем примере показано, как использовать операторы `Continue For` и `Exit For`.

[!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]

В цикле `For Each` можно разместить любое количество `Exit For` инструкций. При использовании внутри вложенных циклов `For Each` `Exit For` вызывает завершение самого внутреннего цикла и передает управление следующему более высокому уровню вложенности.

`Exit For` часто используется после оценки некоторого условия, например, в структуре `If`...`Then`...`Else`. `Exit For` может потребоваться использовать для следующих условий:

- Продолжение итерации не требуется или невозможно. Это может быть вызвано ошибочным значением или запросом на завершение.

- Исключение перехвачено в `Try`...`Catch`...`Finally`. В конце блока `Finally` можно использовать `Exit For`.

- Существует бесконечный цикл, который может выполняться с большим или даже бесконечным числом раз. При обнаружении такого условия можно использовать `Exit For` для экранирования цикла. Дополнительные сведения см. в разделе [Do... Loop, инструкция](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="iterators"></a>Итераторы

*Итератор* используется для выполнения пользовательской итерации по коллекции. Итератор может быть функцией или методом доступа `Get`. Он использует оператор `Yield` для возвращения каждого элемента коллекции по одному за раз.

Итератор вызывается с помощью оператора `For Each...Next`. Каждая итерация цикла `For Each` вызывает итератор. При достижении оператора `Yield` в итераторе возвращается выражение в операторе `Yield`, а текущее расположение в коде сохраняется. При следующем вызове итератора выполнение возобновляется с этого места.

В следующем примере используется функция итератора. Функция итератора содержит оператор `Yield`, который находится внутри блока [for... Следующий](../../../visual-basic/language-reference/statements/for-next-statement.md) цикл. В методе `ListEvenNumbers` каждая итерация тела оператора `For Each` создает вызов функции итератора, который переходит к следующей инструкции `Yield`.

[!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]

Дополнительные сведения см. в разделе [итераторы](../../programming-guide/concepts/iterators.md), [оператор yield](../../../visual-basic/language-reference/statements/yield-statement.md)и [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).

## <a name="technical-implementation"></a>Техническая реализация

Когда `For Each`...`Next` выполняется инструкция, Visual Basic вычисляет коллекцию только один раз перед началом цикла. Если блок инструкции изменяет `element` или `group`, эти изменения не влияют на итерацию цикла.

Когда все элементы в коллекции последовательно назначаются `element`, цикл `For Each` останавливается и управление передается оператору, следующему за оператором `Next`.

Если [параметр Infer](option-infer-statement.md) имеет значение On (значение по умолчанию), то компилятор Visual Basic может определить тип данных `element`. Если она отключена и `element` не объявлена за пределами цикла, необходимо объявить ее в операторе `For Each`. Чтобы явно объявить тип данных `element`, используйте предложение `As`. Если тип данных элемента не определен за пределами конструкции `For Each`...`Next`, его областью является тело цикла. Обратите внимание, что нельзя объявлять `element` как за пределами, так и внутри цикла.

При необходимости можно указать `element` в инструкции `Next`. Это повышает удобочитаемость программы, особенно при наличии вложенных циклов `For Each`. Необходимо указать ту же переменную, которая отображается в соответствующей инструкции `For Each`.

Может возникнуть необходимость избежать изменения значения `element` внутри цикла. Это может усложнить чтение и отладку кода. Изменение значения `group` не влияет на коллекцию или ее элементы, которые были определены при первом входе в цикл.

Если в качестве вложенных циклов используется инструкция `Next` внешнего уровня вложенности перед `Next` внутреннего уровня, компилятор сигнализирует об ошибке. Однако компилятор может обнаружить эту ошибку перекрытия только в том случае, если указать `element` в каждой инструкции `Next`.

Если код зависит от прохода по коллекции в определенном порядке, цикл `For Each`...`Next` не является лучшим выбором, если не известно о характеристиках объекта перечислителя, предоставляемого коллекцией. Порядок обхода не определяется Visual Basic, а методом <xref:System.Collections.IEnumerator.MoveNext%2A> объекта перечислителя. Таким образом, вы не сможете предсказать, какой элемент коллекции будет возвращен в `element`, или что будет возвращено после заданного элемента. Вы можете достичь более надежных результатов, используя другую структуру цикла, например `For`...`Next` или `Do`...`Loop`.

Среда выполнения должна иметь возможность преобразования элементов в `group` в `element`. Оператор [`Option Strict`] определяет, разрешены ли расширяющие и сужающие преобразования (`Option Strict` отключены, значение по умолчанию) или разрешены только расширяющие преобразования (`Option Strict` включен). Дополнительные сведения см. в разделе [сужающие преобразования](#narrowing-conversions).

Тип данных `group` должен быть ссылочным типом, ссылающимся на коллекцию или массив, который является перечислимым. Чаще всего это означает, что `group` ссылается на объект, реализующий интерфейс <xref:System.Collections.IEnumerable> пространства имен `System.Collections` или интерфейс <xref:System.Collections.Generic.IEnumerable%601> пространства имен `System.Collections.Generic`. `System.Collections.IEnumerable` определяет метод <xref:System.Collections.IEnumerable.GetEnumerator%2A>, который возвращает объект перечислителя для коллекции. Объект перечислителя реализует интерфейс `System.Collections.IEnumerator` пространства имен `System.Collections` и предоставляет свойство <xref:System.Collections.IEnumerator.Current%2A> и методы <xref:System.Collections.IEnumerator.Reset%2A> и <xref:System.Collections.IEnumerator.MoveNext%2A>. Visual Basic использует их для прохода по коллекции.

### <a name="narrowing-conversions"></a>Сужающие преобразования

Если `Option Strict` имеет значение `On`, сужающие преобразования обычно приводят к ошибкам компилятора. Однако в операторе `For Each` преобразования из элементов `group` в `element` оцениваются и выполняются во время выполнения, а ошибки компилятора, вызванные сужающими преобразованиями, подавляются.

В следующем примере присваивание `m` в качестве начального значения для `n` не компилируется, если `Option Strict` имеет значение ON, так как преобразование `Long` в `Integer` является узким преобразованием. Однако в инструкции `For Each` сообщение об ошибке компилятора не возникает, даже если для назначения `number` требуется то же преобразование из `Long` в `Integer`. В инструкции `For Each`, содержащей большое число, ошибка времени выполнения возникает при применении <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> к большому числу.

[!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]

### <a name="ienumerator-calls"></a>Вызовы IEnumerator

Когда начинается выполнение цикла `For Each`...`Next`, Visual Basic проверяет, что `group` ссылается на допустимый объект коллекции. В противном случае вызывается исключение. В противном случае он вызывает метод <xref:System.Collections.IEnumerator.MoveNext%2A> и свойство <xref:System.Collections.IEnumerator.Current%2A> объекта перечислителя для возврата первого элемента. Если `MoveNext` указывает, что следующий элемент отсутствует, то есть если коллекция пуста, цикл `For Each` останавливается и управление передается оператору, следующему за оператором `Next`. В противном случае Visual Basic задает `element` первому элементу и выполняет блок операторов.

Каждый раз, когда Visual Basic встречает инструкцию `Next`, она возвращается в инструкцию `For Each`. Снова вызывается `MoveNext` и `Current`, чтобы вернуть следующий элемент, и снова он либо выполняет блок, либо останавливает цикл в зависимости от результата. Этот процесс будет продолжен до тех пор, пока `MoveNext` не покажет, что следующий элемент или инструкция `Exit For` не обнаружены.

**Изменение коллекции.** Объект перечислителя, возвращаемый <xref:System.Collections.IEnumerable.GetEnumerator%2A> обычно не позволяет изменить коллекцию, добавляя, удаляя, заменяя или переупорядочивая любые элементы. При изменении коллекции после запуска цикла `For Each`...`Next` объект перечислителя станет недопустимым, а следующая попытка доступа к элементу вызовет исключение <xref:System.InvalidOperationException>.

Однако эта блокировка изменений не определяется Visual Basic, а реализацией интерфейса <xref:System.Collections.IEnumerable>. Можно реализовать `IEnumerable` способом, позволяющим изменять во время итерации. Если вы планируете выполнять такие динамические изменения, убедитесь, что понимаете характеристики реализации `IEnumerable` в используемой коллекции.

**Изменение элементов коллекции.** Свойство <xref:System.Collections.IEnumerator.Current%2A> объекта перечислителя доступно [только для чтения](../../../visual-basic/language-reference/modifiers/readonly.md)и возвращает локальную копию каждого элемента коллекции. Это означает, что нельзя изменить сами элементы в цикле `For Each`...`Next`. Любые изменения влияют только на локальную копию из `Current` и не отражаются обратно в базовую коллекцию. Однако если элемент является ссылочным типом, можно изменить члены экземпляра, на который он указывает. В следующем примере изменяется элемент `BackColor` каждого элемента `thisControl`. Однако вы не можете изменить сам `thisControl`.

```vb
Sub LightBlueBackground(thisForm As System.Windows.Forms.Form)
    For Each thisControl In thisForm.Controls
        thisControl.BackColor = System.Drawing.Color.LightBlue
    Next thisControl
End Sub
```

В предыдущем примере можно изменить `BackColor` элемент каждого элемента `thisControl`, хотя он не может изменить `thisControl` сам.

**Обход массивов.** Поскольку класс <xref:System.Array> реализует интерфейс <xref:System.Collections.IEnumerable>, все массивы предоставляют метод <xref:System.Array.GetEnumerator%2A>. Это означает, что можно выполнить итерацию массива с помощью цикла `For Each`...`Next`. Однако можно только считывать элементы массива. Их нельзя изменить.

## <a name="example"></a>Пример

В следующем примере выводится список всех папок в папке C:\. каталог с помощью класса <xref:System.IO.DirectoryInfo>.

[!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]

## <a name="example"></a>Пример

Приведенный ниже пример демонстрирует процедуру сортировки коллекции. В этом примере выполняется сортировка экземпляров класса `Car`, которые хранятся в <xref:System.Collections.Generic.List%601>. Класс `Car` реализует интерфейс <xref:System.IComparable%601>, который требует реализации метода <xref:System.IComparable%601.CompareTo%2A>.

Каждый вызов метода <xref:System.IComparable%601.CompareTo%2A> выполняет одно сравнение, которое используется для сортировки. Написанный пользователем код в методе `CompareTo` возвращает значение для каждого сравнения текущего объекта с другим объектом. Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, и равняется нулю, если объекты равны. Это позволяет определить в коде условия для отношения «больше», «меньше» и «равно».

В методе `ListCars` оператор `cars.Sort()` сортирует список. Этот вызов метода <xref:System.Collections.Generic.List%601.Sort%2A> <xref:System.Collections.Generic.List%601> приводит к тому, что метод `CompareTo` вызывается автоматически для объектов `Car` в `List`.

[!code-vb[VbVbalrStatements#125](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#125)]

## <a name="see-also"></a>См. также:

- [Коллекции](../../../standard/collections/index.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
