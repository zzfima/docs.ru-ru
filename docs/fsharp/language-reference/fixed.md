---
title: 'Ключевое слово Fixed (F #)'
description: 'Узнайте, как «закрепить» локальный в стек для предотвращения коллекции с помощью F # «fixed» ключевое слово.'
ms.date: 04/24/2017
ms.openlocfilehash: 1bf1b2ad67d2dd7f854e569cfca7c06e8aec7f4c
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45560377"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="b2ec9-103">Ключевое слово Fixed</span><span class="sxs-lookup"><span data-stu-id="b2ec9-103">The Fixed Keyword</span></span>

<span data-ttu-id="b2ec9-104">Введение в F # 4.1 `fixed` ключевое слово, которое позволяет «закрепить» локальный в стек для предотвращения ее собранные или перемещен во время сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="b2ec9-105">Он используется для низкоуровневых сценариев программирования.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2ec9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2ec9-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="b2ec9-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2ec9-107">Remarks</span></span>

<span data-ttu-id="b2ec9-108">При этом расширяется синтаксис выражений для извлечения указатель и связывание его с именем которой предотвращается собранные или перемещается во время сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="b2ec9-109">Указатель на основе выражения является фиксированным через `fixed` ключевое слово привязывается к идентификатору с помощью `use` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="b2ec9-110">Это семантика аналогичную управление ресурсами с помощью `use` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="b2ec9-111">Указатель является фиксированным, пока он находится в области, и когда она выходит из области действия, он больше не является фиксированным.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="b2ec9-112">`fixed` нельзя использовать вне контекста `use` привязки.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="b2ec9-113">Необходимо привязать указатель к имени с `use`.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="b2ec9-114">Использование `fixed` должно находиться в пределах выражения в функции или метода.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="b2ec9-115">Он не может использоваться в области сценария уровня или уровня модуля.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="b2ec9-116">Как и весь код указатель это является небезопасный функцией и выдает предупреждение при использовании.</span><span class="sxs-lookup"><span data-stu-id="b2ec9-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="b2ec9-117">Пример</span><span class="sxs-lookup"><span data-stu-id="b2ec9-117">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b2ec9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b2ec9-118">See also</span></span>

- [<span data-ttu-id="b2ec9-119">Nativeptr-модуль</span><span class="sxs-lookup"><span data-stu-id="b2ec9-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
