---
title: Оператор For…Next
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 3cae44abb8e790542f11e6c5a5f1e317675ff988
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351186"
---
# <a name="fornext-statement-visual-basic"></a>Оператор For... Next (Visual Basic)

Повторяет группу инструкций указанное число раз.

## <a name="syntax"></a>Синтаксис

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a>Части

|Отделение|Описание|
|----------|-----------------|
|`counter`|Требуется в операторе `For`. Числовая переменная. Управляющая переменная для цикла. Дополнительные сведения см. в подразделе [аргумент Counter](#BKMK_Counter) далее в этой статье.|
|`datatype`|Необязательный элемент. Тип данных `counter`. Дополнительные сведения см. в подразделе [аргумент Counter](#BKMK_Counter) далее в этой статье.|
|`start`|Обязательно. Числовое выражение. Начальное значение `counter`.|
|`end`|Обязательно. Числовое выражение. Конечное значение `counter`.|
|`step`|Необязательный элемент. Числовое выражение. Величина, на которую `counter` увеличивается каждый раз с помощью цикла.|
|`statements`|Необязательный элемент. Одна или несколько инструкций между `For` и `Next`, которые выполняются указанное число раз.|
|`Continue For`|Необязательный элемент. Передает управление в следующую итерацию цикла.|
|`Exit For`|Необязательный элемент. Передает управление за пределы цикла `For`.|
|`Next`|Обязательно. Завершает определение цикла `For`.|

> [!NOTE]
> Ключевое слово `To` используется в этом операторе для указания диапазона счетчика. Это ключевое слово также можно использовать в [SELECT... Оператор Case](../../../visual-basic/language-reference/statements/select-case-statement.md) и в объявлениях массивов. Дополнительные сведения об объявлениях массивов см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).

## <a name="simple-examples"></a>Простые примеры

Используйте структуру `For`...`Next`, если необходимо повторить набор инструкций заданное число раз.

В следующем примере переменная `index` начинается со значения 1 и увеличивается при каждой итерации цикла, после чего значение `index` достигает 5.

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

В следующем примере переменная `number` начинается с 2 и уменьшается на 0,25 в каждой итерации цикла, после чего значение `number` достигнет 0. Аргумент `Step` `-.25` сокращает значение на 0,25 в каждой итерации цикла.

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> Ответ [... Конец оператора while](../../../visual-basic/language-reference/statements/while-end-while-statement.md) или [Do... Оператор Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md) хорошо работает, если заранее неизвестно, сколько раз нужно выполнять инструкции в цикле. Однако, если вы планируете выполнять цикл определенное количество раз, лучше выбрать цикл `For`...`Next`. Число итераций определяется при первом входе в цикл.

## <a name="nesting-loops"></a>Вложенные циклы

Можно вкладывать `For` циклы, помещая один цикл внутрь другого. В следующем примере показаны вложенные структуры `For`...`Next`, которые имеют разные значения шага. Внешний цикл создает строку для каждой итерации цикла. Внутренний цикл уменьшает переменную счетчика цикла для каждой итерации цикла.

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

При вложенных циклах каждый цикл должен иметь уникальную переменную `counter`.

Вы также можете вкладывать различные виды управления в друг друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).

## <a name="exit-for-and-continue-for"></a>Выход и продолжение для

Инструкция `Exit For` немедленно завершает работу `For`...`Next` выполняет цикл и передает управление оператору, который следует за оператором `Next`.

Оператор `Continue For` передает управление сразу в следующую итерацию цикла. Дополнительные сведения см. в разделе [оператор continue](../../../visual-basic/language-reference/statements/continue-statement.md).

В следующем примере показано использование инструкций `Continue For` и `Exit For`.

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

В `For`можно разместить любое количество `Exit For` инструкций...`Next` Повторить. При использовании внутри вложенных `For`...`Next` циклы, `Exit For` выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.

`Exit For` часто используется после вычисления некоторого условия (например, в структуре `If`...`Then`...`Else`). `Exit For` может потребоваться использовать для следующих условий:

- Продолжение итерации не требуется или невозможно. Это условие может быть создано с помощью ошибочного значения или запроса на завершение.

- Инструкция `Try`...`Catch`...`Finally` перехватывает исключение. В конце блока `Finally` можно использовать `Exit For`.

- У вас есть бесконечный цикл, который может выполняться с большим или даже бесконечным числом раз. При обнаружении такого условия можно использовать `Exit For` для экранирования цикла. Дополнительные сведения см. в разделе [Do... Loop, инструкция](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="technical-implementation"></a>Техническая реализация

При запуске цикла `For`...`Next` Visual Basic оценивает `start`, `end`и `step`. Visual Basic вычисляет эти значения только в данный момент, а затем присваивает `start` `counter`. Перед выполнением блока операторов Visual Basic сравнивает `counter` с `end`. Если `counter` уже больше `end`ого значения (или меньше, если `step` отрицательно), цикл `For` завершается и управление передается оператору, который следует за инструкцией `Next`. В противном случае выполняется блок операторов.

Каждый раз, когда Visual Basic встречает инструкцию `Next`, она увеличивает `counter` с `step` и возвращает в инструкцию `For`. Опять же, он сравнивает `counter` с `end`и снова выполняет блок или выходит из цикла, в зависимости от результата. Этот процесс будет продолжен до тех пор, пока `counter` не пройдет `end` или не встретится инструкция `Exit For`.

Цикл не останавливается, пока `counter` не пройдет `end`. Если `counter` равно `end`, цикл продолжится. Сравнение, которое определяет, следует ли запускать блок `counter` <= `end`, если `step` является положительным и `counter` >= `end` если `step` является отрицательным.

Если изменить значение `counter` в цикле, код может оказаться труднее для чтения и отладки. Изменение значения `start`, `end`или `step` не влияет на значения итерации, которые были определены при первом входе в цикл.

При вложении циклов компилятор сообщает об ошибке, если обнаруживает оператор `Next` внешнего уровня вложенности перед инструкцией `Next` внутреннего уровня. Однако компилятор может обнаружить эту ошибку перекрытия только в том случае, если указать `counter` в каждой инструкции `Next`.

### <a name="step-argument"></a>Аргумент Step

Значение `step` может быть либо положительным, либо отрицательным. Этот параметр определяет обработку цикла в соответствии со следующей таблицей.

|**Значение шага**|**Цикл выполняется, если**|
|--------------------|--------------------------|
|Положительный или нулевой|`counter` <= `end`|
|Отрицательное число|`counter` >= `end`|

Значение по умолчанию `step` равно 1.

### <a name="BKMK_Counter"></a>Аргумент счетчика

В следующей таблице показано, определяет ли `counter` новую локальную переменную, ограниченную всем циклом `For…Next`. Это определение зависит от того, существует ли `datatype` и определен ли уже `counter`.

|Имеется `datatype`?|`counter` уже определена?|Результат (`counter` определяет новую локальную переменную, ограниченную всем циклом `For...Next`)|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|Нет|Да|Нет, поскольку `counter` уже определен. Если область `counter` не является локальной для процедуры, возникает предупреждение во время компиляции.|
|Нет|Нет|Да. Тип данных выводится из выражений `start`, `end`и `step`. Дополнительные сведения о выводе типа см. в разделе [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [определение локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|
|Да|Да|Да, но только в том случае, если существующая переменная `counter` определена за пределами процедуры. Эта переменная остается отдельной. Если область существующей переменной `counter` является локальной для процедуры, возникает ошибка времени компиляции.|
|Да|Нет|Да.|

Тип данных `counter` определяет тип итерации, который должен быть одним из следующих типов:

- `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`или `Double`.

- Перечисление, объявляемое с помощью [инструкции enum](../../../visual-basic/language-reference/statements/enum-statement.md).

- Объект `Object`.

- Тип `T`, имеющий следующие операторы, где `B` — это тип, который можно использовать в выражении `Boolean`.

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

При необходимости можно указать переменную `counter` в инструкции `Next`. Этот синтаксис повышает удобочитаемость программы, особенно при наличии вложенных циклов `For`. Необходимо указать переменную, которая отображается в соответствующей инструкции `For`.

Выражения `start`, `end`и `step` могут иметь любой тип данных, который расширяется до типа `counter`. Если для `counter`используется определяемый пользователем тип, может потребоваться определить оператор преобразования `CType`, чтобы преобразовать типы `start`, `end`или `step` в тип `counter`.

## <a name="example"></a>Пример

В следующем примере удаляются все элементы из универсального списка. Вместо a [для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md). в примере показана инструкция `For`...`Next`, которая выполняет итерацию в убывающем порядке. В этом примере используется этот метод, так как метод `removeAt` заставляет элементы после удаленного элемента иметь меньшее значение индекса.

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a>Пример

В следующем примере перебирается перечисление, объявленное с помощью [инструкции enum](../../../visual-basic/language-reference/statements/enum-statement.md).

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a>Пример

В следующем примере параметры инструкции используют класс с перегрузками операторов `+`, `-`, `>=`и `<=`.

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic.List%601>
- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Коллекции](../../programming-guide/concepts/collections.md)
