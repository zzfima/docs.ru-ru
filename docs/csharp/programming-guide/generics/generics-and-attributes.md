---
title: "Универсальные шаблоны и атрибуты (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
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
ms.openlocfilehash: 5136ae928a3a4b6f8ec4d86100d695f958d55858
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="d893e-102">Универсальные шаблоны и атрибуты (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="d893e-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="d893e-103">Атрибуты можно применять к универсальным типам так же, как и к типам, не являющимся универсальными.</span><span class="sxs-lookup"><span data-stu-id="d893e-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="d893e-104">Дополнительные сведения о применении атрибутов см. в разделе [Атрибуты](../../../csharp/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="d893e-104">For more information on applying attributes, see [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="d893e-105">Настраиваемые атрибуты могут ссылаться только на открытые универсальные типы (универсальные типы, для которых не предоставлены аргументы типа) и закрытые сконструированные универсальные типы (типы, для всех параметров типа которых предоставлены аргументы).</span><span class="sxs-lookup"><span data-stu-id="d893e-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="d893e-106">Такой настраиваемый атрибут используется в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="d893e-106">The following examples use this custom attribute:</span></span>  
  
 <span data-ttu-id="d893e-107">[!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d893e-107">[!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]</span></span>  
  
 <span data-ttu-id="d893e-108">Атрибут может ссылаться на открытый универсальный тип:</span><span class="sxs-lookup"><span data-stu-id="d893e-108">An attribute can reference an open generic type:</span></span>  
  
 <span data-ttu-id="d893e-109">[!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d893e-109">[!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]</span></span>  
  
 <span data-ttu-id="d893e-110">Укажите несколько параметров типа, используя соответствующее количество запятых.</span><span class="sxs-lookup"><span data-stu-id="d893e-110">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="d893e-111">В этом примере `GenericClass2` имеет два параметра типа:</span><span class="sxs-lookup"><span data-stu-id="d893e-111">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 <span data-ttu-id="d893e-112">[!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d893e-112">[!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]</span></span>  
  
 <span data-ttu-id="d893e-113">Атрибут может ссылаться на закрытый сконструированный универсальный тип:</span><span class="sxs-lookup"><span data-stu-id="d893e-113">An attribute can reference a closed constructed generic type:</span></span>  
  
 <span data-ttu-id="d893e-114">[!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="d893e-114">[!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]</span></span>  
  
 <span data-ttu-id="d893e-115">Если атрибут ссылается на параметр универсального типа, возникнет ошибка времени компиляции:</span><span class="sxs-lookup"><span data-stu-id="d893e-115">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 <span data-ttu-id="d893e-116">[!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="d893e-116">[!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]</span></span>  
  
 <span data-ttu-id="d893e-117">Универсальный тип не может наследоваться от <xref:System.Attribute>:</span><span class="sxs-lookup"><span data-stu-id="d893e-117">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 <span data-ttu-id="d893e-118">[!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="d893e-118">[!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]</span></span>  
  
 <span data-ttu-id="d893e-119">Для получения сведений об универсальном типе или параметре типа во время выполнения можно использовать методы из <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="d893e-119">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="d893e-120">Дополнительные сведения см. в разделе [Универсальные типы и отражение](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="d893e-120">For more information, see [Generics and Reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d893e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d893e-121">See Also</span></span>  
 <span data-ttu-id="d893e-122">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d893e-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d893e-123">[Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="d893e-123">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 [<span data-ttu-id="d893e-124">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d893e-124">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)

