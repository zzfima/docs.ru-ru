---
title: Индексированные свойства (F#)
description: Дополнительные сведения о индексированных свойств в F#, разрешающее для доступ через массив к упорядоченных данных.
ms.date: 10/17/2018
ms.openlocfilehash: 3dac60eba3d9e7a9c3e76ad7ee051e6b30b88636
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452252"
---
# <a name="indexed-properties"></a><span data-ttu-id="61400-103">Индексированные свойства</span><span class="sxs-lookup"><span data-stu-id="61400-103">Indexed Properties</span></span>

<span data-ttu-id="61400-104">При определении класс, который абстрагирует упорядоченный данными, иногда бывает полезно предоставить индексированный доступ к этим данным без предоставления базовой реализации.</span><span class="sxs-lookup"><span data-stu-id="61400-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="61400-105">Это делается с помощью `Index` член.</span><span class="sxs-lookup"><span data-stu-id="61400-105">This is done with the `Index` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="61400-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61400-106">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.Index
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property with get only
member self-identifier.Index
    with get(index-values) =
        get-member-body

// Indexed property that has set only.
member self-identifier.Index
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="61400-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="61400-107">Remarks</span></span>

<span data-ttu-id="61400-108">Виды выше синтаксисе показано, как определять индексированные свойства, для которых имеются обе `get` и `set` метод, имеют `get` только метод или иметь `set` только метод.</span><span class="sxs-lookup"><span data-stu-id="61400-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="61400-109">Можно также комбинировать синтаксис, показанный для get только и синтаксис, показанный для набора только и получения свойства с get и set.</span><span class="sxs-lookup"><span data-stu-id="61400-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="61400-110">Эта последняя форма позволяет поместить различные модификаторы доступности и атрибуты на get и методы работы с наборами.</span><span class="sxs-lookup"><span data-stu-id="61400-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="61400-111">С помощью имени `Item`, компилятор считает свойство по умолчанию индексированное свойство.</span><span class="sxs-lookup"><span data-stu-id="61400-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="61400-112">Объект *индексированное свойство по умолчанию* — это свойство, можно получить доступ, используя синтаксис, подобный массиву в экземпляре объекта.</span><span class="sxs-lookup"><span data-stu-id="61400-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="61400-113">Например если `o` — это объект типа, который определяет данное свойство синтаксис `o.[index]` используется для доступа к свойству.</span><span class="sxs-lookup"><span data-stu-id="61400-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="61400-114">Синтаксис для доступа к не по умолчанию индексированное свойство является предоставление имени свойства и индекс в круглые скобки, так же, как обычный член.</span><span class="sxs-lookup"><span data-stu-id="61400-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="61400-115">Например если свойство `o` называется `Ordinal`, написании `o.Ordinal(index)` для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="61400-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="61400-116">Независимо от того, какая форма используется следует всегда использовать Каррированная форма для метода set по индексированному свойству.</span><span class="sxs-lookup"><span data-stu-id="61400-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="61400-117">Сведения о каррированные функции, см. в разделе [функции](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="61400-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="61400-118">Пример</span><span class="sxs-lookup"><span data-stu-id="61400-118">Example</span></span>

<span data-ttu-id="61400-119">В следующем примере кода показано определение и использование по умолчанию и не по умолчанию индексированные свойства, которые имеют get и методы работы с наборами.</span><span class="sxs-lookup"><span data-stu-id="61400-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="61400-120">Вывод</span><span class="sxs-lookup"><span data-stu-id="61400-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="61400-121">Индексированные свойства с несколькими переменными индекса</span><span class="sxs-lookup"><span data-stu-id="61400-121">Indexed Properties with Multiple Index Variables</span></span>

<span data-ttu-id="61400-122">Индексированные свойства могут иметь более одной переменной индекса.</span><span class="sxs-lookup"><span data-stu-id="61400-122">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="61400-123">В этом случае переменные разделяются запятыми при использовании свойства.</span><span class="sxs-lookup"><span data-stu-id="61400-123">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="61400-124">Метод set в такое свойство должен иметь два каррированных аргумента, первый из которых представляет собой кортеж, содержащий ключи, а второй — задаваемое значение.</span><span class="sxs-lookup"><span data-stu-id="61400-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="61400-125">Следующий код демонстрирует использование индексированного свойства с несколькими переменными индекса.</span><span class="sxs-lookup"><span data-stu-id="61400-125">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a><span data-ttu-id="61400-126">См. также</span><span class="sxs-lookup"><span data-stu-id="61400-126">See also</span></span>

- [<span data-ttu-id="61400-127">Члены</span><span class="sxs-lookup"><span data-stu-id="61400-127">Members</span></span>](index.md)
