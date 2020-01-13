---
title: Руководство по программированию на C#. Элементы, воплощающие выражения
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: f212bb707d3dd2d4a7cc917d335a83cff01ed0cf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711991"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="647f2-102">Члены, воплощающие выражения (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="647f2-102">Expression-bodied members (C# programming guide)</span></span>

<span data-ttu-id="647f2-103">Определения тела выражений позволяют предоставлять реализацию члена самым быстрым и удобочитаемым способом.</span><span class="sxs-lookup"><span data-stu-id="647f2-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="647f2-104">Определение тела выражения можно использовать, когда логика для любого поддерживаемого члена, такого как метод или свойство, состоит из одного выражения.</span><span class="sxs-lookup"><span data-stu-id="647f2-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="647f2-105">Определение тела выражения имеет следующий общий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="647f2-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="647f2-106">здесь *expression* является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="647f2-106">where *expression* is a valid expression.</span></span>

<span data-ttu-id="647f2-107">В C# 6 была представлена поддержка для определений тела выражений для методов и свойств только для чтения. В C# 7.0 эта поддержка была расширена.</span><span class="sxs-lookup"><span data-stu-id="647f2-107">Support for expression body definitions was introduced for methods and read-only properties in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="647f2-108">Определения тела выражений можно использовать с членами типа, указанными в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="647f2-108">Expression body definitions can be used with the type members listed in the following table:</span></span>

|<span data-ttu-id="647f2-109">Член</span><span class="sxs-lookup"><span data-stu-id="647f2-109">Member</span></span>  |<span data-ttu-id="647f2-110">Поддерживается как...</span><span class="sxs-lookup"><span data-stu-id="647f2-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="647f2-111">Метод</span><span class="sxs-lookup"><span data-stu-id="647f2-111">Method</span></span>](#methods)  |<span data-ttu-id="647f2-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="647f2-112">C# 6</span></span> |
|[<span data-ttu-id="647f2-113">Свойство только для чтения</span><span class="sxs-lookup"><span data-stu-id="647f2-113">Read-only property</span></span>](#read-only-properties)   |<span data-ttu-id="647f2-114">C# 6</span><span class="sxs-lookup"><span data-stu-id="647f2-114">C# 6</span></span>  |
|[<span data-ttu-id="647f2-115">Property</span><span class="sxs-lookup"><span data-stu-id="647f2-115">Property</span></span>](#properties)  |<span data-ttu-id="647f2-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="647f2-116">C# 7.0</span></span> |
|[<span data-ttu-id="647f2-117">Конструктор</span><span class="sxs-lookup"><span data-stu-id="647f2-117">Constructor</span></span>](#constructors)   |<span data-ttu-id="647f2-118">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="647f2-118">C# 7.0</span></span> |
|[<span data-ttu-id="647f2-119">Метод завершения</span><span class="sxs-lookup"><span data-stu-id="647f2-119">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="647f2-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="647f2-120">C# 7.0</span></span> |
|[<span data-ttu-id="647f2-121">Индексатор</span><span class="sxs-lookup"><span data-stu-id="647f2-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="647f2-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="647f2-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="647f2-123">Методы</span><span class="sxs-lookup"><span data-stu-id="647f2-123">Methods</span></span>

<span data-ttu-id="647f2-124">Метод, воплощающий выражение, состоит из одного выражения, возвращающего значение, тип которого соответствует возвращаемому типу метода, или методов, возвращающих `void`, который выполняет некоторые операции.</span><span class="sxs-lookup"><span data-stu-id="647f2-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="647f2-125">Например, типы, переопределяющие метод <xref:System.Object.ToString%2A>, обычно содержат одно выражение, которое возвращает строковое представление текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="647f2-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span>

<span data-ttu-id="647f2-126">В следующем примере определяется класс `Person`, который переопределяет метод <xref:System.Object.ToString%2A> с помощью определения тела выражения.</span><span class="sxs-lookup"><span data-stu-id="647f2-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="647f2-127">Он также определяет метод `DisplayName`, который отображает имя в консоли.</span><span class="sxs-lookup"><span data-stu-id="647f2-127">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="647f2-128">Обратите внимание, что ключевое слово `return` не используется в определении тела выражения `ToString`.</span><span class="sxs-lookup"><span data-stu-id="647f2-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="647f2-129">Дополнительные сведения см. в разделе [Методы (руководство по программированию на C#)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="647f2-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>

## <a name="read-only-properties"></a><span data-ttu-id="647f2-130">Свойства только для чтения</span><span class="sxs-lookup"><span data-stu-id="647f2-130">Read-only properties</span></span>

<span data-ttu-id="647f2-131">Начиная с C# 6 определение тела выражения можно использовать для реализации свойства только для чтения.</span><span class="sxs-lookup"><span data-stu-id="647f2-131">Starting with C# 6, you can use expression body definition to implement a read-only property.</span></span> <span data-ttu-id="647f2-132">Для этого используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="647f2-132">To do that, use the following syntax:</span></span>

```csharp
PropertyType PropertyName => expression;
```

<span data-ttu-id="647f2-133">В следующем примере определяется класс `Location`, свойство `Name` только для чтения которого реализуется как определение тела выражения, возвращающее значение закрытого поля `locationName`:</span><span class="sxs-lookup"><span data-stu-id="647f2-133">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field:</span></span>

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="647f2-134">Дополнительные сведения о свойствах см. в разделе [Свойства (руководство по программированию на C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="647f2-134">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="properties"></a><span data-ttu-id="647f2-135">Свойства</span><span class="sxs-lookup"><span data-stu-id="647f2-135">Properties</span></span>

<span data-ttu-id="647f2-136">Начиная с C# 7.0 определения тела выражения можно использовать для реализации методов доступа `get` и `set` свойства.</span><span class="sxs-lookup"><span data-stu-id="647f2-136">Starting with C# 7.0, you can use expression body definitions to implement property `get` and `set` accessors.</span></span> <span data-ttu-id="647f2-137">В следующем примере показано, как это сделать:</span><span class="sxs-lookup"><span data-stu-id="647f2-137">The following example demonstrates how to do that:</span></span>

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

<span data-ttu-id="647f2-138">Дополнительные сведения о свойствах см. в разделе [Свойства (руководство по программированию на C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="647f2-138">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="constructors"></a><span data-ttu-id="647f2-139">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="647f2-139">Constructors</span></span>

<span data-ttu-id="647f2-140">Определение тела выражения для конструктора обычно состоит из одного выражения присваивания или вызова метода, который обрабатывает аргументы конструктора или инициализирует состояние экземпляра.</span><span class="sxs-lookup"><span data-stu-id="647f2-140">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span>

<span data-ttu-id="647f2-141">В следующем примере определяется класс `Location`, конструктор которого имеет один строковый параметр *name*.</span><span class="sxs-lookup"><span data-stu-id="647f2-141">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="647f2-142">Определение тела выражения присваивает аргумент свойству `Name`.</span><span class="sxs-lookup"><span data-stu-id="647f2-142">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="647f2-143">Дополнительные сведения см. в разделе [Конструкторы (руководство по программированию на C#)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="647f2-143">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="647f2-144">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="647f2-144">Finalizers</span></span>

<span data-ttu-id="647f2-145">Определение тела выражения для метода завершения обычно содержит операторы очистки, например операторы, высвобождающие неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="647f2-145">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="647f2-146">В следующем примере определяется метод завершения, который использует определение тела выражения для указания того, что был вызван метод завершения.</span><span class="sxs-lookup"><span data-stu-id="647f2-146">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="647f2-147">Дополнительные сведения см. в разделе [Методы завершения (руководство по программированию на C#)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="647f2-147">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="647f2-148">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="647f2-148">Indexers</span></span>

<span data-ttu-id="647f2-149">Как при использовании свойств, методы доступа `get` и `set` индексатора состоят из определений тела выражений, если метод доступа `get` состоит из одного выражения, которое возвращает значение, или метод доступа `set` выполняет простое присваивание.</span><span class="sxs-lookup"><span data-stu-id="647f2-149">Like with properties, indexer `get` and `set` accessors consist of expression body definitions if the `get` accessor consists of a single expression that returns a value or the `set` accessor performs a simple assignment.</span></span>

<span data-ttu-id="647f2-150">В следующем примере определяется класс с именем `Sports`, включающий внутренний массив <xref:System.String>, который содержит названия нескольких видов спорта.</span><span class="sxs-lookup"><span data-stu-id="647f2-150">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="647f2-151">Методы доступа `get` и `set` индексатора реализуются как определения тела выражений.</span><span class="sxs-lookup"><span data-stu-id="647f2-151">Both the indexer `get` and `set` accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

<span data-ttu-id="647f2-152">Дополнительные сведения см. в разделе [Индексаторы (руководство по программированию на C#)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="647f2-152">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>
