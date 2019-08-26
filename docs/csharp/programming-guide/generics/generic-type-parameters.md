---
title: Руководство по программированию на C#. Параметры универсального типа
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 27cd89c8e82036bf6353030b4f235c2ebe738e6d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589688"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="c2605-102">Руководство по программированию на C#. Параметры универсального типа</span><span class="sxs-lookup"><span data-stu-id="c2605-102">Generic type parameters (C# Programming Guide)</span></span>

<span data-ttu-id="c2605-103">В определении универсального типа или метода параметр типа является заполнителем для определенного типа, который клиент задает при создании экземпляра переменной универсального типа.</span><span class="sxs-lookup"><span data-stu-id="c2605-103">In a generic type or method definition, a type parameter is a placeholder for a specific type that a client specifies when they create an instance of the generic type.</span></span> <span data-ttu-id="c2605-104">Универсальный класс, например `GenericList<T>` из раздела [Общие сведения об универсальных шаблонах](./index.md), нельзя использовать в исходном виде, поскольку он представляет собой не фактически тип, а, скорее, заготовку типа.</span><span class="sxs-lookup"><span data-stu-id="c2605-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](./index.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="c2605-105">Чтобы использовать класс `GenericList<T>`, в коде клиента необходимо объявить сконструированный тип и создать его экземпляр, указав аргумент типа в угловых скобках.</span><span class="sxs-lookup"><span data-stu-id="c2605-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="c2605-106">Аргумент типа для этого конкретного класса может иметь любой тип, распознаваемый компилятором.</span><span class="sxs-lookup"><span data-stu-id="c2605-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="c2605-107">Можно создать любое число экземпляров сконструированного типа, каждый из которых будет использовать разные аргументы типа, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="c2605-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
<span data-ttu-id="c2605-108">В каждом из этих экземпляров `GenericList<T>` каждое вхождение `T` в классе во время выполнения будет заменяться аргументом типа.</span><span class="sxs-lookup"><span data-stu-id="c2605-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class is substituted at run time with the type argument.</span></span> <span data-ttu-id="c2605-109">Посредством такой замены в этом случае создается три отдельных типобезопасных эффективных объекта, использующих одно определение класса.</span><span class="sxs-lookup"><span data-stu-id="c2605-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="c2605-110">Дополнительные сведения о том, как в среде CLR реализуется эта замена, см. в разделе [Универсальные типы во время выполнения](./generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="c2605-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](./generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="c2605-111">Правила именования параметров типа</span><span class="sxs-lookup"><span data-stu-id="c2605-111">Type parameter naming guidelines</span></span>  
  
- <span data-ttu-id="c2605-112">**Присваивайте** параметрам универсального типа описательные имена, кроме случаев, когда достаточно одной буквы и описательное имя не имеет практической ценности.</span><span class="sxs-lookup"><span data-stu-id="c2605-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- <span data-ttu-id="c2605-113">**Используйте** имя параметра типа T для типов, содержащих только однобуквенный параметр типа.</span><span class="sxs-lookup"><span data-stu-id="c2605-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- <span data-ttu-id="c2605-114">**Используйте** префикс "T" для описательных имен параметров типа.</span><span class="sxs-lookup"><span data-stu-id="c2605-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- <span data-ttu-id="c2605-115">**Указывайте** ограничения, связанные с параметром типа, в его имени.</span><span class="sxs-lookup"><span data-stu-id="c2605-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="c2605-116">Например, параметр с ограничением `ISession` может называться `TSession`.</span><span class="sxs-lookup"><span data-stu-id="c2605-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>

<span data-ttu-id="c2605-117">Правило анализа кода [CA1715](/visualstudio/code-quality/ca1715-identifiers-should-have-correct-prefix) можно использовать, чтобы убедиться, что параметры типа, именуются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="c2605-117">The code analysis rule [CA1715](/visualstudio/code-quality/ca1715-identifiers-should-have-correct-prefix) can be used to ensure that type parameters are named appropriately.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c2605-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c2605-118">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="c2605-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c2605-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c2605-120">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="c2605-120">Generics</span></span>](./index.md)
- [<span data-ttu-id="c2605-121">Различия между шаблонами языка C++ и универсальными шаблонами языка C#</span><span class="sxs-lookup"><span data-stu-id="c2605-121">Differences Between C++ Templates and C# Generics</span></span>](./differences-between-cpp-templates-and-csharp-generics.md)
