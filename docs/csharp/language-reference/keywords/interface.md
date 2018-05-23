---
title: interface (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 0320b1e287f8c7a3eb7751b68b40120f74e8f61c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="interface-c-reference"></a><span data-ttu-id="0d97d-102">interface (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0d97d-102">interface (C# Reference)</span></span>
<span data-ttu-id="0d97d-103">Интерфейс содержит только сигнатуры [методов](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойств](../../../csharp/programming-guide/classes-and-structs/properties.md), [событий](../../../csharp/programming-guide/events/index.md) или [индексаторов](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="0d97d-103">An interface contains only the signatures of [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [events](../../../csharp/programming-guide/events/index.md) or [indexers](../../../csharp/programming-guide/indexers/index.md).</span></span> <span data-ttu-id="0d97d-104">Класс или структура, реализующие интерфейс, должны реализовать члены интерфейса, заданные в определении интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0d97d-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="0d97d-105">В следующем примере класс `ImplementationClass` должен реализовать метод с именем `SampleMethod`, не имеющий параметров и возвращающий значение `void`.</span><span class="sxs-lookup"><span data-stu-id="0d97d-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>  
  
 <span data-ttu-id="0d97d-106">Дополнительные сведения и примеры см. в разделе [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="0d97d-106">For more information and examples, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d97d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0d97d-107">Example</span></span>  
 [!code-csharp[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]  
  
 <span data-ttu-id="0d97d-108">Интерфейс может быть членом пространства имен или класса и содержать сигнатуры следующих членов:</span><span class="sxs-lookup"><span data-stu-id="0d97d-108">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>  
  
-   [<span data-ttu-id="0d97d-109">Методы</span><span class="sxs-lookup"><span data-stu-id="0d97d-109">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="0d97d-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="0d97d-110">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="0d97d-111">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="0d97d-111">Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="0d97d-112">События</span><span class="sxs-lookup"><span data-stu-id="0d97d-112">Events</span></span>](../../../csharp/language-reference/keywords/event.md)  
  
 <span data-ttu-id="0d97d-113">Интерфейс может наследовать от одного или нескольких базовых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="0d97d-113">An interface can inherit from one or more base interfaces.</span></span>  
  
 <span data-ttu-id="0d97d-114">Если список базовых типов содержит базовый класс и интерфейсы, базовый класс должен стоять первым в списке.</span><span class="sxs-lookup"><span data-stu-id="0d97d-114">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>  
  
 <span data-ttu-id="0d97d-115">Класс, реализующий интерфейс, может явно реализовывать члены этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0d97d-115">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="0d97d-116">При явной реализации члена к нему можно получить доступ только через экземпляр интерфейса, но не через экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="0d97d-116">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>  
  
 <span data-ttu-id="0d97d-117">Дополнительные сведения и примеры кода с явной реализацией интерфейса см. в разделе [Явная реализация интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="0d97d-117">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d97d-118">Пример</span><span class="sxs-lookup"><span data-stu-id="0d97d-118">Example</span></span>  
 <span data-ttu-id="0d97d-119">В следующем примере показана реализация интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0d97d-119">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="0d97d-120">В этом примере интерфейс содержит объявление свойства, а класс содержит реализацию.</span><span class="sxs-lookup"><span data-stu-id="0d97d-120">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="0d97d-121">Любой экземпляр класса, который реализует `IPoint`, имеет целочисленные свойства `x` и `y`.</span><span class="sxs-lookup"><span data-stu-id="0d97d-121">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0d97d-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0d97d-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d97d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0d97d-123">See Also</span></span>  
 [<span data-ttu-id="0d97d-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0d97d-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0d97d-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0d97d-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0d97d-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0d97d-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0d97d-127">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="0d97d-127">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="0d97d-128">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="0d97d-128">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="0d97d-129">Использование свойств</span><span class="sxs-lookup"><span data-stu-id="0d97d-129">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
 [<span data-ttu-id="0d97d-130">Использование индексаторов</span><span class="sxs-lookup"><span data-stu-id="0d97d-130">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
 [<span data-ttu-id="0d97d-131">class</span><span class="sxs-lookup"><span data-stu-id="0d97d-131">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="0d97d-132">struct</span><span class="sxs-lookup"><span data-stu-id="0d97d-132">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
 [<span data-ttu-id="0d97d-133">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="0d97d-133">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
