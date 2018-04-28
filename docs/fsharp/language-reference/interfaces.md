---
title: Интерфейсы (F#)
description: 'Узнайте, как интерфейсы F # задают наборы связанных членов, которые реализуют другие классы.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: fa299a7e37d4e1e3800a02bf5a77831db9146daf
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="interfaces"></a>интерфейсов,

*Интерфейсы* указать набора связанных элементов, которые реализуют другие классы.

## <a name="syntax"></a>Синтаксис

```fsharp
// Interface declaration:
[ attributes ]
type interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a>Примечания
Объявления интерфейса похоже на объявление класса, но не реализуются члены. Вместо этого все члены, являются абстрактными, как указано ключевое слово `abstract`. Для абстрактных методов не имеют тела метода. Однако, можно предоставить реализацию по умолчанию, дополнительно указав отдельное определение члена как метода с `default` ключевое слово. Это эквивалентно созданию виртуального метода в базовом классе в других языках .NET. Виртуальный метод может переопределяться в классах, которые реализуют интерфейс.

Можно присвоить параметра каждого метода имя, используя обычный синтаксис F #:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

В указанных выше `ISprintable` примере `Print` метод принимает один параметр типа `string` с именем `format`.

Существует два способа реализации интерфейсов: с помощью выражений объектов и с помощью типов классов. В любом случае выражение класса типа или объекта предоставляет тела метода для абстрактных методов интерфейса. Реализации специфичны для каждого типа, который реализует интерфейс. Таким образом методы интерфейса для различных типов может отличаться друг от друга.

Ключевые слова `interface` и `end`, отмечающие начало и конец определения, являются необязательными, если используется упрощенный синтаксис. Если вы не используете эти ключевые слова, компилятор пытается определить, является ли тип классом или интерфейсом, анализируя конструкций, которые можно использовать. Если определение члена или использовать другие синтаксические элементы класса, тип интерпретируется как класс.

Стиль написания кода .NET рекомендуется начинать имена интерфейсов с заглавной буквы `I`.


## <a name="implementing-interfaces-by-using-class-types"></a>Реализация интерфейсов с помощью типов классов
Один или несколько интерфейсов можно реализовать в типе класса с помощью `interface` ключевое слово, имя интерфейса и `with` ключевое слово, и определения членов интерфейса, как показано в следующем коде.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Реализации интерфейсов наследуются, поэтому любые производные классы не нужно повторно реализовать их.


## <a name="calling-interface-methods"></a>Вызов методов интерфейса
Методы интерфейса может вызываться только с помощью интерфейса, а не через объекты типа, который реализует интерфейс. Таким образом, возможно, потребуется привести к типу интерфейса с помощью `:>` оператор или `upcast` оператор для вызова этих методов.

Чтобы вызвать метод интерфейса, если имеется объект типа `SomeClass`, необходимо привести объект к типу интерфейса, как показано в следующем коде.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Альтернативой является объявление метода для объекта, приводит и вызывает метод интерфейса, как показано в следующем примере.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a>Реализация интерфейсов с помощью выражения объекта
Выражения объектов обеспечивают простой способ реализации интерфейса. Они полезны в том случае, когда необходимо создать именованный тип, необходимо просто объекта, который поддерживает методы интерфейса, без дополнительных методов. В следующем коде показано выражение объекта.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a>Наследование интерфейса
Интерфейсы могут наследовать от одного или нескольких базовых интерфейсов.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a>См. также
[Справочник по языку F#](index.md)

[Выражения объекта](object-expressions.md)

[Классы](classes.md)
