---
title: Интерфейсы
description: Узнайте, F# как интерфейсы определяют наборы связанных элементов, реализуемых другими классами.
ms.date: 05/16/2016
ms.openlocfilehash: 8f054a668ad0fbc2453a45883e8052471280eca3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627645"
---
# <a name="interfaces"></a><span data-ttu-id="6ccfe-103">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6ccfe-103">Interfaces</span></span>

<span data-ttu-id="6ccfe-104">*Интерфейсы* указывают наборы связанных элементов, реализуемых другими классами.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ccfe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ccfe-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
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

## <a name="remarks"></a><span data-ttu-id="6ccfe-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="6ccfe-106">Remarks</span></span>

<span data-ttu-id="6ccfe-107">Объявления интерфейсов похожи на объявления классов, за исключением того, что ни один член не реализован.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="6ccfe-108">Вместо этого все члены являются абстрактными, как указано ключевым словом `abstract`.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="6ccfe-109">Не предоставляется тело метода для абстрактных методов.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="6ccfe-110">Однако можно предоставить реализацию по умолчанию, включив отдельное определение члена в качестве метода вместе с `default` ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="6ccfe-111">Это эквивалентно созданию виртуального метода в базовом классе на других языках .NET.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="6ccfe-112">Такой виртуальный метод можно переопределить в классах, реализующих интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="6ccfe-113">По умолчанию для интерфейсов `public`используется уровень доступности.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="6ccfe-114">При необходимости можно присвоить каждому параметру метода имя с F# помощью обычного синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="6ccfe-115">В приведенном `ISprintable` выше примере `Print` метод имеет единственный параметр типа `string` с именем `format`.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="6ccfe-116">Реализовать интерфейсы можно двумя способами: с помощью выражений объектов и типов классов.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="6ccfe-117">В любом случае тип класса или выражение объекта предоставляет тела методов для абстрактных методов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="6ccfe-118">Реализации относятся к каждому типу, реализующему интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="6ccfe-119">Поэтому методы интерфейса для разных типов могут отличаться друг от друга.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="6ccfe-120">Ключевые слова `interface` и `end`, которые отмечают начало и конец определения, являются необязательными при использовании упрощенного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="6ccfe-121">Если эти ключевые слова не используются, компилятор пытается определить, является ли тип классом или интерфейсом, анализируя используемые конструкции.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="6ccfe-122">При определении члена или использовании другого синтаксиса класса тип интерпретируется как класс.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="6ccfe-123">Стиль написания кода .NET — это начало всех интерфейсов с заглавной буквой `I`.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="6ccfe-124">Реализация интерфейсов с помощью типов классов</span><span class="sxs-lookup"><span data-stu-id="6ccfe-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="6ccfe-125">Можно реализовать один или несколько интерфейсов в типе класса с помощью `interface` ключевого слова, имени интерфейса `with` и ключевого слова, а затем определений членов интерфейса, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="6ccfe-126">Реализации интерфейса наследуются, поэтому все производные классы не нуждаются в их повторной реализации.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="6ccfe-127">Вызов методов интерфейса</span><span class="sxs-lookup"><span data-stu-id="6ccfe-127">Calling Interface Methods</span></span>

<span data-ttu-id="6ccfe-128">Методы интерфейса могут вызываться только через интерфейс, а не через какой-либо объект типа, который реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="6ccfe-129">Поэтому для вызова этих методов может потребоваться выполнить приведение к типу интерфейса с помощью `:>` оператора `upcast` или оператора.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="6ccfe-130">Чтобы вызвать метод интерфейса при наличии объекта типа `SomeClass`, необходимо выполнить операцию приведения объекта к типу интерфейса, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="6ccfe-131">Альтернативой является объявление метода для объекта, который выполняет приведение и вызов метода интерфейса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="6ccfe-132">Реализация интерфейсов с помощью выражений объектов</span><span class="sxs-lookup"><span data-stu-id="6ccfe-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="6ccfe-133">Выражения объектов предоставляют короткий способ реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="6ccfe-134">Они полезны в тех случаях, когда не нужно создавать именованный тип и нужен только объект, поддерживающий методы интерфейса, без каких-либо дополнительных методов.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="6ccfe-135">В следующем коде показано выражение объекта.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="6ccfe-136">Наследование интерфейса</span><span class="sxs-lookup"><span data-stu-id="6ccfe-136">Interface Inheritance</span></span>

<span data-ttu-id="6ccfe-137">Интерфейсы могут наследовать от одного или нескольких базовых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="6ccfe-138">См. также</span><span class="sxs-lookup"><span data-stu-id="6ccfe-138">See also</span></span>

- [<span data-ttu-id="6ccfe-139">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="6ccfe-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6ccfe-140">Выражения объекта</span><span class="sxs-lookup"><span data-stu-id="6ccfe-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="6ccfe-141">Классы</span><span class="sxs-lookup"><span data-stu-id="6ccfe-141">Classes</span></span>](classes.md)
