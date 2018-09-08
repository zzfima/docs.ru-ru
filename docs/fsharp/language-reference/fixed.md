---
title: 'Ключевое слово Fixed (F #)'
description: 'Узнайте, как «закрепить» локальный в стек для предотвращения коллекции с помощью F # «fixed» ключевое слово.'
ms.date: 04/24/2017
ms.openlocfilehash: 1bf1b2ad67d2dd7f854e569cfca7c06e8aec7f4c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44201417"
---
# <a name="the-fixed-keyword"></a>Ключевое слово Fixed

Введение в F # 4.1 `fixed` ключевое слово, которое позволяет «закрепить» локальный в стек для предотвращения ее собранные или перемещен во время сбора мусора.  Он используется для низкоуровневых сценариев программирования.

## <a name="syntax"></a>Синтаксис

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Примечания

При этом расширяется синтаксис выражений для извлечения указатель и связывание его с именем которой предотвращается собранные или перемещается во время сбора мусора.  

Указатель на основе выражения является фиксированным через `fixed` ключевое слово привязывается к идентификатору с помощью `use` ключевое слово.  Это семантика аналогичную управление ресурсами с помощью `use` ключевое слово.  Указатель является фиксированным, пока он находится в области, и когда она выходит из области действия, он больше не является фиксированным.  `fixed` нельзя использовать вне контекста `use` привязки.  Необходимо привязать указатель к имени с `use`.

Использование `fixed` должно находиться в пределах выражения в функции или метода.  Он не может использоваться в области сценария уровня или уровня модуля.

Как и весь код указатель это является небезопасный функцией и выдает предупреждение при использовании.

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

- [Nativeptr-модуль](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
