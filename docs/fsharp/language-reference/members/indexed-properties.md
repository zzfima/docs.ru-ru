---
title: "Индексированные свойства (F#)"
description: "Дополнительные сведения о F # индексированные свойства, которые являются свойства, предоставляющие доступ через массив к упорядоченным данным."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f1266b8b-e2e3-4f49-9332-65c6d34dc0f3
ms.openlocfilehash: 78a09a70621e82f073346471e68ec826359641d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="indexed-properties"></a><span data-ttu-id="4f926-104">Индексированные свойства</span><span class="sxs-lookup"><span data-stu-id="4f926-104">Indexed Properties</span></span>

<span data-ttu-id="4f926-105">*Индексированные свойства* свойства, предоставляющие доступ через массив к упорядочиваются данные.</span><span class="sxs-lookup"><span data-stu-id="4f926-105">*Indexed properties* are properties that provide array-like access to ordered data.</span></span>


## <a name="syntax"></a><span data-ttu-id="4f926-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f926-106">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.PropertyName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.PropertyName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.PropertyName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.PropertyName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a><span data-ttu-id="4f926-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f926-107">Remarks</span></span>
<span data-ttu-id="4f926-108">Три вида предыдущем синтаксисе показывают, как определять индексированные свойства, имеющие и `get` и `set` метод, имеют `get` только метод или иметь `set` только метод.</span><span class="sxs-lookup"><span data-stu-id="4f926-108">The three forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="4f926-109">Можно также комбинировать показано только получение и синтаксис, показанный для набора только синтаксис и создать свойство, имеющее get и set.</span><span class="sxs-lookup"><span data-stu-id="4f926-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="4f926-110">Эта последняя форма позволяет размещать различные модификаторы доступности и атрибуты на get методов и set.</span><span class="sxs-lookup"><span data-stu-id="4f926-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="4f926-111">Когда *PropertyName* — `Item`, компилятор рассматривает свойство как индексированное свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4f926-111">When the *PropertyName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="4f926-112">Объект *индексированное свойство по умолчанию* — это свойство, к которой можно обращаться, используя синтаксис, подобный массиву на экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="4f926-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="4f926-113">Например если `obj` — это объект типа, который определяет это свойство синтаксис `obj.[index]` используется для доступа к свойству.</span><span class="sxs-lookup"><span data-stu-id="4f926-113">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="4f926-114">Синтаксис для доступа к не по умолчанию индексированное свойство — для предоставления имени свойства и индекса в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="4f926-114">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="4f926-115">Например, если свойство `Ordinal`, написании `obj.Ordinal(index)` для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="4f926-115">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="4f926-116">Независимо от того, какая форма используется, следует всегда использовать каррированные для `set` метод по индексированному свойству.</span><span class="sxs-lookup"><span data-stu-id="4f926-116">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="4f926-117">Сведения о каррированные функции см. в разделе [функции](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="4f926-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="4f926-118">Пример</span><span class="sxs-lookup"><span data-stu-id="4f926-118">Example</span></span>

<span data-ttu-id="4f926-119">В следующем примере кода показано определение и использование по умолчанию и не по умолчанию индексированные свойства, задать методы get и.</span><span class="sxs-lookup"><span data-stu-id="4f926-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="4f926-120">Вывод</span><span class="sxs-lookup"><span data-stu-id="4f926-120">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="4f926-121">Индексированные свойства с несколькими переменными индекса</span><span class="sxs-lookup"><span data-stu-id="4f926-121">Indexed Properties with Multiple Index Variables</span></span>
<span data-ttu-id="4f926-122">Индексированные свойства могут иметь более одной переменной индекса.</span><span class="sxs-lookup"><span data-stu-id="4f926-122">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="4f926-123">В этом случае переменные разделяются запятыми при использовании свойства.</span><span class="sxs-lookup"><span data-stu-id="4f926-123">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="4f926-124">Метод set в таком свойстве должен иметь два переданными аргументами, первым из которых — кортеж, содержащий ключи, а второй — задаваемое значение.</span><span class="sxs-lookup"><span data-stu-id="4f926-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="4f926-125">В следующем коде показано использование индексированного свойства с несколькими переменными индекса.</span><span class="sxs-lookup"><span data-stu-id="4f926-125">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="4f926-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4f926-126">See Also</span></span>
[<span data-ttu-id="4f926-127">Члены</span><span class="sxs-lookup"><span data-stu-id="4f926-127">Members</span></span>](index.md)
