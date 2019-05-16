---
title: Ограничения
description: Дополнительные сведения о F# ограничений, относящихся к параметров универсального типа для задания требований к аргументу типа в универсальном типе или функции.
ms.date: 05/16/2016
ms.openlocfilehash: 1bf5c6fc4df6c8f2f7f969bd13030172c6b8aab9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645286"
---
# <a name="constraints"></a>Ограничения

В этом разделе описываются ограничения, которые можно применять к универсальным введите параметры для задания требований к аргументу типа в универсальном типе или функции.

## <a name="syntax"></a>Синтаксис

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>Примечания

Существует несколько ограничений, которые можно применить ограничивает типы, которые могут использоваться в универсальном типе. В следующей таблице перечислены и описаны эти ограничения.

|Ограничение|Синтаксис|Описание|
|----------|------|-----------|
|Ограничения типа|*параметр типа* :&gt; *типа*|Указанный тип должен быть равным или быть производным от указанного типа или, если тип является интерфейсом, предоставленный тип должен реализовывать интерфейс.|
|Ограничение NULL|*параметр типа* : null|Переданный тип должен поддерживать литерал null. Сюда входят все типы объектов .NET, но не F# списка, кортежа, функции, класса, записи или типы объединений.|
|Ограничение явных членов|[(]*параметр типа* [или... или *параметр типа*)]: (*сигнатура члена*)|Хотя бы один из переданных аргументов типа должен иметь член, имеющий указанную подпись; не предназначен для общего пользования. Члены должны быть либо явно определены в тип или частью неявный тип расширения, чтобы быть допустимыми целевыми объектами для явное ограничение члена.|
|Ограничение конструктора|*параметр типа* : (новых: единица -&gt; ")|Указанный тип должен иметь конструктор по умолчанию.|
|Ограничение типа значения|: структура|Указанный тип должен быть типом значения .NET.|
|Ограничение ссылочного типа|: не структуры|Переданный тип должен быть ссылочным типом .NET.|
|Ограничение типа перечисления|: перечисление&lt;*базовый тип*&gt;|Указанный тип должен быть перечислимый тип с указанным базовым типом; не предназначен для общего пользования.|
|Ограничения делегата|: делегировать&lt;*параметра типа кортежа*, *типа возвращаемого значения*&gt;|Указанный тип должен быть типом делегата, с заданными аргументами и возвращаемое значение; не предназначен для общего пользования.|
|Ограничение по сравнению|: сравнение|Переданный тип должен поддерживать сравнение.|
|Ограничения равенства|: на равенство|Переданный тип должен поддерживать на равенство.|
|Неуправляемое ограничение|: неуправляемые|Переданный тип должен быть неуправляемого типа. Неуправляемые типы являются определенных примитивных типов (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, или `decimal`), типы перечисления `nativeptr<_>`, или к неуниверсальным структуры, поля которого предназначены всех неуправляемых типов.|

Необходимо добавить ограничение в том случае, если код должен использовать функцию, которая доступна на тип ограничения, но не для типов в целом. Например если ограничение типа используется для указания типа класса, можно использовать одного из методов этого класса в универсальной функции или типа.

Указание ограничений иногда это необходимо при написании параметры типа явно, так как без ограничения, компилятор не может проверить, что функции, которые вы используете, будут доступны для любого типа, может потребоваться указать во время выполнения для типа параметр.

В наиболее распространенных ограничений F# кода являются ограничения типа, которые задают базовые классы или интерфейсы. Другие ограничения либо используются в F# библиотеки для реализации определенных функций, таких как ограничения явных членов, которое используется для реализации перегрузки операторов для арифметических операторов или предоставляются в основном потому, что F# поддерживает полный набор ограничений, поддерживаемый средой CLR.

В процессе вывода типа некоторые ограничения автоматически выводятся компилятором. Например, если вы используете `+` оператор в функции, компилятор выводит явных членов ограничения на типы переменных, которые используются в выражении.

Следующий код иллюстрирует некоторые объявления ограничение.

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a>См. также

- [Универсальные шаблоны](index.md)
- [Ограничения](constraints.md)
