---
title: "Привязки do в классах (F#)"
description: "Сведения об использовании выполните привязку в определении класса, который выполняет действия, при создании объекта или при первом использовании типа F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 78987cb8-bdba-46e2-b5b2-994c83fe42c4
ms.openlocfilehash: f9582338306d87c3dd799425083037cc95b31b1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="c4174-104">Привязки do в классах</span><span class="sxs-lookup"><span data-stu-id="c4174-104">do Bindings in Classes</span></span>

<span data-ttu-id="c4174-105">Объект `do` привязки в определении класса выполняет действия, при создании объекта или для статических `do` привязки, когда тип первого использования.</span><span class="sxs-lookup"><span data-stu-id="c4174-105">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>


## <a name="syntax"></a><span data-ttu-id="c4174-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4174-106">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="c4174-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4174-107">Remarks</span></span>
<span data-ttu-id="c4174-108">Объект `do` привязки отображается вместе с или после `let` привязки, но до определения членов в определении класса.</span><span class="sxs-lookup"><span data-stu-id="c4174-108">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="c4174-109">Несмотря на то что `do` ключевое слово является обязательным для `do` привязки на уровне модуля, он не является необязательным для `do` привязки в определении класса.</span><span class="sxs-lookup"><span data-stu-id="c4174-109">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="c4174-110">Для построения всех объектов любого заданного типа нестатические `do` привязок и нестатические `let` выполняются в порядке, в котором они появляются в определении класса.</span><span class="sxs-lookup"><span data-stu-id="c4174-110">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="c4174-111">Несколько `do` привязки могут возникать в один тип.</span><span class="sxs-lookup"><span data-stu-id="c4174-111">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="c4174-112">Нестатические `let` привязок и нестатические `do` становятся основной первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="c4174-112">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="c4174-113">Код в нестатических `do` раздел привязок могут ссылаться на параметры главного конструктора и любые значения или функции, определенные в `let` разделе привязок.</span><span class="sxs-lookup"><span data-stu-id="c4174-113">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="c4174-114">Для не являющегося статическим `do` привязки можно получить доступ к членам класса при условии, что класс имеет собственный идентификатор, определяемый `as` ключевое слово в заголовке класса, а при условии, что все случаи использования этих элементов указаны с собственный идентификатор для класса.</span><span class="sxs-lookup"><span data-stu-id="c4174-114">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="c4174-115">Так как `let` привязок инициализируют закрытые поля класса, который часто необходимо, чтобы обеспечить правильное поведение членов, как ожидалось, `do` привязки обычно помещаются после `let` привязок, что код в `do` может привязки выполните с полностью инициализированный объект.</span><span class="sxs-lookup"><span data-stu-id="c4174-115">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="c4174-116">Если ваш код пытается использовать член до завершения инициализации, возникает исключение InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="c4174-116">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="c4174-117">Статические `do` привязки могут ссылаться на статические члены или поля включающего класса, но не члены или поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c4174-117">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="c4174-118">Статические `do` привязки становятся частью статический инициализатор для класса, который гарантированно выполняется до первого использования класса.</span><span class="sxs-lookup"><span data-stu-id="c4174-118">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="c4174-119">Атрибуты учитываются для `do` привязки в типы.</span><span class="sxs-lookup"><span data-stu-id="c4174-119">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="c4174-120">Если атрибут требуется для кода, который выполняется в `do` привязки, он должен применяться к первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="c4174-120">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="c4174-121">В следующем коде класс имеет статическое `do` привязки и нестатическую `do` привязки.</span><span class="sxs-lookup"><span data-stu-id="c4174-121">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="c4174-122">Объект имеет конструктор, который имеет два параметра `a` и `b`, и два закрытых поля определены в `let` привязки для класса.</span><span class="sxs-lookup"><span data-stu-id="c4174-122">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="c4174-123">Также определяются два свойства.</span><span class="sxs-lookup"><span data-stu-id="c4174-123">Two properties are also defined.</span></span> <span data-ttu-id="c4174-124">Все они находятся в области видимости нестатические `do` раздел привязки, как продемонстрировано в строке, которая выводит эти значения.</span><span class="sxs-lookup"><span data-stu-id="c4174-124">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="c4174-125">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c4174-125">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="c4174-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c4174-126">See Also</span></span>
[<span data-ttu-id="c4174-127">Члены</span><span class="sxs-lookup"><span data-stu-id="c4174-127">Members</span></span>](index.md)

[<span data-ttu-id="c4174-128">Классы</span><span class="sxs-lookup"><span data-stu-id="c4174-128">Classes</span></span>](../classes.md)

[<span data-ttu-id="c4174-129">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="c4174-129">Constructors</span></span>](constructors.md)

[<span data-ttu-id="c4174-130">Привязки `let` в классах</span><span class="sxs-lookup"><span data-stu-id="c4174-130">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)

[<span data-ttu-id="c4174-131">`do`Привязки</span><span class="sxs-lookup"><span data-stu-id="c4174-131">`do` Bindings</span></span>](../functions/do-Bindings.md)
