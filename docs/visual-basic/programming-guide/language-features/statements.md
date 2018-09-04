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
ms.openlocfilehash: e66acae5e98d561883f4ad59853dfd862c8ebfee
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506294"
---
# <a name="statements-in-visual-basic"></a>Операторы в Visual Basic

Оператор в Visual Basic — это полная инструкция. Он может содержать ключевые слова, операторы, переменные, константы и выражения. Каждая инструкция принадлежит к одной из следующих категорий:

- **Операторы объявления**, который переменную, константу или процедуру, а также можно указать тип данных.

- **Исполняемые операторы**, запуска действия. Эти инструкции можно вызвать метод или функция, и они могут цикл или ветвь, состоящие из блоков кода. Исполняемые операторы содержат **операторы присваивания**, которые присваивают значение или выражение переменной или константы.

В этом разделе описывается каждой категории. Кроме того в этом разделе описывается, как объединить несколько операторов в одной строке и дальнейшие инструкции на нескольких строках.

## <a name="declaration-statements"></a>Операторы объявления

Используйте операторы объявления для именования и определения процедур, переменных, свойства, массивов и констант. При объявлении элемента программирования, можно также определить его тип данных, уровень доступа и область. Дополнительные сведения см. в разделе [характеристики объявленных элементов](./declared-elements/declared-element-characteristics.md).

В следующем примере содержится три объявления.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

Первое объявление — `Sub` инструкции. Вместе с соответствующим ему `End Sub` оператор, он объявляет процедуру с именем `applyFormat`. Он также указывает, что `applyFormat` является `Public`, означающее, что его можно вызвать любой код, который могут ссылаться на нее.

Второе объявление — `Const` инструкцию, которая объявляет константу `limit`, указав `Integer` тип данных и значение 33.

Третье объявление — `Dim` инструкцию, которая объявляет переменную `thisWidget`. Тип данных — это конкретный объект, а именно объект создан из `Widget` класса. Можно объявить переменную любой простой тип данных или любого типа объекта, который предоставляется в приложении, которое вы используете.

### <a name="initial-values"></a>Начальные значения

При выполнении кода, содержащего оператор объявления, Visual Basic резервирует память, необходимую для объявленного элемента. Если элемент содержит значение, Visual Basic инициализирует его значением по умолчанию для типа данных. Дополнительные сведения см. в разделе «Поведение» в [оператор Dim](../../language-reference/statements/dim-statement.md).

Можно назначить начальное значение переменной как часть ее объявлении, как показано в следующем примере.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Если переменная является объектной переменной, можно явно создать экземпляр своего класса, при объявлении с помощью [оператор New](../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово, как показано следующем примере.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Обратите внимание на то, что начальное значение, указываемое в операторе объявления не назначен переменной, пока выполнение не достигнет его оператора объявления. До этого времени переменная содержит значение по умолчанию для типа данных.

## <a name="executable-statements"></a>Исполняемые операторы

Выполняемая инструкция выполняет действие. Его можно вызвать процедуру, переход в другое место в коде, цикл через несколько операторов, или вычислить это выражение. Оператор присваивания является особым случаем исполняемого оператора.

В следующем примере используется `If...Then...Else` управления структурой для выполнения различных блоков кода в зависимости от значения переменной. В каждом блоке кода `For...Next` цикл выполняется заданное число раз.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

`If` Инструкции в предыдущем примере проверяет значение параметра `clockwise`. Если значение равно `True`, он вызывает `spinClockwise` метод `aWidget`. Если значение равно `False`, он вызывает `spinCounterClockwise` метод `aWidget`. `If...Then...Else` Заканчивается структуру управления `End If`.

`For...Next` Цикла в каждом блоке вызывает соответствующий метод несколько раз, равное значению `revolutions` параметра.

## <a name="assignment-statements"></a>Операторы присваивания

Операторы присваивания выполняют операции присваивания, состоящих старта значение правой части оператора присваивания (`=`) и сохранив его в элемент слева, как показано в следующем примере.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

В предыдущем примере, оператор присваивания сохраняет значение литерала 42 в переменной `v`.

### <a name="eligible-programming-elements"></a>Соответствующие элементы программирования

Программный элемент слева от оператора присваивания, должно иметь возможность принять и сохранить значение. Это означает, что он должен быть переменной или свойства, не [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), или он должен быть элемент массива. В контексте оператора присваивания, иногда называется такой элемент *lvalue*, «левое значение».

Значение справа от оператора присваивания, создается с помощью выражения, которое может содержать любое сочетание литералы, константы, переменные, свойства, элементы массива, другие выражения или вызовы функций. Это показано в следующем примере.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

В предыдущем примере добавляется на значение, содержащееся в переменной `y` со значением в переменной `z`и затем добавляет значение, возвращаемое вызовом функции `findResult`. Общее значение этого выражения затем сохраняется в переменной `x`.

### <a name="data-types-in-assignment-statements"></a>Типы данных в операторах присваивания

Помимо числовых значений можно также назначить оператор присваивания `String` значения, как показано в следующем примере.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

Можно также назначить `Boolean` значения, с помощью либо `Boolean` литерал или `Boolean` выражение, как приведенный ниже пример иллюстрирует.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Аналогичным образом, можно назначить соответствующие значения для элементов программирования из `Char`, `Date`, или `Object` тип данных. Кроме того, экземпляр объекта можно назначить элемент, объявленный в классе, из которого создается этот экземпляр.

### <a name="compound-assignment-statements"></a>Составные операторы присваивания

*Составные операторы присваивания* сначала выполняют операцию над выражения перед назначением его к программному элементу. В следующем примере демонстрируется один из этих операторов `+=`, которая увеличивает значение переменной в левой части оператора значение выражения в правой части.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

Предыдущий пример добавляет 1 к значению `n`, а затем сохраняет новое значение в `n`. Это краткий эквивалент следующего оператора:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

Использование операторов этого типа могут выполняться различные операции составного присваивания. Список этих операторов и Дополнительные сведения о них, см. в разделе [операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md).

Оператор объединения и присваивания (`&=`) можно использовать для добавления строки в конец уже существующих строк, как показано в следующем примере.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Преобразования типов в операторах присваивания

Значение, назначенное переменной, свойства или элемента массива должно иметь тип данных конечного элемента. В общем случае следует попытаться создать значение одного типа данных, что и у конечного элемента. Тем не менее некоторые типы могут преобразовываться в другие типы во время назначения.

Сведения о преобразовании типов данных, см. в разделе [преобразования типов в Visual Basic](./data-types/type-conversions.md). В двух словах Visual Basic автоматически преобразует значение заданного типа в любой другой тип, к которому он может быть расширен. Объект *расширяющее преобразование* — один, всегда является успешным во время выполнения и приводит к потере данных. Например, Visual Basic преобразует `Integer` значение `Double` при необходимости, так как `Integer` можно расширить до `Double`. Для получения дополнительной информации см. [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

*Сужающие преобразования* (те, которые не являются расширяющими) выполняются с риском сбоя во время выполнения или потери данных. Явное сужающее преобразование можно выполнять с помощью функции преобразования типа, или можно направить компилятор неявно выполнять все преобразования, задав `Option Strict Off`. Дополнительные сведения см. в разделе [явные и неявные преобразования](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Размещение нескольких операторов на одной строке

Можно использовать несколько операторов в одной строке, разделяя их точкой с запятой (`:`) символов. Это показано в следующем примере.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Хотя иногда и удобно, эта форма синтаксиса делает код сложно читать и обслуживать. Таким образом рекомендуется хранить один оператор для строки.

## <a name="continuing-a-statement-over-multiple-lines"></a>Продолжение инструкции на нескольких строках

Инструкция обычно занимает на одной строке, но если она слишком велика, продолжить его на следующую строку, с помощью последовательность продолжения строки, который состоит из пробела и символа подчеркивания (`_`) следуют символ возврата каретки. В следующем примере `MsgBox` исполняемой инструкцией располагается на двух строках.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Неявное продолжение строки

Во многих случаях можно продолжить инструкцию на следующей строке без символа подчеркивания (`_`). Следующие элементы синтаксиса неявно продолжают инструкцию на следующей строке кода.

- После запятой (`,`). Пример:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- После открывающей скобки (`(`) или перед закрывающей скобкой (`)`). Пример:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- После открывающей фигурной скобки (`{`) или перед закрывающей фигурной скобки (`}`). Пример:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Дополнительные сведения см. в разделе [инициализаторы объектов: именованные и анонимные типы](./objects-and-classes/object-initializers-named-and-anonymous-types.md) или [Инициализаторы коллекций](./collection-initializers/index.md).

- После открытого встроенного выражения (`<%=`) или перед закрытием встроенного выражения (`%>`) в XML-литерала. Пример:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Дополнительные сведения см. в разделе [встроенные выражения в XML](./xml/embedded-expressions-in-xml.md).

- После оператора объединения (`&`). Пример:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Дополнительные сведения см. в разделе [операторы, перечисленные по функциональным возможностям](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- После операторов присваивания (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`). Пример:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Дополнительные сведения см. в разделе [операторы, перечисленные по функциональным возможностям](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- После бинарных операторов (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) в выражении. Пример:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Дополнительные сведения см. в разделе [операторы, перечисленные по функциональным возможностям](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- После `Is` и `IsNot` операторы. Пример:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Дополнительные сведения см. в разделе [операторы, перечисленные по функциональным возможностям](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- После знака квалификатора элемента (`.`) и перед именем члена. Пример:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Тем не менее, необходимо использовать знак продолжения строки (`_`) после знака квалификатора элемента при использовании `With` инструкции или указании значений в списке инициализации для типа. Рассмотрите возможность разрыва строки после оператора присваивания (например, `=`) при использовании `With` инструкций или списки инициализации объекта. Пример:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Дополнительные сведения см. в разделе [с... Завершить с помощью инструкции](../../../visual-basic/language-reference/statements/with-end-with-statement.md) или [инициализаторы объектов: именованные и анонимные типы](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- После квалификатор свойство оси XML (`.` или `.@` или `...`). Тем не менее, необходимо использовать знак продолжения строки (`_`) при указании квалификатора элемента при использовании `With` ключевое слово. Пример:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Дополнительные сведения см. в разделе [свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md).

- После меньше-символ "больше" (<) или перед больше-знак больше (`>`) при указании атрибута. Также после-знак больше (`>`) при указании атрибута. Тем не менее, необходимо использовать знак продолжения строки (`_`) при указании атрибутов уровня сборки или уровня модуля. Пример:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Дополнительные сведения см. в разделе [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md).

- До и после операторов запроса (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, и `Descending`). Не удается прервать линию между ключевыми словами операторов запросов, состоящих из нескольких ключевых слов (`Order By`, `Group Join`, `Take While`, и `Skip While`). Пример:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Дополнительные сведения см. в разделе [запросы](../../../visual-basic/language-reference/queries/index.md).

- После `In` ключевое слово в `For Each` инструкции. Пример:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Дополнительные сведения см. в разделе [для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).

- После `From` ключевое слово в инициализатор коллекции. Пример:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Дополнительные сведения см. в разделе [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

## <a name="adding-comments"></a>Добавление комментариев

Исходный код не всегда говорит само за себя, даже для программиста, написавшего его. Для документирования кода таким образом, большинство программистов использует комментарии. Комментарии в коде можно описать в процедуру или определенную инструкцию для тех, кто будет работать с ним в дальнейшем. Visual Basic игнорирует комментарии во время компиляции, и они не влияют на скомпилированный код.

Строки комментариев начинаются с апостроф (`'`) или `REM` разделенных пробелами. Они могут добавляться в любом месте в коде, за исключением в строке. Для добавления комментария в инструкцию вставьте апостроф или `REM` после инструкции, за которой следует комментарий. Комментарии можно также перейти на отдельной строке. В следующем примере показано эти возможности.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Проверка ошибок компиляции

Если после ввода строки кода, отображается строка синей волнистой (а также появляется сообщение об ошибке), есть синтаксическая ошибка в инструкции. Необходимо найти сведения об ошибках с помощью инструкции (по в списке задач или ошибки с помощью указателя мыши при наведении и чтения сообщение об ошибке) и исправить ее. До устранения всех синтаксических ошибок в коде, приложение скомпилировано не будет правильно.

## <a name="related-sections"></a>Связанные разделы

|Термин|Определение|
|---|---|
|[Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)|Ссылки на разделы справочника по языку охватывающий операторы присваивания, такие как `=`, `*=`, и `&=`.|
|[Операторы и выражения](./operators-and-expressions/index.md)|Показано, как объединить элементы с операторами для получения новых значений.|
|[Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Показано, как разбить на несколько строк одной инструкции и размещение нескольких операторов на той же строке.|
|[Практическое руководство. Операторы меток](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Показано, как пометить строку кода.|
