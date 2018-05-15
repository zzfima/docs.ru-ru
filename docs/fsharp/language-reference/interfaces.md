---
title: Интерфейсы (F#)
description: 'Узнайте, как интерфейсы F # задают наборы связанных членов, которые реализуют другие классы.'
ms.date: 05/16/2016
ms.openlocfilehash: 54ae8a2840ce26814be25f08c3ed02e12df6b7c0
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2018
---
# <a name="interfaces"></a><span data-ttu-id="abfae-103">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="abfae-103">Interfaces</span></span>

<span data-ttu-id="abfae-104">*Интерфейсы* указать набора связанных элементов, которые реализуют другие классы.</span><span class="sxs-lookup"><span data-stu-id="abfae-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="abfae-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abfae-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="abfae-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="abfae-106">Remarks</span></span>
<span data-ttu-id="abfae-107">Объявления интерфейса похоже на объявление класса, но не реализуются члены.</span><span class="sxs-lookup"><span data-stu-id="abfae-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="abfae-108">Вместо этого все члены, являются абстрактными, как указано ключевое слово `abstract`.</span><span class="sxs-lookup"><span data-stu-id="abfae-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="abfae-109">Для абстрактных методов не имеют тела метода.</span><span class="sxs-lookup"><span data-stu-id="abfae-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="abfae-110">Однако, можно предоставить реализацию по умолчанию, дополнительно указав отдельное определение члена как метода с `default` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="abfae-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="abfae-111">Это эквивалентно созданию виртуального метода в базовом классе в других языках .NET.</span><span class="sxs-lookup"><span data-stu-id="abfae-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="abfae-112">Виртуальный метод может переопределяться в классах, которые реализуют интерфейс.</span><span class="sxs-lookup"><span data-stu-id="abfae-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="abfae-113">По умолчанию для интерфейсов является `public`.</span><span class="sxs-lookup"><span data-stu-id="abfae-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="abfae-114">Можно присвоить параметра каждого метода имя, используя обычный синтаксис F #:</span><span class="sxs-lookup"><span data-stu-id="abfae-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="abfae-115">В указанных выше `ISprintable` примере `Print` метод принимает один параметр типа `string` с именем `format`.</span><span class="sxs-lookup"><span data-stu-id="abfae-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="abfae-116">Существует два способа реализации интерфейсов: с помощью выражений объектов и с помощью типов классов.</span><span class="sxs-lookup"><span data-stu-id="abfae-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="abfae-117">В любом случае выражение класса типа или объекта предоставляет тела метода для абстрактных методов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="abfae-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="abfae-118">Реализации специфичны для каждого типа, который реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="abfae-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="abfae-119">Таким образом методы интерфейса для различных типов может отличаться друг от друга.</span><span class="sxs-lookup"><span data-stu-id="abfae-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="abfae-120">Ключевые слова `interface` и `end`, отмечающие начало и конец определения, являются необязательными, если используется упрощенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="abfae-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="abfae-121">Если вы не используете эти ключевые слова, компилятор пытается определить, является ли тип классом или интерфейсом, анализируя конструкций, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="abfae-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="abfae-122">Если определение члена или использовать другие синтаксические элементы класса, тип интерпретируется как класс.</span><span class="sxs-lookup"><span data-stu-id="abfae-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="abfae-123">Стиль написания кода .NET рекомендуется начинать имена интерфейсов с заглавной буквы `I`.</span><span class="sxs-lookup"><span data-stu-id="abfae-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>


## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="abfae-124">Реализация интерфейсов с помощью типов классов</span><span class="sxs-lookup"><span data-stu-id="abfae-124">Implementing Interfaces by Using Class Types</span></span>
<span data-ttu-id="abfae-125">Один или несколько интерфейсов можно реализовать в типе класса с помощью `interface` ключевое слово, имя интерфейса и `with` ключевое слово, и определения членов интерфейса, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="abfae-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="abfae-126">Реализации интерфейсов наследуются, поэтому любые производные классы не нужно повторно реализовать их.</span><span class="sxs-lookup"><span data-stu-id="abfae-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>


## <a name="calling-interface-methods"></a><span data-ttu-id="abfae-127">Вызов методов интерфейса</span><span class="sxs-lookup"><span data-stu-id="abfae-127">Calling Interface Methods</span></span>
<span data-ttu-id="abfae-128">Методы интерфейса может вызываться только с помощью интерфейса, а не через объекты типа, который реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="abfae-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="abfae-129">Таким образом, возможно, потребуется привести к типу интерфейса с помощью `:>` оператор или `upcast` оператор для вызова этих методов.</span><span class="sxs-lookup"><span data-stu-id="abfae-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="abfae-130">Чтобы вызвать метод интерфейса, если имеется объект типа `SomeClass`, необходимо привести объект к типу интерфейса, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="abfae-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="abfae-131">Альтернативой является объявление метода для объекта, приводит и вызывает метод интерфейса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="abfae-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="abfae-132">Реализация интерфейсов с помощью выражения объекта</span><span class="sxs-lookup"><span data-stu-id="abfae-132">Implementing Interfaces by Using Object Expressions</span></span>
<span data-ttu-id="abfae-133">Выражения объектов обеспечивают простой способ реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="abfae-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="abfae-134">Они полезны в том случае, когда необходимо создать именованный тип, необходимо просто объекта, который поддерживает методы интерфейса, без дополнительных методов.</span><span class="sxs-lookup"><span data-stu-id="abfae-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="abfae-135">В следующем коде показано выражение объекта.</span><span class="sxs-lookup"><span data-stu-id="abfae-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a><span data-ttu-id="abfae-136">Наследование интерфейса</span><span class="sxs-lookup"><span data-stu-id="abfae-136">Interface Inheritance</span></span>
<span data-ttu-id="abfae-137">Интерфейсы могут наследовать от одного или нескольких базовых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="abfae-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a><span data-ttu-id="abfae-138">См. также</span><span class="sxs-lookup"><span data-stu-id="abfae-138">See Also</span></span>
[<span data-ttu-id="abfae-139">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="abfae-139">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="abfae-140">Выражения объекта</span><span class="sxs-lookup"><span data-stu-id="abfae-140">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="abfae-141">Классы</span><span class="sxs-lookup"><span data-stu-id="abfae-141">Classes</span></span>](classes.md)
