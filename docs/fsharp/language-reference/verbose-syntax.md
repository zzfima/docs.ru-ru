---
title: Подробный синтаксис (F#)
description: 'О различиях между verbose и упрощенный синтаксис в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: b4f2354738da4692cb444e5e7dd9531d80d26664
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44063122"
---
# <a name="verbose-syntax"></a><span data-ttu-id="69b6e-103">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="69b6e-103">Verbose Syntax</span></span>

<span data-ttu-id="69b6e-104">Существуют две формы синтаксиса для многих конструкций на языке F #: *подробный синтаксис* и *упрощенный синтаксис*.</span><span class="sxs-lookup"><span data-stu-id="69b6e-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="69b6e-105">Подробный синтаксис используется не так часто, но имеет преимущество меньшей чувствительности к отступа.</span><span class="sxs-lookup"><span data-stu-id="69b6e-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="69b6e-106">Упрощенный синтаксис короче и использование отступов для обозначения начала и конца конструкции, а не дополнительные ключевые слова, такие как `begin`, `end`, `in`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="69b6e-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="69b6e-107">По умолчанию используется упрощенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="69b6e-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="69b6e-108">В этом разделе описывает синтаксис для конструкций F #, когда упрощенный синтаксис отключен.</span><span class="sxs-lookup"><span data-stu-id="69b6e-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="69b6e-109">Подробный синтаксис всегда включен, поэтому даже если включен упрощенный синтаксис, можно по-прежнему использовать подробный синтаксис для некоторых конструкций.</span><span class="sxs-lookup"><span data-stu-id="69b6e-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="69b6e-110">Упрощенный синтаксис можно отключить с помощью `#light "off"` директива.</span><span class="sxs-lookup"><span data-stu-id="69b6e-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="69b6e-111">Таблица конструкций</span><span class="sxs-lookup"><span data-stu-id="69b6e-111">Table of Constructs</span></span>

<span data-ttu-id="69b6e-112">В следующей таблице показаны упрощенный и подробный синтаксис для конструкций языка F # в контекстах, где есть разница между двумя формами.</span><span class="sxs-lookup"><span data-stu-id="69b6e-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="69b6e-113">В этой таблице в угловые скобки (&lt;&gt;) заключать элементы синтаксиса, предоставленное пользователем.</span><span class="sxs-lookup"><span data-stu-id="69b6e-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="69b6e-114">Обратитесь к документации для каждой языковой конструкции, более подробные сведения о синтаксисе, используемом в этих конструкций.</span><span class="sxs-lookup"><span data-stu-id="69b6e-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="69b6e-115">Языковая конструкция</span><span class="sxs-lookup"><span data-stu-id="69b6e-115">Language construct</span></span></th>
<th><span data-ttu-id="69b6e-116">Упрощенный синтаксис</span><span class="sxs-lookup"><span data-stu-id="69b6e-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="69b6e-117">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="69b6e-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="69b6e-118">составные выражения</span><span class="sxs-lookup"><span data-stu-id="69b6e-118">compound expressions</span></span>
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


<span data-ttu-id="69b6e-119">вложенные `let` привязки</span><span class="sxs-lookup"><span data-stu-id="69b6e-119">nested `let` bindings</span></span>

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
<span data-ttu-id="69b6e-120">блок кода</span><span class="sxs-lookup"><span data-stu-id="69b6e-120">code block</span></span>
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
<tr><td><span data-ttu-id="69b6e-121">record</span><span class="sxs-lookup"><span data-stu-id="69b6e-121">record</span></span>
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
<tr><td><span data-ttu-id="69b6e-122">класс</span><span class="sxs-lookup"><span data-stu-id="69b6e-122">class</span></span>
</td><td><span data-ttu-id="69b6e-123">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="69b6e-123">
```
type <class-name>(<params>) = ... ```

</span></span></td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td><span data-ttu-id="69b6e-124">структура</span><span class="sxs-lookup"><span data-stu-id="69b6e-124">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="69b6e-125">размеченное объединение</span><span class="sxs-lookup"><span data-stu-id="69b6e-125">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="69b6e-126">интерфейс</span><span class="sxs-lookup"><span data-stu-id="69b6e-126">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="69b6e-127">выражение объекта</span><span class="sxs-lookup"><span data-stu-id="69b6e-127">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="69b6e-128">реализация интерфейсов</span><span class="sxs-lookup"><span data-stu-id="69b6e-128">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="69b6e-129">расширение типа</span><span class="sxs-lookup"><span data-stu-id="69b6e-129">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="69b6e-130">module</span><span class="sxs-lookup"><span data-stu-id="69b6e-130">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="69b6e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="69b6e-131">See also</span></span>

- [<span data-ttu-id="69b6e-132">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="69b6e-132">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="69b6e-133">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="69b6e-133">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="69b6e-134">Рекомендации по форматированию кода</span><span class="sxs-lookup"><span data-stu-id="69b6e-134">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
