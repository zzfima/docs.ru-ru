---
title: интерфейсов,
description: Узнайте, как F# интерфейсы задают наборы связанных элементов, реализуемых другими классами.
ms.date: 05/16/2016
ms.openlocfilehash: 85b5506d96c26be5e52670c0c62d27cae047d1a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666382"
---
# <a name="interfaces"></a><span data-ttu-id="97912-103">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="97912-103">Interfaces</span></span>

<span data-ttu-id="97912-104">*Интерфейсы* указать наборы связанных элементов, реализуемых другими классами.</span><span class="sxs-lookup"><span data-stu-id="97912-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="97912-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97912-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="97912-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="97912-106">Remarks</span></span>

<span data-ttu-id="97912-107">Объявления интерфейса похоже на объявление класса за исключением того, что члены не реализуются.</span><span class="sxs-lookup"><span data-stu-id="97912-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="97912-108">Вместо этого все члены являются абстрактными, обозначенный ключевое слово `abstract`.</span><span class="sxs-lookup"><span data-stu-id="97912-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="97912-109">Вы не укажете тела метода для абстрактных методов.</span><span class="sxs-lookup"><span data-stu-id="97912-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="97912-110">Тем не менее, можно добавить реализацию по умолчанию, также указав отдельное определение члена как метода с `default` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="97912-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="97912-111">Это эквивалентно созданию виртуальный метод в базовом классе в других языках .NET.</span><span class="sxs-lookup"><span data-stu-id="97912-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="97912-112">Виртуальный метод может переопределяться в классах, реализующих интерфейс.</span><span class="sxs-lookup"><span data-stu-id="97912-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="97912-113">Доступность по умолчанию для интерфейсов `public`.</span><span class="sxs-lookup"><span data-stu-id="97912-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="97912-114">Можно присвоить каждого параметра метода имя, с помощью обычного F# синтаксис:</span><span class="sxs-lookup"><span data-stu-id="97912-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="97912-115">В указанных выше `ISprintable` примере `Print` метод имеет один параметр типа `string` с именем `format`.</span><span class="sxs-lookup"><span data-stu-id="97912-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="97912-116">Существует два способа реализации интерфейсов: с помощью выражений объектов и с помощью типов классов.</span><span class="sxs-lookup"><span data-stu-id="97912-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="97912-117">В любом случае выражение типа или объекта класса предоставляет тел методов для абстрактных методов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="97912-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="97912-118">Реализации для каждого типа, который реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="97912-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="97912-119">Таким образом методы интерфейса на разных типах, может отличаться друг от друга.</span><span class="sxs-lookup"><span data-stu-id="97912-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="97912-120">Ключевые слова `interface` и `end`, отмечающие начало и конец определения, являются необязательными, если используется упрощенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="97912-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="97912-121">Если вы не используете эти ключевые слова, компилятор пытается определить, является ли тип классом или интерфейсом, анализируя конструкции, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="97912-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="97912-122">Если определение элемента или использовать другой синтаксис класса, тип интерпретируется как класс.</span><span class="sxs-lookup"><span data-stu-id="97912-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="97912-123">Стиль написания кода .NET является начало интерфейсов с заглавной буквы `I`.</span><span class="sxs-lookup"><span data-stu-id="97912-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="97912-124">Реализация интерфейсов с помощью типов классов</span><span class="sxs-lookup"><span data-stu-id="97912-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="97912-125">Один или несколько интерфейсов можно реализовать в типе класса с помощью `interface` ключевое слово, имя интерфейса и `with` ключевое слово, и определения членов интерфейса, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="97912-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="97912-126">Реализации интерфейса наследуются, поэтому всем производным классам не нужно повторно реализовать их.</span><span class="sxs-lookup"><span data-stu-id="97912-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="97912-127">Вызов методов интерфейса</span><span class="sxs-lookup"><span data-stu-id="97912-127">Calling Interface Methods</span></span>

<span data-ttu-id="97912-128">Методы интерфейса может вызываться только через интерфейс, не с помощью любого объекта типа, который реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="97912-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="97912-129">Таким образом, может потребоваться привести к типу интерфейса с помощью `:>` оператор или `upcast` оператор для вызова этих методов.</span><span class="sxs-lookup"><span data-stu-id="97912-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="97912-130">Для вызова метода интерфейса, при наличии объекта типа `SomeClass`, необходимо привести объект к типу интерфейса, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="97912-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="97912-131">Альтернативой является объявление метода для объекта, приводит и вызывает метод интерфейса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="97912-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="97912-132">Реализация интерфейсов с помощью выражения объекта</span><span class="sxs-lookup"><span data-stu-id="97912-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="97912-133">Выражения объектов обеспечивают простой способ реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="97912-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="97912-134">Они полезны в тех случаях, когда нет необходимости создавать именованный тип, и вам требуется объект, поддерживающий методов интерфейса, без дополнительных методов.</span><span class="sxs-lookup"><span data-stu-id="97912-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="97912-135">В следующем коде показано выражение объекта.</span><span class="sxs-lookup"><span data-stu-id="97912-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="97912-136">Наследование интерфейса</span><span class="sxs-lookup"><span data-stu-id="97912-136">Interface Inheritance</span></span>

<span data-ttu-id="97912-137">Интерфейсы могут наследовать от одного или нескольких базовых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="97912-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="97912-138">См. также</span><span class="sxs-lookup"><span data-stu-id="97912-138">See also</span></span>

- [<span data-ttu-id="97912-139">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="97912-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="97912-140">Выражения объекта</span><span class="sxs-lookup"><span data-stu-id="97912-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="97912-141">Классы</span><span class="sxs-lookup"><span data-stu-id="97912-141">Classes</span></span>](classes.md)