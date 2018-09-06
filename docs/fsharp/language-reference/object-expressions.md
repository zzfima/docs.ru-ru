---
title: Выражения объекта (F#)
description: 'Узнайте, как использовать объектов выражений F #, если вы хотите избежать дополнительного кода и затраты, необходимые для создания нового именованного типа.'
ms.date: 05/16/2016
ms.openlocfilehash: 1a971044d680d3bf5a6fff38affdaf001d5403b4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865466"
---
# <a name="object-expressions"></a><span data-ttu-id="3c036-103">Выражения объекта</span><span class="sxs-lookup"><span data-stu-id="3c036-103">Object Expressions</span></span>

<span data-ttu-id="3c036-104">*Объекта выражение* является выражение, которое создает новый экземпляр динамически создаваемого анонимного типа объекта, который основан на существующем базовом типе, интерфейсе или набор интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="3c036-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c036-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c036-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="3c036-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c036-106">Remarks</span></span>

<span data-ttu-id="3c036-107">В приведенном выше синтаксисе *typename* представляет собой существующий тип класса или тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3c036-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="3c036-108">*Тип params* описывает необязательные параметры универсального типа.</span><span class="sxs-lookup"><span data-stu-id="3c036-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="3c036-109">*Аргументы* используются только для типов классов, которые требуют параметры конструктора.</span><span class="sxs-lookup"><span data-stu-id="3c036-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="3c036-110">*Определения членов* переопределения методов базового класса или реализаций абстрактных методов базового класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3c036-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="3c036-111">Следующий пример иллюстрирует несколько разных типов выражений объекта.</span><span class="sxs-lookup"><span data-stu-id="3c036-111">The following example illustrates several different types of object expressions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a><span data-ttu-id="3c036-112">С использованием выражений объекта</span><span class="sxs-lookup"><span data-stu-id="3c036-112">Using Object Expressions</span></span>

<span data-ttu-id="3c036-113">Объект выражения используются в том случае, если вы хотите избежать дополнительного кода и издержки, который необходим для создания нового именованного типа.</span><span class="sxs-lookup"><span data-stu-id="3c036-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="3c036-114">Если объект выражения позволяют свести к минимуму количество типов, созданный в приложении, можно сократить число строк кода и предотвратить ненужное увеличение числа типов.</span><span class="sxs-lookup"><span data-stu-id="3c036-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="3c036-115">Вместо создания множества типов для различных ситуаций, можно использовать выражение объекта, который настраивает существующий тип или предоставляет подходящую реализацию интерфейса для конкретного случая.</span><span class="sxs-lookup"><span data-stu-id="3c036-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c036-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3c036-116">See also</span></span>

- [<span data-ttu-id="3c036-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="3c036-117">F# Language Reference</span></span>](index.md)
