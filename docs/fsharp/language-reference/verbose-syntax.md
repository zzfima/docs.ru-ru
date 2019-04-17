---
title: Подробный синтаксис
description: О различиях между verbose и упрощенный синтаксис в F# языка программирования.
ms.date: 05/16/2016
ms.openlocfilehash: c770f2843276619cb2878198a537dcfb9c054b6b
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613789"
---
# <a name="verbose-syntax"></a><span data-ttu-id="35ada-103">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="35ada-103">Verbose Syntax</span></span>

<span data-ttu-id="35ada-104">Существуют две формы синтаксиса для многих конструкций в F# языка: *подробный синтаксис* и *упрощенный синтаксис*.</span><span class="sxs-lookup"><span data-stu-id="35ada-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="35ada-105">Подробный синтаксис используется не так часто, но имеет преимущество меньшей чувствительности к отступа.</span><span class="sxs-lookup"><span data-stu-id="35ada-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="35ada-106">Упрощенный синтаксис короче и использование отступов для обозначения начала и конца конструкции, а не дополнительные ключевые слова, такие как `begin`, `end`, `in`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="35ada-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="35ada-107">По умолчанию используется упрощенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="35ada-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="35ada-108">В этом разделе описывается синтаксис F# конструкции, когда упрощенный синтаксис отключен.</span><span class="sxs-lookup"><span data-stu-id="35ada-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="35ada-109">Подробный синтаксис всегда включен, поэтому даже если включен упрощенный синтаксис, можно по-прежнему использовать подробный синтаксис для некоторых конструкций.</span><span class="sxs-lookup"><span data-stu-id="35ada-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="35ada-110">Упрощенный синтаксис можно отключить с помощью `#light "off"` директива.</span><span class="sxs-lookup"><span data-stu-id="35ada-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="35ada-111">Таблица конструкций</span><span class="sxs-lookup"><span data-stu-id="35ada-111">Table of Constructs</span></span>

<span data-ttu-id="35ada-112">В следующей таблице показаны упрощенный и подробный синтаксис F# языковые конструкции в контекстах, где есть разница между двумя формами.</span><span class="sxs-lookup"><span data-stu-id="35ada-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="35ada-113">В этой таблице в угловые скобки (&lt;&gt;) заключать элементы синтаксиса, предоставленное пользователем.</span><span class="sxs-lookup"><span data-stu-id="35ada-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="35ada-114">Обратитесь к документации для каждой языковой конструкции, более подробные сведения о синтаксисе, используемом в этих конструкций.</span><span class="sxs-lookup"><span data-stu-id="35ada-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="35ada-115">Языковая конструкция</span><span class="sxs-lookup"><span data-stu-id="35ada-115">Language construct</span></span></th>
<th><span data-ttu-id="35ada-116">Упрощенный синтаксис</span><span class="sxs-lookup"><span data-stu-id="35ada-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="35ada-117">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="35ada-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="35ada-118">составные выражения</span><span class="sxs-lookup"><span data-stu-id="35ada-118">compound expressions</span></span>
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

<span data-ttu-id="35ada-119">вложенные `let` привязки</span><span class="sxs-lookup"><span data-stu-id="35ada-119">nested `let` bindings</span></span>

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
<span data-ttu-id="35ada-120">блок кода</span><span class="sxs-lookup"><span data-stu-id="35ada-120">code block</span></span>
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
<tr><td><span data-ttu-id="35ada-121">record</span><span class="sxs-lookup"><span data-stu-id="35ada-121">record</span></span>
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
<tr><td><span data-ttu-id="35ada-122">класс</span><span class="sxs-lookup"><span data-stu-id="35ada-122">class</span></span>
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
<tr><td><span data-ttu-id="35ada-123">структура</span><span class="sxs-lookup"><span data-stu-id="35ada-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="35ada-124">размеченное объединение</span><span class="sxs-lookup"><span data-stu-id="35ada-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="35ada-125">интерфейс</span><span class="sxs-lookup"><span data-stu-id="35ada-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="35ada-126">выражение объекта</span><span class="sxs-lookup"><span data-stu-id="35ada-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="35ada-127">реализация интерфейсов</span><span class="sxs-lookup"><span data-stu-id="35ada-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="35ada-128">расширение типа</span><span class="sxs-lookup"><span data-stu-id="35ada-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="35ada-129">module</span><span class="sxs-lookup"><span data-stu-id="35ada-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="35ada-130">См. также</span><span class="sxs-lookup"><span data-stu-id="35ada-130">See also</span></span>

- [<span data-ttu-id="35ada-131">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="35ada-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="35ada-132">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="35ada-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="35ada-133">Рекомендации по форматированию кода</span><span class="sxs-lookup"><span data-stu-id="35ada-133">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)