---
title: "Ключевое слово Fixed (F #)"
description: "Дополнительные сведения о том, как можно «закрепить» локальный стек коллекции с помощью F # во избежание «fixed» ключевое слово."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5795ce1f-11bf-4798-9f1f-6e44ffa1477e
ms.openlocfilehash: 1605603bc35941e21c798600140036fb678869b5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="b6ba5-104">Ключевое слово Fixed</span><span class="sxs-lookup"><span data-stu-id="b6ba5-104">The Fixed Keyword</span></span>

<span data-ttu-id="b6ba5-105">4.1 F # представлены `fixed` ключевое слово, которое позволяет «закрепить» локальный, чтобы он перемещен во время сбора мусора или собраны в стек.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-105">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="b6ba5-106">Он используется для низкоуровневых сценариев программирования.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-106">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6ba5-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6ba5-107">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="b6ba5-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6ba5-108">Remarks</span></span>

<span data-ttu-id="b6ba5-109">Это расширяет возможности синтаксиса выражений для извлечения указатель и связывание его с именем, что помешало собранные или перемещен во время сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-109">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="b6ba5-110">Указатель на основе выражения является фиксированным через `fixed` ключевое слово привязан к идентификатору через `use` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-110">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="b6ba5-111">Это семантика аналогично управление ресурсами через `use` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-111">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="b6ba5-112">Указатель зафиксирован, пока она находится в области, а после его за пределы области, он больше не является фиксированным.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-112">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="b6ba5-113">`fixed`не может использоваться вне контекста `use` привязки.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-113">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="b6ba5-114">Необходимо привязать указатель к имени с `use`.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-114">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="b6ba5-115">Использование `fixed` должно находиться в пределах выражения в функции или метода.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-115">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="b6ba5-116">Он не может использоваться в область уровня модуля или сценария.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-116">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="b6ba5-117">Как весь код указатель это является возможностью unsafe и выдаст предупреждение при использовании.</span><span class="sxs-lookup"><span data-stu-id="b6ba5-117">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="b6ba5-118">Пример</span><span class="sxs-lookup"><span data-stu-id="b6ba5-118">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b6ba5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b6ba5-119">See Also</span></span>

[<span data-ttu-id="b6ba5-120">Nativeptr-модуль</span><span class="sxs-lookup"><span data-stu-id="b6ba5-120">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
