---
title: Руководство по программированию на C#. Универсальные шаблоны и атрибуты
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 47bf4e8f07a8b6778db8fa675d745d362dc10d7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75703030"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="ac9de-102">Универсальные шаблоны и атрибуты (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="ac9de-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="ac9de-103">Атрибуты можно применять к универсальным типам так же, как и к типам, не являющимся универсальными.</span><span class="sxs-lookup"><span data-stu-id="ac9de-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="ac9de-104">Дополнительные сведения о применении атрибутов см. в разделе [Атрибуты](../concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="ac9de-104">For more information on applying attributes, see [Attributes](../concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="ac9de-105">Настраиваемые атрибуты могут ссылаться только на открытые универсальные типы (универсальные типы, для которых не предоставлены аргументы типа) и закрытые сконструированные универсальные типы (типы, для всех параметров типа которых предоставлены аргументы).</span><span class="sxs-lookup"><span data-stu-id="ac9de-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="ac9de-106">Такой настраиваемый атрибут используется в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="ac9de-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 <span data-ttu-id="ac9de-107">Атрибут может ссылаться на открытый универсальный тип:</span><span class="sxs-lookup"><span data-stu-id="ac9de-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 <span data-ttu-id="ac9de-108">Укажите несколько параметров типа, используя соответствующее количество запятых.</span><span class="sxs-lookup"><span data-stu-id="ac9de-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="ac9de-109">В этом примере `GenericClass2` имеет два параметра типа:</span><span class="sxs-lookup"><span data-stu-id="ac9de-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 <span data-ttu-id="ac9de-110">Атрибут может ссылаться на закрытый сконструированный универсальный тип:</span><span class="sxs-lookup"><span data-stu-id="ac9de-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 <span data-ttu-id="ac9de-111">Если атрибут ссылается на параметр универсального типа, возникнет ошибка времени компиляции:</span><span class="sxs-lookup"><span data-stu-id="ac9de-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 <span data-ttu-id="ac9de-112">Универсальный тип не может наследоваться от <xref:System.Attribute>:</span><span class="sxs-lookup"><span data-stu-id="ac9de-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 <span data-ttu-id="ac9de-113">Для получения сведений об универсальном типе или параметре типа во время выполнения можно использовать методы из <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="ac9de-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="ac9de-114">Дополнительные сведения см. в разделе [Универсальные типы и отражение](./generics-and-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="ac9de-114">For more information, see [Generics and Reflection](./generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9de-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ac9de-115">See also</span></span>

- [<span data-ttu-id="ac9de-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ac9de-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ac9de-117">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="ac9de-117">Generics</span></span>](./index.md)
- [<span data-ttu-id="ac9de-118">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ac9de-118">Attributes</span></span>](../../../standard/attributes/index.md)
