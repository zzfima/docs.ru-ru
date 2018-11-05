---
title: Подробный синтаксис (F#)
description: О различиях между verbose и упрощенный синтаксис в языке F#.
ms.date: 05/16/2016
ms.openlocfilehash: e697c6fe619df7ffe12f7d4e2a234a5a5cb401ff
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "50196769"
---
# <a name="verbose-syntax"></a><span data-ttu-id="f217c-103">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="f217c-103">Verbose Syntax</span></span>

<span data-ttu-id="f217c-104">Существуют две формы синтаксиса для многих конструкций на языке F#: *подробный синтаксис* и *упрощенный синтаксис*.</span><span class="sxs-lookup"><span data-stu-id="f217c-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="f217c-105">Подробный синтаксис используется не так часто, но имеет преимущество меньшей чувствительности к отступа.</span><span class="sxs-lookup"><span data-stu-id="f217c-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="f217c-106">Упрощенный синтаксис короче и использование отступов для обозначения начала и конца конструкции, а не дополнительные ключевые слова, такие как `begin`, `end`, `in`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="f217c-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="f217c-107">По умолчанию используется упрощенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="f217c-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="f217c-108">В этом разделе описывает синтаксис для конструкций F#, когда упрощенный синтаксис отключен.</span><span class="sxs-lookup"><span data-stu-id="f217c-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="f217c-109">Подробный синтаксис всегда включен, поэтому даже если включен упрощенный синтаксис, можно по-прежнему использовать подробный синтаксис для некоторых конструкций.</span><span class="sxs-lookup"><span data-stu-id="f217c-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="f217c-110">Упрощенный синтаксис можно отключить с помощью `#light "off"` директива.</span><span class="sxs-lookup"><span data-stu-id="f217c-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="f217c-111">Таблица конструкций</span><span class="sxs-lookup"><span data-stu-id="f217c-111">Table of Constructs</span></span>

<span data-ttu-id="f217c-112">В следующей таблице показаны упрощенный и подробный синтаксис для конструкций языка F# в контекстах, где есть разница между двумя формами.</span><span class="sxs-lookup"><span data-stu-id="f217c-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="f217c-113">В этой таблице в угловые скобки (&lt;&gt;) заключать элементы синтаксиса, предоставленное пользователем.</span><span class="sxs-lookup"><span data-stu-id="f217c-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="f217c-114">Обратитесь к документации для каждой языковой конструкции, более подробные сведения о синтаксисе, используемом в этих конструкций.</span><span class="sxs-lookup"><span data-stu-id="f217c-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="f217c-115">Языковая конструкция</span><span class="sxs-lookup"><span data-stu-id="f217c-115">Language construct</span></span></th>
<th><span data-ttu-id="f217c-116">Упрощенный синтаксис</span><span class="sxs-lookup"><span data-stu-id="f217c-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="f217c-117">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="f217c-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="f217c-118">составные выражения</span><span class="sxs-lookup"><span data-stu-id="f217c-118">compound expressions</span></span>
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

<span data-ttu-id="f217c-119">вложенные `let` привязки</span><span class="sxs-lookup"><span data-stu-id="f217c-119">nested `let` bindings</span></span>

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
<span data-ttu-id="f217c-120">блок кода</span><span class="sxs-lookup"><span data-stu-id="f217c-120">code block</span></span>
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
<tr><td><span data-ttu-id="f217c-121">record</span><span class="sxs-lookup"><span data-stu-id="f217c-121">record</span></span>
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
<tr><td><span data-ttu-id="f217c-122">класс</span><span class="sxs-lookup"><span data-stu-id="f217c-122">class</span></span>
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
<tr><td><span data-ttu-id="f217c-123">структура</span><span class="sxs-lookup"><span data-stu-id="f217c-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="f217c-124">размеченное объединение</span><span class="sxs-lookup"><span data-stu-id="f217c-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="f217c-125">интерфейс</span><span class="sxs-lookup"><span data-stu-id="f217c-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="f217c-126">выражение объекта</span><span class="sxs-lookup"><span data-stu-id="f217c-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="f217c-127">реализация интерфейсов</span><span class="sxs-lookup"><span data-stu-id="f217c-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="f217c-128">расширение типа</span><span class="sxs-lookup"><span data-stu-id="f217c-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="f217c-129">module</span><span class="sxs-lookup"><span data-stu-id="f217c-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="f217c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f217c-130">See also</span></span>

- [<span data-ttu-id="f217c-131">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="f217c-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f217c-132">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="f217c-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="f217c-133">Рекомендации по форматированию кода</span><span class="sxs-lookup"><span data-stu-id="f217c-133">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
