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
ms.openlocfilehash: 8c54189499b7d5b52cf93b4a0ae6cc47356bf57e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605333"
---
# <a name="fornext-statement-visual-basic"></a>Оператор For... Next (Visual Basic)
Повторяет группу операторов заданное число раз.  
  
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
|`counter`|Требуется в `For` инструкции. Числовой переменной. Управляющая переменная цикла for. Дополнительные сведения см. в разделе [аргумент счетчика](#BKMK_Counter) далее в этом разделе.|  
|`datatype`|Необязательный. Тип данных `counter`. Дополнительные сведения см. в разделе [аргумент счетчика](#BKMK_Counter) далее в этом разделе.|  
|`start`|Обязательно. Числовое выражение. Начальное значение `counter`.|  
|`end`|Обязательно. Числовое выражение. Конечное значение `counter`.|  
|`step`|Необязательный. Числовое выражение. Величина, на которую `counter` увеличивается при каждом прохождении цикла.|  
|`statements`|Необязательный. Один или несколько операторов между `For` и `Next` , выполняемых указанное число раз.|  
|`Continue For`|Необязательный. Передает управление следующей итерации цикла.|  
|`Exit For`|Необязательный. Передает управление из `For` цикла.|  
|`Next`|Обязательно. Завершает определение `For` цикла.|  
  
> [!NOTE]
>  `To` В этом операторе используется ключевое слово для указания диапазона для счетчика. Можно также использовать это ключевое слово в [выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md) и в объявлении массива. Дополнительные сведения об объявлениях массивов см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="simple-examples"></a>Простые примеры  
 Вы используете `For`... `Next` структуры, если вы хотите повторить набор инструкций заданное количество раз.  
  
 В следующем примере `index` переменной начинается со значения 1 и увеличивается при каждой итерации цикла, заканчивается после изменения значения `index` достигает 5.  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 В следующем примере `number` переменной начинается с позиции 2 и уменьшается на 0,25 на каждой итерации цикла, заканчивается после изменения значения `number` становится равным нулю. `Step` Аргумент `-.25` уменьшает значение 0,25 на каждой итерации цикла.  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  Объект [во время... Завершить оператор While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) или [сделать... Оператор цикла](../../../visual-basic/language-reference/statements/do-loop-statement.md) работает хорошо, если не известен заранее сколько раз, чтобы выполнить инструкции в цикле. Тем не менее, если предполагается, что для запуска цикла определенное количество раз, `For`... `Next` цикла является лучшим выбором. Определите количество итераций, при вводе цикла.  
  
## <a name="nesting-loops"></a>Вложенные циклы  
 Можно вложить `For` циклы, поместив цикл один в другой. В следующем примере демонстрируется вложенных `For`... `Next` структуры с различными значениями. Внешний цикл создает строку для каждой итерации цикла. Внутренний цикл уменьшает переменную счетчика цикла для каждой итерации цикла.  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 При наличии вложенных циклов, каждый цикл должен иметь уникальный `counter` переменной.  
  
 Также можно вложить структур управления различных типов друг в друге. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Для выхода и для продолжения  
 `Exit For` Инструкция немедленно завершает работу `For`...`Next` цикл передает управление оператору, следующему `Next` инструкции.  
  
 `Continue For` Оператор передачу управления сразу же к следующей итерации цикла. Дополнительные сведения см. в разделе [оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Следующий пример иллюстрирует использование `Continue For` и `Exit For` инструкции.  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 Можно поместить любое число `Exit For` инструкций в `For`...`Next` Цикл. При использовании внутри вложенной `For`...`Next` циклы, `Exit For` выходит из самого внутреннего цикла и передает управление верхнего уровня вложенности.  
  
 `Exit For` часто используется после оценки некоторого условия (например, в `If`... `Then`... `Else` структуры). Вы можете использовать `Exit For` для следующих условий:  
  
-   Продолжение для выполнения итерации ненужные или невозможно. Ошибочное значение или запрос на завершение может создать это условие.  
  
-   Объект `Try`... `Catch`... `Finally` инструкция перехватывает исключение. Можно использовать `Exit For` в конце `Finally` блока.  
  
-   У вас есть бесконечный цикл, являющийся цикл, который может запустить большое или возможно, бесконечное число раз. При обнаружении таких условий, можно использовать `Exit For` для выхода из цикла. Дополнительные сведения см. в разделе [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="technical-implementation"></a>Техническая реализация  
 Когда `For`... `Next` начинает цикл, Visual Basic вычисляет `start`, `end`, и `step`. Visual Basic вычисляет эти значения только в это время, а затем назначает `start` для `counter`. Перед оператором блок выполняется, Visual Basic сравнивает `counter` для `end`. Если `counter` уже больше, чем `end` значение (или меньше, если `step` является отрицательным), `For` завершения цикла и управление передается оператору, следующему `Next` инструкции. В противном случае выполняется блок операторов.  
  
 При каждом запуске Visual Basic встречает `Next` инструкция, он увеличивает `counter` по `step` и возвращает `For` инструкции. После этого сравниваются `counter` для `end`, и еще раз она выполняется блок или выходит из цикла, в зависимости от результата. Этот процесс продолжается до `counter` передает `end` или `Exit For` инструкции.  
  
 Цикл не останавливается до `counter` достиг `end`. Если `counter` равен `end`, выполнение цикла продолжается. Сравнение, которое определяет, будет ли выполняться блок является `counter`  <=  `end` Если `step` является положительным и `counter`  >=  `end` Если `step` является отрицательным значением.  
  
 Если изменить значение `counter` внутри цикла, может быть более сложным для чтения и отладки кода. Изменение значения `start`, `end`, или `step` не влияет на значения итерации, которые были определены при первом входе цикла.  
  
 Если вложить циклы, компилятор сообщает об ошибке при обнаружении `Next` инструкции внешнего уровня вложенности перед `Next` инструкции внутреннего уровня. Однако компилятор может обнаружить это перекрывающихся ошибки только в том случае, если указать `counter` в каждом `Next` инструкции.  
  
### <a name="step-argument"></a>Аргумент шаг  
 Значение `step` может быть положительными или отрицательными. Этот параметр определяет цикла обработки согласно следующей таблице:  
  
|**Значение шага**|**Цикл выполняется, если**|  
|--------------------|--------------------------|  
|Положительным или равняться нулю|`counter` <= `end`|  
|Отрицательное число|`counter` >= `end`|  
  
 Значение по умолчанию `step` -1.  
  
###  <a name="BKMK_Counter"></a> Аргумент счетчика  
 Следующая таблица показывает, является ли `counter` определяет новую локальную переменную, которая предназначена для всего `For…Next` цикла. Это решение зависит от того `datatype` присутствует и ли `counter` уже определен.  
  
|— `datatype` Присутствует?|— `counter` Уже определен?|Результат (ли `counter` определяет новую локальную переменную, которая предназначена для всего `For...Next` цикла)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|Нет|Да|Нет, поскольку `counter` уже определен. Если область `counter` не локальными в пределах процедуры возникает предупреждение во время компиляции.|  
|Нет|Нет|Да. Тип данных выводится из `start`, `end`, и `step` выражения. Сведения о вывод типа, в разделе [Option Infer-оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Да|Да|Да, но только если существующий `counter` определена переменная вне процедуры. Остается этой переменной. Если область существующего `counter` переменная является локальной для процедуры, то возникает ошибка времени компиляции.|  
|Да|Нет|Да.|  
  
 Тип данных `counter` определяет тип итерации, который должен быть одним из следующих типов:  
  
-   Объект `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, или `Double`.  
  
-   Перечисление, которое объявляется с помощью [оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
-   Объект `Object`.  
  
-   Тип `T` , имеет следующие операторы, где `B` — это тип, который может использоваться в `Boolean` выражение.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 Дополнительно можно указать `counter` переменных в `Next` инструкции. Этот синтаксис повышает удобочитаемость программы, особенно в том случае, если имеются вложенные `For` циклы. Необходимо указать переменную, которая отображается в соответствующем `For` инструкции.  
  
 `start`, `end`, И `step` вычисленные выражений могут иметь любой тип данных, который расширяется до типа `counter`. При использовании определяемых пользователем типов для `counter`, возможно, потребуется определить `CType` оператор преобразования типов `start`, `end`, или `step` типу `counter`.  
  
## <a name="example"></a>Пример  
 Следующий пример удаляет все элементы из универсального списка. Вместо [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md), показано в примере `For`... `Next` , выполняющий перебор в порядке убывания. В примере используется этот способ, поскольку `removeAt` метод вызывает элементов после удаляемым иметь меньшее значение индекса.  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример перебор элементов перечисления, который объявлен с помощью [оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере параметры инструкции используйте класс, имеющий перегрузки операторов для `+`, `-`, `>=`, и `<=` операторы.  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic.List%601>  
 [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Коллекции](../../programming-guide/concepts/collections.md)
