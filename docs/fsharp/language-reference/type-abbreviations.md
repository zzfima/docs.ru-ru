---
title: Сокращенные обозначения типов
description: Дополнительные сведения о F# введите сокращения для предоставления более значимое имя для типа, чтобы сделать код более удобным для чтения.
ms.date: 05/16/2016
ms.openlocfilehash: 2930db1dcaa66741900bc91937aa1fd2f006c5f8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641686"
---
# <a name="type-abbreviations"></a><span data-ttu-id="a595e-103">Сокращенные обозначения типов</span><span class="sxs-lookup"><span data-stu-id="a595e-103">Type Abbreviations</span></span>

<span data-ttu-id="a595e-104">Объект *-сокращенная форма типа* — это псевдоним или альтернативное имя для типа.</span><span class="sxs-lookup"><span data-stu-id="a595e-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="a595e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a595e-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="a595e-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="a595e-106">Remarks</span></span>

<span data-ttu-id="a595e-107">Сокращенные формы типов можно использовать для предоставления типа более значимое имя, чтобы сделать код более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="a595e-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="a595e-108">Их также можно использовать для создания простой в использовании имен для типа, который представляет сложность для записи. Кроме того можно использовать сокращенные формы типов, чтобы упростить изменение базового типа, не изменяя весь код, который использует тип.</span><span class="sxs-lookup"><span data-stu-id="a595e-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="a595e-109">Ниже приведен сокращение простого типа.</span><span class="sxs-lookup"><span data-stu-id="a595e-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="a595e-110">По умолчанию используется уровень доступности сокращенные формы типов `public`.</span><span class="sxs-lookup"><span data-stu-id="a595e-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="a595e-111">Сокращенные формы типов могут содержать базовые параметры, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="a595e-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="a595e-112">В приведенном выше коде `Transform` — это сокращенная форма типа, представляющий функцию, которая принимает один аргумент любого типа и возвращает одно значение того же типа.</span><span class="sxs-lookup"><span data-stu-id="a595e-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="a595e-113">Сокращенные формы типов, не сохраняются в .NET Framework MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="a595e-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="a595e-114">Таким образом, при использовании F# сборки из другого языка .NET Framework, необходимо использовать имя базового типа для сокращенная форма типа.</span><span class="sxs-lookup"><span data-stu-id="a595e-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="a595e-115">Сокращенные формы типов можно также использовать в единицах измерения.</span><span class="sxs-lookup"><span data-stu-id="a595e-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="a595e-116">Дополнительные сведения см. в разделе [единицы измерения](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="a595e-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a595e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a595e-117">See also</span></span>

- [<span data-ttu-id="a595e-118">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="a595e-118">F# Language Reference</span></span>](index.md)
