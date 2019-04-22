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
ms.openlocfilehash: 5d47d57b75005d5c13dbf8633981dfb2d57d3e90
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826331"
---
# <a name="fornext-statement-visual-basic"></a>Оператор For... Next (Visual Basic)
Повторяет блок операторов указанное число раз.  
  
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
|`counter`|Требуется в `For` инструкции. Числовой переменной. Переменная управления циклом for. Дополнительные сведения см. в разделе [встречный аргумент](#BKMK_Counter) далее в этом разделе.|  
|`datatype`|Необязательный параметр. Тип данных `counter`. Дополнительные сведения см. в разделе [встречный аргумент](#BKMK_Counter) далее в этом разделе.|  
|`start`|Обязательный. Числовое выражение. Начальное значение `counter`.|  
|`end`|Обязательный. Числовое выражение. Конечное значение `counter`.|  
|`step`|Необязательный параметр. Числовое выражение. Величина, на которую `counter` увеличивается при каждом повторении цикла.|  
|`statements`|Необязательный параметр. Один или несколько операторов между `For` и `Next` под управлением указанное число раз.|  
|`Continue For`|Необязательный параметр. Передает управление следующей итерации цикла.|  
|`Exit For`|Необязательный параметр. Передает управление из `For` цикла.|  
|`Next`|Обязательный. Завершает определение `For` цикла.|  
  
> [!NOTE]
>  `To` Ключевое слово используется в этой инструкции для указания диапазона для счетчика. Можно также использовать это ключевое слово в [выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md) и в объявлении массива. Дополнительные сведения об объявлениях массивов см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="simple-examples"></a>Простые примеры  
 Использовании `For`... `Next` структуры, когда нужно повторить набор инструкций set несколько раз.  
  
 В следующем примере `index` переменной начинается со значения 1 и увеличивается при каждой итерации цикла, заканчивается после значение `index` достигает 5.  
  
 [!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]  
  
 В следующем примере `number` переменной начинается с 2 и уменьшается на 0,25 на каждой итерации цикла, заканчивается после значение `number` становится равным нулю. `Step` Аргумент `-.25` уменьшает значение, 0,25 на каждой итерации цикла.  
  
 [!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]  
  
> [!TIP]
>  Объект [хотя... Завершить оператор While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) или [сделать... Оператор цикла](../../../visual-basic/language-reference/statements/do-loop-statement.md) работает хорошо, если не известно заранее сколько раз следует выполнить инструкции в цикле. Тем не менее, если предполагается, что для выполнения цикла определенное количество раз, `For`... `Next` цикла является лучшим выбором. При первом входе в цикл, определите количество итераций.  
  
## <a name="nesting-loops"></a>Вложенные циклы  
 Можно вложить `For` циклы, поместив в одном цикле в другую. В следующем примере демонстрируется вложенных `For`... `Next` структуры с разными значениями шага. Внешний цикл создает строку для каждой итерации цикла. Внутренний цикл уменьшает переменную счетчика цикла для каждой итерации цикла.  
  
 [!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]  
  
 При наличии вложенных циклов, каждый цикл должен иметь уникальный `counter` переменной.  
  
 Можно также вложить структур управления различных типов в друг с другом. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Возврата для и продолжите для  
 `Exit For` Инструкция немедленно завершает работу `For`...`Next` цикл передает управление оператору, который расположен `Next` инструкции.  
  
 `Continue For` Оператор передает управление непосредственно в следующую итерацию цикла. Дополнительные сведения см. в разделе [оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Следующий пример иллюстрирует использование `Continue For` и `Exit For` инструкций.  
  
 [!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]  
  
 Можно поместить любое количество `Exit For` инструкций в `For`...`Next` Цикл. При использовании внутри вложенной `For`...`Next` циклы, `Exit For` выходит из самого внутреннего цикла и передает управление повысить уровень вложенности.  
  
 `Exit For` часто используется после оценки некоторого условия (например, в `If`... `Then`... `Else` структуры). Вы можете использовать `Exit For` для следующих условий:  
  
-   Продолжение для выполнения итерации, ненужных или невозможно. Ошибочное значение или запрос на завершение может создать это условие.  
  
-   Объект `Try`... `Catch`... `Finally` инструкция перехватывает исключение. Можно использовать `Exit For` в конце `Finally` блока.  
  
-   У вас есть бесконечный цикл, который является цикл, который может запустить большое или возможно, бесконечное число раз. При обнаружении таких условий, можно использовать `Exit For` для выхода из цикла. Дополнительные сведения см. в разделе [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="technical-implementation"></a>Техническая реализация  
 Когда `For`... `Next` начале цикла, Visual Basic вычисляет `start`, `end`, и `step`. Visual Basic вычисляет эти значения только в это время, а затем назначает `start` для `counter`. Перед оператором блок выполняется, Visual Basic сравнивает `counter` для `end`. Если `counter` уже больше, чем `end` значение (или меньшего размера, если `step` отрицательное), `For` завершения цикла и управление передается оператору, который расположен `Next` инструкции. В противном случае выполняется блок операторов.  
  
 При каждом запуске Visual Basic встречает `Next` инструкция, он увеличивает `counter` по `step` и возвращает `For` инструкции. После этого сравниваются `counter` для `end`, и еще раз она выполняется блок или выходит из цикла, в зависимости от результата. Этот процесс продолжается до `counter` передает `end` или `Exit For` встречается.  
  
 Цикл не останавливается до `counter` достиг `end`. Если `counter` равен `end`, цикл продолжается. Сравнение, которое определяет, следует ли выполнять блок является `counter`  <=  `end` Если `step` положительно и `counter`  >=  `end` Если `step` является отрицательным.  
  
 Если изменить значение `counter` во время в цикле, ваш код может быть более сложным для чтения и отладки. Изменение значения `start`, `end`, или `step` не влияет на значения итерации, которые были определены при цикла.  
  
 Если вы вкладывать циклы, компилятор сообщает об ошибке при обнаружении `Next` инструкции внешнего уровня вложенности перед `Next` инструкции внутреннего уровня. Тем не менее, компилятор может определить, это перекрытие ошибки только в том случае, если указать `counter` в каждом `Next` инструкции.  
  
### <a name="step-argument"></a>Аргумент шаг  
 Значение `step` может быть положительным или отрицательным. Этот параметр определяет цикл обработки согласно следующей таблице:  
  
|**Значение шага**|**Цикл выполняется, если**|  
|--------------------|--------------------------|  
|Положительным или нулем|`counter` <= `end`|  
|Отрицательное число|`counter` >= `end`|  
  
 Значение по умолчанию `step` -1.  
  
### <a name="BKMK_Counter"></a> Встречный аргумент  
 В следующей таблице перечислены ли `counter` определяет новую локальную переменную, которая предназначена для всего `For…Next` цикла. Это определение зависит от того `datatype` присутствует и был ли `counter` уже определен.  
  
|Является `datatype` присутствует?|Является `counter` уже определен?|Результат (ли `counter` определяет новую локальную переменную, которая предназначена для всего `For...Next` цикла)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|Нет|Да|Нет, так как `counter` уже определен. Если область `counter` не является локальным для процедуры, возникает предупреждение во время компиляции.|  
|Нет|Нет|Да. Тип данных выводится из `start`, `end`, и `step` выражения. Сведения о выводе типа см. в разделе [оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Да|Да|Да, но только если существующий `counter` переменная определена вне процедуры. Остается этой переменной. Если область существующего `counter` переменная является локальной для процедуры, то возникает ошибка времени компиляции.|  
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
  
 При необходимости можно указать `counter` переменных в `Next` инструкции. Этот синтаксис повышает удобочитаемость программы, особенно в том случае, если имеются вложенные `For` циклы. Необходимо указать переменную, которая отображается в соответствующем `For` инструкции.  
  
 `start`, `end`, И `step` выражения могут иметь любой тип данных, который расширяется до типа `counter`. Если вы используете определяемого пользователем типа для `counter`, может потребоваться определить `CType` оператор преобразования типов `start`, `end`, или `step` типу `counter`.  
  
## <a name="example"></a>Пример  
 Следующий пример удаляет все элементы из универсального списка. Вместо [для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md), показано в примере `For`... `Next` , выполняющий перебор в порядке убывания. В примере используется этот способ, поскольку `removeAt` метод вызывает элементов после удаленным элементом, получают меньшее значение индекса.  
  
 [!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример проходит через перечисления, объявленный с помощью [оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]  
  
## <a name="example"></a>Пример  
 В следующем примере параметры инструкции использовать класс, который имеет перегрузки операторов для `+`, `-`, `>=`, и `<=` операторы.  
  
 [!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic.List%601>
- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Коллекции](../../programming-guide/concepts/collections.md)
