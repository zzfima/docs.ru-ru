---
title: Сокращенные обозначения типов
description: Узнайте о F# сокращении типов, чтобы дать типу более значимое имя, чтобы облегчить чтение кода.
ms.date: 05/16/2016
ms.openlocfilehash: 339b22a675e3f1ad8a3da207053e611942b55a22
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630213"
---
# <a name="type-abbreviations"></a><span data-ttu-id="f5a5a-103">Сокращенные обозначения типов</span><span class="sxs-lookup"><span data-stu-id="f5a5a-103">Type Abbreviations</span></span>

<span data-ttu-id="f5a5a-104">*Аббревиатура типа* — это псевдоним или альтернативное имя для типа.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="f5a5a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5a5a-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="f5a5a-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5a5a-106">Remarks</span></span>

<span data-ttu-id="f5a5a-107">Аббревиатуры типов можно использовать для присвоения типу более понятного имени, чтобы облегчить чтение кода.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="f5a5a-108">Их также можно использовать для создания простого в использовании имени типа, который в противном случае будет громоздким для записи. Кроме того, можно использовать сокращения типов, чтобы упростить изменение базового типа, не изменяя весь код, использующий этот тип.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="f5a5a-109">Ниже приведена простая аббревиатура типа.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="f5a5a-110">По умолчанию в качестве специальных возможностей для `public`аббревиатур типа используется.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="f5a5a-111">Аббревиатуры типов могут включать в себя универсальные параметры, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="f5a5a-112">В предыдущем коде `Transform` — это аббревиатура типа, представляющая функцию, которая принимает один аргумент любого типа и возвращает одно значение этого же типа.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="f5a5a-113">Сокращения типов не сохраняются в .NET Framework коде MSIL.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="f5a5a-114">Поэтому при использовании F# сборки на другом языке .NET Framework необходимо использовать базовое имя типа для аббревиатуры типов.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="f5a5a-115">Аббревиатуры типов также можно использовать в единицах измерения.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="f5a5a-116">Дополнительные сведения см. в разделе [единицы измерения](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="f5a5a-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f5a5a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f5a5a-117">See also</span></span>

- [<span data-ttu-id="f5a5a-118">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="f5a5a-118">F# Language Reference</span></span>](index.md)
