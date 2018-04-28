---
title: Аббревиатуры типов (F#)
description: 'Дополнительные сведения о аббревиатуры типов F # для предоставления более значимое имя для типа, чтобы сделать код более удобным для чтения.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bf17ee9795947fdc11fe958f09d52f5730b95bf8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="type-abbreviations"></a><span data-ttu-id="d3e5d-103">Сокращенные обозначения типов</span><span class="sxs-lookup"><span data-stu-id="d3e5d-103">Type Abbreviations</span></span>

<span data-ttu-id="d3e5d-104">Объект *-сокращенная форма типа* — это псевдоним или альтернативное имя для типа.</span><span class="sxs-lookup"><span data-stu-id="d3e5d-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3e5d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3e5d-105">Syntax</span></span>

```fsharp
type type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="d3e5d-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3e5d-106">Remarks</span></span>
<span data-ttu-id="d3e5d-107">Сокращенные обозначения типов можно использовать для предоставления типа более значимое имя, чтобы сделать код более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="d3e5d-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="d3e5d-108">Их также можно использовать для создания простой в использовании имени типа, в противном случае сложно записать. Кроме того чтобы облегчить изменение базового типа, не изменяя весь код, который использует этот тип можно использовать сокращенные обозначения типов.</span><span class="sxs-lookup"><span data-stu-id="d3e5d-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="d3e5d-109">Ниже приведен пример простой аббревиатуры типа.</span><span class="sxs-lookup"><span data-stu-id="d3e5d-109">The following is a simple type abbreviation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="d3e5d-110">Сокращенные обозначения типов могут содержать базовые параметры, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="d3e5d-110">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="d3e5d-111">В приведенном выше коде `Transform` представляет собой сокращенную форму типа, который представляет функцию, которая принимает один аргумент любого типа и возвращает одно значение того же типа.</span><span class="sxs-lookup"><span data-stu-id="d3e5d-111">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="d3e5d-112">Сокращенные обозначения типов, не сохраняются в .NET Framework MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="d3e5d-112">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="d3e5d-113">Таким образом при использовании сборки F # из другого языка .NET Framework, необходимо использовать имя базового типа для сокращенная форма типа.</span><span class="sxs-lookup"><span data-stu-id="d3e5d-113">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="d3e5d-114">Сокращенные обозначения типов также может использоваться в единицах измерения.</span><span class="sxs-lookup"><span data-stu-id="d3e5d-114">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="d3e5d-115">Дополнительные сведения см. в разделе [единицы измерения](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="d3e5d-115">For more information, see [Units of Measure](units-of-measure.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="d3e5d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d3e5d-116">See Also</span></span>
[<span data-ttu-id="d3e5d-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="d3e5d-117">F# Language Reference</span></span>](index.md)

