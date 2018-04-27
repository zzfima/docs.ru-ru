---
title: Оператор For Each...Next (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 56
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b1593d279d4338ebadca803fe757a201cbcd654b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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
|`element`|Требуется в `For Each` инструкции. Необязательно для `Next` инструкции. Переменная. Используется для итерации элементов коллекции.|  
|`datatype`|Обязателен, если `element` уже не объявлен. Тип данных `element`.|  
|`group`|Обязательно. Переменная с типом, который является типом коллекции или объекта. Относится к коллекции, по которому `statements` будут повторяться.|  
|`statements`|Необязательный. Один или несколько операторов между `For Each` и `Next` , запустите на каждый элемент `group`.|  
|`Continue For`|Необязательный. Передает управление в начало `For Each` цикла.|  
|`Exit For`|Необязательный. Передает управление из `For Each` цикла.|  
|`Next`|Обязательно. Завершает определение `For Each` цикла.|  
  
## <a name="simple-example"></a>Простой пример  
 Используйте `For Each`... `Next` цикл, повторяемый набор инструкций для каждого элемента коллекции или массива.  
  
> [!TIP]
>  Объект [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) работает хорошо, когда можно связать каждую итерацию цикла с управляющей переменной и определить начальное и конечное значения этой переменной. Однако при работе с коллекцией концепцию начальное и конечное значения лишено смысла и не требуется знать количество элементов в коллекции. В таком случае `For Each`... `Next` цикл часто является лучшим выбором.  
  
 В следующем примере `For Each`...`Next` инструкция выполняет итерацию всех элементов коллекции списка.  
  
 [!code-vb[VbVbalrStatements#121](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_1.vb)]  
  
 Дополнительные примеры см. в разделе [коллекций](../../../standard/collections/index.md) и [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="nested-loops"></a>Вложенные циклы  
 Можно вложить `For Each` циклы, поместив цикл один в другой.  
  
 В следующем примере демонстрируется вложенных `For Each`...`Next` структуры.  
  
 [!code-vb[VbVbalrStatements#122](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_2.vb)]  
  
 При вложении циклы каждый цикл должен иметь уникальный `element` переменной.  
  
 Также можно вложить различные виды управляющих структур друг с другом. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Для выхода и для продолжения  
 [Выхода для](../../../visual-basic/language-reference/statements/exit-statement.md) оператор прерывает выполнение выхода `For`...`Next` цикл передает управление оператору, следующему `Next` инструкции.  
  
 `Continue For` Оператор передачу управления сразу же к следующей итерации цикла. Дополнительные сведения см. в разделе [оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 В следующем примере показано, как использовать `Continue For` и `Exit For` инструкции.  
  
 [!code-vb[VbVbalrStatements#123](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_3.vb)]  
  
 Можно поместить любое число `Exit For` инструкций в `For Each` цикла. При использовании внутри вложенной `For Each` циклы, `Exit For` выполнение выхода из внутреннего цикла и передачи управления следующий уровень вложенности.  
  
 `Exit For` часто используется после оценки некоторого условия, например, в `If`... `Then`... `Else` структуры. Вы можете использовать `Exit For` для следующих условий:  
  
-   Продолжение для выполнения итерации ненужные или невозможно. Это может быть вызвано ошибочное значение или запрос на завершение.  
  
-   Исключение перехватывается в `Try`... `Catch`... `Finally`. Можно использовать `Exit For` в конце `Finally` блока.  
  
-   Здесь бесконечный цикл, являющийся цикл, который может запустить большое или возможно, бесконечное число раз. При обнаружении таких условий, можно использовать `Exit For` для выхода из цикла. Дополнительные сведения см. в разделе [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="iterators"></a>Итераторы  
 Вы используете *итератор* для выполнения настраиваемого перебора элементов коллекции. Итератор может быть функцией или `Get` метода доступа. Она использует `Yield` инструкции для возврата всех элементов коллекции по одному за раз.  
  
 Итератор вызывается с помощью `For Each...Next` инструкции. Каждая итерация цикла `For Each` вызывает итератор. Когда `Yield` в итераторе выражение в достижении оператора `Yield` инструкции возвращается и сохраняется текущее расположение в коде. При следующем вызове итератора выполнение возобновляется с этого места.  
  
 В следующем примере функции итератора. Имеет функции итератора `Yield` инструкцию, которая находится внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла. В `ListEvenNumbers` метод, каждой итерации `For Each` тела оператора создает вызов функции итератора, который переходит к следующему `Yield` инструкции.  
  
 [!code-vb[VbVbalrStatements#127](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_4.vb)]  
  
 Дополнительные сведения см. в разделе [итераторы](../../programming-guide/concepts/iterators.md), [оператор Yield](../../../visual-basic/language-reference/statements/yield-statement.md), и [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## <a name="technical-implementation"></a>Техническая реализация  
 Когда `For Each`...`Next` выполняется инструкция, Visual Basic вычисляет коллекцию только один раз, до начала цикла. Если в блоке операторов изменяется `element` или `group`, эти изменения не влияют на итерацию цикла.  
  
 Когда все элементы в коллекции успешно назначены `element`, `For Each` цикла прекращается и управление передается оператору, следующему `Next` инструкции.  
  
 Если `element` еще не был объявлен вне цикла, необходимо объявить ее в `For Each` инструкции. Можно объявить тип `element` явным образом с помощью `As` инструкции, или можно положиться на определение типа для типа назначения. В любом случае область `element` является тело цикла. Однако нельзя объявлять `element` и снаружи цикла.  
  
 Дополнительно можно указать `element` в `Next` инструкции. Это повышает удобочитаемость программы, особенно в том случае, если имеются вложенные `For Each` циклы. Необходимо указать ту же переменную, которая отображается в соответствующем `For Each` инструкции.  
  
 Не изменяйте значение может потребоваться `element` внутри цикла. Это можно сделать его более трудными для понимания и отладки кода. Изменение значения `group` не влияет на коллекцию или ее элементы, которые были определены при первом входе цикла.  
  
 Когда вложенные циклы, если `Next` сталкивалась инструкции внешнего уровня вложенности `Next` внутреннего уровня, компилятор сообщает об ошибке. Однако компилятор может обнаружить это перекрывающихся ошибки только в том случае, если указать `element` в каждом `Next` инструкции.  
  
 Если код исходит обхода коллекции в определенном порядке, `For Each`... `Next` цикла не лучший выбор, если вы не знаете характеристик объекта перечислителя обеспечивает доступ к коллекции. Порядок обхода не определить с помощью Visual Basic, а от <xref:System.Collections.IEnumerator.MoveNext%2A> метод объекта перечислителя. Таким образом, вы не сможете прогнозировать, какой элемент в коллекции является первым должен быть возвращен в `element`, или который представляет Далее возвращается после заданного элемента. Можно достичь более надежных результатов с помощью другой циклической структуры, например `For`... `Next` или `Do`... `Loop`.  
  
 Тип данных `element` должен быть таким образом, чтобы тип данных элементов `group` может быть преобразован к нему.  
  
 Тип данных `group` должен быть ссылочного типа, который ссылается на коллекцию или перечислимый массив. Чаще всего это означает, что `group` ссылается на объект, реализующий <xref:System.Collections.IEnumerable> интерфейс `System.Collections` пространства имен или <xref:System.Collections.Generic.IEnumerable%601> интерфейс `System.Collections.Generic` пространства имен. `System.Collections.IEnumerable` Определяет <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод, который возвращает объект перечислителя для коллекции. Реализует объект перечислителя `System.Collections.IEnumerator` интерфейс `System.Collections` пространства имен и предоставляет <xref:System.Collections.IEnumerator.Current%2A> свойство и <xref:System.Collections.IEnumerator.Reset%2A> и <xref:System.Collections.IEnumerator.MoveNext%2A> методы. Visual Basic использует их для перемещения по коллекции.  
  
### <a name="narrowing-conversions"></a>сужающие преобразования  
 Когда `Option Strict` равно `On`, сужающее преобразование обычно вызывает ошибки компилятора. В `For Each` инструкции, однако преобразование из элементов в `group` для `element` вычисляются и во время выполнения и ошибки компилятора, вызванные сужающие преобразования подавляются.  
  
 В следующем примере назначение `m` как начальное значение для `n` не будет компилироваться при `Option Strict` включен, так как преобразование `Long` для `Integer` сужающего преобразования. В `For Each` инструкции, однако никакие ошибки компилятора не включены в отчет, даже если назначения `number` требует одного преобразования из `Long` для `Integer`. В `For Each` инструкции, содержит много, то во время выполнения возникает ошибка при <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> применяется к большим числом.  
  
 [!code-vb[VbVbalrStatements#89](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_5.vb)]  
  
### <a name="ienumerator-calls"></a>Вызовы IEnumerator  
 При выполнении `For Each`... `Next` начинает цикл, Visual Basic проверяет, что `group` ссылается на объект допустимую коллекцию. В противном случае создается исключение. В противном случае он вызывает <xref:System.Collections.IEnumerator.MoveNext%2A> метод и <xref:System.Collections.IEnumerator.Current%2A> свойства объекта перечислителя, который требуется возвратить первый элемент. Если `MoveNext` указывает, что не следующий элемент, то есть, если коллекция пуста, `For Each` цикла прекращается и управление передается оператору, следующему `Next` инструкции. В противном случае Visual Basic задает `element` для первого элемента и выполняется блок операторов.  
  
 При каждом запуске Visual Basic встречает `Next` инструкции, возвращается `For Each` инструкции. Снова вызывает `MoveNext` и `Current` для возврата следующего элемента и еще раз выполняет блок либо останавливающее цикл в зависимости от результата. Этот процесс продолжается до `MoveNext` указывает, что элемент не далее или `Exit For` инструкции.  
  
 **Изменение коллекции.** Объект перечислителя, возвращенный <xref:System.Collections.IEnumerable.GetEnumerator%2A> обычно не позволяет изменить путем добавления, удаления, замены или изменяя порядок элементов в коллекцию. При изменении коллекции после запуска `For Each`... `Next` цикла, перечислитель становится недействительным, в результате чего следующей попытки доступа к элементу <xref:System.InvalidOperationException> исключение.  
  
 Однако эта блокировка изменения не определяются по Visual Basic, а также путем реализации <xref:System.Collections.IEnumerable> интерфейса. Это можно реализовать `IEnumerable` образом, который позволяет изменять во время итерации. Если вы собираетесь производить такие динамические изменения, убедитесь, что вы понимаете характеристики `IEnumerable` реализацию на коллекцию, вы используете.  
  
 **Изменение элементов коллекции.** <xref:System.Collections.IEnumerator.Current%2A> Свойство объекта перечислителя [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), и возвращает локальную копию каждого элемента коллекции. Это означает, что нельзя изменить непосредственно к элементам в `For Each`... `Next` цикла. Любые изменения, вносимые влияет только на локальную копию из `Current` и не отражается в базовой коллекции. Тем не менее если элемент является ссылочным типом, можно изменить члены экземпляра, на который он указывает. В следующем примере изменяется `BackColor` каждого элемента `thisControl` элемент. Не удается Однако изменять `thisControl` сам.  
  
```vb  
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)  
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls  
        thisControl.BackColor = System.Drawing.Color.LightBlue  
    Next thisControl  
End Sub  
```  
  
 Предыдущий пример можно изменить `BackColor` каждого элемента `thisControl` элемент, несмотря на то, что он не может изменить `thisControl` сам.  
  
 **Обход массива.** Поскольку <xref:System.Array> класс реализует <xref:System.Collections.IEnumerable> интерфейс, предоставлять все массивы <xref:System.Array.GetEnumerator%2A> метод. Это означает, что можно выполнить итерацию массива с `For Each`... `Next` цикла. Тем не менее можно только считывать элементы массива. Их нельзя изменить.  
  
## <a name="example"></a>Пример  
 В следующем примере перечислены все папки в каталоге C:\ с помощью <xref:System.IO.DirectoryInfo> класса.  
  
 [!code-vb[VbVbalrStatements#124](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_6.vb)]  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример демонстрирует процедуру сортировки коллекции. В примере выполняется сортировка экземпляров `Car` классов, которые хранятся в <xref:System.Collections.Generic.List%601>. Класс `Car` реализует интерфейс <xref:System.IComparable%601>, который требует реализации метода <xref:System.IComparable%601.CompareTo%2A>.  
  
 Каждый вызов <xref:System.IComparable%601.CompareTo%2A> метод выполняет одно сравнение, используемое для сортировки. Написанный пользователем код в методе `CompareTo` возвращает значение для каждого сравнения текущего объекта с другим объектом. Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, и равняется нулю, если объекты равны. Это позволяет определить в коде условия для отношения «больше», «меньше» и «равно».  
  
 В методе `ListCars` оператор `cars.Sort()` сортирует список. Этот вызов метода <xref:System.Collections.Generic.List%601.Sort%2A> <xref:System.Collections.Generic.List%601> приводит к тому, что метод `CompareTo` вызывается автоматически для объектов `Car` в `List`.  
  
 [!code-vb[VbVbalrStatements#125](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_7.vb)]  
  
## <a name="see-also"></a>См. также  
 [Коллекции](../../../standard/collections/index.md)  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
