---
title: object (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: 67eaf7f1fd2f01e433395ed21701c3b7fad7c7b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="object-c-reference"></a><span data-ttu-id="f646e-102">object (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f646e-102">object (C# Reference)</span></span>
<span data-ttu-id="f646e-103">Тип `object` — это псевдоним для <xref:System.Object> в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f646e-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="f646e-104">В унифицированной системе типов C# все типы, стандартные и определяемые пользователем, ссылочные типы и типы значений напрямую или косвенно наследуются из <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="f646e-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="f646e-105">Переменным типа `object` можно назначать значения любого типа.</span><span class="sxs-lookup"><span data-stu-id="f646e-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="f646e-106">Если переменная типа значения преобразуется в объект, она считается *упакованной*.</span><span class="sxs-lookup"><span data-stu-id="f646e-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="f646e-107">Если переменная типа значения преобразуется в тип значения, она считается *распакованной*.</span><span class="sxs-lookup"><span data-stu-id="f646e-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="f646e-108">Дополнительные сведения см. в разделе [Упаковка-преобразование и распаковка-преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="f646e-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f646e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="f646e-109">Example</span></span>  
 <span data-ttu-id="f646e-110">В следующем примере показано, как переменные типа `object` могут принимать значения любого типа данных и как переменные типа `object` могут применять методы к <xref:System.Object> из платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f646e-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f646e-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f646e-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f646e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f646e-112">See Also</span></span>  
 [<span data-ttu-id="f646e-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f646e-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f646e-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f646e-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f646e-115">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f646e-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f646e-116">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="f646e-116">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="f646e-117">Типы значений</span><span class="sxs-lookup"><span data-stu-id="f646e-117">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
