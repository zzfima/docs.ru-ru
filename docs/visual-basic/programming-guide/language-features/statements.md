---
title: Операторы в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
ms.openlocfilehash: 9953fb949c58c074169596dcf48b6df5e7b8f0af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="statements-in-visual-basic"></a>Операторы в Visual Basic
Инструкции в Visual Basic — это полная инструкция. Он может содержать ключевые слова, операторы, переменные, константы и выражения. Каждая инструкция принадлежит к одной из следующих категорий:  
  
-   **Операторы объявления**, который переменную, константу или процедуру, а также можно указать тип данных.  
  
-   **Исполняемые операторы**, запуска действия. Эти операторы могут вызывать метод или функцию, и они могут цикл или ветвь, состоящие из блоков кода. Исполняемые операторы содержат **операторы присваивания**, которые присваивают значение или выражение переменной или константы.  
  
 В этом разделе описана каждая категорий. Кроме того в этом разделе описываются способы объединения нескольких инструкций в одной строке и продолжения инструкции на нескольких строках.  
  
## <a name="declaration-statements"></a>Операторы объявления  
 Инструкции объявления используются для именования и определения процедур, переменных, свойств, массивы и константы. При объявлении элемента программирования можно также определить его тип данных, уровень доступа и область. Дополнительные сведения см. в разделе [характеристики объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
 В следующем примере содержится три объявления.  
  
 [!code-vb[VbVbalrStatements#80](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_1.vb)]  
  
 Первое объявление — `Sub` инструкции. Вместе с соответствующим ему `End Sub` инструкции, объявляет процедуру с именем `applyFormat`. Также указывает, что `applyFormat` — `Public`, что означает, что любой код, который можно ссылаться на него можно вызвать.  
  
 Второе объявление — `Const` оператор, который объявляет константу `limit`, указав `Integer` тип данных и значение 33.  
  
 Третье объявление — `Dim` инструкцию, которая объявляет переменную `thisWidget`. Тип данных — это конкретный объект, а именно: объект создан из `Widget` класса. Можно объявить переменную, чтобы иметь любой простой тип данных или любой тип объекта, который предоставляется в приложение, которое вы используете.  
  
### <a name="initial-values"></a>Начальные значения  
 При выполнении кода, содержащего оператор объявления, Visual Basic резервирует память, требуемую для объявленного элемента. Если элемент содержит значение, Visual Basic инициализирует ее значением по умолчанию для его типа данных. Дополнительные сведения см. в разделе «Поведение» в [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
 Можно назначить начальное значение переменной в рамках его объявления, как показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements#81](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_2.vb)]  
  
 Если переменная является объектной переменной, можно явно создать экземпляр своего класса при ее объявлении с помощью [оператор New](../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово, как приведенный ниже пример иллюстрирует.  
  
 [!code-vb[VbVbalrStatements#82](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_3.vb)]  
  
 Обратите внимание, что начальное значение, указанная в операторе объявления не назначается переменной, пока выполнение не достигнет его оператора объявления. До этого времени переменная содержит значение по умолчанию для своего типа данных.  
  
## <a name="executable-statements"></a>Исполняемые операторы  
 Выполняемая инструкция выполняет действие. Его можно вызвать процедуру, переход в другое место в коде, цикл по нескольким инструкциям или вычислить выражение. Оператор присваивания является особым случаем является исполняемой инструкцией.  
  
 В следующем примере используется `If...Then...Else` управления структурой для выполнения различных блоков кода на основе значения переменной. В каждом блоке кода `For...Next` цикл выполняется заданное число раз.  
  
 [!code-vb[VbVbalrStatements#83](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_4.vb)]  
  
 `If` Инструкции в предыдущем примере проверяет значение параметра `clockwise`. Если значение равно `True`, он вызывает `spinClockwise` метод `aWidget`. Если значение равно `False`, он вызывает `spinCounterClockwise` метод `aWidget`. `If...Then...Else` Заканчивается структуру управления `End If`.  
  
 `For...Next` Цикла в каждом блоке вызывает соответствующий метод определенное количество раз равны значению `revolutions` параметра.  
  
## <a name="assignment-statements"></a>Операторы присваивания  
 Операторы присваивания выполняют операции присваивания, состоящих из принимающий значение справа от оператора присваивания (`=`) и сохранении ее в элемента слева, как показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements#73](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_5.vb)]  
  
 В предыдущем примере оператор присваивания сохраняет значение литерала 42 в переменной `v`.  
  
### <a name="eligible-programming-elements"></a>Допустимые элементы программирования  
 Программный элемент слева от оператора присваивания должен иметь возможность принимать и хранить значение. Это означает, что он должен быть переменная или свойство, которое не является [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), или он должен быть элемент массива. В контексте оператора присваивания такой элемент иногда называется *lvalue*, «левое значение».  
  
 Это значение справа от оператора присваивания формируется с помощью выражения, которое может содержать любое сочетание литералов, константы, переменные, свойства, элементы массива, другие выражения или вызовы функций. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements#74](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_6.vb)]  
  
 Предыдущий пример добавляет значение, содержащееся в переменной `y` на значение, содержащееся в переменной `z`, а затем добавляет значение, возвращаемое при вызове функции `findResult`. Общее значение этого выражения затем сохраняется в переменной `x`.  
  
### <a name="data-types-in-assignment-statements"></a>Типы данных в операторах присваивания  
 Помимо числовых значений, оператор присваивания также может назначать `String` значения, как показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements#75](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_7.vb)]  
  
 Можно также назначить `Boolean` значения, с помощью либо `Boolean` литерала или `Boolean` выражение, как приведенный ниже пример иллюстрирует.  
  
 [!code-vb[VbVbalrStatements#76](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_8.vb)]  
  
 Аналогичным образом можно назначить соответствующие значения элементов программирования из `Char`, `Date`, или `Object` тип данных. Можно также назначить экземпляр объекта для элемента, объявленного в классе, из которого создается этот экземпляр.  
  
### <a name="compound-assignment-statements"></a>Составные операторы присваивания  
 *Составные операторы присваивания* сначала выполняют операцию над выражением перед присваиванием его к программному элементу. В следующем примере показан один из этих операторов `+=`, которая увеличивает значение переменной в левой части оператора по значению выражения справа.  
  
 [!code-vb[VbVbalrStatements#77](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_9.vb)]  
  
 Предыдущий пример добавляет 1 к значению `n`, а затем сохраняет новое значение в `n`. Это краткий эквивалент следующей инструкции:  
  
 [!code-vb[VbVbalrStatements#78](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_10.vb)]  
  
 С помощью операторов этого типа могут выполняться различные операции составного присваивания. Список этих операторов и Дополнительные сведения о них см. в разделе [операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md).  
  
 Оператор объединения и присваивания (`&=`) можно использовать для добавления строки в конец уже существующих строк, как показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements#79](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_11.vb)]  
  
### <a name="type-conversions-in-assignment-statements"></a>Преобразование типов в операторах присваивания  
 Значение, назначенное переменной, свойством или элементом массива должен иметь тип данных, соответствующие конечного элемента. Как правило можно попытаться создать значение того же типа данных, что и у конечного элемента. Тем не менее некоторые типы можно преобразовать в другие типы во время назначения.  
  
 Сведения о преобразовании типов данных см. в разделе [преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md). Вкратце Visual Basic автоматически преобразует значение заданного типа в любой другой тип, к которому он может быть расширен. Объект *расширяющее преобразование* — один в том, что всегда успешно во время выполнения и приводит к потере данных. Например, Visual Basic преобразует `Integer` значение `Double` при необходимости, так как `Integer` расширяется до `Double`. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 *Сужающие преобразования* (те, которые не являются расширяющими) выполняются с риском сбоя во время выполнения или потери данных. Явное сужающее преобразование можно выполнять с помощью функции преобразования типа, или можно направить компилятор неявно выполнять все преобразования, установив `Option Strict Off`. Дополнительные сведения см. в разделе [неявные и явные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## <a name="putting-multiple-statements-on-one-line"></a>Размещение нескольких операторов на одной строке  
 Имеется несколько инструкций в одной строке, разделяя их точкой с запятой (`:`) символов. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements#70](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_12.vb)]  
  
 Иногда и удобно, если бы Эта форма синтаксиса делает код трудно чтение и обслуживание. Таким образом рекомендуется хранить один оператор для строки.  
  
## <a name="continuing-a-statement-over-multiple-lines"></a>Продолжение инструкции на нескольких строках  
 Оператор обычно занимает одну строку, но если он превышает допустимую длину, можно продолжить на следующую строку, используя последовательность продолжения строки, который состоит из пробела и символ подчеркивания (`_`) и символ возврата каретки. В следующем примере `MsgBox` исполняемой инструкцией располагается на двух строках.  
  
 [!code-vb[VbVbalrStatements#71](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_13.vb)]  
  
### <a name="implicit-line-continuation"></a>Неявное продолжение строки  
 Во многих случаях инструкцию можно продолжить на следующей строке без символа подчеркивания (_). В следующей таблице перечислены элементы синтаксиса, которые неявно продолжают инструкцию на следующей строке кода.  
  
|Элемент синтаксиса|Пример|  
|---|---|  
|После запятой (`,`).|[!code-vb[VbVbalrLineContinuation#1](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_14.vb)]|  
|После открывающей скобки (`(`) или перед закрывающей скобкой (`)`).|[!code-vb[VbVbalrLineContinuation#2](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_15.vb)]|  
|После открывающей фигурной скобки (`{`) или перед закрывающей фигурной скобки (`}`).|[!code-vb[VbVbalrLineContinuation#3](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_16.vb)]<br /><br /> Дополнительные сведения см. в разделе [инициализаторы объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) или [инициализаторы](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
|После открытого встроенного выражения (`<%=`) или перед закрытием встроенного выражения (`%>`) в XML-литерал.|[!code-vb[VbVbalrLineContinuation#4](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_17.vb)]<br /><br /> Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
|После оператора объединения (`&`).|[!code-vb[VbVbcnConventions#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_18.vb)]<br /><br /> Дополнительные сведения см. в разделе [операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|После операторов присваивания (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br /><br /> Дополнительные сведения см. в разделе [операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|После бинарных операторов (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) в выражении.|[!code-vb[VbVbalrLineContinuation#7](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_20.vb)]<br /><br /> Дополнительные сведения см. в разделе [операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|После `Is` и `IsNot` операторы.|[!code-vb[VbVbalrLineContinuation#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_21.vb)]<br /><br /> Дополнительные сведения см. в разделе [операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|После знака квалификатора элемента (`.`) и перед именем элемента. Тем не менее, необходимо включить символ продолжения строки (_) после знака квалификатора элемента при использовании `With` инструкции или указании значений в списке инициализации для типа. Попробуйте разорвать строку после оператора назначения (например, `=`) при использовании `With` инструкции или списки инициализации объекта.|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br />[!code-vb[VbVbalrLineContinuation#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_22.vb)]<br /><br /> Дополнительные сведения см. в разделе [с... Завершить с инструкцией](../../../visual-basic/language-reference/statements/with-end-with-statement.md) или [инициализаторах объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).|  
|После описателя свойства оси XML (`.` или `.@` или `...`). Тем не менее, необходимо включить символ продолжения строки (_) при указании квалификатора элемента при использовании `With` ключевое слово.|[!code-vb[VbVbalrLineContinuation#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_23.vb)]<br /><br /> Дополнительные сведения см. в разделе [свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).|  
|После меньше-символ «больше» (<) или до больше-знак "больше" (`>`) при указании атрибута. Также после-знак "больше" (`>`) при указании атрибута. Тем не менее необходимо включить символ продолжения строки (_), при указании атрибуты уровня сборки или уровня модуля.|[!code-vb[VbVbalrLineContinuation#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_24.vb)]<br /><br /> Дополнительные сведения см. в разделе [Общие сведения об атрибутах](../../../visual-basic/programming-guide/concepts/attributes/index.md).|  
|До и после операторов запроса (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, и `Descending`). Невозможно разделить одну строку между ключевыми словами операторов запросов, состоящих из нескольких ключевых слов (`Order By`, `Group Join`, `Take While`, и `Skip While`).|[!code-vb[VbVbalrLineContinuation#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_25.vb)]<br /><br /> Дополнительные сведения см. в разделе [запросы](../../../visual-basic/language-reference/queries/queries.md).|  
|После `In` ключевое слово в `For Each` инструкции.|[!code-vb[VbVbalrLineContinuation#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_26.vb)]<br /><br /> Дополнительные сведения см. в разделе [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).|  
|После `From` ключевое слово в инициализаторе коллекции.|[!code-vb[VbVbalrLineContinuation#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_27.vb)]<br /><br /> Дополнительные сведения см. в разделе [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
  
## <a name="adding-comments"></a>Добавление комментариев  
 Исходный код не всегда очевидно, даже для программиста, который его создал. Для документирования кода таким образом, большинство программистов использует комментарии. Комментарии в коде можно описать процедуру или определенную инструкцию для тех, кто будет работать с ним в дальнейшем. Visual Basic игнорирует комментарии во время компиляции, и они не влияют на скомпилированный код.  
  
 Строки комментариев начинаются с апострофа (`'`) или `REM` пробел. Могут быть добавлены в любом месте в коде, за исключением того, в строке. Для добавления комментария в инструкцию вставьте апостроф или `REM` после инструкции, следуют комментарий. Комментарии можно также перейти на отдельной строке. В следующем примере показаны эти возможности.  
  
 [!code-vb[VbVbalrStatements#72](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_28.vb)]  
  
## <a name="checking-compilation-errors"></a>Проверка ошибок компиляции  
 Если после ввода строки кода, строка отображается синей волнистой (сообщение об ошибке также может быть выведено), имеется синтаксическая ошибка в инструкции. Необходимо определить, что ошибка инструкции (путем поиска в списке задач или наведении указателя мыши на ошибку с курсором и чтения сообщение об ошибке) и исправить ее. До устранения всех синтаксических ошибок в коде программы будет давать сбой при компиляции.  
  
## <a name="related-sections"></a>Связанные разделы  
  
|Термин|Определение|  
|---|---|  
|[Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)|Содержит ссылки на разделы справочника по языку охватывающие операторы присваивания, такие как `=`, `*=`, и `&=`.|  
|[Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)|Показывает способ совместного использования элементов и операторов для получения новых значений.|  
|[Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Показывает, как разбить один оператор на несколько строк и как разместить несколько операторов в одной строке.|  
|[Практическое руководство. Операторы меток](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Показано, как пометить строку кода.|
