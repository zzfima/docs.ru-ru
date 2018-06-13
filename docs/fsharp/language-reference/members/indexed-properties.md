---
title: Индексированные свойства (F#)
description: 'Дополнительные сведения о F # индексированные свойства, которые являются свойства, предоставляющие доступ через массив к упорядоченным данным.'
ms.date: 05/16/2016
ms.openlocfilehash: 503cef9693cfe5e13d4e2d19a721d65bff1ce749
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235945"
---
# <a name="indexed-properties"></a><span data-ttu-id="89168-103">Индексированные свойства</span><span class="sxs-lookup"><span data-stu-id="89168-103">Indexed Properties</span></span>

<span data-ttu-id="89168-104">*Индексированные свойства* свойства, предоставляющие доступ через массив к упорядочиваются данные.</span><span class="sxs-lookup"><span data-stu-id="89168-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span> <span data-ttu-id="89168-105">Они бывают трех видов:</span><span class="sxs-lookup"><span data-stu-id="89168-105">They come in three forms:</span></span>

* `Item`
* `Ordinal`
* `Cardinal`

<span data-ttu-id="89168-106">F # член должен иметь имя одного из этих трех имен, чтобы предоставить доступ через массив.</span><span class="sxs-lookup"><span data-stu-id="89168-106">An F# member must be named one of these three names to provide array-like access.</span></span> <span data-ttu-id="89168-107">`IndexerName` используется для представления любого из этих трех параметров:</span><span class="sxs-lookup"><span data-stu-id="89168-107">`IndexerName` is used to represent any of the three options below:</span></span>


## <a name="syntax"></a><span data-ttu-id="89168-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89168-108">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.IndexerName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.IndexerName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.IndexerName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.IndexerName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a><span data-ttu-id="89168-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="89168-109">Remarks</span></span>
<span data-ttu-id="89168-110">Виды предыдущем синтаксисе показывают, как определять индексированные свойства, имеющие и `get` и `set` метод, имеют `get` только метод или иметь `set` только метод.</span><span class="sxs-lookup"><span data-stu-id="89168-110">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="89168-111">Можно также комбинировать показано только получение и синтаксис, показанный для набора только синтаксис и создать свойство, имеющее get и set.</span><span class="sxs-lookup"><span data-stu-id="89168-111">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="89168-112">Эта последняя форма позволяет размещать различные модификаторы доступности и атрибуты на get методов и set.</span><span class="sxs-lookup"><span data-stu-id="89168-112">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="89168-113">Когда *IndexerName* — `Item`, компилятор рассматривает свойство как индексированное свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="89168-113">When the *IndexerName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="89168-114">Объект *индексированное свойство по умолчанию* — это свойство, к которой можно обращаться, используя синтаксис, подобный массиву на экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="89168-114">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="89168-115">Например если `obj` — это объект типа, который определяет это свойство синтаксис `obj.[index]` используется для доступа к свойству.</span><span class="sxs-lookup"><span data-stu-id="89168-115">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="89168-116">Синтаксис для доступа к не по умолчанию индексированное свойство — для предоставления имени свойства и индекса в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="89168-116">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="89168-117">Например, если свойство `Ordinal`, написании `obj.Ordinal(index)` для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="89168-117">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="89168-118">Независимо от того, какая форма используется, следует всегда использовать каррированные для `set` метод по индексированному свойству.</span><span class="sxs-lookup"><span data-stu-id="89168-118">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="89168-119">Сведения о каррированные функции см. в разделе [функции](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="89168-119">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="89168-120">Пример</span><span class="sxs-lookup"><span data-stu-id="89168-120">Example</span></span>

<span data-ttu-id="89168-121">В следующем примере кода показано определение и использование по умолчанию и не по умолчанию индексированные свойства, задать методы get и.</span><span class="sxs-lookup"><span data-stu-id="89168-121">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="89168-122">Вывод</span><span class="sxs-lookup"><span data-stu-id="89168-122">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="89168-123">Индексированные свойства с несколькими переменными индекса</span><span class="sxs-lookup"><span data-stu-id="89168-123">Indexed Properties with Multiple Index Variables</span></span>
<span data-ttu-id="89168-124">Индексированные свойства могут иметь более одной переменной индекса.</span><span class="sxs-lookup"><span data-stu-id="89168-124">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="89168-125">В этом случае переменные разделяются запятыми при использовании свойства.</span><span class="sxs-lookup"><span data-stu-id="89168-125">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="89168-126">Метод set в таком свойстве должен иметь два переданными аргументами, первым из которых — кортеж, содержащий ключи, а второй — задаваемое значение.</span><span class="sxs-lookup"><span data-stu-id="89168-126">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="89168-127">В следующем коде показано использование индексированного свойства с несколькими переменными индекса.</span><span class="sxs-lookup"><span data-stu-id="89168-127">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="89168-128">См. также</span><span class="sxs-lookup"><span data-stu-id="89168-128">See Also</span></span>
[<span data-ttu-id="89168-129">Члены</span><span class="sxs-lookup"><span data-stu-id="89168-129">Members</span></span>](index.md)
