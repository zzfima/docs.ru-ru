---
title: "Для каждого... Next Statement (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
dev_langs:
- VB
helpviewer_keywords:
- infinite loops
- Next statement, For Each...Next
- endless loops
- loop structures, For Each...Next
- loops, endless
- Each keyword
- instructions, repeating
- For Each statement
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement, For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
caps.latest.revision: 56
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e0173877fa4a57da76fd774d70ce63d2beda23ad
ms.lasthandoff: 03/13/2017

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
|`element`|Требуется в `For Each` инструкции. Необязательно в `Next` инструкции. Переменная. Используется для итерации элементов коллекции.|  
|`datatype`|Обязателен, если `element` уже не объявлен. Тип данных `element`.|  
|`group`|Обязательный. Переменная с типом, который является типом коллекции или объекта. Относится к коллекции, по которому `statements` будут повторяться.|  
|`statements`|Необязательный. Один или несколько операторов между `For Each` и `Next` , работающих на каждый элемент в `group`.|  
|`Continue For`|Необязательный. Передача управления в начало `For Each` цикла.|  
|`Exit For`|Необязательный. Передает управление из `For Each` цикла.|  
|`Next`|Обязательный. Завершает определение `For Each` цикла.|  
  
## <a name="simple-example"></a>Простой пример  
 Use a `For Each`... `Next` цикл, когда требуется выполнить набор инструкций для каждого элемента коллекции или массива.  
  
> [!TIP]
>  A [For... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) работает хорошо, когда можно связать каждую итерацию цикла с управляющей переменной и определить начальное и конечное значения этой переменной. Однако при работе с коллекцией, концепция начального и конечного значений лишено смысла и не требуется знать количество элементов в коллекции может. В таком случае `For Each`... `Next` цикл часто является лучшим выбором.  
  
 В следующем примере `For Each`...`Next` Инструкция перебор всех элементов коллекции списка.  
  
 [!code-vb[VbVbalrStatements&#121;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_1.vb)]  
  
 Дополнительные примеры см. в разделе [коллекции](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) и [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="nested-loops"></a>Вложенные циклы  
 Можно вложить `For Each` циклы, поместив один цикл внутри другого.  
  
 В следующем примере вложенные `For Each`...`Next` структуры.  
  
 [!code-vb[VbVbalrStatements&#122;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_2.vb)]  
  
 При вложении циклы каждый цикл должен иметь уникальный `element` переменной.  
  
 Также можно вложить различные виды управляющих структур друг с другом. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Для выхода и повторите эти действия для  
 [Выхода для](../../../visual-basic/language-reference/statements/exit-statement.md) оператор прерывает выполнение выхода `For`...`Next` цикл передает управление оператору, следующему `Next` инструкции.  
  
 `Continue For` Оператор передает управление непосредственно следующей итерации цикла. Дополнительные сведения см. в разделе [оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 В следующем примере показано, как использовать `Continue For` и `Exit For` инструкции.  
  
 [!code-vb[VbVbalrStatements&#123;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_3.vb)]  
  
 Можно поместить любое число `Exit For` инструкций в `For Each` цикла. При использовании внутри вложенных `For Each` циклы, `Exit For` приводит к выполнению выйти из внутреннего цикла и передачи управления на следующий уровень вложенности.  
  
 `Exit For`часто используется после оценки некоторого условия, например, в `If`... `Then`... `Else` структуры. Вы можете использовать `Exit For` для следующих условий:  
  
-   Продолжение выполнения итерации, ненужных или невозможно. Это может быть вызвано ошибочное значение или запрос на завершение.  
  
-   Исключение будет перехвачено в `Try`... `Catch`... `Finally`. Можно использовать `Exit For` в конце `Finally` блок.  
  
-   Существует бесконечный цикл является цикл, повторяемый большими или бесконечными даже несколько раз. При обнаружении таких условий, можно использовать `Exit For` для выхода из цикла. Дополнительные сведения см. в разделе [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="iterators"></a>Итераторы  
 Использовать *итератор* для выполнения пользовательских итерации по коллекции. Итератор может быть функцией или `Get` доступа. Он использует `Yield` инструкции для возврата каждого элемента коллекции одной за раз.  
  
 Итератор вызывается с помощью `For Each...Next` инструкции. Каждая итерация `For Each` цикл вызывает итератор. Когда `Yield` в итераторе выражение в достижении оператора `Yield` инструкции возвращается и сохраняется текущее расположение в коде. При следующем вызове итератора выполнение возобновляется с этого места.  
  
 В следующем примере функции итератора. У функции итератора `Yield` оператор, находящийся внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла. В `ListEvenNumbers` метод, каждая итерация `For Each` тела оператора создает вызов функции итератора, который переходит к следующему `Yield` инструкции.  
  
 [!code-vb[VbVbalrStatements&#127;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_4.vb)]  
  
 Дополнительные сведения см. в разделе [итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7), [оператор Yield](../../../visual-basic/language-reference/statements/yield-statement.md), и [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## <a name="technical-implementation"></a>Техническая реализация  
 Когда `For Each`...`Next` выполняется инструкция, Visual Basic вычисляет коллекцию только один раз, до начала цикла. Если в блоке операторов изменяется `element` или `group`, эти изменения не влияют на итерации цикла.  
  
 Когда все элементы в коллекции успешно назначены `element`, `For Each` цикл прекращается и управление передается оператору, следующему `Next` инструкции.  
  
 Если `element` еще не был объявлен вне цикла, необходимо объявить ее в `For Each` инструкции. Можно объявить тип `element` явным образом с помощью `As` оператор, или можно положиться на определение типа для типа назначения. В любом случае область `element` является тело цикла. Однако нельзя объявлять `element` и снаружи цикла.  
  
 При необходимости можно указать `element` в `Next` инструкции. Это повышает удобочитаемость программы, особенно в том случае, если имеются вложенные `For Each` циклы. Необходимо указать ту же переменную, которая отображается в соответствующем `For Each` инструкции.  
  
 Не изменяйте значение может потребоваться `element` внутри цикла. Это можно сделать его более трудными для понимания и отладки кода. Изменение значения `group` не влияет на коллекцию или ее элементы, которые были определены при первом входе цикла.  
  
 Когда вложенные циклы, если `Next` перед встречается оператор внешнего уровня вложенности `Next` внутреннего уровня, компилятор сообщает об ошибке. Однако компилятор может обнаружить это перекрытие ошибки только в том случае, если указать `element` в каждом `Next` инструкции.  
  
 Если код зависит от обхода коллекции в определенном порядке, `For Each`... `Next` цикл не лучшим выбором, если известны характеристики объекта перечислителя, предоставляемого коллекцией. Порядок обхода не определяет Visual Basic, но <xref:System.Collections.IEnumerator.MoveNext%2A>метод объекта-перечислителя.</xref:System.Collections.IEnumerator.MoveNext%2A> Таким образом, вы не сможете предсказать, какой элемент коллекции является первым должен быть возвращен в `element`, или это Далее возвращается после заданного элемента. Можно достичь более надежных результатов с помощью другой циклической структуры, например `For`... `Next` or `Do`... `Loop`.  
  
 Тип данных `element` должен быть таким, чтобы тип данных элементов `group` может быть преобразован к нему.  
  
 Тип данных `group` должен быть ссылочный тип, который ссылается на коллекцию или массив, который является перечислимым. Обычно это означает, что `group` ссылается на объект, реализующий интерфейс <xref:System.Collections.IEnumerable>интерфейс `System.Collections` пространства имен или <xref:System.Collections.Generic.IEnumerable%601>интерфейс `System.Collections.Generic` имен.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable> `System.Collections.IEnumerable`Определяет <xref:System.Collections.IEnumerable.GetEnumerator%2A>метод, который возвращает объект перечислителя для коллекции.</xref:System.Collections.IEnumerable.GetEnumerator%2A> Объект перечислителя реализует `System.Collections.IEnumerator` интерфейс `System.Collections` пространства имен и предоставляет <xref:System.Collections.IEnumerator.Current%2A>свойство и <xref:System.Collections.IEnumerator.Reset%2A>и <xref:System.Collections.IEnumerator.MoveNext%2A>методы.</xref:System.Collections.IEnumerator.MoveNext%2A> </xref:System.Collections.IEnumerator.Reset%2A> </xref:System.Collections.IEnumerator.Current%2A> Visual Basic использует их для перемещения по коллекции.  
  
### <a name="narrowing-conversions"></a>Сужающие преобразования  
 Когда `Option Strict` равен `On`, сужающее преобразование обычно вызывает ошибки компилятора. В `For Each` инструкции, однако, преобразования из элементов в `group` для `element` вычисляются и во время выполнения и ошибки компилятора, вызванные сужающие преобразования подавляются.  
  
 В следующем примере назначение `m` как начальное значение для `n` не будет компилироваться при `Option Strict` включен, поскольку преобразование `Long` для `Integer` сужающего преобразования. В `For Each` инструкции, однако никакие ошибки компилятора не сообщается, даже если назначения `number` требуется то же самое преобразование из `Long` в `Integer`. В `For Each` инструкция, содержащая большое число, то во время выполнения возникает ошибка при <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>применяется к большим числом.</xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>  
  
 [!code-vb[VbVbalrStatements&#89;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_5.vb)]  
  
### <a name="ienumerator-calls"></a>IEnumerator вызовов  
 При выполнении `For Each`... `Next` начинается цикл, Visual Basic проверяет, что `group` ссылается на объект допустимым коллекции. В противном случае возникает исключение. В противном случае, он вызывает <xref:System.Collections.IEnumerator.MoveNext%2A>метод и <xref:System.Collections.IEnumerator.Current%2A>Свойства объекта перечислителя, который требуется возвратить первый элемент.</xref:System.Collections.IEnumerator.Current%2A> </xref:System.Collections.IEnumerator.MoveNext%2A> Если `MoveNext` указывает, что отсутствует следующий элемент, то есть, если коллекция пуста, `For Each` цикл прекращается и управление передается оператору, следующему `Next` инструкции. В противном случае — Visual Basic устанавливает `element` для первого элемента и выполняется блок операторов.  
  
 При каждом запуске Visual Basic встречает `Next` оператор, она возвращает `For Each` инструкции. Снова вызывает `MoveNext` и `Current` для получения следующего элемента и снова либо выполняется блок или останавливает цикла в зависимости от результата. Этот процесс продолжается до `MoveNext` указывает, что следующего элемента не существует или `Exit For` встречается оператор.  
  
 **Изменение коллекции.** Объект перечислителя, возвращенный <xref:System.Collections.IEnumerable.GetEnumerator%2A>обычно не позволяет изменить коллекцию путем добавления, удаления, замены или изменяя порядок элементов.</xref:System.Collections.IEnumerable.GetEnumerator%2A> При изменении коллекции после запуска `For Each`... `Next` цикла, перечислитель становится недействительным, и вызывает следующей попытки доступа к элементу <xref:System.InvalidOperationException>исключение.</xref:System.InvalidOperationException>  
  
 Однако, эта блокировка изменения не определяются [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], но реализация <xref:System.Collections.IEnumerable>интерфейса.</xref:System.Collections.IEnumerable> Это можно реализовать `IEnumerable` способом, который позволяет изменять во время итерации. Если вы собираетесь производить такие динамические изменения, убедитесь, что вы понимаете характеристики `IEnumerable` реализацию на коллекцию, вы используете.  
  
 **Изменение элементов коллекции.** <xref:System.Collections.IEnumerator.Current%2A>Свойство объекта перечислителя [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), и возвращает локальную копию каждого элемента коллекции.</xref:System.Collections.IEnumerator.Current%2A> Это означает, что нельзя изменить сами элементы в `For Each`... `Next` loop. Любые изменения, внесенные влияет только на локальную копию из `Current` и не отражается в коллекции. Тем не менее если элемент является ссылочным типом, можно изменить члены экземпляра, на который он указывает. В следующем примере изменяется `BackColor` каждого элемента `thisControl` элемент. Однако невозможно изменить `thisControl` сам.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Предыдущий пример можно изменить `BackColor` каждого элемента `thisControl` элемент, несмотря на то, что он не может изменить `thisControl` сам.  
  
 **Обход массива.** Поскольку <xref:System.Array>реализует <xref:System.Collections.IEnumerable>интерфейс, предоставляет все массивы <xref:System.Array.GetEnumerator%2A>метод.</xref:System.Array.GetEnumerator%2A> </xref:System.Collections.IEnumerable> </xref:System.Array> Это означает, что можно выполнить итерацию массива с `For Each`... `Next` loop. Тем не менее доступные только для чтения элементов массива. Их нельзя изменить.  
  
## <a name="example"></a>Пример  
 В следующем примере перечислены все папки в каталоге C:\ с помощью <xref:System.IO.DirectoryInfo>класса.</xref:System.IO.DirectoryInfo>  
  
 [!code-vb[VbVbalrStatements&#124;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_6.vb)]  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример демонстрирует процедуру сортировки коллекции. В примере выполняется сортировка экземпляров `Car` класса, которые хранятся в папке <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> `Car` Реализует <xref:System.IComparable%601>интерфейс, который требует <xref:System.IComparable%601.CompareTo%2A>метод будет реализован.</xref:System.IComparable%601.CompareTo%2A> </xref:System.IComparable%601>  
  
 Каждый вызов <xref:System.IComparable%601.CompareTo%2A>метод делает одну сравнения, используемый для сортировки.</xref:System.IComparable%601.CompareTo%2A> Пользовательский код в `CompareTo` метод возвращает значение для каждого сравнения текущего объекта с другим объектом. Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, и равняется нулю, если объекты равны. Это позволяет определить в коде условия для отношения «больше», «меньше» и «равно».  
  
 В `ListCars` метода `cars.Sort()` инструкция сортирует список. Этот вызов <xref:System.Collections.Generic.List%601.Sort%2A>метод <xref:System.Collections.Generic.List%601>вызывает `CompareTo` метод, который вызывается автоматически для `Car` объектов в `List`.</xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.List%601.Sort%2A>  
  
 [!code-vb[VbVbalrStatements&#125;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_7.vb)]  
  
## <a name="see-also"></a>См. также  
 [Коллекции](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)   
 [Для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [While... Завершить оператор While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Сделать... Оператор Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Инициализаторы объектов: Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
