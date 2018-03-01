---
title: "void (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a71cac30132417abce60cdde54322b5f2067d39d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="void-c-reference"></a><span data-ttu-id="559d2-102">void (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="559d2-102">void (C# Reference)</span></span>
<span data-ttu-id="559d2-103">При использовании в качестве типа возвращаемого значения для метода ключевое слово `void` указывает, что метод не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="559d2-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="559d2-104">Ключевое слово `void` не допускается в списке параметров метода.</span><span class="sxs-lookup"><span data-stu-id="559d2-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="559d2-105">Не принимающий параметров и не возвращающий значений метод объявляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="559d2-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="559d2-106">Ключевое слово `void` также используется в небезопасном контексте для объявления указателя на неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="559d2-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="559d2-107">Дополнительные сведения см. в разделе [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="559d2-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="559d2-108">`void` — это псевдоним для типа <xref:System.Void?displayProperty=nameWithType> в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="559d2-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="559d2-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="559d2-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="559d2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="559d2-110">See also</span></span>
 [<span data-ttu-id="559d2-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="559d2-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="559d2-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="559d2-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="559d2-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="559d2-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="559d2-114">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="559d2-114">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="559d2-115">Типы значений</span><span class="sxs-lookup"><span data-stu-id="559d2-115">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="559d2-116">Методы</span><span class="sxs-lookup"><span data-stu-id="559d2-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="559d2-117">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="559d2-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
