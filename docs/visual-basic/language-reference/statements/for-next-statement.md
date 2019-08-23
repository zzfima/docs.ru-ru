---
title: Оператор For... Next (Visual Basic)
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
ms.openlocfilehash: 9a9aed51f6d7bf3233e6e89116b8209b22f3d15d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912414"
---
# <a name="fornext-statement-visual-basic"></a>Оператор For... Next (Visual Basic)
Повторяет группу инструкций указанное число раз.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
|`counter`|Требуется в `For` инструкции. Числовая переменная. Управляющая переменная для цикла. Дополнительные сведения см. в подразделе [аргумент Counter](#BKMK_Counter) далее в этой статье.|  
|`datatype`|Необязательный параметр. Тип `counter`данных. Дополнительные сведения см. в подразделе [аргумент Counter](#BKMK_Counter) далее в этой статье.|  
|`start`|Обязательный. Числовое выражение. Начальное значение `counter`.|  
|`end`|Обязательный. Числовое выражение. Конечное значение `counter`.|  
|`step`|Необязательный параметр. Числовое выражение. Величина, на `counter` которую увеличивается каждый раз с помощью цикла.|  
|`statements`|Необязательный параметр. Одна или несколько инструкций между `For` и `Next` выполняются указанное число раз.|  
|`Continue For`|Необязательный параметр. Передает управление в следующую итерацию цикла.|  
|`Exit For`|Необязательный параметр. Передает управление за пределы `For` цикла.|  
|`Next`|Обязательный. Завершает определение `For` цикла.|  
  
> [!NOTE]
> `To` Ключевое слово используется в этом операторе для указания диапазона счетчика. Это ключевое слово также можно использовать в [SELECT... Оператор Case](../../../visual-basic/language-reference/statements/select-case-statement.md) и в объявлениях массивов. Дополнительные сведения об объявлениях массивов см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="simple-examples"></a>Простые примеры  
 Вы используете `For`... `Next` структура, если необходимо повторить набор инструкций заданное число раз.  
  
 В следующем примере `index` переменная начинается со значения 1 и увеличивается при каждой итерации цикла, после чего `index` значение достигает 5.  
  
 [!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]  
  
 В следующем примере `number` переменная начинается с 2 и уменьшается на 0,25 в каждой итерации цикла, после чего `number` значение достигнет 0. `Step` Аргумент класса`-.25` сокращает значение на 0,25 при каждой итерации цикла.  
  
 [!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]  
  
> [!TIP]
>  Ответ [... Конец оператора while](../../../visual-basic/language-reference/statements/while-end-while-statement.md) или [Do... Оператор Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md) хорошо работает, если заранее неизвестно, сколько раз нужно выполнять инструкции в цикле. Однако, если вы планируете запускать цикл определенное число раз, a `For`... `Next` лучше выбрать цикл. Число итераций определяется при первом входе в цикл.  
  
## <a name="nesting-loops"></a>Вложенные циклы  
 Можно вложить `For` циклы, поместив один цикл в другой. В следующем примере демонстрируется `For`вложенное... `Next` структуры, имеющие разные значения шага. Внешний цикл создает строку для каждой итерации цикла. Внутренний цикл уменьшает переменную счетчика цикла для каждой итерации цикла.  
  
 [!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]  
  
 При вложенных циклах каждый цикл должен иметь уникальную `counter` переменную.  
  
 Вы также можете вкладывать различные виды управления в друг друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Выход и продолжение для  
 Оператор немедленно завершает работу `For`... `Exit For``Next` выполняет цикл и передает управление оператору, который следует `Next` за оператором.  
  
 `Continue For` Оператор передает управление сразу в следующую итерацию цикла. Дополнительные сведения см. в разделе [оператор continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 В следующем примере показано использование `Continue For` операторов и. `Exit For`  
  
 [!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]  
  
 Можно разместить любое количество `Exit For` операторов `For`в...`Next` повторить. При использовании внутри вложенного `For`...`Next` выполняет цикл `Exit For` , выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.  
  
 `Exit For`часто используется после вычисления некоторого условия (например, в `If`... `Then`... `Else` структура). Может потребоваться использовать `Exit For` для следующих условий:  
  
- Продолжение итерации не требуется или невозможно. Это условие может быть создано с помощью ошибочного значения или запроса на завершение.  
  
- А `Try`... `Catch`... `Finally` перехватывает исключение. В конце `Exit For` `Finally` блока можно использовать.  
  
- У вас есть бесконечный цикл, который может выполняться с большим или даже бесконечным числом раз. При обнаружении такого условия можно использовать `Exit For` для экранирования цикла. Дополнительные сведения см. в разделе [Do... Loop, инструкция](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="technical-implementation"></a>Техническая реализация  
 `For`Когда... начинается цикл, Visual Basic `start`вычисляет, `end`и `step`. `Next` Visual Basic вычисляет эти значения только в данный момент, а затем присваивает `start` `counter`значение. Перед выполнением блока операторов Visual Basic сравнивается `counter` с. `end` Если `counter` `step` уже `For` больше значения (или меньше, если имеет отрицательное значение), `Next` цикл завершается, и управление передается оператору, следующему за оператором. `end` В противном случае выполняется блок операторов.  
  
 Каждый раз, когда Visual Basic обнаруживает `Next` оператор, он `counter` увеличивается `step` на и возвращается в `For` оператор. Затем он сравнивает `counter` с `end`и снова либо выполняет блок, либо выходит из цикла, в зависимости от результата. Этот процесс выполняется до `counter` тех `end` пор, `Exit For` пока не будет пройден или не встретится оператор.  
  
 Цикл не останавливается, пока `counter` не будет `end`пройден. `counter` Если`end`равно, цикл продолжится. `counter` Сравнение, которое определяет, следует ли запускать блок `end` `counter` `end` `step`  <=  , если является положительным и `step`  >=  отрицательным.  
  
 Если изменить значение `counter` во время цикла, код может оказаться труднее для чтения и отладки. Изменение значения `start`, `end`или `step` не влияет на значения итерации, которые были определены при первом входе в цикл.  
  
 При вложении циклов компилятор сообщает об ошибке, если обнаруживает `Next` оператор внешнего уровня вложенности `Next` перед инструкцией внутреннего уровня. Однако компилятор может обнаружить эту перекрытие ошибки только в том случае, `counter` если указать `Next` в каждой инструкции.  
  
### <a name="step-argument"></a>Аргумент Step  
 Значение `step` может быть либо положительным, либо отрицательным. Этот параметр определяет обработку цикла в соответствии со следующей таблицей.  
  
|**Значение шага**|**Цикл выполняется, если**|  
|--------------------|--------------------------|  
|Положительный или нулевой|`counter` <= `end`|  
|Отрицательное число|`counter` >= `end`|  
  
 Значение по умолчанию `step` равно 1.  
  
### <a name="BKMK_Counter"></a>Аргумент счетчика  
 В следующей таблице показано, `counter` определяет ли новая локальная переменная, областью действия которой является `For…Next` весь цикл. Это определение зависит от того `datatype` , существует ли оно `counter` и уже определено ли оно.  
  
|`datatype` Имеется?|`counter` Уже определено?|Результат (определяет `counter` , определена ли новая локальная переменная в пределах всего `For...Next` цикла)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|Нет|Да|Нет, так `counter` как уже определено. Если область действия `counter` не является локальной для процедуры, возникает предупреждение во время компиляции.|  
|Нет|Нет|Да. Тип данных выводится из `start`выражений, `end`и `step` . Дополнительные сведения о выводе типа см. в разделе [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [определение локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Да|Да|Да, но только в том случае `counter` , если существующая переменная определена за пределами процедуры. Эта переменная остается отдельной. Если область существующей `counter` переменной является локальной для процедуры, возникает ошибка времени компиляции.|  
|Да|Нет|Да.|  
  
 Тип данных параметра `counter` определяет тип итерации, который должен быть одним из следующих типов:  
  
- A `Byte`, `SByte`, ,`UShort` ,`UInteger`, ,`ULong`,,, или`Single`. `Short` `Integer` `Long` `Decimal` `Double`  
  
- Перечисление, объявляемое с помощью [инструкции enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
- Объект `Object`.  
  
- Тип `T` , имеющий следующие операторы, где `B` — это тип, который `Boolean` можно использовать в выражении.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 При необходимости можно указать `counter` переменную `Next` в инструкции. Этот синтаксис повышает удобочитаемость программы, особенно при наличии вложенных `For` циклов. Необходимо указать переменную, которая отображается в соответствующем `For` операторе.  
  
 Выражения `start`, `end`и `counter`могут иметь любой тип данных, который расширяется до типа. `step` При использовании `counter`определяемого пользователем типа для может потребоваться `CType` определить оператор преобразования `start`для преобразования типов, `end`или `step` в тип `counter`.  
  
## <a name="example"></a>Пример  
 В следующем примере удаляются все элементы из универсального списка. Вместо a [для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md), в примере показано `For`... `Next` инструкция, которая выполняет итерацию в убывающем порядке. В этом примере используется этот метод, `removeAt` поскольку метод заставляет элементы после удаленного элемента иметь меньшее значение индекса.  
  
 [!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]  
  
## <a name="example"></a>Пример  
 В следующем примере перебирается перечисление, объявленное с помощью [инструкции enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]  
  
## <a name="example"></a>Пример  
 В следующем примере параметры инструкции используют класс, который содержит перегрузки `+`операторов для операторов `>=`, `-`, и `<=` .  
  
 [!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic.List%601>
- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Коллекции](../../programming-guide/concepts/collections.md)
