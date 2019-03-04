---
title: Руководство по программированию на C#. Универсальные шаблоны и атрибуты
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 000ce5a72cede9d1f23b0efb7ccf8638090a9032
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979597"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="1cba5-102">Универсальные шаблоны и атрибуты (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="1cba5-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="1cba5-103">Атрибуты можно применять к универсальным типам так же, как и к типам, не являющимся универсальными.</span><span class="sxs-lookup"><span data-stu-id="1cba5-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="1cba5-104">Дополнительные сведения о применении атрибутов см. в разделе [Атрибуты](../../../csharp/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="1cba5-104">For more information on applying attributes, see [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="1cba5-105">Настраиваемые атрибуты могут ссылаться только на открытые универсальные типы (универсальные типы, для которых не предоставлены аргументы типа) и закрытые сконструированные универсальные типы (типы, для всех параметров типа которых предоставлены аргументы).</span><span class="sxs-lookup"><span data-stu-id="1cba5-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="1cba5-106">Такой настраиваемый атрибут используется в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="1cba5-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 <span data-ttu-id="1cba5-107">Атрибут может ссылаться на открытый универсальный тип:</span><span class="sxs-lookup"><span data-stu-id="1cba5-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 <span data-ttu-id="1cba5-108">Укажите несколько параметров типа, используя соответствующее количество запятых.</span><span class="sxs-lookup"><span data-stu-id="1cba5-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="1cba5-109">В этом примере `GenericClass2` имеет два параметра типа:</span><span class="sxs-lookup"><span data-stu-id="1cba5-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 <span data-ttu-id="1cba5-110">Атрибут может ссылаться на закрытый сконструированный универсальный тип:</span><span class="sxs-lookup"><span data-stu-id="1cba5-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 <span data-ttu-id="1cba5-111">Если атрибут ссылается на параметр универсального типа, возникнет ошибка времени компиляции:</span><span class="sxs-lookup"><span data-stu-id="1cba5-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 <span data-ttu-id="1cba5-112">Универсальный тип не может наследоваться от <xref:System.Attribute>:</span><span class="sxs-lookup"><span data-stu-id="1cba5-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 <span data-ttu-id="1cba5-113">Для получения сведений об универсальном типе или параметре типа во время выполнения можно использовать методы из <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="1cba5-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="1cba5-114">Дополнительные сведения см. в разделе [Универсальные типы и отражение](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="1cba5-114">For more information, see [Generics and Reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cba5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1cba5-115">See also</span></span>

- [<span data-ttu-id="1cba5-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1cba5-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1cba5-117">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="1cba5-117">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="1cba5-118">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1cba5-118">Attributes</span></span>](../../../../docs/standard/attributes/index.md)
