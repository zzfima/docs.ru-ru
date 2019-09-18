---
title: Гибкие типы
description: Узнайте, как использовать F# гибкую аннотацию типа, которая указывает, что параметр, переменная или значение имеют тип, совместимый с указанным типом.
ms.date: 05/16/2016
ms.openlocfilehash: bf05f78f163d1f9c73c667df60925b66a5315627
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083066"
---
# <a name="flexible-types"></a><span data-ttu-id="8b537-103">Гибкие типы</span><span class="sxs-lookup"><span data-stu-id="8b537-103">Flexible Types</span></span>

<span data-ttu-id="8b537-104">*Заметка гибкого типа* указывает, что параметр, переменная или значение имеют тип, совместимый с указанным типом, где совместимость определяется положением в объектно-ориентированной иерархии классов или интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="8b537-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="8b537-105">Гибкие типы полезны в частности, если автоматическое преобразование в типы выше в иерархии типов не выполняется, но все равно требуется обеспечить работу функций с любым типом в иерархии или любым типом, реализующим интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8b537-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b537-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b537-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="8b537-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b537-107">Remarks</span></span>

<span data-ttu-id="8b537-108">В предыдущем синтаксисе *тип* представляет базовый тип или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8b537-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="8b537-109">Гибкий тип эквивалентен универсальному типу, имеющему ограничение, которое ограничивает допустимые типы типами, совместимыми с базовым или интерфейсным типом.</span><span class="sxs-lookup"><span data-stu-id="8b537-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="8b537-110">То есть следующие две строки кода эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="8b537-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="8b537-111">Гибкие типы полезны в ситуациях нескольких типов.</span><span class="sxs-lookup"><span data-stu-id="8b537-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="8b537-112">Например, если имеется функция более высокого порядка (функция, которая принимает функцию в качестве аргумента), часто бывает полезно, чтобы функция возвращала гибкий тип.</span><span class="sxs-lookup"><span data-stu-id="8b537-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="8b537-113">В следующем примере использование гибкого типа с аргументом последовательности в `iterate2` позволяет функции более высокого порядка работать с функциями, создающими последовательности, массивы, списки и любые другие перечислимые типы.</span><span class="sxs-lookup"><span data-stu-id="8b537-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="8b537-114">Рассмотрим следующие две функции, одна из которых возвращает последовательность, а другая — гибкий тип.</span><span class="sxs-lookup"><span data-stu-id="8b537-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="8b537-115">В качестве другого примера рассмотрим функцию [Seq. Concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) Library:</span><span class="sxs-lookup"><span data-stu-id="8b537-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="8b537-116">В эту функцию можно передать любую из следующих перечислимых последовательностей:</span><span class="sxs-lookup"><span data-stu-id="8b537-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="8b537-117">Список списков</span><span class="sxs-lookup"><span data-stu-id="8b537-117">A list of lists</span></span>
- <span data-ttu-id="8b537-118">Список массивов</span><span class="sxs-lookup"><span data-stu-id="8b537-118">A list of arrays</span></span>
- <span data-ttu-id="8b537-119">Массив списков</span><span class="sxs-lookup"><span data-stu-id="8b537-119">An array of lists</span></span>
- <span data-ttu-id="8b537-120">Массив последовательностей</span><span class="sxs-lookup"><span data-stu-id="8b537-120">An array of sequences</span></span>
- <span data-ttu-id="8b537-121">Любое другое сочетание перечислимых последовательностей</span><span class="sxs-lookup"><span data-stu-id="8b537-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="8b537-122">В следующем коде используется `Seq.concat` для демонстрации сценариев, которые можно поддерживать с помощью гибких типов.</span><span class="sxs-lookup"><span data-stu-id="8b537-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="8b537-123">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8b537-123">The output is as follows.</span></span>

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="8b537-124">В F#, как и в других объектно-ориентированных языках, существуют контексты, в которых производные типы или типы, реализующие интерфейсы, автоматически преобразуются в базовый тип или тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8b537-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="8b537-125">Эти автоматические преобразования происходят в прямых аргументах, но не в том случае, если тип находится в подчиненной положении, как часть более сложного типа, например тип возвращаемого значения типа функции, или как аргумент типа.</span><span class="sxs-lookup"><span data-stu-id="8b537-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="8b537-126">Таким образом, нотация гибкого типа особенно полезна, когда тип, к которому он применяется, является частью более сложного типа.</span><span class="sxs-lookup"><span data-stu-id="8b537-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b537-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8b537-127">See also</span></span>

- [<span data-ttu-id="8b537-128">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="8b537-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="8b537-129">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="8b537-129">Generics</span></span>](./generics/index.md)
