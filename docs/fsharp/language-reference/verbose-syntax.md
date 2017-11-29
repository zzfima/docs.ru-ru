---
title: "Подробный синтаксис (F#)"
description: "Различие между verbose и упрощенный синтаксис в языке F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0a6792b3-b312-4453-a025-21d9760eee5d
ms.openlocfilehash: 2cef359a879897825733a3186be97b38896f5953
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="verbose-syntax"></a>Подробный синтаксис

Существует две формы синтаксиса для многих конструкций в языке F #: *подробный синтаксис* и *упрощенный синтаксис*. Подробный синтаксис используется не так часто, но имеет преимущество меньшей чувствительности к отступов. Упрощенный синтаксис короче и использование отступов для обозначения начала и окончания конструкций вместо дополнительных ключевых слов, например `begin`, `end`, `in`, и т. д. По умолчанию используется упрощенный синтаксис. В этом разделе описывается синтаксис, конструкций F #, когда упрощенный синтаксис не включен. Подробный синтаксис всегда включен, поэтому даже при включении упрощенный синтаксис, можно по-прежнему использовать подробный синтаксис для некоторых конструкций. Упрощенный синтаксис можно отключить с помощью `#light "off"` директивы.


## <a name="table-of-constructs"></a>Таблица конструкций
В следующей таблице показаны упрощенный и подробный синтаксис конструкций языка F # в контекстах, где есть различие между ними. В этой таблице в угловые скобки (&lt;&gt;) включать в себя элементы синтаксиса, предоставленное пользователем. Обратитесь к документации для каждой языковой конструкции более подробные сведения о синтаксисе, используемом в этих конструкций.



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

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


вложенные `let` привязки

</td><td>
```
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```
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

```
(
    <expression1>
    <expression2>
)
```

</td><td>

```
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

```
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

```
while <condition> do
    ...
```

</td><td>

```
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```
for var in start .. finish do
    ...
```

</td><td>

```
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```
do
    ...
```

</td><td>

```
do
    ...
in
```

</td>
</tr>
<tr><td>record
</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```
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
```
type <class-name>(<params>) = ... ```

</td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td>структура</td><td>

```
[<StructAttribute>]
type <structure-name> =
    ...
```
</td><td>

```
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td>размеченные объединения</td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```
</td><td>

```
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

```
type <interface-name> =
    ...
```
</td><td>

```
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td>выражение объекта</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```
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

```
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>Тип расширения</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>module</td><td>

```
module <module-name> =
    ...
```

</td><td>

```
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>



## <a name="see-also"></a>См. также
[Справочник по языку F#](index.md)

[Директивы компилятора](compiler-directives.md)

[Рекомендации по форматированию кода](code-formatting-guidelines.md)
