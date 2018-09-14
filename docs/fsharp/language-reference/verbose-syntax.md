---
title: Подробный синтаксис (F#)
description: 'О различиях между verbose и упрощенный синтаксис в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: b4f2354738da4692cb444e5e7dd9531d80d26664
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45589317"
---
# <a name="verbose-syntax"></a><span data-ttu-id="032a4-103">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="032a4-103">Verbose Syntax</span></span>

<span data-ttu-id="032a4-104">Существуют две формы синтаксиса для многих конструкций на языке F #: *подробный синтаксис* и *упрощенный синтаксис*.</span><span class="sxs-lookup"><span data-stu-id="032a4-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="032a4-105">Подробный синтаксис используется не так часто, но имеет преимущество меньшей чувствительности к отступа.</span><span class="sxs-lookup"><span data-stu-id="032a4-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="032a4-106">Упрощенный синтаксис короче и использование отступов для обозначения начала и конца конструкции, а не дополнительные ключевые слова, такие как `begin`, `end`, `in`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="032a4-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="032a4-107">По умолчанию используется упрощенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="032a4-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="032a4-108">В этом разделе описывает синтаксис для конструкций F #, когда упрощенный синтаксис отключен.</span><span class="sxs-lookup"><span data-stu-id="032a4-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="032a4-109">Подробный синтаксис всегда включен, поэтому даже если включен упрощенный синтаксис, можно по-прежнему использовать подробный синтаксис для некоторых конструкций.</span><span class="sxs-lookup"><span data-stu-id="032a4-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="032a4-110">Упрощенный синтаксис можно отключить с помощью `#light "off"` директива.</span><span class="sxs-lookup"><span data-stu-id="032a4-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="032a4-111">Таблица конструкций</span><span class="sxs-lookup"><span data-stu-id="032a4-111">Table of Constructs</span></span>

<span data-ttu-id="032a4-112">В следующей таблице показаны упрощенный и подробный синтаксис для конструкций языка F # в контекстах, где есть разница между двумя формами.</span><span class="sxs-lookup"><span data-stu-id="032a4-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="032a4-113">В этой таблице в угловые скобки (&lt;&gt;) заключать элементы синтаксиса, предоставленное пользователем.</span><span class="sxs-lookup"><span data-stu-id="032a4-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="032a4-114">Обратитесь к документации для каждой языковой конструкции, более подробные сведения о синтаксисе, используемом в этих конструкций.</span><span class="sxs-lookup"><span data-stu-id="032a4-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="032a4-115">Языковая конструкция</span><span class="sxs-lookup"><span data-stu-id="032a4-115">Language construct</span></span></th>
<th><span data-ttu-id="032a4-116">Упрощенный синтаксис</span><span class="sxs-lookup"><span data-stu-id="032a4-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="032a4-117">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="032a4-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="032a4-118">составные выражения</span><span class="sxs-lookup"><span data-stu-id="032a4-118">compound expressions</span></span>
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


<span data-ttu-id="032a4-119">вложенные `let` привязки</span><span class="sxs-lookup"><span data-stu-id="032a4-119">nested `let` bindings</span></span>

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
<span data-ttu-id="032a4-120">блок кода</span><span class="sxs-lookup"><span data-stu-id="032a4-120">code block</span></span>
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
<tr><td><span data-ttu-id="032a4-121">record</span><span class="sxs-lookup"><span data-stu-id="032a4-121">record</span></span>
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
<tr><td><span data-ttu-id="032a4-122">класс</span><span class="sxs-lookup"><span data-stu-id="032a4-122">class</span></span>
</td><td><span data-ttu-id="032a4-123">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="032a4-123">
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
<tr><td><span data-ttu-id="032a4-124">структура</span><span class="sxs-lookup"><span data-stu-id="032a4-124">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="032a4-125">размеченное объединение</span><span class="sxs-lookup"><span data-stu-id="032a4-125">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="032a4-126">интерфейс</span><span class="sxs-lookup"><span data-stu-id="032a4-126">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="032a4-127">выражение объекта</span><span class="sxs-lookup"><span data-stu-id="032a4-127">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="032a4-128">реализация интерфейсов</span><span class="sxs-lookup"><span data-stu-id="032a4-128">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="032a4-129">расширение типа</span><span class="sxs-lookup"><span data-stu-id="032a4-129">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="032a4-130">module</span><span class="sxs-lookup"><span data-stu-id="032a4-130">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="032a4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="032a4-131">See also</span></span>

- [<span data-ttu-id="032a4-132">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="032a4-132">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="032a4-133">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="032a4-133">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="032a4-134">Рекомендации по форматированию кода</span><span class="sxs-lookup"><span data-stu-id="032a4-134">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
