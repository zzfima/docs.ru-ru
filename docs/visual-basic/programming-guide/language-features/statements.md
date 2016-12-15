---
title: "Операторы в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "подчеркивание синим цветом"
  - "двоеточие (:)"
  - "константы, определение"
  - "константы, операторы"
  - "исполняемые операторы"
  - "разрывы строк, в коде"
  - "процедуры, операторы"
  - "операторы [Visual Basic], сведения об операторах"
  - "подчеркивание"
  - "переменные [Visual Basic], назначение"
  - "переменные [Visual Basic], объявление"
  - "переменные [Visual Basic], определение"
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Операторы в Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] — это полная инструкция.  В инструкциях содержатся ключевые слова, операторы, переменные, константы и выражения.  Каждая инструкция принадлежит к одной из следующих двух категорий:  
  
-   **Операторы объявления**, которые объявляют переменную, константу или процедуру, и могут также указывать тип данных.  
  
-   **Выполняемые операторы**, которые инициируют действия.  Эти операторы могут вызывать метод или функцию, а также способны выполнять цикл или ветвь, состоящие из блоков кода.  Исполняемые операторы содержат **Операторы присваивания**, которые присваивают значение или выражение переменной или константе.  
  
 В этом разделе описана каждая категория.  Также в этом разделе описано, как поместить несколько операторов в одной строке и как продолжить оператор на несколько строк.  
  
## Операторы объявления  
 Операторы объявления используются для именования и определения процедур, переменных, свойств, массивов и констант.  При объявлении элемента программирования можно также определить его тип данных, уровень доступа и область действия.  Дополнительные сведения см. в разделе [Характеристики объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
 В следующем примере показаны три объявления.  
  
 [!code-vb[VbVbalrStatements#80](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_1.vb)]  
  
 Первое объявление — это оператор `Sub`.  Он совместно с соответствующим ему оператором `End Sub` объявляет процедуру с именем `applyFormat`.  Он также указывает, что `applyFormat` является `Public`, что означает, что любой код, который к нему обращается, может его вызвать.  
  
 Второе объявление — это оператор `Const`, который объявляет константу `limit`, указывая тип данных `Integer` и значение 33.  
  
 Третье объявление — это оператор `Dim`, который объявляет переменную `thisWidget`.  Тип данных является определенным объектом, а именно объектом, созданным из класса `Widget`.  Можно объявить переменную любого простейшего типа данных или типа объекта, который предоставляется в приложении.  
  
### Исходное значение  
 При выполнении кода, содержащего оператор объявления, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] резервирует память, требуемую для объявленного элемента.  Если элемент содержит значение, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] инициализирует его значением по умолчанию для его типа данных.  Дополнительные сведения см. в разделе "Поведение" в [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
 Присвоение переменной начального значения может быть частью ее объявления, как показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements#81](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_2.vb)]  
  
 Если переменная является объектной переменной, можно явно создать экземпляр ее класса при ее объявлении с помощью ключевого слова [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md), например:  
  
 [!code-vb[VbVbalrStatements#82](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_3.vb)]  
  
 Обратите внимание, что начальное значение в операторе объявления не присваивается переменной до тех пор, пока выполнение не достигнет его оператора объявления.  До этого времени переменная содержит значение по умолчанию для своего типа данных.  
  
## Исполняемые операторы  
 Исполняемый оператор выполняет действия.  Он может вызвать процедуру, переход на другое место в коде, цикл по нескольким инструкциям или вычислить значение выражения.  Оператор присваивания является особым случаем исполняемого оператора.  
  
 В следующем примере используется управляющая структура `If...Then...Else` для выполнения различных блоков кода на основе значения переменной.  В каждом блоке кода цикл `For...Next` выполняется заданное число раз.  
  
 [!code-vb[VbVbalrStatements#83](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_4.vb)]  
  
 Инструкция `If` в предыдущем примере проверяет значение параметра `clockwise`.  Если значение равно `True`, то вызывается метод `spinClockwise` из `aWidget`.  Если значение равно `False`, то вызывается метод `spinCounterClockwise` из `aWidget`.  Управляющая структура `If...Then...Else` завершается `End If`.  
  
 Цикл `For...Next` в каждом блоке вызывает соответствующий метод определенное количество раз, равное значению параметра `revolutions`.  
  
## Операторы присваивания  
 Операторы присваивания выполняют присваивание, сводящееся к вычислению значения справа от оператора присваивания \(`=`\) и его записи в элемент слева, как в следующем примере.  
  
 [!code-vb[VbVbalrStatements#73](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_5.vb)]  
  
 В этом примере оператор присваивания сохраняет значение литерала 42 в переменной `v`.  
  
### Подходящие элементы программирования  
 Элемент программирования слева от оператора присваивания должен иметь возможность принимать и хранить значение.  Это означает, что он должен быть переменной или свойством, не являющимся [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), или же элементом массива.  В контексте оператора присваивания такой элемент иногда называется *lvalue* \("левое значение"\).  
  
 Значение в правой части оператора присваивания формируется с помощью выражения, которое может содержать любую комбинацию литералов, констант, переменных, свойств, элементов массива и другие выражения или вызовы функций.  Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbalrStatements#74](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_6.vb)]  
  
 В этом примере осуществляется сложение значения переменной `y` со значением переменной `z`, а затем сложение со значением, возвращаемым функцией `findResult`.  Общее значение этого выражения затем сохраняется в переменной `x`.  
  
### Типы данных в операторах присваивания  
 В дополнение к числовым значениям оператор присваивания также может присваивать значения типа `String`, как показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements#75](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_7.vb)]  
  
 Можно также присваивать значения `Boolean` с помощью литерала `Boolean` или выражения `Boolean`, как показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements#76](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_8.vb)]  
  
 Аналогично, можно присваивать соответствующие значения элементам программирования типов `Char`, `Date` и `Object`.  Можно также присвоить экземпляр объекта элементу класса, из которого этот экземпляр был создан.  
  
### Составные операторы присваивания  
 *Составные операторы присваивания* сначала выполняют операцию над выражением перед присваиванием его значения программному элементу.  В следующем примере показан один из этих операторов, `+=`, который прибавляет значение переменной в левой части оператора к значению выражения справа:  
  
 [!code-vb[VbVbalrStatements#77](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_9.vb)]  
  
 В предыдущем примере к значению `n` прибавляется 1, а затем новое значение записывается в `n`.  Это краткий эквивалент следующего оператора:  
  
 [!code-vb[VbVbalrStatements#78](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_10.vb)]  
  
 Многие составные операции присваивания выполняются с помощью операторов этого типа.  Список этих операторов и дополнительные сведения о них см. в разделе [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md).  
  
 Оператор объединения и присваивания \(`&=`\) удобен при добавлении строки в конец уже существующих строк, например:  
  
 [!code-vb[VbVbalrStatements#79](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_11.vb)]  
  
### Преобразование типов в операторах присваивания  
 Значение, присваиваемое переменной, свойству или элементу массива, должно иметь тип данных конечного элемента.  В общем случае следует стремиться создавать значение того же типа данных, что и у конечного элемента.  Тем не менее, во время присваивания некоторые типы могут быть преобразованы в другие.  
  
 Сведения о преобразовании типов данных см. в разделе [Преобразование типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md).  Говоря коротко, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически преобразует значение заданного типа к любому другому типу, до которого он может быть расширен.  *Расширяющее преобразование* всегда успешно завершается во время выполнения и не приводит к потере данных.  Например, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] при необходимости преобразует значение типа `Integer` к `Double`, поскольку `Integer` имеет меньшую разрядность, чем `Double`.  Дополнительные сведения см. в разделе [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 *Сужающие преобразования* \(не являющиеся расширяющими\) выполняются с риском сбоя или потери данных во время выполнения.  Явное сужающее преобразование можно выполнять с помощью функции преобразования типа; также можно указать компилятору выполнять все преобразования неявно, установив параметр `Option Strict Off`.  Дополнительные сведения см. в разделе [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## Размещение нескольких операторов на одной строке  
 На одной строке возможно размещение нескольких операторов, разделенных символом двоеточия \(`:`\).  Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbalrStatements#70](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_12.vb)]  
  
 Хотя это иногда и удобно, эта форма синтаксиса осложняет чтение и сопровождение кода.  Поэтому рекомендуется писать по одному оператору на строке.  
  
## Продолжение оператора на нескольких строках  
 Оператор обычно занимает одну строку, но длинный оператор можно продолжить на следующих строках с помощью символа продолжения строки, состоящего из символа подчеркивания \(`_`\), за которым следует перевод строки.  В следующем примере выполняемый оператор `MsgBox` располагается на двух строках.  
  
 [!code-vb[VbVbalrStatements#71](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_13.vb)]  
  
### Неявное продолжение строки  
 Во многих случаях инструкцию можно продолжить на следующей строке, не используя знак подчеркивания \(\_\).  В следующей таблице приведен список элементов синтаксиса, которые неявно продолжают инструкцию на следующей строке кода.  
  
|||  
|-|-|  
|Элемент синтаксиса|Пример|  
|После запятой \(`,`\).|[!code-vb[VbVbalrLineContinuation#1](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_14.vb)]|  
|После открывающей скобки \(`(`\) или перед закрывающей скобкой \(`)`\).|[!code-vb[VbVbalrLineContinuation#2](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_15.vb)]|  
|После открывающей фигурной скобки \(`{`\) или перед закрывающей фигурной скобкой \(`}`\).|[!code-vb[VbVbalrLineContinuation#3](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_16.vb)]<br /><br /> Дополнительные сведения см. в разделе [Инициализаторы объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) или [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
|После открытого встроенного выражения \(`<%=`\) или перед закрытием встроенного выражения \(`%>`\) в рамках XML\-литерала.|[!code-vb[VbVbalrLineContinuation#4](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_17.vb)]<br /><br /> Дополнительные сведения см. в разделе [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
|После оператора объединения \(`&`\).|[!code-vb[VbVbcnConventions#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_18.vb)]<br /><br /> Дополнительные сведения см. в разделе [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|После операторов назначения \(`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`\).|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br /><br /> Дополнительные сведения см. в разделе [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|После двоичных операторов \(`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`\) в рамках выражения.|[!code-vb[VbVbalrLineContinuation#7](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_20.vb)]<br /><br /> Дополнительные сведения см. в разделе [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|После операторов `Is` и `IsNot`.|[!code-vb[VbVbalrLineContinuation#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_21.vb)]<br /><br /> Дополнительные сведения см. в разделе [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|После символа квалификатора элемента \(`.`\) перед именем элемента.  Однако необходимо использовать знак продолжения строки \(\_\) после знака квалификатора элемента при использовании оператора `With` или указании значений в списке инициализации для типа.  При использовании оператора `With` или списков инициализации объектов попробуйте разорвать строку после оператора назначения \(например, `=`\).|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br />[!code-vb[VbVbalrLineContinuation#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_22.vb)]<br /><br /> Дополнительные сведения см. в разделе [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md) или [Инициализаторы объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).|  
|После квалификатора свойства XML\-оси \(`.` или `.@` или `...`\).  Однако необходимо использовать знак продолжения строки \(\_\) при указании квалификатора элемента с использованием ключевого слова `With`.|[!code-vb[VbVbalrLineContinuation#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_23.vb)]<br /><br /> Дополнительные сведения см. в разделе [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).|  
|После знака "меньше" \(\<\) или перед знаком "больше" \(`>`\) при задании атрибута.  Также после знака "больше" \(`>`\) при задании атрибута.  Однако необходимо использовать знак продолжения строки \(\_\) при задании атрибутов уровня сборки или уровня модуля.|[!code-vb[VbVbalrLineContinuation#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_24.vb)]<br /><br /> Дополнительные сведения см. в разделе [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md).|  
|До и после операторов запроса \(`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending` и `Descending`\).  Нельзя разрывать строку между ключевыми словами операторов запросов, состоящих из нескольких ключевых слов \(`Order By`, `Group Join`, `Take While` и `Skip While`\).|[!code-vb[VbVbalrLineContinuation#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_25.vb)]<br /><br /> Дополнительные сведения см. в разделе [Запросы](../../../visual-basic/language-reference/queries/queries.md).|  
|После ключевого слова `In` в операторе `For Each`.|[!code-vb[VbVbalrLineContinuation#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_26.vb)]<br /><br /> Дополнительные сведения см. в разделе [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md).|  
|После ключевого слова `From` в инициализаторе коллекции.|[!code-vb[VbVbalrLineContinuation#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_27.vb)]<br /><br /> Дополнительные сведения см. в разделе [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
  
## Добавление комментариев  
 Исходный код не всегда понятен без пояснений даже для написавшего его программиста.  Поэтому для документирования своих кодов большинство программистов использует комментарии.  С помощью комментариев в коде можно описать процедуру или определенную инструкцию для тех, кто будет в дальнейшем просматривать этот код или работать с ним.  При компиляции в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] комментарии игнорируются, и они не влияют на скомпилированный код.  
  
 Строки комментариев начинаются с апострофа \(`'`\) или `REM`, за которым следует пробел.  Они могут быть добавлены в любое место кода, за исключением места внутри строковых типов данных.  Для добавления комментария в инструкцию вставьте апостроф или `REM` после оператора, за которым следует комментарий.  Комментарии также могут размещаться на отдельной строке.  В следующем примере показаны эти возможности.  
  
 [!code-vb[VbVbalrStatements#72](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_28.vb)]  
  
## Проверка ошибок компиляции  
 Если после набора строки кода строка отображается с подчеркнутой волнистой голубой линией \(также может быть выведено и сообщение об ошибке\), это означает, что в операторе допущена синтаксическая ошибка.  Необходимо узнать, в чем заключается ошибка инструкции \(для этого просмотрите список задач или поместите указатель мыши на ошибку и прочтите ее описание\) и исправить ее.  До тех пор, пока все синтаксические ошибки не будут исправлены, программа будет давать сбой при компиляции.  
  
## Связанные разделы  
  
|||  
|-|-|  
|Термин|Определение|  
|[Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)|Ссылки на разделы справочника по языку, в которых рассматриваются операторы присваивания, такие как `=`, `*=` и`&=`.|  
|[Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)|Описание процедуры совместного использования элементов и операторов для получения новых значений.|  
|[Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Описывает, как разбить один оператор на несколько строк и как разместить несколько операторов на одной строке.|  
|[Практическое руководство. Операторы меток](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Описывает, как пометить строку кода.|