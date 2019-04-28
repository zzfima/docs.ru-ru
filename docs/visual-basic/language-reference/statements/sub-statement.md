---
title: Оператор Sub (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: ab94865f4881b40b38f67eb40d2f9fa2e1982af8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783842"
---
# <a name="sub-statement-visual-basic"></a>Оператор Sub (Visual Basic)

Объявляет имя, параметры и код, которые определяют `Sub` процедуры.

## <a name="syntax"></a>Синтаксис

```
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a>Части

- `attributelist`

  Необязательный параметр. См. в разделе [список атрибутов](attribute-list.md).

- `Partial`

  Необязательный параметр. Указывает определение разделяемого метода. См. в разделе [разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).

- `accessmodifier`

  Необязательный параметр. Ниже указаны доступные значения.

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Закрытые](../modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Необязательный параметр. Ниже указаны доступные значения.

  - [Перегрузки](../modifiers/overloads.md)

  - [Переопределения](../modifiers/overrides.md)

  - [Переопределяемые](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Необязательный параметр. См. в разделе [общих](../modifiers/shared.md).

- `Shadows`

  Необязательный параметр. См. в разделе [Shadows](../modifiers/shadows.md).

- `Async`

  Необязательный параметр. См. в разделе [Async](../modifiers/async.md).

- `name`

  Обязательный. Имя процедуры. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Чтобы создать процедуру конструктора для класса, задайте имя `Sub` процедура `New` ключевое слово. Дополнительные сведения см. в разделе [время жизни объекта: Как создаются и удаляются объекты](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

- `typeparamlist`

  Необязательный параметр. Список параметров типа для универсальной процедуры. См. в разделе [введите список](type-list.md).

- `parameterlist`

  Необязательный параметр. Список имен локальных переменных, представляющих параметры этой процедуры. См. в разделе [список параметров](parameter-list.md).

- `Implements`

  Необязательный параметр. Указывает, что эта процедура реализует один или несколько `Sub` процедуры, каждая из которых определена в интерфейс, реализуемый этой процедуры классом или структурой. См. в разделе [реализует оператор](implements-statement.md).

- `implementslist`

  Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Sub`.

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

  Необязательный параметр. Блок операторов для выполнения в рамках этой процедуры.

- `End Sub`

  Завершает определение этой процедуры.

## <a name="remarks"></a>Примечания

Весь исполняемый код должен быть внутри процедуры. Используйте `Sub` процедуре, если не требуется возвращать значение вызывающему коду. Используйте `Function` процедуре, если необходимо вернуть значение.

## <a name="defining-a-sub-procedure"></a>Определение процедуры Sub

Вы можете определить `Sub` процедуры только на уровне модуля. Контекст объявления для процедуры sub таким образом, должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедура или блок. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

`Sub` процедуры по умолчанию для общего доступа. Уровни доступа можно настроить с помощью модификаторов доступа.

Если в процедуре используется `Implements` должен иметь ключевое слово, содержащим классом или структурой `Implements` оператор, который следует сразу за его `Class` или `Structure` инструкции. `Implements` Инструкция должна включать каждого интерфейса, который указан в `implementslist`. Тем не менее имя, по которому определяется интерфейс `Sub` (в `definedname`) не должен совпадать с именем этой процедуры (в `name`).

## <a name="returning-from-a-sub-procedure"></a>Возвращение из процедуры Sub

Когда `Sub` процедура возвращает в вызывающий код, выполнение продолжается с оператора после оператора, который вызвал ее.

В следующем примере показано отклик на `Sub` процедуры.

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

`Exit Sub` И `Return` инструкции вызывают Немедленный выход из `Sub` процедуры. Любое количество `Exit Sub` и `Return` инструкций может находиться в любом в процедуре, и вы можете комбинировать `Exit Sub` и `Return` инструкций.

## <a name="calling-a-sub-procedure"></a>Вызов процедуры Sub

Вы вызываете `Sub` процедуры с помощью имени процедуры в инструкции и затем согласно это имя с помощью списка своих аргументов в скобках. Скобки могут опускаться только в том случае, если не предоставляет никакие аргументы. Тем не менее код является более удобочитаемым, если всегда использовать круглые скобки.

Объект `Sub` процедуры и `Function` процедуры могут иметь параметры и выполнять последовательность операторов. Тем не менее `Function` процедура возвращает значение, а также `Sub` не процедуры. Следовательно, нельзя использовать `Sub` процедуры в выражении.

Можно использовать `Call` ключевое слово при вызове `Sub` процедура, но его не рекомендуется для большинства случаев. Дополнительные сведения см. в разделе [инструкции Call](call-statement.md).

Visual Basic иногда упорядочение арифметические выражения для повышения эффективности внутренней. По этой причине, если список аргументов включает выражения, которые вызывают другие процедуры, нет оснований предполагать, что эти выражения будут вызываться в определенном порядке.

## <a name="async-sub-procedures"></a>Async Sub-процедуры

С помощью функции Async можно вызывать асинхронные функции без использованию явных обратных вызовов или ручному разделению кода между несколькими функции или лямбда-выражения.

Если пометить процедуры с [Async](../modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в процедуре. Когда управление достигает `Await` выражение в `Async` процедуры, управление возвращается вызывающему объекту и выполнение в процедуре приостанавливается до завершения выполнения ожидающей задачи. После завершения задачи можно возобновить выполнение в процедуре.

> [!NOTE]
> `Async` Процедура возвращает вызывающий объект при обнаружении либо первый ожидаемый объект, который еще не завершено или в конце `Async` процедуры будет достигнут, что произойдет раньше.

Можно также пометить [инструкции Function](function-statement.md) с `Async` модификатор. `Async` Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>. Пример далее в этом разделе показано, `Async` функции с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>.

`Async` `Sub` процедуры в основном используются для обработчиков событий, в которой не может быть возвращено значение. `Async` `Sub` Процедуру нельзя ожидать и вызывающий `Async` `Sub` процедура не может перехватывать исключения, `Sub` процедура вызывает исключение.

`Async` Процедура не может объявлять [ByRef](../modifiers/byref.md) параметров.

Дополнительные сведения о `Async` процедуры, см. в разделе [асинхронное программирование с использованием Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), и [асинхронные типы возвращаемых значений](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

## <a name="example"></a>Пример

В следующем примере используется `Sub` инструкции для определения имени, параметров и кода, образующих текст `Sub` процедуры.

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>Пример

В следующем примере `DelayAsync` — `Async` `Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>. `DelayAsync` имеет инструкцию `Return` , которая возвращает целое число. Таким образом, объявление функции `DelayAsync` должен иметь тип возвращаемого значения `Task(Of Integer)`. Так как возвращаемый тип — `Task(Of Integer)`, вычисление `Await` выражение в `DoSomethingAsync` создает целое, как показано в следующей инструкции: `Dim result As Integer = Await delayTask`.

`startButton_Click` Процедура является примером `Async Sub` процедуры. Так как `DoSomethingAsync` — `Async` функции, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показано в следующей инструкции: `Await DoSomethingAsync()`. `startButton_Click` `Sub` Процедура должна быть определена с помощью `Async` модификатор из-за `Await` выражение.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>См. также

- [Оператор Implements](implements-statement.md)
- [Оператор Function](function-statement.md)
- [Список параметров](parameter-list.md)
- [Оператор Dim](dim-statement.md)
- [Оператор Call](call-statement.md)
- [Of](of-clause.md)
- [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Рекомендации по устранению неполадок](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
