---
title: void. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 0624b547ee2586334ac35d366ae3c8dfd14963ee
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742760"
---
# <a name="void-c-reference"></a><span data-ttu-id="de0cc-102">void (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="de0cc-102">void (C# Reference)</span></span>

<span data-ttu-id="de0cc-103">При использовании в качестве типа возвращаемого значения для метода ключевое слово `void` указывает, что метод не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="de0cc-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="de0cc-104">Ключевое слово `void` не допускается в списке параметров метода.</span><span class="sxs-lookup"><span data-stu-id="de0cc-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="de0cc-105">Не принимающий параметров и не возвращающий значений метод объявляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="de0cc-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="de0cc-106">Ключевое слово `void` также используется в небезопасном контексте для объявления указателя на неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="de0cc-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="de0cc-107">Дополнительные сведения см. в разделе [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="de0cc-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="de0cc-108">`void` — это псевдоним для типа <xref:System.Void?displayProperty=nameWithType> в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de0cc-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="de0cc-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="de0cc-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="de0cc-110">См. также</span><span class="sxs-lookup"><span data-stu-id="de0cc-110">See also</span></span>

- [<span data-ttu-id="de0cc-111">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="de0cc-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="de0cc-112">Ключевые слова C#</span><span class="sxs-lookup"><span data-stu-id="de0cc-112">C# keywords</span></span>](index.md)
- [<span data-ttu-id="de0cc-113">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="de0cc-113">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="de0cc-114">Типы значений</span><span class="sxs-lookup"><span data-stu-id="de0cc-114">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="de0cc-115">Методы</span><span class="sxs-lookup"><span data-stu-id="de0cc-115">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="de0cc-116">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="de0cc-116">Unsafe code and pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
