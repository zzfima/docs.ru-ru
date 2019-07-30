---
title: Привязки do в классах
description: Узнайте, как использовать F# привязку do в определении класса, которая выполняет действия при создании объекта или при первом использовании типа.
ms.date: 05/16/2016
ms.openlocfilehash: ced4f1bb17d9e23bf51cc79b5a275cc334cca013
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627590"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="b78e2-103">Привязки do в классах</span><span class="sxs-lookup"><span data-stu-id="b78e2-103">do Bindings in Classes</span></span>

<span data-ttu-id="b78e2-104">Привязка в определении класса выполняет действия при создании объекта или для статической `do` привязки при первом использовании типа. `do`</span><span class="sxs-lookup"><span data-stu-id="b78e2-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="b78e2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b78e2-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="b78e2-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="b78e2-106">Remarks</span></span>

<span data-ttu-id="b78e2-107">Привязка отображается вместе с привязками или `let` после них, но до определений элементов в определении класса. `do`</span><span class="sxs-lookup"><span data-stu-id="b78e2-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="b78e2-108">Хотя ключевое слово является необязательным для `do` привязок на уровне модуля, оно не является обязательным `do` для привязок в определении класса. `do`</span><span class="sxs-lookup"><span data-stu-id="b78e2-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="b78e2-109">Для создания каждого объекта любого заданного типа нестатические `do` привязки и нестатические `let` привязки выполняются в том порядке, в котором они указаны в определении класса.</span><span class="sxs-lookup"><span data-stu-id="b78e2-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="b78e2-110">В `do` одном типе может быть несколько привязок.</span><span class="sxs-lookup"><span data-stu-id="b78e2-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="b78e2-111">Нестатические `let` привязки и нестатические `do` привязки становятся телом основного конструктора.</span><span class="sxs-lookup"><span data-stu-id="b78e2-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="b78e2-112">Код в разделе нестатические `do` привязки может ссылаться на параметры первичного конструктора и любые значения или функции, определенные `let` в разделе привязки.</span><span class="sxs-lookup"><span data-stu-id="b78e2-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="b78e2-113">Нестатические `do` привязки могут обращаться к членам класса, если у класса есть собственный идентификатор, определяемый `as` ключевым словом в заголовке класса, и при условии, что все варианты использования этих членов дополнены идентификатором Self для класса.</span><span class="sxs-lookup"><span data-stu-id="b78e2-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="b78e2-114">Поскольку `let` привязки инициализируют закрытые поля класса, что часто требуется, чтобы гарантировать, что элементы будут вести себя ожидаемым `do` образом, привязки обычно помещаются `let` после привязок, чтобы код в `do` привязке мог выполните с полностью инициализированным объектом.</span><span class="sxs-lookup"><span data-stu-id="b78e2-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="b78e2-115">Если код пытается использовать член до завершения инициализации, создается исключение InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="b78e2-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="b78e2-116">Статические `do` привязки могут ссылаться на статические члены или поля включающего класса, но не на элементы или поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b78e2-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="b78e2-117">Статические `do` привязки становятся частью статического инициализатора класса, который гарантированно выполняется перед первым использованием класса.</span><span class="sxs-lookup"><span data-stu-id="b78e2-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="b78e2-118">Атрибуты для `do` привязок в типах игнорируются.</span><span class="sxs-lookup"><span data-stu-id="b78e2-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="b78e2-119">Если для кода, выполняемого в `do` привязке, требуется атрибут, он должен быть применен к основному конструктору.</span><span class="sxs-lookup"><span data-stu-id="b78e2-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="b78e2-120">В следующем коде класс имеет статическую `do` привязку и нестатичную `do` привязку.</span><span class="sxs-lookup"><span data-stu-id="b78e2-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="b78e2-121">Объект содержит конструктор с двумя параметрами: `a` `b`, и два закрытых `let` поля определены в привязках для класса.</span><span class="sxs-lookup"><span data-stu-id="b78e2-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="b78e2-122">Также определяются два свойства.</span><span class="sxs-lookup"><span data-stu-id="b78e2-122">Two properties are also defined.</span></span> <span data-ttu-id="b78e2-123">Все они находятся в области в разделе нестатические `do` привязки, как показано в строке, в которой печатаются все эти значения.</span><span class="sxs-lookup"><span data-stu-id="b78e2-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="b78e2-124">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b78e2-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="b78e2-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b78e2-125">See also</span></span>

- [<span data-ttu-id="b78e2-126">Члены</span><span class="sxs-lookup"><span data-stu-id="b78e2-126">Members</span></span>](index.md)
- [<span data-ttu-id="b78e2-127">Классы</span><span class="sxs-lookup"><span data-stu-id="b78e2-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="b78e2-128">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="b78e2-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="b78e2-129">Привязки `let` в классах</span><span class="sxs-lookup"><span data-stu-id="b78e2-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="b78e2-130">`do`Привязки</span><span class="sxs-lookup"><span data-stu-id="b78e2-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
