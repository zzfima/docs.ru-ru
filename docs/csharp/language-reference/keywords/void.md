---
title: void. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 87ccc3a18f0956ffe800ae97598e621e5ca72480
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238381"
---
# <a name="void-c-reference"></a><span data-ttu-id="d7fba-102">void (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d7fba-102">void (C# Reference)</span></span>
<span data-ttu-id="d7fba-103">При использовании в качестве типа возвращаемого значения для метода ключевое слово `void` указывает, что метод не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="d7fba-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="d7fba-104">Ключевое слово `void` не допускается в списке параметров метода.</span><span class="sxs-lookup"><span data-stu-id="d7fba-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="d7fba-105">Не принимающий параметров и не возвращающий значений метод объявляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d7fba-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="d7fba-106">Ключевое слово `void` также используется в небезопасном контексте для объявления указателя на неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="d7fba-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="d7fba-107">Дополнительные сведения см. в разделе [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="d7fba-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="d7fba-108">`void` — это псевдоним для типа <xref:System.Void?displayProperty=nameWithType> в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d7fba-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d7fba-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d7fba-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d7fba-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d7fba-110">See also</span></span>

- [<span data-ttu-id="d7fba-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d7fba-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="d7fba-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d7fba-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d7fba-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d7fba-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="d7fba-114">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="d7fba-114">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
- [<span data-ttu-id="d7fba-115">Типы значений</span><span class="sxs-lookup"><span data-stu-id="d7fba-115">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
- [<span data-ttu-id="d7fba-116">Методы</span><span class="sxs-lookup"><span data-stu-id="d7fba-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
- [<span data-ttu-id="d7fba-117">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="d7fba-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
