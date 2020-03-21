---
title: Инструкции
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
ms.openlocfilehash: f63f0f0212913f95baab2a8a43c4b7f25a859cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401469"
---
# <a name="statements-in-visual-basic"></a>Операторы в Visual Basic

Заявление в Visual Basic — это полная инструкция. Он может содержать ключевые слова, операторы, переменные, константы и выражения. Каждая утверждение относится к одной из следующих категорий:

- **Заявления о**декларациях, которые называют переменную, постоянную или процедуру, а также могут указывать тип данных.

- **Исполняемые заявления,** которые инициируют действия. Эти операторы могут вызывать метод или функцию, и они могут цикл или ветвь через блоки кода. Выполняемые операторы включают **заявления о назначении,** которые присваивают значение или выражение переменной или постоянной.

Эта тема описывает каждую категорию. Кроме того, эта тема описывает, как объединить несколько инструкций на одной строке и как продолжить оператор в течение нескольких строк.

## <a name="declaration-statements"></a>Операторы объявления

Вы используете заявления о декларациях для определения и определения процедур, переменных, свойств, массивов и констант. Когда вы объявляете элемент программирования, можно также определить его тип данных, уровень доступа и область охвата. Для получения дополнительной информации [см.](./declared-elements/declared-element-characteristics.md)

Следующий пример содержит три декларации.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

Первая декларация `Sub` – это заявление. Вместе со `End Sub` своим соответствующим заявлением, `applyFormat`он объявляет процедуру под названием . Он также указывает, `applyFormat` что `Public`это, что означает, что любой код, который может относиться к нему можно назвать его.

Вторая декларация `Const` — это заявление, `limit`в котором `Integer` декларируется постоянное, определяющее тип данных и значение 33.

Третьей декларацией `Dim` является заявление, в `thisWidget`котором декларируется переменная. Тип данных является определенным объектом, а `Widget` именно объектом, созданным из класса. Вы можете объявить переменную любого элементарного типа данных или любого типа объекта, который подвергается в приложении, которое вы используете.

### <a name="initial-values"></a>Начальные значения

При запуске кода, содержащего заявление о декларировании, Visual Basic резервирует память, необходимую для заявленного элемента. Если элемент имеет значение, Visual Basic инициализирует его к значению по умолчанию для своего типа данных. Для получения дополнительной информации, [Dim Statement](../../language-reference/statements/dim-statement.md)см.

Исходное значение можно назначить переменной как часть ее декларации, как показано в следующем примере.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Если переменная является переменной объекта, можно явно создать экземпляр своего класса, когда вы объявляете ее с помощью ключевого слова [нового оператора,](../../../visual-basic/language-reference/operators/new-operator.md) как показано в следующем примере.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Обратите внимание, что исходное значение, указанное в заявлении декларации, не присваивается переменной до тех пор, пока выполнение не достигнет своей декларааторной декларации. До этого времени переменная содержит значение по умолчанию для своего типа данных.

## <a name="executable-statements"></a>Исполняемые заявления

Исполняемое заявление выполняет действие. Он может вызвать процедуру, ветку в другое место в коде, цикл через несколько инструкций, или оценить выражение. Заявление о назначении — это особый случай исполняемого оператора.

В следующем примере `If...Then...Else` используется структура управления для выполнения различных блоков кода на основе значения переменной. В каждом блоке `For...Next` кода цикл выполняет определенное количество раз.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

Заявление `If` в предыдущем примере проверяет значение `clockwise`параметра. Если `True`значение, он называет `spinClockwise` метод `aWidget`. Если `False`значение, он называет `spinCounterClockwise` метод `aWidget`. Структура `If...Then...Else` управления заканчивается `End If`.

Цикл `For...Next` в каждом блоке вызывает соответствующий метод в несколько раз, равный значению `revolutions` параметра.

## <a name="assignment-statements"></a>Заявления о назначении

Операторы назначения выполняют операции назначения, которые состоят из принятия значения`=`на правой стороне оператора назначения () и хранения его в элементе слева, как в следующем примере.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

В предыдущем примере в выписке о назначении хранится буквальное значение 42 в переменной `v`.

### <a name="eligible-programming-elements"></a>Соответствующие элементы программирования

Элемент программирования на левой стороне оператора назначения должен быть в состоянии принимать и хранить значение. Это означает, что она должна быть переменной или свойством, которое не [является ReadOnly,](../../../visual-basic/language-reference/modifiers/readonly.md)или должно быть элементом массива. В контексте оператора назначения такой элемент иногда называется *lvalue*для "левого значения".

Значение на правой стороне оператора назначения генерируется выражением, которое может состоять из любого сочетания буквальных букваров, констант, переменных, свойств, элементов массива, других выражений или вызовов функций. Это показано в следующем примере.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

Предыдущий пример добавляет значение, `y` удерживаемые `z`в переменной, к значению, `findResult`удерживаемому в переменной, а затем добавляет значение, возвращаемые вызовом, для функции. Общее значение этого выражения затем хранится в переменной. `x`

### <a name="data-types-in-assignment-statements"></a>Типы данных в инструкциях по назначению

Помимо числовых значений, оператор назначения может `String` также назначить значения, как показано в следующем примере.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

Можно также присвоить `Boolean` значения, `Boolean` используя буквальный `Boolean` или выражение, как показано в следующем примере.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Аналогичным образом можно присвоить соответствующие значения `Char` `Date`элементам `Object` программирования , или типу данных. Можно также назначить экземпляр объекта элементу, объявленного классом, из которого создается этот экземпляр.

### <a name="compound-assignment-statements"></a>Заявления о комплексных уступках

*Сложные операторы назначения* сначала выполняют операцию на экспрессе, а затем присваивают его элементу программирования. Следующий пример иллюстрирует один из `+=`этих операторов, который приращает значение переменной на левой стороне оператора значением выражения на право.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

Предыдущий пример добавляет 1 `n`к значению , а `n`затем хранит, что новое значение в . Это краткое эквиваленто следующему заявлению:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

Различные операции комплексного назначения могут выполняться с помощью операторов этого типа. Список этих операторов и более подробную информацию о них можно найти в списках [операторов назначения.](../../../visual-basic/language-reference/operators/assignment-operators.md)

Оператор назначения concatenation`&=`() полезен для добавления строки к концу уже существующих строк, как показано в следующем примере.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Конверсии типа в заявлениях о назначении

Значение, присвоенное элементу переменной, свойства или массива, должно быть типа данных, соответствующего этому элементу назначения. Как правило, следует попытаться создать значение того же типа данных, что и элемент назначения. Однако некоторые типы могут быть преобразованы в другие типы во время назначения.

Для получения информации о преобразовании между типами данных см. [Конверсии типа в Visual Basic](./data-types/type-conversions.md). Короче говоря, Visual Basic автоматически преобразует значение данного типа в любой другой тип, к которому он расширяется. *Расширение преобразования* является одним в том, что всегда удается во время выполнения и не теряет никаких данных. Например, Visual Basic `Integer` преобразует `Double` значение в `Integer` соответствующие `Double`сроки, потому что расширяется до . Для получения дополнительной информации см. [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

*Сужение конверсий* (те, которые не расширяются) несет в себе риск сбоя во время выполнения или потери данных. Вы можете выполнить сужение преобразования явно с помощью функции преобразования типа, или вы `Option Strict Off`можете направить компилятор для выполнения всех преобразований неявно, установив. Для получения дополнительной [информации см.](./data-types/implicit-and-explicit-conversions.md)

## <a name="putting-multiple-statements-on-one-line"></a>Размещение нескольких инструкций на одной строке

Вы можете иметь несколько инструкций на`:`одной строке, разделенной толстой кишки ( ) характер. Это показано в следующем примере.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Хотя иногда удобно, эта форма синтаксиса делает ваш код трудно читать и поддерживать. Таким образом, рекомендуется держать одно утверждение на строке.

## <a name="continuing-a-statement-over-multiple-lines"></a>Продолжение оператора по нескольким линиям

Заявление обычно помещается на одной строке, но когда оно слишком длинное, вы можете продолжить его на следующую строку, используя последовательность продолжения строки, которая состоит из пространства, за которым следует символ подчеркивания (),`_`за которым следует возвращение перевозки. В следующем примере `MsgBox` исполняемое заявление выполняется в течение двух строк.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Неявное продолжение строки

Во многих случаях вы можете продолжить выписку на следующей последовательной строке без использования персонажа подчеркивая ().`_` Следующие элементы синтаксиса неявно продолжают утверждение на следующей строке кода.

- После запятой`,`(). Пример:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- После открытой скобки ()`(`или перед закрытием скобки ().`)` Пример:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- После открытой фигурной`{`скобки () или перед`}`закрытием фигурные скобки ( ). Пример:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Для получения дополнительной информации [см. Инициаторы объектов: именованные и анонимные типы](./objects-and-classes/object-initializers-named-and-anonymous-types.md) или [инициализаторы коллекции.](./collection-initializers/index.md)

- После открытого встроенного выражения ()`<%=`или`%>`до закрытия встроенного выражения ( ) в буквальном XML. Пример:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Для получения дополнительной информации смотрите [встроенные выражения в XML](./xml/embedded-expressions-in-xml.md).

- После конкатации`&`оператора (). Пример:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Для получения дополнительной информации смотрите [Операторы, перечисленные по функциональности](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- После назначения`=`операторы `:=` `+=`(, `*=` `&=` `/=`, `\=` `^=`, `<<=` `>>=`, `-=`, , , . Пример:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Для получения дополнительной информации смотрите [Операторы, перечисленные по функциональности](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- После бинарных `-` `/`операторов `<>`(, `>` `<=` `>=` `^` `>>` `<<` `And` `AndAlso` `Or` `OrElse` `Like` `<``+`, , `*`, `Mod`, , `Xor`, , , , , , , , , ) в пределах выражения. Пример:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Для получения дополнительной информации смотрите [Операторы, перечисленные по функциональности](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- После `Is` и `IsNot` операторов. Пример:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Для получения дополнительной информации смотрите [Операторы, перечисленные по функциональности](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- После персонажа квалификатора ()`.`и до имени участника. Пример:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Тем не менее, необходимо включить`_`символ продолжения строки () после `With` символа квалификатора участника, когда вы используете значение оператора или поставляете значения в списке инициализации для типа. Рассмотрите возможность взлома строки после `=`оператора назначения (например), когда вы используете `With` операторы инициализации объектов. Пример:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Для получения дополнительной информации, [см. Конец с заявлением](../../../visual-basic/language-reference/statements/with-end-with-statement.md) или [инициализаторов объекта: Именованные и анонимные типы](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- После квалификатора свойства`.` `.@` оси XML (или). `...` Тем не менее, необходимо включить`_`символ продолжения строки (), когда `With` вы указываете квалификатор участника, когда вы используете ключевое слово. Пример:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Для получения дополнительной [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md)информации см.

- После менее чем знак (<) или до больше, чем знак ()`>`при указании атрибута. Кроме того, после больше, чем знак (),`>`когда вы указываете атрибут. Тем не менее, необходимо включить`_`символ продолжения строки (), когда вы указываете атрибуты уровня сборки или уровня модуля. Пример:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Для получения дополнительной информации смотрите [обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md).

- До и после запроса `Distinct` `From`операторы `Join`(, `Order By` `Select` `Skip` `Skip While` `Take``Aggregate`, `On`, `Ascending` `Descending` `Take While` `Where` `In` `Group By`, `Group Join` `Let` `Into`, , , , , , , , , , и ). Вы не можете разорвать грань между ключевыми словами операторов`Order By`запросов, которые состоят из нескольких ключевых слов (, `Group Join` `Take While`, и `Skip While`). Пример:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Для получения дополнительной [информации см.](../../../visual-basic/language-reference/queries/index.md)

- После `In` ключевого слова `For Each` в заявлении. Пример:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Для получения дополнительной информации, [см. Следующее заявление](../../../visual-basic/language-reference/statements/for-each-next-statement.md).

- После `From` ключевого слова в коллекции инициализатор. Пример:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Дополнительные сведения см. в разделе [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

## <a name="adding-comments"></a>Добавление комментариев

Исходный код не всегда говорит сам по себе, даже для программиста, который написал его. Таким образом, чтобы помочь задокументировать свой код, большинство программистов используют встроенные комментарии. Комментарии в коде могут объяснить процедуру или конкретную инструкцию любому, кто читает или работает с ней позже. Visual Basic игнорирует комментарии во время компиляции, и они не влияют на компилированный код.

Линии комментариев начинаются с`'`апострофа () или `REM` следуют пробелы. Они могут быть добавлены в любом месте кода, за исключением строки. Чтобы придать комментарий к заявлению, вставьте `REM` апостроф или после заявления, а затем комментарий. Комментарии также могут быть походить на их собственную отдельную строку. Следующий пример демонстрирует эти возможности.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Проверка ошибок компиляции

Если после ввода строки кода строка отображается с волнистым синим подчеркиванием (также может появиться сообщение об ошибке), в заявлении появляется ошибка синтаксиса. Вы должны выяснить, что не так с утверждением (загнав в список задач, или зависания над ошибкой с указателем мыши и чтение сообщения об ошибке) и исправить его. До тех пор, пока вы не исправите все ошибки синтаксиса в коде, ваша программа не сможет компилироваться правильно.

## <a name="related-sections"></a>См. также

|Термин|Определение|
|---|---|
|[Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)|Предоставляет ссылки на языковые `=`справочные страницы, охватывающие операторы назначения, такие как , `*=`и `&=`.|
|[Операторы и выражения](./operators-and-expressions/index.md)|Показывает, как объединить элементы с операторами для получения новых значений.|
|[Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Показывает, как разбить одно утверждение на несколько строк и как разместить несколько инструкций на одной строке.|
|[Практическое руководство. Операторы меток](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Показывает, как пометить строку кода.|
