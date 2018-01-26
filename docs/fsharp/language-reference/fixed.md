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
# <a name="the-fixed-keyword"></a>Ключевое слово Fixed

4.1 F # представлены `fixed` ключевое слово, которое позволяет «закрепить» локальный, чтобы он перемещен во время сбора мусора или собраны в стек.  Он используется для низкоуровневых сценариев программирования.

## <a name="syntax"></a>Синтаксис

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Примечания

Это расширяет возможности синтаксиса выражений для извлечения указатель и связывание его с именем, что помешало собранные или перемещен во время сбора мусора.  

Указатель на основе выражения является фиксированным через `fixed` ключевое слово привязан к идентификатору через `use` ключевое слово.  Это семантика аналогично управление ресурсами через `use` ключевое слово.  Указатель зафиксирован, пока она находится в области, а после его за пределы области, он больше не является фиксированным.  `fixed`не может использоваться вне контекста `use` привязки.  Необходимо привязать указатель к имени с `use`.

Использование `fixed` должно находиться в пределах выражения в функции или метода.  Он не может использоваться в область уровня модуля или сценария.

Как весь код указатель это является возможностью unsafe и выдаст предупреждение при использовании.

## <a name="example"></a>Пример

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

## <a name="see-also"></a>См. также

[Nativeptr-модуль](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
