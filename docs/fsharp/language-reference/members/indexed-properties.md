---
title: Индексированные свойства (F#)
description: 'Дополнительные сведения о F # индексированные свойства, которые являются свойства, предоставляющие доступ через массив к данным упорядоченный.'
ms.date: 05/16/2016
ms.openlocfilehash: e56e4e2ea3f35df4c8ec46012357242cb6ce69f3
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46321370"
---
# <a name="indexed-properties"></a><span data-ttu-id="c4e63-103">Индексированные свойства</span><span class="sxs-lookup"><span data-stu-id="c4e63-103">Indexed Properties</span></span>

<span data-ttu-id="c4e63-104">*Индексированные свойства* свойства, предоставляющие доступ через массив к упорядочиваются данные.</span><span class="sxs-lookup"><span data-stu-id="c4e63-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span> <span data-ttu-id="c4e63-105">Они бывают трех видов:</span><span class="sxs-lookup"><span data-stu-id="c4e63-105">They come in three forms:</span></span>

* `Item`
* `Ordinal`
* `Cardinal`

<span data-ttu-id="c4e63-106">В F # член должен иметь имя одного из этих трех имен, чтобы предоставить доступ через массив.</span><span class="sxs-lookup"><span data-stu-id="c4e63-106">An F# member must be named one of these three names to provide array-like access.</span></span> <span data-ttu-id="c4e63-107">`IndexerName` используется для представления любой из трех вариантов ниже:</span><span class="sxs-lookup"><span data-stu-id="c4e63-107">`IndexerName` is used to represent any of the three options below:</span></span>

## <a name="syntax"></a><span data-ttu-id="c4e63-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4e63-108">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="c4e63-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4e63-109">Remarks</span></span>

<span data-ttu-id="c4e63-110">Виды выше синтаксисе показано, как определять индексированные свойства, для которых имеются обе `get` и `set` метод, имеют `get` только метод или иметь `set` только метод.</span><span class="sxs-lookup"><span data-stu-id="c4e63-110">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="c4e63-111">Можно также комбинировать синтаксис, показанный для get только и синтаксис, показанный для набора только и получения свойства с get и set.</span><span class="sxs-lookup"><span data-stu-id="c4e63-111">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="c4e63-112">Эта последняя форма позволяет поместить различные модификаторы доступности и атрибуты на get и методы работы с наборами.</span><span class="sxs-lookup"><span data-stu-id="c4e63-112">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="c4e63-113">Когда *IndexerName* является `Item`, компилятор считает свойство по умолчанию индексированное свойство.</span><span class="sxs-lookup"><span data-stu-id="c4e63-113">When the *IndexerName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="c4e63-114">Объект *индексированное свойство по умолчанию* — это свойство, можно получить доступ, используя синтаксис, подобный массиву в экземпляре объекта.</span><span class="sxs-lookup"><span data-stu-id="c4e63-114">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="c4e63-115">Например если `obj` — это объект типа, который определяет данное свойство синтаксис `obj.[index]` используется для доступа к свойству.</span><span class="sxs-lookup"><span data-stu-id="c4e63-115">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="c4e63-116">Синтаксис для доступа к не по умолчанию индексированное свойство является предоставление имени свойства и индекс в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="c4e63-116">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="c4e63-117">Например, если свойство является `Ordinal`, написании `obj.Ordinal(index)` для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="c4e63-117">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="c4e63-118">Независимо от того, какая форма используется, следует всегда использовать каррированные для `set` метод по индексированному свойству.</span><span class="sxs-lookup"><span data-stu-id="c4e63-118">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="c4e63-119">Сведения о каррированные функции, см. в разделе [функции](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="c4e63-119">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="c4e63-120">Пример</span><span class="sxs-lookup"><span data-stu-id="c4e63-120">Example</span></span>

<span data-ttu-id="c4e63-121">В следующем примере кода показано определение и использование по умолчанию и не по умолчанию индексированные свойства, которые имеют get и методы работы с наборами.</span><span class="sxs-lookup"><span data-stu-id="c4e63-121">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="c4e63-122">Вывод</span><span class="sxs-lookup"><span data-stu-id="c4e63-122">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="c4e63-123">Индексированные свойства с несколькими переменными индекса</span><span class="sxs-lookup"><span data-stu-id="c4e63-123">Indexed Properties with Multiple Index Variables</span></span>

<span data-ttu-id="c4e63-124">Индексированные свойства могут иметь более одной переменной индекса.</span><span class="sxs-lookup"><span data-stu-id="c4e63-124">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="c4e63-125">В этом случае переменные разделяются запятыми при использовании свойства.</span><span class="sxs-lookup"><span data-stu-id="c4e63-125">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="c4e63-126">Метод set в такое свойство должен иметь два каррированных аргумента, первый из которых представляет собой кортеж, содержащий ключи, а второй — задаваемое значение.</span><span class="sxs-lookup"><span data-stu-id="c4e63-126">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="c4e63-127">Следующий код демонстрирует использование индексированного свойства с несколькими переменными индекса.</span><span class="sxs-lookup"><span data-stu-id="c4e63-127">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a><span data-ttu-id="c4e63-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c4e63-128">See also</span></span>

- [<span data-ttu-id="c4e63-129">Члены</span><span class="sxs-lookup"><span data-stu-id="c4e63-129">Members</span></span>](index.md)
