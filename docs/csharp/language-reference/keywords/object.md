---
title: "object (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- object_CSharpKeyword
- object
dev_langs:
- CSharp
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
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
ms.openlocfilehash: 744debc51f68cc52f03bce09c9f276a66ae085e1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="object-c-reference"></a><span data-ttu-id="bb5bc-102">object (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bb5bc-102">object (C# Reference)</span></span>
<span data-ttu-id="bb5bc-103">Тип `object` — это псевдоним для <xref:System.Object> в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb5bc-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="bb5bc-104">В унифицированной системе типов C# все типы, стандартные и определяемые пользователем, ссылочные типы и типы значений напрямую или косвенно наследуются из <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="bb5bc-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="bb5bc-105">Переменным типа `object` можно назначать значения любого типа.</span><span class="sxs-lookup"><span data-stu-id="bb5bc-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="bb5bc-106">Если переменная типа значения преобразуется в объект, она считается *упакованной*.</span><span class="sxs-lookup"><span data-stu-id="bb5bc-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="bb5bc-107">Если переменная типа значения преобразуется в тип значения, она считается *распакованной*.</span><span class="sxs-lookup"><span data-stu-id="bb5bc-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="bb5bc-108">Дополнительные сведения см. в разделе [Упаковка-преобразование и распаковка-преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="bb5bc-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb5bc-109">Пример</span><span class="sxs-lookup"><span data-stu-id="bb5bc-109">Example</span></span>  
 <span data-ttu-id="bb5bc-110">В следующем примере показано, как переменные типа `object` могут принимать значения любого типа данных и как переменные типа `object` могут применять методы к <xref:System.Object> из платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb5bc-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 <span data-ttu-id="bb5bc-111">[!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb5bc-111">[!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bb5bc-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="bb5bc-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bb5bc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bb5bc-113">See Also</span></span>  
 <span data-ttu-id="bb5bc-114">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb5bc-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bb5bc-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb5bc-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bb5bc-116">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb5bc-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="bb5bc-117">[Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="bb5bc-117">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 [<span data-ttu-id="bb5bc-118">Типы значений</span><span class="sxs-lookup"><span data-stu-id="bb5bc-118">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)

