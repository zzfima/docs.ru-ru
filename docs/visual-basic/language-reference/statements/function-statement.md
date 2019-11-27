---
title: Оператор Function
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 8140c7e6267e66c69c20d413a11d04372400c581
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345921"
---
# <a name="function-statement-visual-basic"></a>Оператор Function (Visual Basic)

Объявляет имя, параметры и код, определяющие процедуру `Function`.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a>Части

- `attributelist`

  Необязательный элемент. См. [список атрибутов](attribute-list.md).

- `accessmodifier`

  Необязательный элемент. Ниже указаны доступные значения.

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Необязательный элемент. Ниже указаны доступные значения.

  - [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Необязательный элемент. См. раздел [Shared](../../../visual-basic/language-reference/modifiers/shared.md).

- `Shadows`

  Необязательный элемент. См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

- `Async`

  Необязательный элемент. См. статью [Async](../../../visual-basic/language-reference/modifiers/async.md).

- `Iterator`

  Необязательный элемент. См. [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).

- `name`

  Обязательно. Имя процедуры. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

- `typeparamlist`

  Необязательный элемент. Список параметров типа для универсальной процедуры. См. [список типов](type-list.md).

- `parameterlist`

  Необязательный элемент. Список имен локальных переменных, представляющих параметры этой процедуры. См. [список параметров](parameter-list.md).

- `returntype`

  Требуется, если `Option Strict` `On`. Тип данных значения, возвращаемого этой процедурой.

- `Implements`

  Необязательный элемент. Указывает, что эта процедура реализует одну или несколько `Function` процедур, каждая из которых определена в интерфейсе, реализуемом классом или структурой этой процедуры. См. [инструкцию Implements](implements-statement.md).

- `implementslist`

  Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Function`.

  `implementedprocedure [ , implementedprocedure ... ]`

  Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.

  `interface.definedname`

  |Отделение|Описание|
  |---|---|
  |`interface`|Обязательно. Имя интерфейса, реализованного классом или структурой, содержащейся в этой процедуре.|
  |`definedname`|Обязательно. Имя, под которым процедура определена в `interface`.|

- `Handles`

  Необязательный элемент. Указывает, что эта процедура может управлять одним или несколькими конкретными событиями. См. раздел [Handles](handles-clause.md).

- `eventlist`

  Является обязательным, если предоставлен параметр `Handles`. Список событий, обрабатываемых этой процедурой.

  `eventspecifier [ , eventspecifier ... ]`

  Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.

  `eventvariable.event`

  |Отделение|Описание|
  |---|---|
  |`eventvariable`|Обязательно. Объектная переменная, объявленная с типом данных класса или структуры, которая вызывает событие.|
  |`event`|Обязательно. Имя события, обрабатываемого этой процедурой.|

- `statements`

  Необязательный элемент. Блок инструкций для выполнения в рамках этой процедуры.

- `End Function`

  Завершает определение этой процедуры.

## <a name="remarks"></a>Примечания

Весь исполняемый код должен находиться внутри процедуры. Каждая процедура, в свою очередь, объявляется в классе, структуре или модуле, который называется содержащим классом, структурой или модулем.

Чтобы вернуть значение в вызывающий код, используйте процедуру `Function`. в противном случае используйте `Sub` процедуру.

## <a name="defining-a-function"></a>Определение функции

Процедуру `Function` можно определить только на уровне модуля. Таким образом, контекст объявления для функции должен быть классом, структурой, модулем или интерфейсом и не может быть исходным файлом, пространством имен, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

`Function` процедуры по умолчанию имеют общий доступ. Уровни доступа можно изменить с помощью модификаторов доступа.

`Function` процедура может объявлять тип данных значения, возвращаемого процедурой. Можно указать любой тип данных или имя перечисления, структуру, класс или интерфейс. Если параметр `returntype` не указан, процедура возвращает `Object`.

Если в этой процедуре используется ключевое слово `Implements`, содержащий класс или структуру также должны иметь инструкцию `Implements`, которая сразу следует за инструкцией `Class` или `Structure`. Оператор `Implements` должен содержать каждый интерфейс, указанный в `implementslist`. Однако имя, по которому интерфейс определяет `Function` (в `definedname`), не должно соответствовать имени этой процедуры (в `name`).

> [!NOTE]
> Лямбда-выражения можно использовать для определения выражений функций встроенным. Дополнительные сведения см. в разделе [выражение функции](../../../visual-basic/language-reference/operators/function-expression.md) и [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="returning-from-a-function"></a>Возврат из функции

Когда процедура `Function` возвращается в вызывающий код, выполнение переходит к инструкции, следующей за инструкцией, вызвавшей эту процедуру.

Чтобы вернуть значение из функции, можно либо присвоить значение имени функции, либо включить его в инструкцию `Return`.

Оператор `Return` одновременно назначает возвращаемое значение и завершает функцию, как показано в следующем примере.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

В следующем примере возвращаемое значение присваивается имени функции `myFunction` а затем используется инструкция `Exit Function` для возврата.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

Операторы `Exit Function` и `Return` вызывают немедленный выход из процедуры `Function`. Любое число инструкций `Exit Function` и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Function` и `Return` операторы.

Если вы используете `Exit Function` без присвоения значения `name`, процедура возвращает значение по умолчанию для типа данных, указанного в `returntype`. Если `returntype` не указан, процедура возвращает `Nothing`, которая является значением по умолчанию для `Object`.

## <a name="calling-a-function"></a>Вызов функции

Вы вызываете `Function` процедуру, используя имя процедуры, за которым следует список аргументов в выражении в круглых скобках. Скобки можно опустить, только если вы не предоставляете никаких аргументов. Однако код является более удобочитаемым, если всегда включать круглые скобки.

Вы вызываете `Function` процедуру так же, как вызов любой библиотечной функции, такой как `Sqrt`, `Cos`или `ChrW`.

Функцию также можно вызвать с помощью ключевого слова `Call`. В этом случае возвращаемое значение игнорируется. В большинстве случаев использование ключевого слова `Call` не рекомендуется. Дополнительные сведения см. в разделе [оператор Call](call-statement.md).

Visual Basic иногда переупорядочивает арифметические выражения для повышения внутренней эффективности. По этой причине не следует использовать `Function` процедуру в арифметическом выражении, когда функция изменяет значение переменных в том же выражении.

## <a name="async-functions"></a>Асинхронные функции

Функция *Async* позволяет вызывать асинхронные функции без использования явных обратных вызовов или вручную разделять код между несколькими функциями или лямбда-выражениями.

Если вы помечаете функцию модификатором [Async](../../../visual-basic/language-reference/modifiers/async.md) , то можете использовать оператор [await](../../../visual-basic/language-reference/operators/await-operator.md) в функции. Когда управление достигает `Await` выражения в функции `Async`, управление возвращается вызывающему объекту, и ход выполнения функции приостанавливается до тех пор, пока не завершится ожидаемая задача. После завершения задачи выполнение может возобновиться в функции.

> [!NOTE]
> `Async` процедура возвращается к вызывающему объекту, когда он встречает первый ожидающий объект, который еще не завершен, или на конец процедуры `Async` (в зависимости от того, что происходит раньше).

Функция `Async` может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>. Ниже приведен пример функции `Async` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>.

Функция `Async` не может объявлять никакие параметры [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) .

[Оператор](sub-statement.md) подвыражения также может быть помечен модификатором `Async`. Это в основном используется для обработчиков событий, где значение не может быть возвращено. Процедуру `Async` `Sub` нельзя ожидать, и вызывающая процедура `Async` `Sub` не может перехватывать исключения, вызываемые процедурой `Sub`.

Дополнительные сведения о функциях `Async` см. в разделе [Асинхронное программирование с использованием Async и await](../../../visual-basic/programming-guide/concepts/async/index.md), [потока управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)и [асинхронных возвращаемых типов](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

## <a name="iterator-functions"></a>Функции итератора

Функция *итератора* выполняет настраиваемую итерацию для коллекции, например списка или массива. Функция итератора использует оператор [yield](yield-statement.md) для возвращения каждого элемента по одному за раз. При достижении оператора [yield](yield-statement.md) текущее расположение в коде запоминается. При следующем вызове функции итератора выполнение возобновляется с этого места.

Итератор вызывается из клиентского кода с помощью метода [For Each... Следующий](for-each-next-statement.md) оператор.

Тип возвращаемого значения функции итератора может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>или <xref:System.Collections.Generic.IEnumerator%601>.

Дополнительные сведения см. в разделе [Итераторы](../../programming-guide/concepts/iterators.md).

## <a name="example"></a>Пример

В следующем примере оператор `Function` используется для объявления имени, параметров и кода, образующих тело процедуры `Function`. Модификатор `ParamArray` позволяет функции принимать переменное число аргументов.

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>Пример

В следующем примере вызывается функция, объявленная в предыдущем примере.

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>Пример

В следующем примере `DelayAsync` является `Async` `Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>. `DelayAsync` имеет инструкцию `Return` , которая возвращает целое число. Поэтому объявление функции `DelayAsync` должно иметь тип возвращаемого значения `Task(Of Integer)`. Поскольку тип возвращаемого значения — `Task(Of Integer)`, вычисление выражения `Await` в `DoSomethingAsync` создает целое число. Это продемонстрировано в этой инструкции: `Dim result As Integer = Await delayTask`.

`startButton_Click` процедура является примером процедуры `Async Sub`. Поскольку `DoSomethingAsync` является `Async`ной функцией, необходимо ожидать, что задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показано в следующей инструкции: `Await DoSomethingAsync()`. Процедура `startButton_Click` `Sub` должна быть определена с помощью модификатора `Async`, так как она содержит выражение `Await`.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>См. также

- [Оператор Sub](sub-statement.md)
- [Процедуры функций](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [Список параметров](parameter-list.md)
- [Оператор Dim](dim-statement.md)
- [Оператор Call](call-statement.md)
- [Of](of-clause.md)
- [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Рекомендации по устранению неполадок](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Выражение функции](../../../visual-basic/language-reference/operators/function-expression.md)
