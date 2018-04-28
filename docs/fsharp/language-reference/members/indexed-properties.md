---
title: Индексированные свойства (F#)
description: 'Дополнительные сведения о F # индексированные свойства, которые являются свойства, предоставляющие доступ через массив к упорядоченным данным.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 39396b3a5ec43f9a8ab0df96afeb69e05801c752
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="indexed-properties"></a><span data-ttu-id="c07cc-103">Индексированные свойства</span><span class="sxs-lookup"><span data-stu-id="c07cc-103">Indexed Properties</span></span>

<span data-ttu-id="c07cc-104">*Индексированные свойства* свойства, предоставляющие доступ через массив к упорядочиваются данные.</span><span class="sxs-lookup"><span data-stu-id="c07cc-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span>


## <a name="syntax"></a><span data-ttu-id="c07cc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c07cc-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="c07cc-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="c07cc-106">Remarks</span></span>
<span data-ttu-id="c07cc-107">Три вида предыдущем синтаксисе показывают, как определять индексированные свойства, имеющие и `get` и `set` метод, имеют `get` только метод или иметь `set` только метод.</span><span class="sxs-lookup"><span data-stu-id="c07cc-107">The three forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="c07cc-108">Можно также комбинировать показано только получение и синтаксис, показанный для набора только синтаксис и создать свойство, имеющее get и set.</span><span class="sxs-lookup"><span data-stu-id="c07cc-108">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="c07cc-109">Эта последняя форма позволяет размещать различные модификаторы доступности и атрибуты на get методов и set.</span><span class="sxs-lookup"><span data-stu-id="c07cc-109">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="c07cc-110">Когда *PropertyName* — `Item`, компилятор рассматривает свойство как индексированное свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c07cc-110">When the *PropertyName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="c07cc-111">Объект *индексированное свойство по умолчанию* — это свойство, к которой можно обращаться, используя синтаксис, подобный массиву на экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="c07cc-111">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="c07cc-112">Например если `obj` — это объект типа, который определяет это свойство синтаксис `obj.[index]` используется для доступа к свойству.</span><span class="sxs-lookup"><span data-stu-id="c07cc-112">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="c07cc-113">Синтаксис для доступа к не по умолчанию индексированное свойство — для предоставления имени свойства и индекса в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="c07cc-113">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="c07cc-114">Например, если свойство `Ordinal`, написании `obj.Ordinal(index)` для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="c07cc-114">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="c07cc-115">Независимо от того, какая форма используется, следует всегда использовать каррированные для `set` метод по индексированному свойству.</span><span class="sxs-lookup"><span data-stu-id="c07cc-115">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="c07cc-116">Сведения о каррированные функции см. в разделе [функции](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="c07cc-116">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="c07cc-117">Пример</span><span class="sxs-lookup"><span data-stu-id="c07cc-117">Example</span></span>

<span data-ttu-id="c07cc-118">В следующем примере кода показано определение и использование по умолчанию и не по умолчанию индексированные свойства, задать методы get и.</span><span class="sxs-lookup"><span data-stu-id="c07cc-118">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="c07cc-119">Вывод</span><span class="sxs-lookup"><span data-stu-id="c07cc-119">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="c07cc-120">Индексированные свойства с несколькими переменными индекса</span><span class="sxs-lookup"><span data-stu-id="c07cc-120">Indexed Properties with Multiple Index Variables</span></span>
<span data-ttu-id="c07cc-121">Индексированные свойства могут иметь более одной переменной индекса.</span><span class="sxs-lookup"><span data-stu-id="c07cc-121">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="c07cc-122">В этом случае переменные разделяются запятыми при использовании свойства.</span><span class="sxs-lookup"><span data-stu-id="c07cc-122">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="c07cc-123">Метод set в таком свойстве должен иметь два переданными аргументами, первым из которых — кортеж, содержащий ключи, а второй — задаваемое значение.</span><span class="sxs-lookup"><span data-stu-id="c07cc-123">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="c07cc-124">В следующем коде показано использование индексированного свойства с несколькими переменными индекса.</span><span class="sxs-lookup"><span data-stu-id="c07cc-124">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="c07cc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c07cc-125">See Also</span></span>
[<span data-ttu-id="c07cc-126">Члены</span><span class="sxs-lookup"><span data-stu-id="c07cc-126">Members</span></span>](index.md)
