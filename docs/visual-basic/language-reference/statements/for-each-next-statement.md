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
ms.openlocfilehash: ebfd05a39c290e379bea2b925e7ea30c40d303fe
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046320"
---
# <a name="for-eachnext-statement-visual-basic"></a>Оператор For Each...Next (Visual Basic)

Повторяет группу операторов для каждого элемента в коллекции.

## <a name="syntax"></a>Синтаксис

```
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
|`element`|Требуется в `For Each` инструкции. Необязательный `Next` в инструкции. Перемен. Используется для прохода по элементам коллекции.|
|`datatype`|Необязательный параметр, если [`Option Infer`](option-infer-statement.md) имеет значение On (по умолчанию) или `Option Infer` `element` уже объявлен; `element` требуется, если параметр имеет значение OFF и еще не объявлен. Тип данных `element`.|
|`group`|Обязательный. Переменная типа, которая является типом коллекции или объектом. Ссылается на коллекцию, для которой `statements` повторяются.|
|`statements`|Необязательный параметр. Одна или несколько инструкций между `For Each` и `Next` выполняются для каждого элемента в `group`.|
|`Continue For`|Необязательный параметр. Передает управление в начало `For Each` цикла.|
|`Exit For`|Необязательный параметр. Передает управление за пределы `For Each` цикла.|
|`Next`|Обязательный. Завершает определение `For Each` цикла.|

## <a name="simple-example"></a>Простой пример

`For Each`Использовать... `Next` цикл, если необходимо повторить набор инструкций для каждого элемента коллекции или массива.

> [!TIP]
> A [для... Оператор Next](../../../visual-basic/language-reference/statements/for-next-statement.md) работает хорошо, когда можно связать каждую итерацию цикла с управляющей переменной и определить начальные и конечные значения переменной. Однако при работе с коллекцией концепция начальных и конечных значений не имеет смысла, и вам не обязательно быть уверенным, сколько элементов имеет коллекция. В этом случае `For Each`... `Next` часто является лучшим выбором.

В следующем примере `For Each`...`Next` выполняет перебор всех элементов коллекции списков.

[!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]

Дополнительные примеры см. в разделе [коллекции](../../../standard/collections/index.md) и [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).

## <a name="nested-loops"></a>Вложенные циклы

Можно вложить `For Each` циклы, поместив один цикл в другой.

В следующем примере демонстрируется `For Each`вложенное...`Next` сотрудник.

[!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]

При вложении циклов каждый цикл должен иметь уникальную `element` переменную.

Можно также вкладывать различные виды управляющих структур друг в друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).

## <a name="exit-for-and-continue-for"></a>Выход и продолжение для

Оператор [Exit For](../../../visual-basic/language-reference/statements/exit-statement.md) вызывает завершение `For`выполнения...`Next` выполняет цикл и передает управление оператору, который следует `Next` за оператором.

`Continue For` Оператор передает управление сразу в следующую итерацию цикла. Дополнительные сведения см. в разделе [оператор continue](../../../visual-basic/language-reference/statements/continue-statement.md).

В следующем примере показано, как использовать `Continue For` операторы и. `Exit For`

[!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]

В цикле можно разместить любое `Exit For` количество операторов. `For Each` При использовании внутри вложенных `For Each` `Exit For` циклов выполнение вызывает выход из внутреннего цикла и передает управление следующему более высокому уровню вложенности.

`Exit For`часто используется после вычисления некоторого условия, например в `If`... `Then`... `Else` структура. Может потребоваться использовать `Exit For` для следующих условий:

- Продолжение итерации не требуется или невозможно. Это может быть вызвано ошибочным значением или запросом на завершение.

- Исключение перехвачено в `Try`... `Catch`... `Finally`. В конце `Exit For` `Finally` блока можно использовать.

- Существует бесконечный цикл, который может выполняться с большим или даже бесконечным числом раз. При обнаружении такого условия можно использовать `Exit For` для экранирования цикла. Дополнительные сведения см. в разделе [Do... Loop, инструкция](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="iterators"></a>Итераторы

*Итератор* используется для выполнения пользовательской итерации по коллекции. Итератор может быть функцией или `Get` методом доступа. Он использует `Yield` инструкцию для возвращения каждого элемента коллекции по одному за раз.

Итератор вызывается с помощью `For Each...Next` оператора. Каждая итерация цикла `For Each` вызывает итератор. При достижении `Yield`операторав итераторе возвращается выражение в операторе, а текущее расположение в коде сохраняется. `Yield` При следующем вызове итератора выполнение возобновляется с этого места.

В следующем примере используется функция итератора. Функция итератора содержит `Yield` оператор, который находится внутри блока [for... Следующий](../../../visual-basic/language-reference/statements/for-next-statement.md) цикл. В методе каждая итерация `For Each` тела оператора создает вызов функции итератора, который переходит к следующему `Yield` оператору. `ListEvenNumbers`

[!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]

Дополнительные сведения см. в разделе [итераторы](../../programming-guide/concepts/iterators.md), [оператор yield](../../../visual-basic/language-reference/statements/yield-statement.md)и [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).

## <a name="technical-implementation"></a>Техническая реализация

`For Each`Когда...`Next` выполняется инструкция, Visual Basic вычисляет коллекцию только один раз перед началом цикла. Если блок инструкций изменяется `element` или `group`, эти изменения не влияют на итерацию цикла.

Когда все элементы в коллекции были последовательно назначены `element` `For Each` , цикл останавливается и управление передается оператору, следующему за `Next` оператором.

Если [параметр Infer](option-infer-statement.md) имеет значение On (значение по умолчанию), то компилятор Visual Basic может определить тип `element`данных. Если он отключен и `element` не объявлен вне цикла, необходимо объявить его `For Each` в операторе. Чтобы объявить тип `element` данных явным образом, `As` используйте предложение. Если тип данных элемента не определен за пределами `For Each`... `Next` , областью действия является тело цикла. Обратите внимание, что `element` нельзя объявлять как за пределами, так и внутри цикла.

При необходимости можно указать `element` `Next` в инструкции. Это повышает удобочитаемость программы, особенно при наличии вложенных `For Each` циклов. Необходимо указать ту же переменную, которая указана в соответствующем `For Each` операторе.

Может возникнуть необходимость избежать изменения значения `element` внутри цикла. Это может усложнить чтение и отладку кода. Изменение значения `group` не влияет на коллекцию или ее элементы, которые были определены при первом входе в цикл.

При вложении циклов, если `Next` оператор внешнего уровня вложенности встречается `Next` перед внутренним уровнем, компилятор сообщает об ошибке. Однако компилятор может обнаружить эту перекрытие ошибки только в том случае, `element` если указать `Next` в каждой инструкции.

Если код зависит от прохода по коллекции в определенном порядке, то `For Each`... `Next` не лучший выбор, если не известно о характеристиках объекта перечислителя, предоставляемых коллекцией. Порядок обхода не определяется Visual Basic, а <xref:System.Collections.IEnumerator.MoveNext%2A> методом объекта перечислителя. Поэтому вы не сможете предсказать, какой элемент коллекции первым должен возвращаться `element`, или что будет возвращено после заданного элемента. Вы можете достичь более надежных результатов, используя другую структуру цикла, например `For`... `Next` или`Do`... `Loop`.

Среда выполнения должна иметь возможность преобразования элементов в `group`. `element` Оператор [`Option Strict`] определяет, разрешены ли расширяющие и сужающие преобразования (`Option Strict` значение по умолчанию) или разрешены только расширяющие преобразования (`Option Strict` включено). Дополнительные сведения см. в разделе [сужающие преобразования](#narrowing-conversions).

Тип `group` данных должен быть ссылочным типом, ссылающимся на коллекцию или массив, который является перечислимым. Чаще всего это означает, `group` что ссылается на объект, <xref:System.Collections.IEnumerable> реализующий интерфейс `System.Collections` пространства имен или <xref:System.Collections.Generic.IEnumerable%601> интерфейс `System.Collections.Generic` пространства имен. `System.Collections.IEnumerable`<xref:System.Collections.IEnumerable.GetEnumerator%2A> определяет метод, который возвращает объект перечислителя для коллекции. Объект `System.Collections.IEnumerator` перечислителя реализует интерфейс <xref:System.Collections.IEnumerator.Current%2A> `System.Collections` пространства имен и <xref:System.Collections.IEnumerator.Reset%2A> предоставляет свойства и методы и <xref:System.Collections.IEnumerator.MoveNext%2A> . Visual Basic использует их для прохода по коллекции.

### <a name="narrowing-conversions"></a>сужающие преобразования

Если `Option Strict` параметр имеет `On`значение, сужающие преобразования обычно приводят к ошибкам компилятора. Однако в `group` `element` операторе преобразования из элементов в в вычисляются и выполняются во время выполнения, а ошибки компилятора, вызванные сужающими преобразованиями, подавляются. `For Each`

В `m` следующем примере присваивание в качестве начального значения для `n` не компилируется, если `Option Strict` имеет значение `Integer` on, так как преобразование `Long` в в представляет собой понижающие преобразования. Однако в `number` `Long` `Integer`инструкции не сообщается об ошибке компилятора, даже если для назначения требуется такое же преобразование из в. `For Each` В инструкции, содержащей большое число, при <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> применении к большому числу возникает ошибка времени выполнения. `For Each`

[!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]

### <a name="ienumerator-calls"></a>Вызовы IEnumerator

При выполнении `For Each`... начинается цикл, Visual Basic проверяет, что `group` ссылается на допустимый объект коллекции. `Next` В противном случае вызывается исключение. В противном случае он <xref:System.Collections.IEnumerator.MoveNext%2A> вызывает метод <xref:System.Collections.IEnumerator.Current%2A> и свойство объекта перечислителя, чтобы вернуть первый элемент. Если `MoveNext` значение указывает, что следующий элемент отсутствует, то есть если коллекция пуста `For Each` , цикл останавливается и управление передается оператору, следующему за `Next` оператором. В противном случае `element` Visual Basic задает первый элемент и выполняет блок операторов.

Каждый раз, когда Visual Basic обнаруживает `Next` оператор, он возвращается `For Each` в инструкцию. Снова вызывает метод `MoveNext` и `Current` , чтобы вернуть следующий элемент, и снова он либо выполняет блок, либо останавливает цикл в зависимости от результата. Этот процесс будет продолжен `MoveNext` до тех пор, пока не будет указано, `Exit For` что следующий элемент или оператор не обнаружен.

**Изменение коллекции.** Объект перечислителя, возвращаемый <xref:System.Collections.IEnumerable.GetEnumerator%2A> обычным способом, не позволяет изменить коллекцию, добавляя, удаляя, заменяя или переупорядочивая любые элементы. При изменении коллекции после запуска `For Each`... , объект перечислителя станет недопустимым, и следующая попытка доступа к элементу <xref:System.InvalidOperationException> вызовет исключение. `Next`

Однако эта блокировка изменений не определяется Visual Basic, а реализацией <xref:System.Collections.IEnumerable> интерфейса. Можно реализовать `IEnumerable` таким образом, чтобы можно было вносить изменения во время итерации. Если вы планируете выполнять такие динамические изменения, убедитесь, что понимаете характеристики `IEnumerable` реализации используемой коллекции.

**Изменение элементов коллекции.** Свойство объекта перечислителя доступно [только для чтения](../../../visual-basic/language-reference/modifiers/readonly.md)и возвращает локальную копию каждого элемента коллекции. <xref:System.Collections.IEnumerator.Current%2A> Это означает, что нельзя изменить сами элементы в `For Each`... `Next` цикл. Любые изменения влияют только на локальную копию из `Current` и не отражаются обратно в базовую коллекцию. Однако если элемент является ссылочным типом, можно изменить члены экземпляра, на который он указывает. В следующем примере изменяется `BackColor` элемент каждого `thisControl` элемента. Однако вы не можете изменить `thisControl` само себя.

```vb
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls
        thisControl.BackColor = System.Drawing.Color.LightBlue
    Next thisControl
End Sub
```

В предыдущем примере можно изменить `BackColor` элемент каждого `thisControl` элемента, хотя он не может изменить `thisControl` сам элемент.

**Обход массивов.** Поскольку класс реализует интерфейс, все массивы предоставляют метод. <xref:System.Array.GetEnumerator%2A> <xref:System.Collections.IEnumerable> <xref:System.Array> Это означает, что можно выполнить итерацию массива с `For Each`помощью... `Next` цикл. Однако можно только считывать элементы массива. Их нельзя изменить.

## <a name="example"></a>Пример

В следующем примере выводится список всех папок в папке C:\. каталог с помощью <xref:System.IO.DirectoryInfo> класса.

[!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]

## <a name="example"></a>Пример

Приведенный ниже пример демонстрирует процедуру сортировки коллекции. В этом примере `Car` <xref:System.Collections.Generic.List%601>выполняется сортировка экземпляров класса, которые хранятся в. Класс `Car` реализует интерфейс <xref:System.IComparable%601>, который требует реализации метода <xref:System.IComparable%601.CompareTo%2A>.

Каждый вызов <xref:System.IComparable%601.CompareTo%2A> метода выполняет одно сравнение, которое используется для сортировки. Написанный пользователем код в методе `CompareTo` возвращает значение для каждого сравнения текущего объекта с другим объектом. Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, и равняется нулю, если объекты равны. Это позволяет определить в коде условия для отношения «больше», «меньше» и «равно».

В методе `ListCars` оператор `cars.Sort()` сортирует список. Этот вызов метода <xref:System.Collections.Generic.List%601.Sort%2A> <xref:System.Collections.Generic.List%601> приводит к тому, что метод `CompareTo` вызывается автоматически для объектов `Car` в `List`.

[!code-vb[VbVbalrStatements#125](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#125)]

## <a name="see-also"></a>См. также

- [Коллекции](../../../standard/collections/index.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Инициализаторы объектов: Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
