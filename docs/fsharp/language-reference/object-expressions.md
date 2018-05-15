---
title: Выражения объекта (F#)
description: 'Узнайте, как для использования объекта выражениями языка F #, если вы хотите избежать дополнительного кода и служебные данные, необходимые для создания нового, именованного типа.'
ms.date: 05/16/2016
ms.openlocfilehash: fed78e2be52838eedf55759b195696f1210a8a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="object-expressions"></a><span data-ttu-id="f2866-103">Выражения объекта</span><span class="sxs-lookup"><span data-stu-id="f2866-103">Object Expressions</span></span>

<span data-ttu-id="f2866-104">*Объекта выражение* является выражение, которое создает новый экземпляр динамически создаваемого анонимного типа объекта, который основан на существующих базовых типов, интерфейс или набор интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f2866-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>


## <a name="syntax"></a><span data-ttu-id="f2866-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2866-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="f2866-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2866-106">Remarks</span></span>
<span data-ttu-id="f2866-107">В предыдущем синтаксисе *typename* представляет собой существующий тип класса или тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f2866-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="f2866-108">*Тип params* описывает необязательные параметры универсального типа.</span><span class="sxs-lookup"><span data-stu-id="f2866-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="f2866-109">*Аргументы* используются только для типов классов, которые требуют параметры конструктора.</span><span class="sxs-lookup"><span data-stu-id="f2866-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="f2866-110">*Определения членов* переопределения методов базового класса или реализаций абстрактных методов базового класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f2866-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="f2866-111">В следующем примере показано несколько разных типов выражений объекта.</span><span class="sxs-lookup"><span data-stu-id="f2866-111">The following example illustrates several different types of object expressions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a><span data-ttu-id="f2866-112">С использованием выражений объекта</span><span class="sxs-lookup"><span data-stu-id="f2866-112">Using Object Expressions</span></span>
<span data-ttu-id="f2866-113">Выражения объекта используются в том случае, когда вы хотите избежать дополнительного кода и служебных данных, необходимые для создания нового именованного типа.</span><span class="sxs-lookup"><span data-stu-id="f2866-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="f2866-114">При использовании выражения объекта для минимизации числа типов, созданный в приложении, можно уменьшить число строк кода и предотвратить ненужное увеличение числа типов.</span><span class="sxs-lookup"><span data-stu-id="f2866-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="f2866-115">Вместо создания множества типов для различных ситуаций, можно использовать выражение объекта, которое настроит существующий тип или предоставит соответствующую реализацию интерфейса для конкретного случая.</span><span class="sxs-lookup"><span data-stu-id="f2866-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>


## <a name="see-also"></a><span data-ttu-id="f2866-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f2866-116">See Also</span></span>
[<span data-ttu-id="f2866-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="f2866-117">F# Language Reference</span></span>](index.md)
