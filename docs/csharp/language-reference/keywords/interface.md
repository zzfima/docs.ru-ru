---
title: "interface (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- interface_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 126e674a2c56f04f54f35a011c24ebf0f713ee8d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="interface-c-reference"></a><span data-ttu-id="1fc6c-102">interface (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1fc6c-102">interface (C# Reference)</span></span>
<span data-ttu-id="1fc6c-103">Интерфейс содержит только сигнатуры [методов](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойств](../../../csharp/programming-guide/classes-and-structs/properties.md), [событий](../../../csharp/programming-guide/events/index.md) или [индексаторов](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="1fc6c-103">An interface contains only the signatures of [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [events](../../../csharp/programming-guide/events/index.md) or [indexers](../../../csharp/programming-guide/indexers/index.md).</span></span> <span data-ttu-id="1fc6c-104">Класс или структура, реализующие интерфейс, должны реализовать члены интерфейса, заданные в определении интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1fc6c-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="1fc6c-105">В следующем примере класс `ImplementationClass` должен реализовать метод с именем `SampleMethod`, не имеющий параметров и возвращающий значение `void`.</span><span class="sxs-lookup"><span data-stu-id="1fc6c-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>  
  
 <span data-ttu-id="1fc6c-106">Дополнительные сведения и примеры см. в разделе [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="1fc6c-106">For more information and examples, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fc6c-107">Пример</span><span class="sxs-lookup"><span data-stu-id="1fc6c-107">Example</span></span>  
 <span data-ttu-id="1fc6c-108">[!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1fc6c-108">[!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]</span></span>  
  
 <span data-ttu-id="1fc6c-109">Интерфейс может быть членом пространства имен или класса и содержать сигнатуры следующих членов:</span><span class="sxs-lookup"><span data-stu-id="1fc6c-109">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>  
  
-   [<span data-ttu-id="1fc6c-110">Методы</span><span class="sxs-lookup"><span data-stu-id="1fc6c-110">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="1fc6c-111">Свойства</span><span class="sxs-lookup"><span data-stu-id="1fc6c-111">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="1fc6c-112">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="1fc6c-112">Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="1fc6c-113">События</span><span class="sxs-lookup"><span data-stu-id="1fc6c-113">Events</span></span>](../../../csharp/language-reference/keywords/event.md)  
  
 <span data-ttu-id="1fc6c-114">Интерфейс может наследовать от одного или нескольких базовых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="1fc6c-114">An interface can inherit from one or more base interfaces.</span></span>  
  
 <span data-ttu-id="1fc6c-115">Если список базовых типов содержит базовый класс и интерфейсы, базовый класс должен стоять первым в списке.</span><span class="sxs-lookup"><span data-stu-id="1fc6c-115">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>  
  
 <span data-ttu-id="1fc6c-116">Класс, реализующий интерфейс, может явно реализовывать члены этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1fc6c-116">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="1fc6c-117">При явной реализации члена к нему можно получить доступ только через экземпляр интерфейса, но не через экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="1fc6c-117">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>  
  
 <span data-ttu-id="1fc6c-118">Дополнительные сведения и примеры кода с явной реализацией интерфейса см. в разделе [Явная реализация интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="1fc6c-118">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fc6c-119">Пример</span><span class="sxs-lookup"><span data-stu-id="1fc6c-119">Example</span></span>  
 <span data-ttu-id="1fc6c-120">В следующем примере показана реализация интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1fc6c-120">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="1fc6c-121">В этом примере интерфейс содержит объявление свойства, а класс содержит реализацию.</span><span class="sxs-lookup"><span data-stu-id="1fc6c-121">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="1fc6c-122">Любой экземпляр класса, который реализует `IPoint`, имеет целочисленные свойства `x` и `y`.</span><span class="sxs-lookup"><span data-stu-id="1fc6c-122">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>  
  
 <span data-ttu-id="1fc6c-123">[!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1fc6c-123">[!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1fc6c-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1fc6c-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1fc6c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1fc6c-125">See Also</span></span>  
 <span data-ttu-id="1fc6c-126">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1fc6c-126">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1fc6c-127">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1fc6c-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1fc6c-128">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="1fc6c-128">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="1fc6c-129">[Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="1fc6c-129">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="1fc6c-130">[Интерфейсы](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="1fc6c-130">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 <span data-ttu-id="1fc6c-131">[Использование свойств](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1fc6c-131">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="1fc6c-132">[Использование индексаторов](../../../csharp/programming-guide/indexers/using-indexers.md) </span><span class="sxs-lookup"><span data-stu-id="1fc6c-132">[Using Indexers](../../../csharp/programming-guide/indexers/using-indexers.md) </span></span>  
 <span data-ttu-id="1fc6c-133">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="1fc6c-133">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="1fc6c-134">[struct](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="1fc6c-134">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 [<span data-ttu-id="1fc6c-135">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="1fc6c-135">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

