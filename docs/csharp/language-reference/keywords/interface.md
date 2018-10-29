---
title: interface (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 4adc7ba106e0044ba6aff94ea3180d9c8e3ded7b
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48872947"
---
# <a name="interface-c-reference"></a><span data-ttu-id="f8c63-102">interface (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f8c63-102">interface (C# Reference)</span></span>

<span data-ttu-id="f8c63-103">Интерфейс содержит только сигнатуры [методов](../../programming-guide/classes-and-structs/methods.md), [свойств](../../programming-guide/classes-and-structs/properties.md), [событий](../../programming-guide/events/index.md) или [индексаторов](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="f8c63-103">An interface contains only the signatures of [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [events](../../programming-guide/events/index.md) or [indexers](../../programming-guide/indexers/index.md).</span></span> <span data-ttu-id="f8c63-104">Класс или структура, реализующие интерфейс, должны реализовать члены интерфейса, заданные в определении интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f8c63-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="f8c63-105">В следующем примере класс `ImplementationClass` должен реализовать метод с именем `SampleMethod`, не имеющий параметров и возвращающий значение `void`.</span><span class="sxs-lookup"><span data-stu-id="f8c63-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="f8c63-106">Дополнительные сведения и примеры см. в разделе [Интерфейсы](../../programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="f8c63-106">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="f8c63-107">Пример</span><span class="sxs-lookup"><span data-stu-id="f8c63-107">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="f8c63-108">Интерфейс может быть членом пространства имен или класса и содержать сигнатуры следующих членов:</span><span class="sxs-lookup"><span data-stu-id="f8c63-108">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>

- [<span data-ttu-id="f8c63-109">Методы</span><span class="sxs-lookup"><span data-stu-id="f8c63-109">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="f8c63-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="f8c63-110">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)

- [<span data-ttu-id="f8c63-111">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="f8c63-111">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)

- [<span data-ttu-id="f8c63-112">События</span><span class="sxs-lookup"><span data-stu-id="f8c63-112">Events</span></span>](event.md)

<span data-ttu-id="f8c63-113">Интерфейс может наследовать от одного или нескольких базовых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f8c63-113">An interface can inherit from one or more base interfaces.</span></span>

<span data-ttu-id="f8c63-114">Если список базовых типов содержит базовый класс и интерфейсы, базовый класс должен стоять первым в списке.</span><span class="sxs-lookup"><span data-stu-id="f8c63-114">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="f8c63-115">Класс, реализующий интерфейс, может явно реализовывать члены этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f8c63-115">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="f8c63-116">При явной реализации члена к нему можно получить доступ только через экземпляр интерфейса, но не через экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="f8c63-116">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>

<span data-ttu-id="f8c63-117">Дополнительные сведения и примеры кода с явной реализацией интерфейса см. в разделе [Явная реализация интерфейса](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="f8c63-117">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="f8c63-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f8c63-118">Example</span></span>

<span data-ttu-id="f8c63-119">В следующем примере показана реализация интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f8c63-119">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="f8c63-120">В этом примере интерфейс содержит объявление свойства, а класс содержит реализацию.</span><span class="sxs-lookup"><span data-stu-id="f8c63-120">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="f8c63-121">Любой экземпляр класса, который реализует `IPoint`, имеет целочисленные свойства `x` и `y`.</span><span class="sxs-lookup"><span data-stu-id="f8c63-121">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="f8c63-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f8c63-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f8c63-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f8c63-123">See also</span></span>

- [<span data-ttu-id="f8c63-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f8c63-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f8c63-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f8c63-125">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="f8c63-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f8c63-126">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="f8c63-127">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="f8c63-127">Reference Types</span></span>](reference-types.md)  
- [<span data-ttu-id="f8c63-128">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f8c63-128">Interfaces</span></span>](../../programming-guide/interfaces/index.md)  
- [<span data-ttu-id="f8c63-129">Использование свойств</span><span class="sxs-lookup"><span data-stu-id="f8c63-129">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)  
- [<span data-ttu-id="f8c63-130">Использование индексаторов</span><span class="sxs-lookup"><span data-stu-id="f8c63-130">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)  
- [<span data-ttu-id="f8c63-131">class</span><span class="sxs-lookup"><span data-stu-id="f8c63-131">class</span></span>](class.md)  
- [<span data-ttu-id="f8c63-132">struct</span><span class="sxs-lookup"><span data-stu-id="f8c63-132">struct</span></span>](struct.md)  
- [<span data-ttu-id="f8c63-133">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f8c63-133">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
