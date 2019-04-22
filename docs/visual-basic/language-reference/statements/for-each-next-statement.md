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
ms.openlocfilehash: 5081f80ad0da738ebb950bcd649af7a593582356
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824352"
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
|`element`|Требуется в `For Each` инструкции. Необязательно в `Next` инструкции. переменная. Используется для итерации по элементам коллекции.|  
|`datatype`|Обязателен, если `element` уже не объявлен. Тип данных `element`.|  
|`group`|Обязательный. Переменная с типом, который является типом коллекции или объект. Ссылается на коллекцию, по которому `statements` будут повторяться.|  
|`statements`|Необязательный параметр. Один или несколько операторов между `For Each` и `Next` , выполните на каждом элементе в `group`.|  
|`Continue For`|Необязательный параметр. Передает управление в начало `For Each` цикла.|  
|`Exit For`|Необязательный параметр. Передает управление из `For Each` цикла.|  
|`Next`|Обязательный. Завершает определение `For Each` цикла.|  
  
## <a name="simple-example"></a>Простой пример  
 Используйте `For Each`... `Next` цикл, когда нужно повторить набор инструкций для каждого элемента коллекции или массиве.  
  
> [!TIP]
>  Объект [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) работает хорошо, когда вы можете связать каждой итерации цикла с управляющей переменной и определить начальное и конечное значения этой переменной. Тем не менее при работе с коллекцией, концепция начальное и конечное значения лишено смысла и не требуется знать количество элементов, коллекция имеет. В таком случае `For Each`... `Next` цикл часто является наиболее предпочтительной.  
  
 В следующем примере `For Each`...`Next` оператор используется для итерации по все элементы коллекции-списка.  
  
 [!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]  
  
 Дополнительные примеры см. в разделе [коллекций](../../../standard/collections/index.md) и [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="nested-loops"></a>Вложенные циклы  
 Можно вложить `For Each` циклы, поместив в одном цикле в другую.  
  
 В следующем примере демонстрируется вложенных `For Each`...`Next` структуры.  
  
 [!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]  
  
 При вложении циклы, каждый цикл должен иметь уникальный `element` переменной.  
  
 Можно также вложить разные виды структур управления друг с другом. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Возврата для и продолжите для  
 [Выхода для](../../../visual-basic/language-reference/statements/exit-statement.md) инструкция вызывает выполнение выйти из `For`...`Next` цикл передает управление оператору, который расположен `Next` инструкции.  
  
 `Continue For` Оператор передает управление непосредственно в следующую итерацию цикла. Дополнительные сведения см. в разделе [оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 В следующем примере показано, как использовать `Continue For` и `Exit For` инструкций.  
  
 [!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]  
  
 Можно поместить любое количество `Exit For` инструкций в `For Each` цикла. При использовании внутри вложенной `For Each` циклы, `Exit For` выполнение выйти из самого внутреннего цикла передает управление на следующий уровень вложенности.  
  
 `Exit For` часто используется после оценки некоторого условия, например, в `If`... `Then`... `Else` структуры. Вы можете использовать `Exit For` для следующих условий:  
  
-   Продолжение для выполнения итерации, ненужных или невозможно. Это может быть вызвано ошибочное значение или запрос на завершение.  
  
-   Исключение перехватывается в `Try`... `Catch`... `Finally`. Можно использовать `Exit For` в конце `Finally` блока.  
  
-   Там бесконечный цикл, который является цикл, который может запустить большое или возможно, бесконечное число раз. При обнаружении таких условий, можно использовать `Exit For` для выхода из цикла. Дополнительные сведения см. в разделе [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="iterators"></a>Итераторы  
 Использовании *итератор* для выполнения настраиваемого перебора коллекции. Итератор, который может быть функцией или `Get` метода доступа. Она использует `Yield` инструкцию для возврата всех элементов коллекции по одному за раз.  
  
 Итератор вызывается с помощью `For Each...Next` инструкции. Каждая итерация цикла `For Each` вызывает итератор. Когда `Yield` в итераторе, выражение в достижении оператора `Yield` инструкции возвращается и сохраняется текущее расположение в коде. При следующем вызове итератора выполнение возобновляется с этого места.  
  
 Следующий пример использует функцию итератора. Имеет функции итератора `Yield` инструкцию, которая находится внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла. В `ListEvenNumbers` метод, каждая итерация `For Each` тела оператора создает вызов функции итератора, который переходит к следующему `Yield` инструкции.  
  
 [!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]  
  
 Дополнительные сведения см. в разделе [итераторы](../../programming-guide/concepts/iterators.md), [оператор Yield](../../../visual-basic/language-reference/statements/yield-statement.md), и [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## <a name="technical-implementation"></a>Техническая реализация  
 Когда `For Each`...`Next` Инструкция переходит, Visual Basic анализирует всю коллекцию только один раз, перед началом цикла. Если в блоке операторов изменяется `element` или `group`, эти изменения не влияют на итерации цикла.  
  
 Когда все элементы в коллекции, можно последовательно назначенные `element`, `For Each` цикл останавливается и управление передается оператору, следующему `Next` инструкции.  
  
 Если `element` еще не была объявлена вне цикла, необходимо объявить ее в `For Each` инструкции. Можно объявить тип `element` явным образом с помощью `As` инструкции, или можно положиться на определение типа для типа назначения. В любом случае рамки `element` является тело цикла. Тем не менее, нельзя объявлять `element` и снаружи цикла.  
  
 При необходимости можно указать `element` в `Next` инструкции. Это повышает удобочитаемость программы, особенно в том случае, если имеются вложенные `For Each` циклы. Необходимо указать ту же переменную, что отображается в соответствующем `For Each` инструкции.  
  
 Может потребоваться не следует изменять значение `element` внутри цикла. Это может затруднить его для чтения и отладки кода. Изменение значения `group` не влияет на коллекции или ее элементы, которые были определены при цикла.  
  
 Когда вложенные циклы, если `Next` внешнего уровня вложенности встречается перед `Next` внутреннего уровня, компилятор сообщает об ошибке. Тем не менее, компилятор может определить, это перекрытие ошибки только в том случае, если указать `element` в каждом `Next` инструкции.  
  
 Если код исходит обхода коллекции в определенном порядке, `For Each`... `Next` цикл не лучшим выбором, если вы не знаете характеристики объекта-перечислителя коллекции представляет. Порядок обхода не определить с помощью Visual Basic, а от <xref:System.Collections.IEnumerator.MoveNext%2A> метод объекта перечислителя. Таким образом, вы не сможете прогнозировать, какой элемент коллекции является первым должен быть возвращен в `element`, или это Далее возвращается после заданного элемента. Можно достичь более надежных результатов с помощью другой циклической структуры, например `For`... `Next` или `Do`... `Loop`.  
  
 Тип данных `element` должен быть таким образом, чтобы тип данных элементов `group` может быть преобразован к нему.  
  
 Тип данных `group` должен быть ссылочного типа, который ссылается на коллекцию или массив, который является перечислимым. Чаще всего это означает, что `group` ссылается на объект, реализующий <xref:System.Collections.IEnumerable> интерфейс `System.Collections` пространства имен или <xref:System.Collections.Generic.IEnumerable%601> интерфейс `System.Collections.Generic` пространства имен. `System.Collections.IEnumerable` Определяет <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод, который возвращает объект перечислителя для коллекции. Реализует объект перечислителя `System.Collections.IEnumerator` интерфейс `System.Collections` пространства имен и предоставляет <xref:System.Collections.IEnumerator.Current%2A> свойство и <xref:System.Collections.IEnumerator.Reset%2A> и <xref:System.Collections.IEnumerator.MoveNext%2A> методы. Visual Basic использует их для перемещения по коллекции.  
  
### <a name="narrowing-conversions"></a>сужающие преобразования  
 Когда `Option Strict` присваивается `On`, сужающее преобразование обычно вызывает ошибки компилятора. В `For Each` инструкции, тем не менее, преобразования из элементов в `group` для `element` вычисляются и во время выполнения и ошибки компилятора, из-за сужающие преобразования подавляются.  
  
 В следующем примере, назначение `m` как начальное значение для `n` не будет компилироваться при `Option Strict` включен, так как преобразование `Long` для `Integer` является сужающим преобразованием. В `For Each` инструкции, однако никакие ошибки компилятора не сообщается, даже если назначения `number` требуется то же самое преобразование из `Long` для `Integer`. В `For Each` инструкцию, которая содержит множество, то во время выполнения возникает ошибка при <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> применяется к большим числом.  
  
 [!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]  
  
### <a name="ienumerator-calls"></a>IEnumerator вызовов  
 При выполнении `For Each`... `Next` начале цикла, Visual Basic проверяет, что `group` ссылается на объект допустимую коллекцию. В противном случае создается исключение. В противном случае он вызывает <xref:System.Collections.IEnumerator.MoveNext%2A> метод и <xref:System.Collections.IEnumerator.Current%2A> свойство объекта перечислителя для возвращения первого элемента. Если `MoveNext` указывает, что отсутствует следующий элемент, то есть, если коллекция пуста, `For Each` цикл останавливается и управление передается оператору, следующему `Next` инструкции. В противном случае Visual Basic задает `element` первого элемента и выполняется блок операторов.  
  
 При каждом запуске Visual Basic встречает `Next` оператор, он возвращает `For Each` инструкции. Еще раз он вызывает `MoveNext` и `Current` для возврата следующего элемента и еще раз выполняет блок либо останавливающее цикл в зависимости от результата. Этот процесс продолжается до `MoveNext` указывает, что отсутствует следующий элемент или `Exit For` встречается.  
  
 **Изменение коллекции.** Объект перечислителя, возвращенный <xref:System.Collections.IEnumerable.GetEnumerator%2A> обычно не позволяет изменять коллекцию, добавление, удаление, замена или изменяя порядок элементов. При изменении параметров сбора после запуска `For Each`... `Next` цикл, он становится недействительным, а также приводит к следующей попытке обращения к элементу <xref:System.InvalidOperationException> исключение.  
  
 Тем не менее, эта блокировка изменения не определяются по Visual Basic, а также путем реализации <xref:System.Collections.IEnumerable> интерфейс. Это можно реализовать `IEnumerable` способом, который позволяет изменять во время итерации. Если вы собираетесь производить такие динамические изменения, убедитесь, что вы понимаете характеристики `IEnumerable` реализации на коллекцию, вы используете.  
  
 **Изменение элементов коллекции.** <xref:System.Collections.IEnumerator.Current%2A> Свойство объекта перечислителя [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), и возвращает локальную копию каждого элемента коллекции. Это означает, что нельзя изменить непосредственно к элементам в `For Each`... `Next` цикла. Любые изменения, внесенные влияет только на локальную копию из `Current` и не отражается в базовой коллекции. Тем не менее если элемент является ссылочным типом, можно изменить члены экземпляра, на который он указывает. В следующем примере изменяется `BackColor` члены каждой `thisControl` элемент. Нельзя Однако изменять `thisControl` сам.  
  
```vb  
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)  
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls  
        thisControl.BackColor = System.Drawing.Color.LightBlue  
    Next thisControl  
End Sub  
```  
  
 Предыдущий пример можно изменить `BackColor` члены каждой `thisControl` элемент, несмотря на то, что он не может изменить `thisControl` сам.  
  
 **Обход массива.** Так как <xref:System.Array> класс реализует <xref:System.Collections.IEnumerable> интерфейс, предоставлять все массивы <xref:System.Array.GetEnumerator%2A> метод. Это означает, что можно выполнить итерацию массива с `For Each`... `Next` цикла. Тем не менее доступен только для чтения элементов массива. Их нельзя изменить.  
  
## <a name="example"></a>Пример  
 В следующем примере перечисляются все папки в каталоге C:\ с помощью <xref:System.IO.DirectoryInfo> класса.  
  
 [!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример демонстрирует процедуру сортировки коллекции. В примере сортируются экземпляры `Car` класса, которые хранятся в <xref:System.Collections.Generic.List%601>. Класс `Car` реализует интерфейс <xref:System.IComparable%601>, который требует реализации метода <xref:System.IComparable%601.CompareTo%2A>.  
  
 Каждый вызов <xref:System.IComparable%601.CompareTo%2A> метод выполняет одно сравнение, используемое для сортировки. Написанный пользователем код в методе `CompareTo` возвращает значение для каждого сравнения текущего объекта с другим объектом. Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, и равняется нулю, если объекты равны. Это позволяет определить в коде условия для отношения «больше», «меньше» и «равно».  
  
 В методе `ListCars` оператор `cars.Sort()` сортирует список. Этот вызов метода <xref:System.Collections.Generic.List%601.Sort%2A> <xref:System.Collections.Generic.List%601> приводит к тому, что метод `CompareTo` вызывается автоматически для объектов `Car` в `List`.  
  
 [!code-vb[VbVbalrStatements#125](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#125)]  
  
## <a name="see-also"></a>См. также

- [Коллекции](../../../standard/collections/index.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
