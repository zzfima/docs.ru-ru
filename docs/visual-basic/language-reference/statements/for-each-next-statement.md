---
title: "Оператор For Each...Next (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ForEach"
  - "vb.ForEachNext"
  - "vb.Each"
  - "ForEachNext"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "бесконечные циклы"
  - "оператор Next, For Each...Next"
  - "бесконечные циклы"
  - "циклические структуры, For Each...Next"
  - "циклы, бесконечные"
  - "Each - ключевое слово"
  - "инструкции, повтор"
  - "For Each - оператор"
  - "коллекции, повторение инструкции"
  - "циклы, бесконечные"
  - "For Each...Next - операторы"
  - "ключевое слово For [Visual Basic], операторы For Each...Next"
  - "оператор Exit, операторы For Each...Next"
  - "итерация"
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
caps.latest.revision: 56
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 56
---
# Оператор For Each...Next (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Повторяет группу операторов применительно к каждому элементу коллекции.  
  
## Синтаксис  
  
```  
For Each element [ As datatype ] In group  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ element ]  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`element`|Обязателен в операторе `For Each`.  Необязателен в операторе `Next`.  Переменная.  Используется для циклического прохода \(итерации\) элементов коллекции.|  
|`datatype`|Является обязательным, если `element` еще не объявлен.  Тип данных `element`.|  
|`group`|Обязательное.  Переменную с типом, тип коллекции или объект.  Указывает на коллекцию, применительно к элементам которой будут повторяться операторы `statements`.|  
|`statements`|Необязательный параметр.  Один или несколько операторов, стоящих между операторами `For Each` и `Next` и выполняющихся применительно к каждому элементу `group`.|  
|`Continue For`|Необязательный параметр.  Передача управления в начало цикла `For Each`.|  
|`Exit For`|Необязательный параметр.  Передача управления из цикла `For Each`.|  
|`Next`|Обязательное.  Завершение определения цикла `For Each`.|  
  
## Простой пример  
 Цикл `For Each`...`Next` используется при необходимости повтора набора инструкций для каждого элемента коллекции или массива.  
  
> [!TIP]
>  Оператор [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md) работает лучше, когда можно связать каждую итерацию цикла с управляющей переменной и определить ее начальное и конечное значения.  Однако при работе с коллекцией, понятие начальных и окончательных значений не учитывается, и его обязательно неизвестен, сколько элементов коллекции имеется.  В этом типе так, цикл `For Each`…`Next` часто является лучшим вариантом.  
  
 В следующем примере, выписка `For Each`…`Next` просматривает все элементы коллекции списка.  
  
 [!code-vb[VbVbalrStatements#121](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_1.vb)]  
  
 Дополнительные примеры см. в разделах [Коллекции](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md) и [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Вложенные циклы  
 Циклы `For Each` могут вкладываться друг в друга.  
  
 В следующем примере демонстрируется вложенные структуры `For Each`…`Next`.  
  
 [!code-vb[VbVbalrStatements#122](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_2.vb)]  
  
 При поместите циклы, каждый цикл должен иметь уникальное имя переменной `element`.  
  
 Также можно вложить друг в друга различные виды управляющих структур.  Для получения дополнительной информации см. [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## Оставьте для; для  
 Выполнение причин выписки [Оставьте для](../../../visual-basic/language-reference/statements/exit-statement.md), чтобы отключить цикл `For`…`Next` и управление передач на инструкцию, которая следует за выписка `Next`.  
  
 Оператор `Continue For` передает управление непосредственно следующей итерации цикла.  Для получения дополнительной информации см. [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 В следующем примере показано, как используются операторы `Continue For` и `Exit For`.  
  
 [!code-vb[VbVbalrStatements#123](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_3.vb)]  
  
 Любое число операторов `Exit For` можно разместить в цикле `For Each`.  При использовании вложенных циклов `For Each` оператор `Exit For` вызывает выход из самого внутреннего цикла и передает управление следующему уровню вложения.  
  
 `Exit For` часто используется после оценки некоторого условия, например в структуре `If`...`Then`...`Else`.  Можно использовать `Exit For` при следующих условиях:  
  
-   Продолжать выполнение итераций не нужно или невозможно.  Это может быть вызвано ошибочным значением или запросом на прерывание.  
  
-   Исключение перехватывается в `Try`...`Catch`...`Finally`.  Можно использовать `Exit For` в конце блока `Finally`.  
  
-   Там бесконечный цикл, то есть цикл, которые может быть запущен большое или даже бесконечное количество раз.  При обнаружении таких условий для выхода из цикла можно использовать `Exit For`.  Дополнительные сведения см. в разделе [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## Итераторы  
 Используется *итератор*, чтобы выполнять пользовательскую итерации по коллекции.  Итератор может быть функцией или доступом `Get`.  Он использует оператора `Yield` для получения каждого элемента коллекции по одному.  
  
 Следует вызвать итератор выписки с помощью `For Each...Next`.  Каждая итерация цикла `For Each` вызывает итератор.  При достижении выписка `Yield` в итераторе, возвращается выражение в инструкцию `Yield`, и текущего расположения в коде сохраняются.  При следующем вызове итератора выполнение возобновляется с этого места.  
  
 В следующем примере используется функция итератора.  Функция итератора имеет оператора `Yield`, внутри цикла [For… Next](../../../visual-basic/language-reference/statements/for-next-statement.md).  В методе `ListEvenNumbers` на каждую итерацию тела выписки `For Each` создает вызов функции итератора, которая переходит на следующую инструкцию `Yield`.  
  
 [!code-vb[VbVbalrStatements#127](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_4.vb)]  
  
 Дополнительные сведения см. в разделах [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md), [Оператор Yield](../../../visual-basic/language-reference/statements/yield-statement.md) и [Итератор](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## Техническая реализация  
 Когда выписка `For Each`…`Next` выполняется, Visual Basic возвращает коллекцию только один раз, перед началом цикла.  Если блок выписки изменяет `element` или `group`, то эти изменения не влияют на итерации цикла.  
  
 Когда переменной `element` будут присвоены все элементы коллекции, цикл `For Each` остановится и управление будет передано оператору, следующему за оператором `Next`.  
  
 Если `element` не было объявлено вне этого цикла, необходимо объявить его в инструкцию `For Each`.  Можно объявить тип `element` явным образом при помощи оператора `As`, или можно использовать определение типа для назначения типа.  В этом случае областью действия `element` является основная часть цикла.  В то же время нельзя определять `element` и внутри, и снаружи цикла.  
  
 Можно дополнительно указать `element` в инструкции `Next`.  Это повышает удобочитаемость программы, особенно если в ней имеются вложенные циклы `For Each`.  При этом следует указать ту же переменную, что и в соответствующем операторе `For Each`.  
  
 Можно избежать изменения значения `element` внутри цикла.  Это может сделать его более сложным для чтения и отладку кода.  Изменение значения `group` не влияет на коллекцию или элементы, которые были определены при цикл сначала был введен.  
  
 Если циклы вложения, если выписка `Next` внешнего уровень вложенности обнаружении перед `Next` внутреннего уровня, компилятор сигнализирует об ошибке.  При этом компилятор может обнаружить эту ошибку только в том случае, если в каждой инструкции `Next` указан `element`.  
  
 Если код зависит от переместить коллекцию в определенном порядке, цикл `For Each`…`Next` нет рекомендуемые варианта, если не требуется знать характеристики объекта перечислителя коллекции предоставляет.  Порядок обхода не определен Visual Basic, но методом <xref:System.Collections.IEnumerator.MoveNext%2A> объекта перечислителя.  Это означает, что пользователь не может задать, какой элемент должен быть первым записан в `element`, или какой элемент должен следовать за каким\-либо элементом.  С помощью другой циклической структуры, например `For`...`Next` или `Do`...`Loop`, можно добиться более надежных результатов.  
  
 Тип данных `element` должен быть таким, чтобы тип данных элементов в `group` мог быть преобразован к нему.  
  
 Тип данных `group` должен быть ссылочным типом, который ссылается на коллекцию или массив, который доступен для перечисления.  Чаще всего это означает, что `group` ссылается на объект, реализующий интерфейс <xref:System.Collections.IEnumerable> из пространства имен `System.Collections` или интерфейс <xref:System.Collections.Generic.IEnumerable%601> из пространства имен `System.Collections.Generic`.  `System.Collections.IEnumerable` задает метод <xref:System.Collections.IEnumerable.GetEnumerator%2A>, который возвращает объект перечислителя для коллекции.  Объект перечислителя реализует интерфейс `System.Collections.IEnumerator` пространства имен `System.Collections`, а также имеет свойство <xref:System.Collections.IEnumerator.Current%2A>, методы <xref:System.Collections.IEnumerator.Reset%2A> и <xref:System.Collections.IEnumerator.MoveNext%2A>.  Visual Basic использует их для перемещения по коллекции.  
  
### Сужающие преобразования  
 Если `Option Strict` равно `On`, сужающее преобразование обычно вызывает ошибки компилятора.  Однако в операторе `For Each` преобразования из элементов `group` в `element` оцениваются и выполняются во время выполнения и ошибка компилятора, вызванная сужающим преобразованием, может быть подавлена.  
  
 В следующем примере, назначения `m` как начальное значение для `n` не будет компилироваться при `Option Strict`, поскольку преобразование `Long` в `Integer` сужающее преобразование.  В операторе`For Each`  однако, не ошибка компилятора сообщается, даже несмотря на то, что присвоение `number` требует того же преобразования из `Long` в `Integer`.  В операторе `For Each` , содержащем большое число, то во время выполнения возникает ошибка, когда к большому числу применяется <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>.  
  
 [!code-vb[VbVbalrStatements#89](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_5.vb)]  
  
### Вызовы IEnumerator  
 В начале выполнения цикла `For Each`...`Next` Visual Basic проверяет, на допустимую ли коллекцию объектов ссылается `group`.  Если это не так, то создается исключение.  В противном случае вызывается метод <xref:System.Collections.IEnumerator.MoveNext%2A> и свойство <xref:System.Collections.IEnumerator.Current%2A> объекта перечислителя, возвращающее первый элемент.  Если `MoveNext` указывает, что следующий элемент отсутствует, то есть коллекция пуста, то цикл `For Each` останавливается и управление передается оператору, следующему за оператором `Next`.  В противном случае Visual Basic присваивает `element` значение первого элемента и выполняет блок операторов.  
  
 Каждый раз, обнаруживая инструкцию `Next`, Visual Basic возвращается на инструкцию `For Each`.  Снова для получения следующего элемента вызывается метод `MoveNext` и свойство `Current`, и снова в зависимости от результата либо выполняется блок, либо цикл останавливается.  Этот процесс продолжается до тех пор, пока метод `MoveNext` не укажет на отсутствие следующего элемента, или пока не встретится оператор `Exit For`.  
  
 **Изменение коллекции.** Возвращает объект перечислителя <xref:System.Collections.IEnumerable.GetEnumerator%2A> обычно не позволяет изменять коллекцию путем добавления, удаления и переупорядочивания заменить все элементы.  Если пользователь изменит коллекцию после запуска цикла `For Each`...`Next`, то объект перечислителя станет недействительным, и следующая попытка обращения к элементу коллекции вызовет исключение <xref:System.InvalidOperationException>.  
  
 Однако эта блокировка изменения не указана, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], а реализацией интерфейса <xref:System.Collections.IEnumerable>.  Можно реализовать `IEnumerable` таким образом, чтобы сделать изменение коллекции во время итерации возможным.  Если планируется производить такие динамические изменения, то необходимо определить характер реализации `IEnumerable` используемой коллекции.  
  
 **Изменение элементов коллекции.** Свойство объекта перечисления <xref:System.Collections.IEnumerator.Current%2A> имеет модификатор [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) и возвращает локальную копию каждого элемента коллекции.  Это означает, что в цикле `For Each`...`Next` нельзя изменить сами элементы.  Любые изменения, сделанные влияет только на локальную копию из `Current` и обратно не отражены в базовую коллекцию.  Тем не менее, если элемент имеет ссылочный тип, то можно изменять члены экземпляра, на который он указывает.  Следующий пример изменяет элемент `BackColor` каждого элемента `thisControl`.  Нельзя изменить, однако сам оператор `thisControl`.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 В предыдущем примере можно изменить член `BackColor` каждого элемента `thisControl`, несмотря на то, что нельзя изменить сам `thisControl` .  
  
 **Обход массива.** Поскольку класс <xref:System.Array> реализует интерфейс <xref:System.Collections.IEnumerable>, все массивы имеют метод <xref:System.Array.GetEnumerator%2A>.  Это означает, что с помощью цикла `For Each`... `Next` можно перебирать и массивы.  Тем не менее, элементы массива можно только считывать.  Это изменить нельзя.  
  
## Пример  
 В следующем примере перечислены все папки в папке C:\\ с помощью класса<xref:System.IO.DirectoryInfo>.  
  
 [!code-vb[VbVbalrStatements#124](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_6.vb)]  
  
## Пример  
 Следующий пример демонстрирует процедуру сортировки коллекции.  Пример сортирует экземпляры класса `Car`, хранящихся в <xref:System.Collections.Generic.List%601>.  Класс `Car` реализует интерфейс <xref:System.IComparable%601>, который требует, чтобы метод <xref:System.IComparable%601.CompareTo%2A> был реализован.  
  
 Каждый вызов метода <xref:System.IComparable%601.CompareTo%2A> делает одно сравнение, используется для сортировки.  Написанный пользователем код в методе `CompareTo` возвращает значение для каждого сравнения текущего объекта с другим объектом.  Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, а также равняется нулю, если объекты равны.  Это позволяет указать в коде условие для отношения "больше", "меньше" и "равно".  
  
 В методе `ListCars` оператор `cars.Sort()` сортирует список.  Этот вызов метода <xref:System.Collections.Generic.List%601.Sort%2A> <xref:System.Collections.Generic.List%601> приводит к тому, что метод `CompareTo` вызывается автоматически для объектов `Car` в `List`.  
  
 [!code-vb[VbVbalrStatements#125](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_7.vb)]  
  
## См. также  
 [Коллекции](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Инициализаторы объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)