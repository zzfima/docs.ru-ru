---
title: Выражения объекта
description: Сведения об использовании F# выражения объекта, если вы хотите избежать дополнительного кода и накладные расходы, необходимые для создания нового именованного типа.
ms.date: 02/08/2019
ms.openlocfilehash: c00b2e329a97b86ec2c8c84c143d2aa199875442
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091673"
---
# <a name="object-expressions"></a>Выражения объекта

*Объекта выражение* является выражение, которое создает новый экземпляр динамически создаваемого анонимного типа объекта, который основан на существующем базовом типе, интерфейсе или набор интерфейсов.

## <a name="syntax"></a>Синтаксис

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>Примечания

В приведенном выше синтаксисе *typename* представляет собой существующий тип класса или тип интерфейса. *Тип params* описывает необязательные параметры универсального типа. *Аргументы* используются только для типов классов, которые требуют параметры конструктора. *Определения членов* переопределения методов базового класса или реализаций абстрактных методов базового класса или интерфейса.

Следующий пример иллюстрирует несколько разных типов выражений объекта.

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn "%A" obj1

// This object expression implements the IFormattable interface.
let delimiter(delim1: string, delim2: string, value: string) =
    { new System.IFormattable with
        member x.ToString(format: string, provider: System.IFormatProvider) =
            if format = "D" then
                delim1 + value + delim2
            else
                value }

let obj2 = delimiter("{","}", "Bananas!");

printfn "%A" (System.String.Format("{0:D}", obj2))

// This object expression implements multiple interfaces.
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements an interface chain.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a>С использованием выражений объекта

Объект выражения используются в том случае, если вы хотите избежать дополнительного кода и издержки, который необходим для создания нового именованного типа. Если объект выражения позволяют свести к минимуму количество типов, созданный в приложении, можно сократить число строк кода и предотвратить ненужное увеличение числа типов. Вместо создания множества типов для различных ситуаций, можно использовать выражение объекта, который настраивает существующий тип или предоставляет подходящую реализацию интерфейса для конкретного случая.

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
