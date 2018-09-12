---
title: Гибкие типы (F#)
description: 'Сведения об использовании F # заметка с гибким типом, который указывает, что параметр, переменная или значение имеет тип, совместимый с указанным типом.'
ms.date: 05/16/2016
ms.openlocfilehash: b6c97c3cc19f15b2c8db74b2c55660a16b2858f7
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44698475"
---
# <a name="flexible-types"></a><span data-ttu-id="adcf5-103">Гибкие типы</span><span class="sxs-lookup"><span data-stu-id="adcf5-103">Flexible Types</span></span>

<span data-ttu-id="adcf5-104">Объект *заметка с гибким типом* указывает, что параметр, переменная или значение имеет тип, который совместим с указанным типом, где совместимость определяется положением в объектно ориентированного иерархии классов или интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="adcf5-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="adcf5-105">Гибкие типы полезны в тех случаях, в частности в том случае, когда не происходит автоматического преобразования в типы, расположенные выше в иерархии типов, но вы по-прежнему хотите включить функциональные возможности по работе для работы с любым типом в иерархии или любой тип, реализующий интерфейс.</span><span class="sxs-lookup"><span data-stu-id="adcf5-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="adcf5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adcf5-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="adcf5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="adcf5-107">Remarks</span></span>

<span data-ttu-id="adcf5-108">В приведенном выше синтаксисе *тип* представляет базовый тип или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="adcf5-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="adcf5-109">Гибкий тип соответствует универсальный тип, который имеет ограничение, которое ограничивает допустимых типов для типов, которые совместимы с типом базового типа или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="adcf5-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="adcf5-110">То есть следующие две строки кода эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="adcf5-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="adcf5-111">Гибкие типы можно использовать в нескольких случаях.</span><span class="sxs-lookup"><span data-stu-id="adcf5-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="adcf5-112">Например если у вас есть функция высшего порядка (функции, которая принимает в качестве аргумента), часто бывает удобно иметь гибкий тип возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="adcf5-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="adcf5-113">В следующем примере, использование гибкий тип с аргументом последовательности в `iterate2` позволяет функции высшего порядка для работы с функциями, которые создают последовательности, массивы, списки и любой другой перечисляемый тип.</span><span class="sxs-lookup"><span data-stu-id="adcf5-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="adcf5-114">Рассмотрим следующие две функции, один из которых возвращает последовательность, а вторая возвращает гибкий тип.</span><span class="sxs-lookup"><span data-stu-id="adcf5-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="adcf5-115">В качестве другого примера рассмотрим [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) функция библиотеки:</span><span class="sxs-lookup"><span data-stu-id="adcf5-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="adcf5-116">Для этой функции можно передать любой из следующих последовательностей enumerable:</span><span class="sxs-lookup"><span data-stu-id="adcf5-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="adcf5-117">Список списков</span><span class="sxs-lookup"><span data-stu-id="adcf5-117">A list of lists</span></span>
- <span data-ttu-id="adcf5-118">Список массивов</span><span class="sxs-lookup"><span data-stu-id="adcf5-118">A list of arrays</span></span>
- <span data-ttu-id="adcf5-119">Массив списков</span><span class="sxs-lookup"><span data-stu-id="adcf5-119">An array of lists</span></span>
- <span data-ttu-id="adcf5-120">Массив из последовательности</span><span class="sxs-lookup"><span data-stu-id="adcf5-120">An array of sequences</span></span>
- <span data-ttu-id="adcf5-121">Любые комбинации перечисляемые последовательности</span><span class="sxs-lookup"><span data-stu-id="adcf5-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="adcf5-122">В следующем коде используется `Seq.concat` для демонстрации сценариев, которые может поддерживать, используя гибкие типы.</span><span class="sxs-lookup"><span data-stu-id="adcf5-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="adcf5-123">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="adcf5-123">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="adcf5-124">В F # как и в других объектно ориентированных языках существуют контексты, в которых производные типы или типы, реализующие интерфейсы автоматически преобразуются в базовый тип или тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="adcf5-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="adcf5-125">Эти автоматические преобразования происходят в прямой аргументов, но не в том случае, если тип находится в подчиненном положении, как часть более сложного типа, такие как тип возвращаемого значения тип функции или как аргумент типа.</span><span class="sxs-lookup"><span data-stu-id="adcf5-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="adcf5-126">Таким образом нотация гибкий тип является особенно удобно использовать, когда типа, которое вы хотите применить его к является частью более сложного типа.</span><span class="sxs-lookup"><span data-stu-id="adcf5-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="adcf5-127">См. также</span><span class="sxs-lookup"><span data-stu-id="adcf5-127">See also</span></span>

- [<span data-ttu-id="adcf5-128">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="adcf5-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="adcf5-129">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="adcf5-129">Generics</span></span>](generics/index.md)
