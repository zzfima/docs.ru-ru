---
title: object (справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0fcced75d3a86fd700e642e48b7e325e554cae53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-c-reference"></a><span data-ttu-id="20025-102">object (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="20025-102">object (C# Reference)</span></span>
<span data-ttu-id="20025-103">Тип `object` — это псевдоним для <xref:System.Object> в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20025-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="20025-104">В унифицированной системе типов C# все типы, стандартные и определяемые пользователем, ссылочные типы и типы значений напрямую или косвенно наследуются из <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="20025-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="20025-105">Переменным типа `object` можно назначать значения любого типа.</span><span class="sxs-lookup"><span data-stu-id="20025-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="20025-106">Если переменная типа значения преобразуется в объект, она считается *упакованной*.</span><span class="sxs-lookup"><span data-stu-id="20025-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="20025-107">Если переменная типа значения преобразуется в тип значения, она считается *распакованной*.</span><span class="sxs-lookup"><span data-stu-id="20025-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="20025-108">Дополнительные сведения см. в разделе [Упаковка-преобразование и распаковка-преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="20025-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="20025-109">Пример</span><span class="sxs-lookup"><span data-stu-id="20025-109">Example</span></span>  
 <span data-ttu-id="20025-110">В следующем примере показано, как переменные типа `object` могут принимать значения любого типа данных и как переменные типа `object` могут применять методы к <xref:System.Object> из платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20025-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="20025-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="20025-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="20025-112">См. также</span><span class="sxs-lookup"><span data-stu-id="20025-112">See Also</span></span>  
 [<span data-ttu-id="20025-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="20025-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="20025-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="20025-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="20025-115">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="20025-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="20025-116">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="20025-116">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="20025-117">Типы значений</span><span class="sxs-lookup"><span data-stu-id="20025-117">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
