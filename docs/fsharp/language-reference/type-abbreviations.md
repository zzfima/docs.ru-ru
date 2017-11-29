---
title: "Аббревиатуры типов (F#)"
description: "Дополнительные сведения о аббревиатуры типов F # для предоставления более значимое имя для типа, чтобы сделать код более удобным для чтения."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 560af74f-935f-415c-af56-604cddb9da6b
ms.openlocfilehash: 235c0240fe89d203b9474dec2b3f91947f453cd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="type-abbreviations"></a><span data-ttu-id="14f1b-104">Сокращенные обозначения типов</span><span class="sxs-lookup"><span data-stu-id="14f1b-104">Type Abbreviations</span></span>

<span data-ttu-id="14f1b-105">Объект *-сокращенная форма типа* — это псевдоним или альтернативное имя для типа.</span><span class="sxs-lookup"><span data-stu-id="14f1b-105">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="14f1b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14f1b-106">Syntax</span></span>

```fsharp
type type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="14f1b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="14f1b-107">Remarks</span></span>
<span data-ttu-id="14f1b-108">Сокращенные обозначения типов можно использовать для предоставления типа более значимое имя, чтобы сделать код более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="14f1b-108">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="14f1b-109">Их также можно использовать для создания простой в использовании имени типа, в противном случае сложно записать. Кроме того чтобы облегчить изменение базового типа, не изменяя весь код, который использует этот тип можно использовать сокращенные обозначения типов.</span><span class="sxs-lookup"><span data-stu-id="14f1b-109">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="14f1b-110">Ниже приведен пример простой аббревиатуры типа.</span><span class="sxs-lookup"><span data-stu-id="14f1b-110">The following is a simple type abbreviation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="14f1b-111">Сокращенные обозначения типов могут содержать базовые параметры, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="14f1b-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="14f1b-112">В приведенном выше коде `Transform` представляет собой сокращенную форму типа, который представляет функцию, которая принимает один аргумент любого типа и возвращает одно значение того же типа.</span><span class="sxs-lookup"><span data-stu-id="14f1b-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="14f1b-113">Сокращенные обозначения типов, не сохраняются в .NET Framework MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="14f1b-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="14f1b-114">Таким образом при использовании сборки F # из другого языка .NET Framework, необходимо использовать имя базового типа для сокращенная форма типа.</span><span class="sxs-lookup"><span data-stu-id="14f1b-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="14f1b-115">Сокращенные обозначения типов также может использоваться в единицах измерения.</span><span class="sxs-lookup"><span data-stu-id="14f1b-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="14f1b-116">Дополнительные сведения см. в разделе [единицы измерения](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="14f1b-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="14f1b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="14f1b-117">See Also</span></span>
[<span data-ttu-id="14f1b-118">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="14f1b-118">F# Language Reference</span></span>](index.md)

