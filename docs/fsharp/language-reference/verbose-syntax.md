---
title: Подробный синтаксис
description: Изучите разницу между подробным и упрощенным синтаксисом в языке F# программирования.
ms.date: 05/16/2016
ms.openlocfilehash: 575585b201acc1366980cfc5cf523c4117259084
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73421181"
---
# <a name="verbose-syntax"></a><span data-ttu-id="0d47b-103">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d47b-103">Verbose Syntax</span></span>

<span data-ttu-id="0d47b-104">Существует две формы синтаксиса, доступные для многих конструкций F# языка: *подробный синтаксис* и *упрощенный синтаксис*.</span><span class="sxs-lookup"><span data-stu-id="0d47b-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="0d47b-105">Синтаксис verbose не так часто используется, но имеет преимущество менее чувствительно к отступу.</span><span class="sxs-lookup"><span data-stu-id="0d47b-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="0d47b-106">Упрощенный синтаксис короче и использует отступы для обозначения начала и окончания конструкций, а не дополнительные ключевые слова, такие как `begin`, `end`, `in`и т. д.</span><span class="sxs-lookup"><span data-stu-id="0d47b-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="0d47b-107">Синтаксис по умолчанию — упрощенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="0d47b-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="0d47b-108">В этом разделе описывается синтаксис F# конструкций, если упрощенный синтаксис не включен.</span><span class="sxs-lookup"><span data-stu-id="0d47b-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="0d47b-109">Подробный синтаксис всегда включен, поэтому даже если включен упрощенный синтаксис, для некоторых конструкций по-прежнему можно использовать подробный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="0d47b-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="0d47b-110">Упрощенный синтаксис можно отключить с помощью директивы `#light "off"`.</span><span class="sxs-lookup"><span data-stu-id="0d47b-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="0d47b-111">Таблица конструкций</span><span class="sxs-lookup"><span data-stu-id="0d47b-111">Table of Constructs</span></span>

<span data-ttu-id="0d47b-112">В следующей таблице показан упрощенный и подробный синтаксис для F# языковых конструкций в контекстах, где существует разница между двумя формами.</span><span class="sxs-lookup"><span data-stu-id="0d47b-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="0d47b-113">В этой таблице угловые скобки (&lt;&gt;) заключают определяемые пользователем элементы синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="0d47b-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="0d47b-114">Более подробные сведения о синтаксисе, используемом в этих конструкциях, см. в документации по каждой языковой конструкции.</span><span class="sxs-lookup"><span data-stu-id="0d47b-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="0d47b-115">Конструкция языка</span><span class="sxs-lookup"><span data-stu-id="0d47b-115">Language construct</span></span></th>
<th><span data-ttu-id="0d47b-116">Упрощенный синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d47b-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="0d47b-117">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d47b-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="0d47b-118">составные выражения</span><span class="sxs-lookup"><span data-stu-id="0d47b-118">compound expressions</span></span>
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

<span data-ttu-id="0d47b-119">вложенные привязки `let`</span><span class="sxs-lookup"><span data-stu-id="0d47b-119">nested `let` bindings</span></span>

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
<span data-ttu-id="0d47b-120">блок кода</span><span class="sxs-lookup"><span data-stu-id="0d47b-120">code block</span></span>
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

```fsharp
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
<tr><td><span data-ttu-id="0d47b-121">record</span><span class="sxs-lookup"><span data-stu-id="0d47b-121">record</span></span>
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
<tr><td><span data-ttu-id="0d47b-122">класс</span><span class="sxs-lookup"><span data-stu-id="0d47b-122">class</span></span>
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
<tr><td><span data-ttu-id="0d47b-123">структура</span><span class="sxs-lookup"><span data-stu-id="0d47b-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="0d47b-124">размеченное объединение</span><span class="sxs-lookup"><span data-stu-id="0d47b-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="0d47b-125">interface</span><span class="sxs-lookup"><span data-stu-id="0d47b-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="0d47b-126">выражение объекта</span><span class="sxs-lookup"><span data-stu-id="0d47b-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="0d47b-127">реализация интерфейсов</span><span class="sxs-lookup"><span data-stu-id="0d47b-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="0d47b-128">расширение типа</span><span class="sxs-lookup"><span data-stu-id="0d47b-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="0d47b-129">module</span><span class="sxs-lookup"><span data-stu-id="0d47b-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="0d47b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="0d47b-130">See also</span></span>

- [<span data-ttu-id="0d47b-131">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="0d47b-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0d47b-132">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="0d47b-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="0d47b-133">Рекомендации по форматированию кода</span><span class="sxs-lookup"><span data-stu-id="0d47b-133">Code Formatting Guidelines</span></span>](../style-guide/formatting.md)
