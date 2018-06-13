---
title: Члены, воплощающие выражения (руководство по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 800280ed9ceaf69b825bb2a3c2c3d0d5f829922d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332758"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="68c3d-102">Члены, воплощающие выражения (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="68c3d-102">Expression-bodied members (C# programming guide)</span></span>
<span data-ttu-id="68c3d-103">Определения тела выражений позволяют предоставлять реализацию члена самым быстрым и удобочитаемым способом.</span><span class="sxs-lookup"><span data-stu-id="68c3d-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="68c3d-104">Определение тела выражения можно использовать, когда логика для любого поддерживаемого члена, такого как метод или свойство, состоит из одного выражения.</span><span class="sxs-lookup"><span data-stu-id="68c3d-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="68c3d-105">Определение тела выражения имеет следующий общий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="68c3d-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="68c3d-106">здесь *expression* является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="68c3d-106">where *expression* is a valid expression.</span></span> 

<span data-ttu-id="68c3d-107">В C# 6 была представлена поддержка для определений тела выражений для методов и методов доступа Property Get. В C# 7.0 эта поддержка была расширена.</span><span class="sxs-lookup"><span data-stu-id="68c3d-107">Support for expression body definitions was introduced for methods and property get accessors in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="68c3d-108">Определения тела выражений можно использовать с членами типа, указанными в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="68c3d-108">Expression body definitions can be used with the type members listed in the following table:</span></span> 

|<span data-ttu-id="68c3d-109">Член</span><span class="sxs-lookup"><span data-stu-id="68c3d-109">Member</span></span>  |<span data-ttu-id="68c3d-110">Поддерживается как...</span><span class="sxs-lookup"><span data-stu-id="68c3d-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="68c3d-111">Метод</span><span class="sxs-lookup"><span data-stu-id="68c3d-111">Method</span></span>](#methods)  |<span data-ttu-id="68c3d-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="68c3d-112">C# 6</span></span> |
|[<span data-ttu-id="68c3d-113">Конструктор</span><span class="sxs-lookup"><span data-stu-id="68c3d-113">Constructor</span></span>](#constructors)   |<span data-ttu-id="68c3d-114">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="68c3d-114">C# 7.0</span></span> |
|[<span data-ttu-id="68c3d-115">Метод завершения</span><span class="sxs-lookup"><span data-stu-id="68c3d-115">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="68c3d-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="68c3d-116">C# 7.0</span></span> |
|[<span data-ttu-id="68c3d-117">Property Get</span><span class="sxs-lookup"><span data-stu-id="68c3d-117">Property Get</span></span>](#property-get-statements)  |<span data-ttu-id="68c3d-118">C# 6</span><span class="sxs-lookup"><span data-stu-id="68c3d-118">C# 6</span></span> |
|[<span data-ttu-id="68c3d-119">Property Set</span><span class="sxs-lookup"><span data-stu-id="68c3d-119">Property Set</span></span>](#property-set-statements)  |<span data-ttu-id="68c3d-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="68c3d-120">C# 7.0</span></span> |
|[<span data-ttu-id="68c3d-121">Индексатор</span><span class="sxs-lookup"><span data-stu-id="68c3d-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="68c3d-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="68c3d-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="68c3d-123">Методы</span><span class="sxs-lookup"><span data-stu-id="68c3d-123">Methods</span></span>

<span data-ttu-id="68c3d-124">Метод, воплощающий выражение, состоит из одного выражения, возвращающего значение, тип которого соответствует возвращаемому типу метода, или методов, возвращающих `void`, который выполняет некоторые операции.</span><span class="sxs-lookup"><span data-stu-id="68c3d-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="68c3d-125">Например, типы, переопределяющие метод <xref:System.Object.ToString%2A>, обычно содержат одно выражение, которое возвращает строковое представление текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="68c3d-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span> 

<span data-ttu-id="68c3d-126">В следующем примере определяется класс `Person`, который переопределяет метод <xref:System.Object.ToString%2A> с помощью определения тела выражения.</span><span class="sxs-lookup"><span data-stu-id="68c3d-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="68c3d-127">Он также определяет метод `Show`, который отображает имя в консоли.</span><span class="sxs-lookup"><span data-stu-id="68c3d-127">It also defines a `Show` method that displays a name to the console.</span></span> <span data-ttu-id="68c3d-128">Обратите внимание, что ключевое слово `return` не используется в определении тела выражения `ToString`.</span><span class="sxs-lookup"><span data-stu-id="68c3d-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="68c3d-129">Дополнительные сведения см. в разделе [Методы (руководство по программированию на C#)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="68c3d-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>
 
## <a name="constructors"></a><span data-ttu-id="68c3d-130">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="68c3d-130">Constructors</span></span>

<span data-ttu-id="68c3d-131">Определение тела выражения для конструктора обычно состоит из одного выражения присваивания или вызова метода, который обрабатывает аргументы конструктора или инициализирует состояние экземпляра.</span><span class="sxs-lookup"><span data-stu-id="68c3d-131">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span> 

<span data-ttu-id="68c3d-132">В следующем примере определяется класс `Location`, конструктор которого имеет один строковый параметр *name*.</span><span class="sxs-lookup"><span data-stu-id="68c3d-132">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="68c3d-133">Определение тела выражения присваивает аргумент свойству `Name`.</span><span class="sxs-lookup"><span data-stu-id="68c3d-133">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="68c3d-134">Дополнительные сведения см. в разделе [Конструкторы (руководство по программированию на C#)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="68c3d-134">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="68c3d-135">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="68c3d-135">Finalizers</span></span>

<span data-ttu-id="68c3d-136">Определение тела выражения для метода завершения обычно содержит операторы очистки, например операторы, высвобождающие неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="68c3d-136">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="68c3d-137">В следующем примере определяется метод завершения, который использует определение тела выражения для указания того, что был вызван метод завершения.</span><span class="sxs-lookup"><span data-stu-id="68c3d-137">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="68c3d-138">Дополнительные сведения см. в разделе [Методы завершения (руководство по программированию на C#)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="68c3d-138">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="property-get-statements"></a><span data-ttu-id="68c3d-139">Операторы Property Get</span><span class="sxs-lookup"><span data-stu-id="68c3d-139">Property get statements</span></span>

<span data-ttu-id="68c3d-140">Если вы решили самостоятельно реализовать метод доступа Property Get, определение тела выражения можно использовать для отдельных выражений, которые просто возвращают значение свойства.</span><span class="sxs-lookup"><span data-stu-id="68c3d-140">If you choose to implement a property get accessor yourself, you can use an expression body definition for single expressions that simply return the property value.</span></span> <span data-ttu-id="68c3d-141">Обратите внимание, что оператор `return` не используется.</span><span class="sxs-lookup"><span data-stu-id="68c3d-141">Note that the `return` statement isn't used.</span></span>

<span data-ttu-id="68c3d-142">В следующем примере определяется свойство `Location.Name`, метод доступа Property Get которого возвращает значение закрытого поля `locationName`, поддерживающего свойство.</span><span class="sxs-lookup"><span data-stu-id="68c3d-142">The following example defines a `Location.Name` property whose property get accessor returns the value of the private `locationName` field that backs the property.</span></span> 

[!code-csharp[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="68c3d-143">Свойства только для чтения, использующие определение тела выражения, можно реализовать без явного оператора `set`.</span><span class="sxs-lookup"><span data-stu-id="68c3d-143">Read-only properties that use an expression body definition can be implemented without an explicit `set` statement.</span></span> <span data-ttu-id="68c3d-144">Синтаксис выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="68c3d-144">The syntax is:</span></span>

```csharp
PropertyName => returnValue;
```

<span data-ttu-id="68c3d-145">В следующем примере определяется класс `Location`, свойство `Name` только для чтения которого реализуется как определение тела выражения, возвращающее значение закрытого поля `locationName`.</span><span class="sxs-lookup"><span data-stu-id="68c3d-145">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="68c3d-146">Дополнительные сведения см. в разделе [Свойства (руководство по программированию на C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="68c3d-146">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="property-set-statements"></a><span data-ttu-id="68c3d-147">Операторы Property Set</span><span class="sxs-lookup"><span data-stu-id="68c3d-147">Property set statements</span></span>

<span data-ttu-id="68c3d-148">Если вы решили самостоятельно реализовать метод доступа Property Set, определение тела выражения можно использовать для однострочного выражения, которое присваивает значение полю, поддерживающему свойство.</span><span class="sxs-lookup"><span data-stu-id="68c3d-148">If you choose to implement a property set accessor yourself, you can use an expression body definition for a single-line expression that assigns a value to the field that backs the property.</span></span>

<span data-ttu-id="68c3d-149">В следующем примере определяется свойство `Location.Name`, метод доступа Property Set которого присваивает входной аргумент закрытому полю `locationName`, поддерживающему свойство.</span><span class="sxs-lookup"><span data-stu-id="68c3d-149">The following example defines a `Location.Name` property whose property set statement assigns its input argument to the private `locationName` field that backs the property.</span></span>

[!code-csharp[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="68c3d-150">Дополнительные сведения см. в разделе [Свойства (руководство по программированию на C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="68c3d-150">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="68c3d-151">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="68c3d-151">Indexers</span></span>

<span data-ttu-id="68c3d-152">Как и свойства, методы доступа set и get индексатора состоят из определений тела выражений, если метод доступа get состоит из одного оператора, который возвращает значение, или метод доступа set выполняет простое присваивание.</span><span class="sxs-lookup"><span data-stu-id="68c3d-152">Like properties, an indexer's get and set accessors consist of expression body definitions if the get accessor consists of a single statement that returns a value or the set accessor performs a simple assignment.</span></span>

<span data-ttu-id="68c3d-153">В следующем примере определяется класс с именем `Sports`, включающий внутренний массив <xref:System.String>, который содержит названия нескольких видов спорта.</span><span class="sxs-lookup"><span data-stu-id="68c3d-153">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="68c3d-154">Методы доступа get и set индексатора реализуются как определения тела выражений.</span><span class="sxs-lookup"><span data-stu-id="68c3d-154">Both the indexer's get and set accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)] 

<span data-ttu-id="68c3d-155">Дополнительные сведения см. в разделе [Индексаторы (руководство по программированию на C#)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="68c3d-155">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>

