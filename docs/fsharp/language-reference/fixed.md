---
title: 'Ключевое слово Fixed (F #)'
description: 'Дополнительные сведения о том, как можно «закрепить» локальный стек коллекции с помощью F # во избежание «fixed» ключевое слово.'
ms.date: 04/24/2017
ms.openlocfilehash: 913ee4d7b0f6b2437793d4788e53556d6be6c4db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563880"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="21091-103">Ключевое слово Fixed</span><span class="sxs-lookup"><span data-stu-id="21091-103">The Fixed Keyword</span></span>

<span data-ttu-id="21091-104">4.1 F # представлены `fixed` ключевое слово, которое позволяет «закрепить» локальный, чтобы он перемещен во время сбора мусора или собраны в стек.</span><span class="sxs-lookup"><span data-stu-id="21091-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="21091-105">Он используется для низкоуровневых сценариев программирования.</span><span class="sxs-lookup"><span data-stu-id="21091-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="21091-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21091-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="21091-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="21091-107">Remarks</span></span>

<span data-ttu-id="21091-108">Это расширяет возможности синтаксиса выражений для извлечения указатель и связывание его с именем, что помешало собранные или перемещен во время сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="21091-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="21091-109">Указатель на основе выражения является фиксированным через `fixed` ключевое слово привязан к идентификатору через `use` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="21091-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="21091-110">Это семантика аналогично управление ресурсами через `use` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="21091-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="21091-111">Указатель зафиксирован, пока она находится в области, а после его за пределы области, он больше не является фиксированным.</span><span class="sxs-lookup"><span data-stu-id="21091-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="21091-112">`fixed` не может использоваться вне контекста `use` привязки.</span><span class="sxs-lookup"><span data-stu-id="21091-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="21091-113">Необходимо привязать указатель к имени с `use`.</span><span class="sxs-lookup"><span data-stu-id="21091-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="21091-114">Использование `fixed` должно находиться в пределах выражения в функции или метода.</span><span class="sxs-lookup"><span data-stu-id="21091-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="21091-115">Он не может использоваться в область уровня модуля или сценария.</span><span class="sxs-lookup"><span data-stu-id="21091-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="21091-116">Как весь код указатель это является возможностью unsafe и выдаст предупреждение при использовании.</span><span class="sxs-lookup"><span data-stu-id="21091-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="21091-117">Пример</span><span class="sxs-lookup"><span data-stu-id="21091-117">Example</span></span>

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a><span data-ttu-id="21091-118">См. также</span><span class="sxs-lookup"><span data-stu-id="21091-118">See Also</span></span>

[<span data-ttu-id="21091-119">Nativeptr-модуль</span><span class="sxs-lookup"><span data-stu-id="21091-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
