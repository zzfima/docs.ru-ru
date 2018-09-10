---
title: Параметры универсального типа (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 5bb19e13a6e34e2e22ebc3f9d46edd85fbe0176e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513713"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="33299-102">Параметры универсального типа (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="33299-102">Generic Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="33299-103">В определении универсального типа или метода параметр типа является заполнителем для определенного типа, который клиент задает при создании экземпляра переменной универсального типа.</span><span class="sxs-lookup"><span data-stu-id="33299-103">In a generic type or method definition, a type parameters is a placeholder for a specific type that a client specifies when they instantiate a variable of the generic type.</span></span> <span data-ttu-id="33299-104">Универсальный класс, например `GenericList<T>` из раздела [Общие сведения об универсальных шаблонах](../../../csharp/programming-guide/generics/introduction-to-generics.md), нельзя использовать в исходном виде, поскольку он представляет собой не фактически тип, а, скорее, заготовку типа.</span><span class="sxs-lookup"><span data-stu-id="33299-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="33299-105">Чтобы использовать класс `GenericList<T>`, в коде клиента необходимо объявить сконструированный тип и создать его экземпляр, указав аргумент типа в угловых скобках.</span><span class="sxs-lookup"><span data-stu-id="33299-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="33299-106">Аргумент типа для этого конкретного класса может иметь любой тип, распознаваемый компилятором.</span><span class="sxs-lookup"><span data-stu-id="33299-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="33299-107">Можно создать любое число экземпляров сконструированного типа, каждый из которых будет использовать разные аргументы типа, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="33299-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 <span data-ttu-id="33299-108">В каждом из этих экземпляров `GenericList<T>` каждое вхождение `T` в классе во время выполнения будет заменяться аргументом типа.</span><span class="sxs-lookup"><span data-stu-id="33299-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class will be substituted at run time with the type argument.</span></span> <span data-ttu-id="33299-109">Посредством такой замены в этом случае создается три отдельных типобезопасных эффективных объекта, использующих одно определение класса.</span><span class="sxs-lookup"><span data-stu-id="33299-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="33299-110">Дополнительные сведения о том, как в среде CLR реализуется эта замена, см. в разделе [Универсальные типы во время выполнения](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="33299-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="33299-111">Правила именования параметра типа</span><span class="sxs-lookup"><span data-stu-id="33299-111">Type Parameter Naming Guidelines</span></span>  
  
-   <span data-ttu-id="33299-112">**Присваивайте** параметрам универсального типа описательные имена, кроме случаев, когда достаточно одной буквы и описательное имя не имеет практической ценности.</span><span class="sxs-lookup"><span data-stu-id="33299-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   <span data-ttu-id="33299-113">**Используйте** имя параметра типа T для типов, содержащих только однобуквенный параметр типа.</span><span class="sxs-lookup"><span data-stu-id="33299-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   <span data-ttu-id="33299-114">**Используйте** префикс "T" для описательных имен параметров типа.</span><span class="sxs-lookup"><span data-stu-id="33299-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
     [!code-csharp[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   <span data-ttu-id="33299-115">**Указывайте** ограничения, связанные с параметром типа, в его имени.</span><span class="sxs-lookup"><span data-stu-id="33299-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="33299-116">Например, параметр с ограничением `ISession` может называться `TSession`.</span><span class="sxs-lookup"><span data-stu-id="33299-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33299-117">См. также</span><span class="sxs-lookup"><span data-stu-id="33299-117">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="33299-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="33299-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="33299-119">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="33299-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
- [<span data-ttu-id="33299-120">Различия между шаблонами языка C++ и универсальными шаблонами языка C#</span><span class="sxs-lookup"><span data-stu-id="33299-120">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
