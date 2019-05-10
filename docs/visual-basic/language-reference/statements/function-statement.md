---
title: Оператор Function (Visual Basic)
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
ms.openlocfilehash: 3a6184164fdc6f2517caf45f7b5e1455c9299666
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754722"
---
# <a name="function-statement-visual-basic"></a>Оператор Function (Visual Basic)

Объявляет имя, параметры и код, которые определяют `Function` процедуры.

## <a name="syntax"></a>Синтаксис

```
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a>Части

- `attributelist`

  Необязательный параметр. См. в разделе [список атрибутов](attribute-list.md).

- `accessmodifier`

  Необязательный параметр. Ниже указаны доступные значения.

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Необязательный параметр. Ниже указаны доступные значения.

  - [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Необязательный параметр. См. в разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).

- `Shadows`

  Необязательный параметр. См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

- `Async`

  Необязательный параметр. См. в разделе [Async](../../../visual-basic/language-reference/modifiers/async.md).

- `Iterator`

  Необязательный параметр. См. в разделе [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).

- `name`

  Обязательный. Имя процедуры. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

- `typeparamlist`

  Необязательный параметр. Список параметров типа для универсальной процедуры. См. в разделе [введите список](type-list.md).

- `parameterlist`

  Необязательный параметр. Список имен локальных переменных, представляющих параметры этой процедуры. См. в разделе [список параметров](parameter-list.md).

- `returntype`

  Обязателен, если `Option Strict` является `On`. Тип данных значения, возвращаемые этой процедурой.

- `Implements`

  Необязательный параметр. Указывает, что эта процедура реализует один или несколько `Function` процедуры, каждая из которых определена в интерфейс, реализуемый этой процедуры классом или структурой. См. в разделе [реализует оператор](implements-statement.md).

- `implementslist`

  Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Function`.

  `implementedprocedure [ , implementedprocedure ... ]`

  Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.

  `interface.definedname`

  |Отделение|Описание|
  |---|---|
  |`interface`|Обязательный. Имя интерфейса, реализуемого этой процедуры содержащей класса или структуры.|
  |`definedname`|Обязательный. Имя, под которым процедура определена в `interface`.|

- `Handles`

  Необязательный параметр. Указывает, что эта процедура может обрабатывать один или несколько определенных событий. См. в разделе [обрабатывает](handles-clause.md).

- `eventlist`

  Является обязательным, если предоставлен параметр `Handles`. Список событий, которые обрабатывает эту процедуру.

  `eventspecifier [ , eventspecifier ... ]`

  Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.

  `eventvariable.event`

  |Отделение|Описание|
  |---|---|
  |`eventvariable`|Обязательный. Объектной переменной, объявленной с типом данных класса или структуры, который вызывает событие.|
  |`event`|Обязательный. Имя события, которое обрабатывает эту процедуру.|

- `statements`

  Необязательный параметр. Блок операторов, выполняемый в рамках этой процедуры.

- `End Function`

  Завершает определение этой процедуры.

## <a name="remarks"></a>Примечания

Весь исполняемый код должен быть внутри процедуры. Каждая процедура в свою очередь, объявляется внутри класса, структуры или модуль, который называется содержащего класса, структуры или модуля.

Чтобы вернуть значение в вызывающий код, используйте `Function` процедуры; в противном случае используйте `Sub` процедуры.

## <a name="defining-a-function"></a>Определение функции

Вы можете определить `Function` процедуры только на уровне модуля. Таким образом контекст объявления для функции должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедура или блок. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

`Function` процедуры по умолчанию для общего доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа.

Объект `Function` процедуре можно объявить тип данных, процедура возвращает значения. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса. Если вы не укажете `returntype` параметра, процедура возвращает `Object`.

Если в этой процедуре используется `Implements` ключевое слово, содержащем классе или структуре также должен иметь `Implements` оператор, который следует сразу за его `Class` или `Structure` инструкции. `Implements` Инструкция должна включать каждого интерфейса, который указан в `implementslist`. Тем не менее имя, по которому определяется интерфейс `Function` (в `definedname`) не должно совпадать с именем этой процедуры (в `name`).

> [!NOTE]
> Лямбда-выражения можно использовать для определения выражения встроенную функцию. Дополнительные сведения см. в разделе [выражение функции](../../../visual-basic/language-reference/operators/function-expression.md) и [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="returning-from-a-function"></a>Возврат из функции

Когда `Function` процедура возвращает в вызывающий код, выполнение продолжается с оператора, который расположен после оператора, который вызвал процедуру.

Для возврата значения из функции, можно присвоить значение имени функции или включить ее в `Return` инструкции.

`Return` Инструкции одновременно назначает возвращаемое значение и выход из функции, как показано в следующем примере.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

В следующем примере присваивается значение имени функции `myFunction` , а затем использует `Exit Function` инструкция возвращает.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

`Exit Function` И `Return` инструкции вызывают Немедленный выход из `Function` процедуры. Любое количество `Exit Function` и `Return` инструкций может находиться в любом в процедуре, и вы можете комбинировать `Exit Function` и `Return` инструкций.

Если вы используете `Exit Function` без присвоения значения `name`, процедура возвращает значение по умолчанию для типа данных, который указан в `returntype`. Если `returntype` не указан, процедура возвращает `Nothing`, который является значением по умолчанию для `Object`.

## <a name="calling-a-function"></a>Вызов функции

Вы вызываете `Function` процедуры с помощью имени процедуры, за которым следует список аргументов в скобки в выражении. Скобки могут опускаться только в том случае, если вы не имеет аргументов. Тем не менее код является более удобочитаемым, если всегда использовать круглые скобки.

Вы вызываете `Function` процедуры, так же, что вызывать любую библиотеку функций, таких как `Sqrt`, `Cos`, или `ChrW`.

Можно также вызвать функцию с помощью `Call` ключевое слово. В этом случае возвращаемое значение учитывается. Использование `Call` ключевое слово не рекомендуется в большинстве случаев. Дополнительные сведения см. в разделе [инструкции Call](call-statement.md).

Visual Basic иногда упорядочение арифметические выражения для повышения эффективности внутренней. По этой причине не следует использовать `Function` процедуры в арифметическом выражении, если функция изменяет значение переменных в одном выражении.

## <a name="async-functions"></a>Асинхронные функции

*Async* позволяет вызывать асинхронные функции без использованию явных обратных вызовов или ручному разделению кода между несколькими функции или лямбда-выражения.

Если пометить функцию с [Async](../../../visual-basic/language-reference/modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в функции. Когда управление достигает `Await` выражение в `Async` функции, управление возвращается вызывающему объекту и выполнение в функции приостанавливается до завершения выполнения ожидающей задачи. После завершения задачи можно возобновить выполнение в функцию.

> [!NOTE]
> `Async` Процедура возвращает вызывающему объекту, когда либо он встречает первый ожидаемый объект, который еще не завершено, или он получает в конец `Async` процедуры, что произойдет раньше.

`Async` Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>. Пример `Async` функции с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601> приведен ниже.

`Async` Функция не может объявлять [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) параметров.

Объект [оператор Sub](sub-statement.md) можно также пометить `Async` модификатор. Это в основном используется для обработчиков событий, где не может быть возвращено значение. `Async` `Sub` Процедуру нельзя ожидать и вызывающий `Async` `Sub` процедура не может перехватывать исключения, вызываемые по `Sub` процедуры.

Дополнительные сведения о `Async` функции, см. в разделе [асинхронное программирование с использованием Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), и [асинхронные типы возвращаемых значений](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

## <a name="iterator-functions"></a>Функции итераторов

*Итератор* функция выполняет настраиваемую итерацию по коллекции, такие как список или массив. Использует функцию итератор [Yield](yield-statement.md) инструкцию для возврата всех элементов одному за раз. Когда [Yield](yield-statement.md) оператору текущее расположение в коде запоминается. При следующем вызове функции итератора выполнение возобновляется с этого места.

Итератор вызывается из клиентского кода с помощью [для каждого... Далее](for-each-next-statement.md) инструкции.

Тип возвращаемого значения функции итератора может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, или <xref:System.Collections.Generic.IEnumerator%601>.

Дополнительные сведения см. в разделе [Итераторы](../../programming-guide/concepts/iterators.md).

## <a name="example"></a>Пример

В следующем примере используется `Function` инструкцию для объявления имени, параметров и кода, образующих текст `Function` процедуры. `ParamArray` Модификатор разрешает функции принимать переменное число аргументов.

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>Пример

В следующем примере вызывается функция, объявленная в предыдущем примере.

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>Пример

В следующем примере `DelayAsync` — `Async` `Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>. `DelayAsync` имеет инструкцию `Return` , которая возвращает целое число. Поэтому объявление функции `DelayAsync` должен иметь тип возвращаемого значения `Task(Of Integer)`. Так как возвращаемый тип — `Task(Of Integer)`, вычисление `Await` выражение в `DoSomethingAsync` создает целое. Это показано в этом операторе: `Dim result As Integer = Await delayTask`.

`startButton_Click` Процедура является примером `Async Sub` процедуры. Так как `DoSomethingAsync` — `Async` функции, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показано в следующей инструкции: `Await DoSomethingAsync()`. `startButton_Click` `Sub` Процедура должна быть определена с помощью `Async` модификатор из-за `Await` выражение.

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
