---
title: Подробный синтаксис
description: О различиях между verbose и упрощенный синтаксис в F# языка программирования.
ms.date: 05/16/2016
ms.openlocfilehash: 05b909d438e9844ad5adcb2a4087ce04f8999751
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610896"
---
# <a name="verbose-syntax"></a>Подробный синтаксис

Существуют две формы синтаксиса для многих конструкций в F# языка: *подробный синтаксис* и *упрощенный синтаксис*. Подробный синтаксис используется не так часто, но имеет преимущество меньшей чувствительности к отступа. Упрощенный синтаксис короче и использование отступов для обозначения начала и конца конструкции, а не дополнительные ключевые слова, такие как `begin`, `end`, `in`, и т. д. По умолчанию используется упрощенный синтаксис. В этом разделе описывается синтаксис F# конструкции, когда упрощенный синтаксис отключен. Подробный синтаксис всегда включен, поэтому даже если включен упрощенный синтаксис, можно по-прежнему использовать подробный синтаксис для некоторых конструкций. Упрощенный синтаксис можно отключить с помощью `#light "off"` директива.

## <a name="table-of-constructs"></a>Таблица конструкций

В следующей таблице показаны упрощенный и подробный синтаксис F# языковые конструкции в контекстах, где есть разница между двумя формами. В этой таблице в угловые скобки (&lt;&gt;) заключать элементы синтаксиса, предоставленное пользователем. Обратитесь к документации для каждой языковой конструкции, более подробные сведения о синтаксисе, используемом в этих конструкций.

<table>
<tr>
<th>Языковая конструкция</th>
<th>Упрощенный синтаксис</th>
<th>Подробный синтаксис</th>
</tr>
<tr>
<td>
составные выражения
</td>
<td>

```xml
<expression1>
<expression2>
```
</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

вложенные `let` привязки

</td><td>

```fsharp
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```fsharp
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
блок кода
</td><td>

```fsharp
(
    <expression1>
    <expression2>
)
```

</td><td>

```fsharp
begin
    <expression1>;
    <expression2>;
end
```
</td>
</tr>
<tr><td>
`for...do`
</td><td>

```fsharp
for counter = start to finish do
    ...
```

</td><td>

```
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```fsharp
while <condition> do
    ...
```

</td><td>

```fsharp
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```fsharp
for var in start .. finish do
    ...
```

</td><td>

```fsharp
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```fsharp
do
    ...
```

</td><td>

```fsharp
do
    ...
in
```

</td>
</tr>
<tr><td>record
</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>класс
</td><td>

```fsharp
type <class-name>(<params>) =
    ...
```

</td><td>

```fsharp
type <class-name>(<params>) =
    class
        ...
    end
```

</td>
</tr>
<tr><td>структура</td><td>

```fsharp
[<StructAttribute>]
type <structure-name> =
    ...
```

</td><td>

```fsharp
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td>размеченное объединение</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```

</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end    
```

</td>
</tr>
<tr><td>интерфейс</td><td>

```fsharp
type <interface-name> =
    ...
```
</td><td>

```fsharp
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td>выражение объекта</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td>реализация интерфейсов</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>расширение типа</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>module</td><td>

```fsharp
module <module-name> =
    ...
```

</td><td>

```fsharp
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Директивы компилятора](compiler-directives.md)
- [Рекомендации по форматированию кода](code-formatting-guidelines.md)