---
title: "Различия между шаблонами языка C++ и универсальными шаблонами языка C# (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], vs. C++ templates
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
caps.latest.revision: 14
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
ms.openlocfilehash: 483d33531141127e083c5b75789f405427e46890
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="differences-between-c-templates-and-c-generics-c-programming-guide"></a><span data-ttu-id="b795f-102">Различия между шаблонами языка C++ и универсальными шаблонами языка C# (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="b795f-102">Differences Between C++ Templates and C# Generics (C# Programming Guide)</span></span>
<span data-ttu-id="b795f-103">Универсальные шаблоны C# и шаблоны C++ — это возможности языков программирования, обеспечивающие поддержку параметризированных типов.</span><span class="sxs-lookup"><span data-stu-id="b795f-103">C# Generics and C++ templates are both language features that provide support for parameterized types.</span></span> <span data-ttu-id="b795f-104">Однако между ними существует немало различий.</span><span class="sxs-lookup"><span data-stu-id="b795f-104">However, there are many differences between the two.</span></span> <span data-ttu-id="b795f-105">На уровне синтаксиса универсальные шаблоны C# представляют собой более простой способ работы с параметризованными типами без сложностей, связанных с шаблонами C++.</span><span class="sxs-lookup"><span data-stu-id="b795f-105">At the syntax level, C# generics are a simpler approach to parameterized types without the complexity of C++ templates.</span></span> <span data-ttu-id="b795f-106">Кроме того, C# не пытается предоставить все функции, предоставляемые шаблонами C++.</span><span class="sxs-lookup"><span data-stu-id="b795f-106">In addition, C# does not attempt to provide all of the functionality that C++ templates provide.</span></span> <span data-ttu-id="b795f-107">На уровне реализации основное различие заключается в том, что замена универсальных типов C# осуществляется во время выполнения, а значит для объектов, экземпляры которых при этом создаются, сохраняются данные об универсальных типах.</span><span class="sxs-lookup"><span data-stu-id="b795f-107">At the implementation level, the primary difference is that C# generic type substitutions are performed at runtime and generic type information is thereby preserved for instantiated objects.</span></span> <span data-ttu-id="b795f-108">Дополнительные сведения см. в разделе [Универсальные типы во время выполнения](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="b795f-108">For more information, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
 <span data-ttu-id="b795f-109">Основные различия между универсальными шаблонами C# и шаблонами C++ состоят в следующем:</span><span class="sxs-lookup"><span data-stu-id="b795f-109">The following are the key differences between C# Generics and C++ templates:</span></span>  
  
-   <span data-ttu-id="b795f-110">Универсальные шаблоны C# не дают такую же гибкость, как шаблоны C++.</span><span class="sxs-lookup"><span data-stu-id="b795f-110">C# generics do not provide the same amount of flexibility as C++ templates.</span></span> <span data-ttu-id="b795f-111">Например, в универсальном классе C# нельзя вызывать арифметические операторы, но можно вызывать операторы, определенные пользователем.</span><span class="sxs-lookup"><span data-stu-id="b795f-111">For example, it is not possible to call arithmetic operators in a C# generic class, although it is possible to call user defined operators.</span></span>  
  
-   <span data-ttu-id="b795f-112">C# не позволяет использовать параметры шаблонов, не являющиеся типами, такие как `template C<int i> {}`.</span><span class="sxs-lookup"><span data-stu-id="b795f-112">C# does not allow non-type template parameters, such as `template C<int i> {}`.</span></span>  
  
-   <span data-ttu-id="b795f-113">C# не поддерживает явную специализацию, т. е. индивидуальную реализацию шаблона для конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="b795f-113">C# does not support explicit specialization; that is, a custom implementation of a template for a specific type.</span></span>  
  
-   <span data-ttu-id="b795f-114">C# не поддерживает частичную специализацию, т. е. индивидуальную реализацию для подмножества аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="b795f-114">C# does not support partial specialization: a custom implementation for a subset of the type arguments.</span></span>  
  
-   <span data-ttu-id="b795f-115">C# не позволяет использовать параметр типа в качестве базового класса для универсального типа.</span><span class="sxs-lookup"><span data-stu-id="b795f-115">C# does not allow the type parameter to be used as the base class for the generic type.</span></span>  
  
-   <span data-ttu-id="b795f-116">C# не позволяет параметрам типов иметь типы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b795f-116">C# does not allow type parameters to have default types.</span></span>  
  
-   <span data-ttu-id="b795f-117">В C# параметр универсального типа сам по себе не может быть универсальным, однако в качестве универсальных типов можно использовать сконструированные типы.</span><span class="sxs-lookup"><span data-stu-id="b795f-117">In C#, a generic type parameter cannot itself be a generic, although constructed types can be used as generics.</span></span> <span data-ttu-id="b795f-118">C++ не позволяет использовать параметры шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b795f-118">C++ does allow template parameters.</span></span>  
  
-   <span data-ttu-id="b795f-119">C++ позволяет использовать код, который может быть недопустимым для всех параметров типа в шаблоне, а затем проверяет, используется ли в качестве параметра типа определенный тип.</span><span class="sxs-lookup"><span data-stu-id="b795f-119">C++ allows code that might not be valid for all type parameters in the template, which is then checked for the specific type used as the type parameter.</span></span> <span data-ttu-id="b795f-120">C# требует, чтобы код в классе был написан так, чтобы он работал с любым типом, соответствующим ограничениям.</span><span class="sxs-lookup"><span data-stu-id="b795f-120">C# requires code in a class to be written in such a way that it will work with any type that satisfies the constraints.</span></span> <span data-ttu-id="b795f-121">Например, в C++ можно написать функцию, которая применяет арифметические операторы `+` и `-` к объектам параметра типа, в связи с чем при создании экземпляра шаблона, тип которого не поддерживает эти операторы, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="b795f-121">For example, in C++ it is possible to write a function that uses the arithmetic operators `+` and `-` on objects of the type parameter, which will produce an error at the time of instantiation of the template with a type that does not support these operators.</span></span> <span data-ttu-id="b795f-122">C# этого не позволяет; допускаются только те языковые конструкции, которые можно вывести из ограничений.</span><span class="sxs-lookup"><span data-stu-id="b795f-122">C# disallows this; the only language constructs allowed are those that can be deduced from the constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b795f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b795f-123">See Also</span></span>  
 <span data-ttu-id="b795f-124">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b795f-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b795f-125">[Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="b795f-125">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 [<span data-ttu-id="b795f-126">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="b795f-126">Templates</span></span>](/cpp/cpp/templates-cpp)

