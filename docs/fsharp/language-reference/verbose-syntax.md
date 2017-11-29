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
# <a name="verbose-syntax"></a><span data-ttu-id="09757-104">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="09757-104">Verbose Syntax</span></span>

<span data-ttu-id="09757-105">Существует две формы синтаксиса для многих конструкций в языке F #: *подробный синтаксис* и *упрощенный синтаксис*.</span><span class="sxs-lookup"><span data-stu-id="09757-105">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="09757-106">Подробный синтаксис используется не так часто, но имеет преимущество меньшей чувствительности к отступов.</span><span class="sxs-lookup"><span data-stu-id="09757-106">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="09757-107">Упрощенный синтаксис короче и использование отступов для обозначения начала и окончания конструкций вместо дополнительных ключевых слов, например `begin`, `end`, `in`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="09757-107">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="09757-108">По умолчанию используется упрощенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="09757-108">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="09757-109">В этом разделе описывается синтаксис, конструкций F #, когда упрощенный синтаксис не включен.</span><span class="sxs-lookup"><span data-stu-id="09757-109">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="09757-110">Подробный синтаксис всегда включен, поэтому даже при включении упрощенный синтаксис, можно по-прежнему использовать подробный синтаксис для некоторых конструкций.</span><span class="sxs-lookup"><span data-stu-id="09757-110">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="09757-111">Упрощенный синтаксис можно отключить с помощью `#light "off"` директивы.</span><span class="sxs-lookup"><span data-stu-id="09757-111">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>


## <a name="table-of-constructs"></a><span data-ttu-id="09757-112">Таблица конструкций</span><span class="sxs-lookup"><span data-stu-id="09757-112">Table of Constructs</span></span>
<span data-ttu-id="09757-113">В следующей таблице показаны упрощенный и подробный синтаксис конструкций языка F # в контекстах, где есть различие между ними.</span><span class="sxs-lookup"><span data-stu-id="09757-113">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="09757-114">В этой таблице в угловые скобки (&lt;&gt;) включать в себя элементы синтаксиса, предоставленное пользователем.</span><span class="sxs-lookup"><span data-stu-id="09757-114">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="09757-115">Обратитесь к документации для каждой языковой конструкции более подробные сведения о синтаксисе, используемом в этих конструкций.</span><span class="sxs-lookup"><span data-stu-id="09757-115">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>



<table>
<tr>
<th><span data-ttu-id="09757-116">Языковая конструкция</span><span class="sxs-lookup"><span data-stu-id="09757-116">Language construct</span></span></th>
<th><span data-ttu-id="09757-117">Упрощенный синтаксис</span><span class="sxs-lookup"><span data-stu-id="09757-117">Lightweight syntax</span></span></th>
<th><span data-ttu-id="09757-118">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="09757-118">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="09757-119">составные выражения</span><span class="sxs-lookup"><span data-stu-id="09757-119">compound expressions</span></span>
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


<span data-ttu-id="09757-120">вложенные `let` привязки</span><span class="sxs-lookup"><span data-stu-id="09757-120">nested `let` bindings</span></span>

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
<span data-ttu-id="09757-121">блок кода</span><span class="sxs-lookup"><span data-stu-id="09757-121">code block</span></span>
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
<tr><td><span data-ttu-id="09757-122">record</span><span class="sxs-lookup"><span data-stu-id="09757-122">record</span></span>
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
<tr><td><span data-ttu-id="09757-123">класс</span><span class="sxs-lookup"><span data-stu-id="09757-123">class</span></span>
</td><td><span data-ttu-id="09757-124">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="09757-124">
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
<tr><td><span data-ttu-id="09757-125">структура</span><span class="sxs-lookup"><span data-stu-id="09757-125">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="09757-126">размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="09757-126">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="09757-127">интерфейс</span><span class="sxs-lookup"><span data-stu-id="09757-127">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="09757-128">выражение объекта</span><span class="sxs-lookup"><span data-stu-id="09757-128">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="09757-129">реализация интерфейсов</span><span class="sxs-lookup"><span data-stu-id="09757-129">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="09757-130">Тип расширения</span><span class="sxs-lookup"><span data-stu-id="09757-130">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="09757-131">module</span><span class="sxs-lookup"><span data-stu-id="09757-131">module</span></span></td><td>

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



## <a name="see-also"></a><span data-ttu-id="09757-132">См. также</span><span class="sxs-lookup"><span data-stu-id="09757-132">See Also</span></span>
[<span data-ttu-id="09757-133">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="09757-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="09757-134">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="09757-134">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="09757-135">Рекомендации по форматированию кода</span><span class="sxs-lookup"><span data-stu-id="09757-135">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
