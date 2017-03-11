---
title: "Оператор For... Next (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Step"
  - "vb.Next"
  - "vb.To"
  - "vb.for"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "бесконечные циклы"
  - "ключевое слово Next, операторы For...Next"
  - "ключевое слово For [Visual Basic], операторы For...Next"
  - "ключевое слово Step, операторы For...Next"
  - "перегрузка операторов, операторы For...Next"
  - "ключевое слово To, операторы For...Next"
  - "бесконечные циклы"
  - "циклы, бесконечные"
  - "инструкции, повтор"
  - "оператор Next, For...Next"
  - "For...Next - операторы"
  - "циклические структуры, For...Next"
  - "циклы, бесконечные"
  - "оператор Exit, операторы For...Next"
  - "For - оператор"
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
caps.latest.revision: 64
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 64
---
# Оператор For... Next (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Повторяет группу операторов заданное количество раз.  
  
## Синтаксис  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## Части  
  
|Часть|Описание|  
|-----------|--------------|  
|`counter`|Требуется в операторе `For`.  Числовая переменная.  Управляющая переменная цикла.  Дополнительные сведения см. в подразделе [Аргумент счетчика](#BKMK_Counter) далее в этом разделе.|  
|`datatype`|Необязательный параметр.  Тип данных `counter`.   Дополнительные сведения см. в подразделе [Аргумент счетчика](#BKMK_Counter) далее в этом разделе.|  
|`start`|Обязательное.  Числовое выражение.  Начальное значение `counter`.|  
|`end`|Обязательное.  Числовое выражение.  Конечное значение `counter`.|  
|`step`|Необязательный параметр.  Числовое выражение.  Шаг, с которым `counter` увеличивается при каждом прохождении цикла.|  
|`statements`|Необязательный параметр.  Одно или несколько выражений между `For` и `Next`, выполняемых указанное число раз.|  
|`Continue For`|Необязательный параметр.  Передает управление следующей итерации цикла.|  
|`Exit For`|Необязательный параметр.  Передает управление из цикла `For`.|  
|`Next`|Обязательное.  Завершает определение цикла `For`.|  
  
> [!NOTE]
>  Ключевое слово `To` используется в эту инструкцию для определения диапазона счетчика.  Можно также использовать ключевое слово в [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md) и в объявлении массива.  Дополнительные сведения об объявлениях массивов см. в разделе [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## Простые примеры  
 Используется структура `For`…`Next`, когда требуется выполнить набор выписок задать количество раз.  
  
 В следующем примере запускается приложение переменной `index` со значением 1 и инкрементированы с каждой итерацией цикла, конечный после значение `index` достигает 5.  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_1.vb)]  
  
 В следующем примере запускается приложение переменной `number` уменьшается на 2 и 0,25 для каждой итерации цикла, конечный после значение `number` достигает 0.  Аргумент `Step``-.25` уменьшает значение 0,25 для каждой итерации цикла.  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) или [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md) хорошо работают при неизвестен заранее раз щелкните выписки в цикле.  Однако, если предполагается повторить цикл определенное число раз, то лучше использовать цикл `For`...`Next`.  Число итераций определяется при первом входе в цикл.  
  
## Вложенные циклы.  
 Циклы `For` могут вкладываться друг в друга.  В следующем примере демонстрируются вложенные структуры `For`...`Next` с разными значениями шага.  Внешний цикл создает строку для каждой итерации цикла.  Внутренний цикл уменьшает переменную счетчика цикла с каждой итерацией цикла.  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_3.vb)]  
  
 Если циклы вложения, каждый цикл должны иметь уникальный переменную `counter`.  
  
 Также можно вложить друг в друга различные виды управляющих структур.  Для получения дополнительной информации см. [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## Оставьте для; для  
 Выписка `Exit For` сразу отобразится цикл `For`…`Next` и управление передач на инструкцию, которая следует за выписка `Next`.  
  
 Оператор `Continue For` передает управление непосредственно следующей итерации цикла.  Для получения дополнительной информации см. [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 В следующем примере показано использование оператора `Continue For` и `Exit For`.  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_4.vb)]  
  
 Любое число операторов `Exit For` можно разместить в цикле `For`…`Next`.  При использовании вложенных циклов `For`…`Next` конструкция `Exit For` закрывает самый внутренний цикл и передает управление следующему уровню вложения.  
  
 `Exit For` часто используется после оценке некоторое условие \(например, в структуре `If`…`Then`…`Else` \).  Можно использовать `Exit For` при следующих условиях:  
  
-   Продолжать выполнение итераций не нужно или невозможно.  Ошибочное значение или завершения запроса можно создать это условие.  
  
-   Выписка `Try`…`Catch`…`Finally` перехватывает исключение.  Можно использовать `Exit For` в конце блока `Finally`.  
  
-   Имеется бесконечный цикл, цикл, может выполнять большой или даже бесконечный количество раз.  При обнаружении таких условий для выхода из цикла можно использовать `Exit For`.  Дополнительные сведения см. в разделе [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## Техническая реализация  
 При начале цикла `For`...`Next` Visual Basic оценивает `start`, `end` и `step`.  Visual Basic возвращает эти значения только в настоящее время, а затем присвоить `start` на `counter`.  Прежде чем блок выписки выполняется Visual Basic сравниваются `counter` значение `end`.  Если `counter` уже больше, чем значение `end` \(или `step` \), если небольшое отрицательное, цикл `For` для выполнения и передаче элемента управления инструкцию, которая следует за выписка `Next`.  В противном случае выполняется блока выписки.  
  
 Каждый раз при обнаружении оператора `Next` Visual Basic увеличивает `counter` на `step` и возвращается к оператору `For`.  После этого сравниваются `counter` и `end`, и в зависимости от результата происходит либо выполнение блока, либо выход из цикла.  Этот процесс продолжается до тех пор, пока `counter` не превысит `end`, или не встретится оператор `Exit For`.  
  
 Цикл не останавливается до тех пор, пока `counter` не будет передачи `end`.  Если `counter` равен `end`, то цикл продолжается.  Сравнением, определяющим, следует ли выполнять блок, является `counter` \<\= `end` для положительного `step` и `counter` \>\= `end` для отрицательного `step`.  
  
 При изменении значения `counter`, внутри цикла, код может быть сложнее для чтения и отладки.  Изменение значения `start`, `end` или `step` не влияют на значения, которые были определены при итерации цикла сначала был введен.  
  
 Если вы поместите циклы, компилятор сигнализирует об ошибке при обнаружении выписка `Next` внешнего уровень вложенности перед выпиской `Next` внутреннего уровня.  При этом компилятор может обнаружить эту ошибку перекрывания только в том случае, если в каждой инструкции `Next` задан `counter`.  
  
### Аргумент шага  
 Значение `step` может быть либо положительным, либо отрицательным.  Этот параметр задает цикл обработки согласно следующей таблице.  
  
|**Значение шага**|**Цикл выполняется, если**|  
|-----------------------|--------------------------------|  
|Положительное или нулевое|`counter` \<\= `end`|  
|Отрицательное число|`counter` \>\= `end`|  
  
 Значение по умолчанию для типа `step` равно 1.  
  
###  <a name="BKMK_Counter"></a> Аргумент счетчика  
 В следующей таблице показаны определяет, является ли `counter` новую локальную переменную, которая относится ко всему циклу `For…Next`.  Это определение зависит от наличия `datatype` и `counter`, определено ли уже.  
  
|У `datatype` ?|`counter` уже определено?|Результат \(определяет, является ли `counter` новую локальную переменную, которая относится ко всему цикл `For...Next` \)|  
|--------------------|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------|  
|Нет|Да|Нет, поскольку класс `counter` уже задано.  Если область `counter` не является в процедуру, возникает предупреждение во время компиляции.|  
|Нет|Нет|Да.  Тип данных выводится из `start`, `end`, `step` и выражений.  Дополнительные сведения об определении типа см. в разделах [Option Infer \- оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Да|Да|Да, но только если существующей переменной `counter` определяется вне процедуры.  Эта переменная остается отдельно.  Если область существующей локальной переменной `counter` в процедуре, происходит ошибка времени компиляции.|  
|Да|Нет|Да.|  
  
 Тип данных `counter` указывает тип итерации, которая должна быть одним из следующих типов:  
  
-   `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single` или `Double`.  
  
-   Перечисление объявляется с использованием [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
-   Объект `Object`.  
  
-   Тип `T`, имеющий следующие операторы, где тип, который может использоваться в выражении`Boolean` — `B` .  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 При необходимости можно определить переменную `counter` в инструкцию `Next`.  Этот синтаксис повышает удобочитаемость программы, особенно если количеством вложенных циклов `For`.  Необходимо указать переменную, которая отображается в соответствующем оператора `For`.  
  
 Выражения `start`, `end` и `step` могут быть приведены к любому большему по разрядности типу, чем тип `counter`.  Если используется пользовательский тип для `counter`, укажите оператор преобразования `CType` для преобразования типов `start`, `end` или `step` в тип `counter`.  
  
## Пример  
 В следующем примере показано удаление всех элементов из универсального списка.  Вместо [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md), пример показывает оператора `For`…`Next`, выполняются в порядке убывания.  В примере этот метод используется, поскольку метод `removeAt` приводит к созданию элементов после удаленного элемента имеет меньшее значение индекса.  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_5.vb)]  
  
## Пример  
 Следующий пример выполняет цикл по перечисление, объявлено с помощью [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_6.vb)]  
  
## Пример  
 В следующем примере параметры оператора используют класс, имеющий перегрузки оператора для `+` `-`, `>=`и `<=` операторов.  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_7.vb)]  
  
## См. также  
 <xref:System.Collections.Generic.List%601>   
 [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Коллекции](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)