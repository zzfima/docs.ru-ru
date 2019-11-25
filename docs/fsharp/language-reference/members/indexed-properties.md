---
title: Индексированные свойства
description: Сведения об индексированных свойствах F#в, которые позволяют обращаться к упорядоченным данным по подобному массиву.
ms.date: 11/04/2019
ms.openlocfilehash: f6cf3bfa737d2bf458e379594be5884696cee3e1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976602"
---
# <a name="indexed-properties"></a><span data-ttu-id="9ccf3-103">Индексированные свойства</span><span class="sxs-lookup"><span data-stu-id="9ccf3-103">Indexed Properties</span></span>

<span data-ttu-id="9ccf3-104">При определении класса, который является абстрактным по отношению к упорядоченным данным, иногда может быть полезно предоставить индексированный доступ к этим данным без предоставления базовой реализации.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="9ccf3-105">Это выполняется с помощью элемента `Item`.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-105">This is done with the `Item` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="9ccf3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ccf3-106">Syntax</span></span>

```fsharp
// Indexed property that can be read and written to
member self-identifier.Item
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property can only be read
member self-identifier.Item
    with get(index-values) =
        get-member-body

// Indexed property that can only be set
member self-identifier.Item
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="9ccf3-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="9ccf3-107">Remarks</span></span>

<span data-ttu-id="9ccf3-108">Формы предыдущего синтаксиса показывают, как определить индексированные свойства, которые содержат как `get`, так и метод `set`, иметь только метод `get` или только метод `set`.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="9ccf3-109">Можно также сочетать синтаксис, показанный только для Get, и синтаксис, показанный только для Set, и создать свойство, которое имеет и Get, и Set.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="9ccf3-110">Эта последняя форма позволяет размещать в методах get и Set разные модификаторы и атрибуты доступа.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="9ccf3-111">При использовании имени `Item`компилятор рассматривает свойство как индексированное свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="9ccf3-112">*Индексированное свойство по умолчанию* — это свойство, доступ к которому можно получить с помощью синтаксиса, подобного массиву, в экземпляре объекта.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="9ccf3-113">Например, если `o` является объектом типа, определяющего это свойство, то синтаксис `o.[index]` используется для доступа к свойству.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="9ccf3-114">Синтаксис для доступа к индексированному свойству, не являющемуся по умолчанию, заключается в предоставлении имени свойства и индекса в круглых скобках, как и обычный элемент.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="9ccf3-115">Например, если свойство в `o` называется `Ordinal`, для доступа к нему `o.Ordinal(index)`ся запись.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="9ccf3-116">Независимо от используемой формы следует всегда использовать каррированных вида метода Set для индексированного свойства.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="9ccf3-117">Дополнительные сведения о каррированных функциях см. в разделе [функции](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="9ccf3-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="9ccf3-118">Пример</span><span class="sxs-lookup"><span data-stu-id="9ccf3-118">Example</span></span>

<span data-ttu-id="9ccf3-119">В следующем примере кода показано определение и использование индексированных свойств по умолчанию и не являющихся свойствами по умолчанию, имеющих методы get и Set.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="9ccf3-120">Вывод</span><span class="sxs-lookup"><span data-stu-id="9ccf3-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="9ccf3-121">Индексированные свойства с несколькими значениями индекса</span><span class="sxs-lookup"><span data-stu-id="9ccf3-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="9ccf3-122">Индексированные свойства могут иметь более одного значения индекса.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="9ccf3-123">В этом случае при использовании свойства значения разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="9ccf3-124">Метод Set в таком свойстве должен иметь два каррированных аргумента, первый из которых является кортежем, содержащим ключи, а второй — заданным значением.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="9ccf3-125">В следующем коде показано использование индексированного свойства с несколькими значениями индекса.</span><span class="sxs-lookup"><span data-stu-id="9ccf3-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member _.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="9ccf3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="9ccf3-126">See also</span></span>

- [<span data-ttu-id="9ccf3-127">Члены</span><span class="sxs-lookup"><span data-stu-id="9ccf3-127">Members</span></span>](index.md)
