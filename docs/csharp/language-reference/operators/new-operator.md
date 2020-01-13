---
title: Справочник по C#. Оператор new
ms.date: 06/25/2019
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: beb55f0765e7f9090f0587f1d2a06cf03ea90ab8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712667"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="76392-102">Оператор new (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="76392-102">new operator (C# reference)</span></span>

<span data-ttu-id="76392-103">Оператор `new` создает экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="76392-103">The `new` operator creates a new instance of a type.</span></span>

<span data-ttu-id="76392-104">Ключевое слово `new` можно также использовать как [модификатор объявления члена](../keywords/new-modifier.md) или [ограничение универсального типа](../keywords/new-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="76392-104">You can also use the `new` keyword as a [member declaration modifier](../keywords/new-modifier.md) or a [generic type constraint](../keywords/new-constraint.md).</span></span>

## <a name="constructor-invocation"></a><span data-ttu-id="76392-105">Вызов конструктора</span><span class="sxs-lookup"><span data-stu-id="76392-105">Constructor invocation</span></span>

<span data-ttu-id="76392-106">Для создания экземпляра типа обычно вызывается один из [конструкторов](../../programming-guide/classes-and-structs/constructors.md) этого типа с помощью оператора `new`:</span><span class="sxs-lookup"><span data-stu-id="76392-106">To create a new instance of a type, you typically invoke one of the [constructors](../../programming-guide/classes-and-structs/constructors.md) of that type using the `new` operator:</span></span>

[!code-csharp-interactive[invoke constructor](~/samples/csharp/language-reference/operators/NewOperator.cs#Constructor)]

<span data-ttu-id="76392-107">Для создания экземпляра объекта и его инициализации в одном операторе можно использовать [инициализатор объекта или элементов](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) с оператором `new`, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="76392-107">You can use an [object or collection initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) with the `new` operator to instantiate and initialize an object in one statement, as the following example shows:</span></span>

[!code-csharp-interactive[constructor with initializer](~/samples/csharp/language-reference/operators/NewOperator.cs#ConstructorWithInitializer)]

## <a name="array-creation"></a><span data-ttu-id="76392-108">создание массива</span><span class="sxs-lookup"><span data-stu-id="76392-108">Array creation</span></span>

<span data-ttu-id="76392-109">С помощью оператора `new` можно также создать экземпляр массива, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="76392-109">You also use the `new` operator to create an array instance, as the following example shows:</span></span>

[!code-csharp-interactive[create array](~/samples/csharp/language-reference/operators/NewOperator.cs#Array)]

<span data-ttu-id="76392-110">Чтобы создать экземпляр массива и заполнить его элементами в одном операторе, используйте синтаксис инициализации массива.</span><span class="sxs-lookup"><span data-stu-id="76392-110">Use array initialization syntax to create an array instance and populate it with elements in one statement.</span></span> <span data-ttu-id="76392-111">В следующем примере показаны различные способы сделать это:</span><span class="sxs-lookup"><span data-stu-id="76392-111">The following example shows various ways how you can do that:</span></span>

[!code-csharp-interactive[initialize array](~/samples/csharp/language-reference/operators/NewOperator.cs#ArrayInitialization)]

<span data-ttu-id="76392-112">Дополнительные сведения см. в руководстве по работе с [массивами](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="76392-112">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="instantiation-of-anonymous-types"></a><span data-ttu-id="76392-113">Создание экземпляров анонимных типов</span><span class="sxs-lookup"><span data-stu-id="76392-113">Instantiation of anonymous types</span></span>

<span data-ttu-id="76392-114">Чтобы создать экземпляр [анонимного типа](../../programming-guide/classes-and-structs/anonymous-types.md), используйте оператор `new` и синтаксис инициализации объекта:</span><span class="sxs-lookup"><span data-stu-id="76392-114">To create an instance of an [anonymous type](../../programming-guide/classes-and-structs/anonymous-types.md), use the `new` operator and object initializer syntax:</span></span>

[!code-csharp-interactive[anonymous type](~/samples/csharp/language-reference/operators/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a><span data-ttu-id="76392-115">Уничтожение экземпляров типа</span><span class="sxs-lookup"><span data-stu-id="76392-115">Destruction of type instances</span></span>

<span data-ttu-id="76392-116">Уничтожать ранее созданные экземпляры типа необязательно.</span><span class="sxs-lookup"><span data-stu-id="76392-116">You don't have to destroy earlier created type instances.</span></span> <span data-ttu-id="76392-117">Экземпляры как ссылочных типов, так и типов значений уничтожаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="76392-117">Instances of both reference and value types are destroyed automatically.</span></span> <span data-ttu-id="76392-118">Экземпляры типов значений уничтожаются, как только уничтожается содержащий их контекст.</span><span class="sxs-lookup"><span data-stu-id="76392-118">Instances of value types are destroyed as soon as the context that contains them is destroyed.</span></span> <span data-ttu-id="76392-119">Экземпляры ссылочных типов уничтожаются [сборщиком мусора](../../../standard/garbage-collection/index.md) в неуказанное время после удаления последней ссылки на них.</span><span class="sxs-lookup"><span data-stu-id="76392-119">Instances of reference types are destroyed by the [garbage collector](../../../standard/garbage-collection/index.md) at unspecified time after the last reference to them is removed.</span></span>

<span data-ttu-id="76392-120">Для экземпляров типа, которые содержат неуправляемые ресурсы, например дескриптор файла, рекомендуется использовать детерминированную очистку, чтобы как можно скорее высвободить эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="76392-120">For type instances that contain unmanaged resources, for example, a file handle, it's recommended to employ deterministic clean-up to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="76392-121">Дополнительные сведения см. в справке по API <xref:System.IDisposable?displayProperty=nameWithType> и статье об [операторе using](../keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="76392-121">For more information, see the <xref:System.IDisposable?displayProperty=nameWithType> API reference and the [using statement](../keywords/using-statement.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="76392-122">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="76392-122">Operator overloadability</span></span>

<span data-ttu-id="76392-123">Пользовательский тип не может перегружать оператор `new`.</span><span class="sxs-lookup"><span data-stu-id="76392-123">A user-defined type cannot overload the `new` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="76392-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="76392-124">C# language specification</span></span>

<span data-ttu-id="76392-125">Дополнительные сведения см. в разделе [Оператор new](~/_csharplang/spec/expressions.md#the-new-operator)[спецификация языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="76392-125">For more information, see [The new operator](~/_csharplang/spec/expressions.md#the-new-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="76392-126">См. также</span><span class="sxs-lookup"><span data-stu-id="76392-126">See also</span></span>

- [<span data-ttu-id="76392-127">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="76392-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="76392-128">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="76392-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="76392-129">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="76392-129">Object and collection initializers</span></span>](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
