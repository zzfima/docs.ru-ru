---
title: "Введение в универсальные шаблоны. (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
caps.latest.revision: "32"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 61baf26c9f942a59e3787ca55a2ac6a824410608
ms.sourcegitcommit: 3fd4e718d1bac9769fe0c1dd08ca1b2323ae272b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2018
---
# <a name="introduction-to-generics-c-programming-guide"></a><span data-ttu-id="cefd3-102">Введение в универсальные шаблоны. (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="cefd3-102">Introduction to Generics (C# Programming Guide)</span></span>
<span data-ttu-id="cefd3-103">Универсальные классы и методы сочетают такие характеристики, как возможность многократного использования, типобезопасность и эффективность, которые не обеспечивают их неуниверсальные аналоги.</span><span class="sxs-lookup"><span data-stu-id="cefd3-103">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="cefd3-104">Универсальные типы наиболее часто используются с коллекциями и методами, которые выполняют с ними операции.</span><span class="sxs-lookup"><span data-stu-id="cefd3-104">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="cefd3-105">Библиотека классов на платформе .NET Framework 2.0 предоставляет новое пространство имен <xref:System.Collections.Generic>, которое содержит несколько новых универсальных классов коллекций.</span><span class="sxs-lookup"><span data-stu-id="cefd3-105">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="cefd3-106">Во всех приложениях, предназначенных для [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 и более поздних версий, рекомендуется использовать новые универсальные классы коллекций вместо старых неуниверсальных аналогов, например <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="cefd3-106">It is recommended that all applications that target the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="cefd3-107">Дополнительные сведения см. в статье [Универсальные шаблоны в библиотеке классов платформы .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span><span class="sxs-lookup"><span data-stu-id="cefd3-107">For more information, see [Generics in the .NET Framework Class Library](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span></span>  
  
 <span data-ttu-id="cefd3-108">Очевидно, вы можете создавать собственные универсальные типы и методы для предоставления собственных типобезопасных и эффективных обобщенных решений и шаблонов разработки.</span><span class="sxs-lookup"><span data-stu-id="cefd3-108">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="cefd3-109">В следующем примере кода показан простой универсальный класс связанного списка для демонстрационных целей.</span><span class="sxs-lookup"><span data-stu-id="cefd3-109">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="cefd3-110">(В большинстве случаев следует использовать класс <xref:System.Collections.Generic.List%601>, предоставляемый библиотекой классов .NET Framework, вместо создания собственного.) Параметр типа `T` используется в нескольких расположениях, где обычно используется конкретный тип для указания типа элемента, хранящегося в списке.</span><span class="sxs-lookup"><span data-stu-id="cefd3-110">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="cefd3-111">Он используется в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="cefd3-111">It is used in the following ways:</span></span>  
  
-   <span data-ttu-id="cefd3-112">в качестве типа параметра метода в методе `AddHead`;</span><span class="sxs-lookup"><span data-stu-id="cefd3-112">As the type of a method parameter in the `AddHead` method.</span></span>  
  
-   <span data-ttu-id="cefd3-113">в качестве типа возвращаемого значения свойства `Data` во вложенном классе `Node`;</span><span class="sxs-lookup"><span data-stu-id="cefd3-113">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
-   <span data-ttu-id="cefd3-114">в качестве типа закрытого члена `data` во вложенном классе.</span><span class="sxs-lookup"><span data-stu-id="cefd3-114">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="cefd3-115">Обратите внимание, что T доступен для вложенного класса `Node`.</span><span class="sxs-lookup"><span data-stu-id="cefd3-115">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="cefd3-116">Когда экземпляр `GenericList<T>` создается с конкретным типом, например `GenericList<int>`, каждое вхождение `T` будет заменено `int`.</span><span class="sxs-lookup"><span data-stu-id="cefd3-116">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 <span data-ttu-id="cefd3-117">В следующем примере кода показано, как клиентский код использует универсальный класс `GenericList<T>` для создания списка целых чисел.</span><span class="sxs-lookup"><span data-stu-id="cefd3-117">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="cefd3-118">Просто изменяя тип аргумента, следующий код можно легко изменить для создания списков строк или любого другого пользовательского типа:</span><span class="sxs-lookup"><span data-stu-id="cefd3-118">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="cefd3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="cefd3-119">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="cefd3-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cefd3-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cefd3-121">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="cefd3-121">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
