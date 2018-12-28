---
title: Ключевое слово fixed
description: Узнайте, как вы можете закрепить локальной в стек для предотвращения коллекции с F# ключевое слово «fixed».
ms.date: 04/24/2017
ms.openlocfilehash: 7fdf66560f3e2ab7584b00c7e4584d7f6c161858
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614365"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="48598-103">Ключевое слово fixed</span><span class="sxs-lookup"><span data-stu-id="48598-103">The fixed keyword</span></span>

<span data-ttu-id="48598-104">F#представляет 4.1 `fixed` ключевое слово, которое позволяет «закрепить» локальный в стек для предотвращения ее собранные или перемещен во время сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="48598-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="48598-105">Он используется для низкоуровневых сценариев программирования.</span><span class="sxs-lookup"><span data-stu-id="48598-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="48598-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48598-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="48598-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="48598-107">Remarks</span></span>

<span data-ttu-id="48598-108">При этом расширяется синтаксис выражений для извлечения указатель и связывание его с именем которой предотвращается собранные или перемещается во время сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="48598-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="48598-109">Указатель на основе выражения является фиксированным через `fixed` ключевое слово привязывается к идентификатору с помощью `use` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="48598-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="48598-110">Это семантика аналогичную управление ресурсами с помощью `use` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="48598-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="48598-111">Указатель является фиксированным, пока он находится в области, и когда она выходит из области действия, он больше не является фиксированным.</span><span class="sxs-lookup"><span data-stu-id="48598-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="48598-112">`fixed` нельзя использовать вне контекста `use` привязки.</span><span class="sxs-lookup"><span data-stu-id="48598-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="48598-113">Необходимо привязать указатель к имени с `use`.</span><span class="sxs-lookup"><span data-stu-id="48598-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="48598-114">Использование `fixed` должно находиться в пределах выражения в функции или метода.</span><span class="sxs-lookup"><span data-stu-id="48598-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="48598-115">Он не может использоваться в области сценария уровня или уровня модуля.</span><span class="sxs-lookup"><span data-stu-id="48598-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="48598-116">Как и весь код указатель это является небезопасный функцией и выдает предупреждение при использовании.</span><span class="sxs-lookup"><span data-stu-id="48598-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="48598-117">Пример</span><span class="sxs-lookup"><span data-stu-id="48598-117">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="48598-118">См. также</span><span class="sxs-lookup"><span data-stu-id="48598-118">See also</span></span>

- [<span data-ttu-id="48598-119">Nativeptr-модуль</span><span class="sxs-lookup"><span data-stu-id="48598-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
