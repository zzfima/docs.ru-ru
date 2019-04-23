---
title: Выражения объекта
description: Сведения об использовании F# выражения объекта, если вы хотите избежать дополнительного кода и накладные расходы, необходимые для создания нового именованного типа.
ms.date: 02/08/2019
ms.openlocfilehash: 63f2c1d7128721b7b8c744e4cf02d73c2a8b4a07
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157856"
---
# <a name="object-expressions"></a><span data-ttu-id="c3a56-103">Выражения объекта</span><span class="sxs-lookup"><span data-stu-id="c3a56-103">Object Expressions</span></span>

<span data-ttu-id="c3a56-104">*Объекта выражение* является выражение, которое создает новый экземпляр динамически создаваемого анонимного типа объекта, который основан на существующем базовом типе, интерфейсе или набор интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="c3a56-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3a56-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3a56-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="c3a56-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3a56-106">Remarks</span></span>

<span data-ttu-id="c3a56-107">В приведенном выше синтаксисе *typename* представляет собой существующий тип класса или тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c3a56-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="c3a56-108">*Тип params* описывает необязательные параметры универсального типа.</span><span class="sxs-lookup"><span data-stu-id="c3a56-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="c3a56-109">*Аргументы* используются только для типов классов, которые требуют параметры конструктора.</span><span class="sxs-lookup"><span data-stu-id="c3a56-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="c3a56-110">*Определения членов* переопределения методов базового класса или реализаций абстрактных методов базового класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c3a56-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="c3a56-111">Следующий пример иллюстрирует несколько разных типов выражений объекта.</span><span class="sxs-lookup"><span data-stu-id="c3a56-111">The following example illustrates several different types of object expressions.</span></span>

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

// Define two interfaces
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements both interfaces.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a><span data-ttu-id="c3a56-112">С использованием выражений объекта</span><span class="sxs-lookup"><span data-stu-id="c3a56-112">Using Object Expressions</span></span>

<span data-ttu-id="c3a56-113">Объект выражения используются в том случае, если вы хотите избежать дополнительного кода и издержки, который необходим для создания нового именованного типа.</span><span class="sxs-lookup"><span data-stu-id="c3a56-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="c3a56-114">Если объект выражения позволяют свести к минимуму количество типов, созданный в приложении, можно сократить число строк кода и предотвратить ненужное увеличение числа типов.</span><span class="sxs-lookup"><span data-stu-id="c3a56-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="c3a56-115">Вместо создания множества типов для различных ситуаций, можно использовать выражение объекта, который настраивает существующий тип или предоставляет подходящую реализацию интерфейса для конкретного случая.</span><span class="sxs-lookup"><span data-stu-id="c3a56-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3a56-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c3a56-116">See also</span></span>

- [<span data-ttu-id="c3a56-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="c3a56-117">F# Language Reference</span></span>](index.md)
