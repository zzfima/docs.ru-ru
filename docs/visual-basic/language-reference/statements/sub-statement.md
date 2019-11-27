---
title: Оператор Sub
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
ms.openlocfilehash: da498a5e0a3633eb98882aaed145fcd21ab169fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346438"
---
# <a name="sub-statement-visual-basic"></a>Оператор Sub (Visual Basic)

Объявляет имя, параметры и код, определяющие процедуру `Sub`.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a>Части

- `attributelist`

  Необязательный элемент. См. [список атрибутов](attribute-list.md).

- `Partial`

  Необязательный элемент. Указывает определение разделяемого метода. См. раздел [разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).

- `accessmodifier`

  Необязательный элемент. Ниже указаны доступные значения.

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Закрытые](../modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Необязательный элемент. Ниже указаны доступные значения.

  - [Overloads](../modifiers/overloads.md)

  - [Переопределения](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Необязательный элемент. См. раздел [Shared](../modifiers/shared.md).

- `Shadows`

  Необязательный элемент. См. раздел [Shadows](../modifiers/shadows.md).

- `Async`

  Необязательный элемент. См. статью [Async](../modifiers/async.md).

- `name`

  Обязательно. Имя процедуры. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Чтобы создать процедуру конструктора для класса, задайте в качестве имени `Sub` процедуры ключевое слово `New`. Дополнительные сведения см. в разделе [время существования объекта: как создаются и уничтожаются объекты](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

- `typeparamlist`

  Необязательный элемент. Список параметров типа для универсальной процедуры. См. [список типов](type-list.md).

- `parameterlist`

  Необязательный элемент. Список имен локальных переменных, представляющих параметры этой процедуры. См. [список параметров](parameter-list.md).

- `Implements`

  Необязательный элемент. Указывает, что эта процедура реализует одну или несколько `Sub` процедур, каждая из которых определена в интерфейсе, реализуемом классом или структурой этой процедуры. См. [инструкцию Implements](implements-statement.md).

- `implementslist`

  Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Sub`.

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

- `End Sub`

  Завершает определение этой процедуры.

## <a name="remarks"></a>Примечания

Весь исполняемый код должен находиться внутри процедуры. Если вы не хотите возвращать значение в вызывающий код, используйте процедуру `Sub`. Используйте `Function` процедуру, если требуется вернуть значение.

## <a name="defining-a-sub-procedure"></a>Определение подпроцедуры

Процедуру `Sub` можно определить только на уровне модуля. Контекст объявления для процедуры, следовательно, должен быть классом, структурой, модулем или интерфейсом и не может быть исходным файлом, пространством имен, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

`Sub` процедуры по умолчанию имеют общий доступ. Уровни доступа можно изменить с помощью модификаторов доступа.

Если процедура использует ключевое слово `Implements`, содержащий класс или структуру должны содержать инструкцию `Implements`, которая сразу же следует за инструкцией `Class` или `Structure`. Оператор `Implements` должен содержать каждый интерфейс, указанный в `implementslist`. Однако имя, по которому интерфейс определяет `Sub` (в `definedname`), не обязательно должен совпадать с именем этой процедуры (в `name`).

## <a name="returning-from-a-sub-procedure"></a>Возврат из подпроцедуры

Когда `Sub` процедура возвращается в вызывающий код, выполнение переходит к инструкции после оператора, вызвавшего ее.

В следующем примере показан возврат из процедуры `Sub`.

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

Операторы `Exit Sub` и `Return` вызывают немедленный выход из процедуры `Sub`. Любое число инструкций `Exit Sub` и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Sub` и `Return` операторы.

## <a name="calling-a-sub-procedure"></a>Вызов процедуры подпрограммы

Процедура `Sub` вызывается с помощью имени процедуры в инструкции и затем после этого имени вместе со списком аргументов в круглых скобках. Скобки можно опустить, только если не указаны аргументы. Однако код является более удобочитаемым, если всегда включать круглые скобки.

Процедура `Sub` и процедура `Function` могут иметь параметры и выполнять ряд инструкций. Однако процедура `Function` возвращает значение, а `Sub` процедура — нет. Поэтому в выражении нельзя использовать `Sub` процедуру.

При вызове `Sub` процедуры можно использовать ключевое слово `Call`, но это ключевое слово не рекомендуется для большинства случаев использования. Дополнительные сведения см. в разделе [оператор Call](call-statement.md).

Visual Basic иногда переупорядочивает арифметические выражения для повышения внутренней эффективности. По этой причине, если список аргументов содержит выражения, вызывающие другие процедуры, не следует рассчитывать на то, что эти выражения будут вызываться в определенном порядке.

## <a name="async-sub-procedures"></a>Процедуры Async

С помощью функции Async можно вызывать асинхронные функции без использования явных обратных вызовов или вручную разделить код по нескольким функциям или лямбда-выражениям.

Если вы пометите процедуру с модификатором [Async](../modifiers/async.md) , то можете использовать оператор [await](../../../visual-basic/language-reference/operators/await-operator.md) в процедуре. Когда управление достигает `Await` выражения в `Async` процедуре, управление возвращается вызывающему объекту, и ход выполнения процедуры приостанавливается до тех пор, пока не завершится ожидаемая задача. После завершения задачи выполнение может быть возобновлено в процедуре.

> [!NOTE]
> `Async` процедура возвращается к вызывающему объекту, когда происходит либо первый ожидающий объект, который еще не завершен, либо достигнут конец процедуры `Async`, в зависимости от того, какое событие произойдет раньше.

Можно также пометить [оператор Function](function-statement.md) с помощью модификатора `Async`. Функция `Async` может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>. В примере далее в этом разделе показана функция `Async` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>.

`Async` процедуры `Sub` в основном используются для обработчиков событий, где значение не может быть возвращено. Процедуру `Async` `Sub` не может быть ожидаемой, и вызывающая процедура `Async` `Sub` не может перехватывать исключения, вызываемые процедурой `Sub`.

Процедура `Async` не может объявлять параметры [ByRef](../modifiers/byref.md) .

Дополнительные сведения о `Async` процедурах см. в разделе [Асинхронное программирование с использованием Async и await](../../../visual-basic/programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)и [асинхронные типы возвращаемых](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)данных.

## <a name="example"></a>Пример

В следующем примере оператор `Sub` используется для определения имени, параметров и кода, образующих тело процедуры `Sub`.

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>Пример

В следующем примере `DelayAsync` является `Async` `Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>. `DelayAsync` имеет инструкцию `Return` , которая возвращает целое число. Поэтому объявление функции `DelayAsync` должно иметь тип возвращаемого значения `Task(Of Integer)`. Поскольку тип возвращаемого значения — `Task(Of Integer)`, вычисление выражения `Await` в `DoSomethingAsync` создает целое число, как показано в следующей инструкции: `Dim result As Integer = Await delayTask`.

`startButton_Click` процедура является примером процедуры `Async Sub`. Поскольку `DoSomethingAsync` является функцией `Async`, необходимо ожидать, что задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показано в следующей инструкции: `Await DoSomethingAsync()`. Процедура `startButton_Click` `Sub` должна быть определена с помощью модификатора `Async`, так как она содержит выражение `Await`.

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
