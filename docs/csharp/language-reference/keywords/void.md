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
ms.openlocfilehash: ce52e4d19335db0e21637b87bbd1589c86c06ae1
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613132"
---
# <a name="void-c-reference"></a><span data-ttu-id="10143-102">void (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="10143-102">void (C# Reference)</span></span>

<span data-ttu-id="10143-103">При использовании в качестве типа возвращаемого значения для метода ключевое слово `void` указывает, что метод не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="10143-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="10143-104">Ключевое слово `void` не допускается в списке параметров метода.</span><span class="sxs-lookup"><span data-stu-id="10143-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="10143-105">Не принимающий параметров и не возвращающий значений метод объявляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="10143-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="10143-106">Ключевое слово `void` также используется в небезопасном контексте для объявления указателя на неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="10143-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="10143-107">Дополнительные сведения см. в разделе [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="10143-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="10143-108">`void` — это псевдоним для типа <xref:System.Void?displayProperty=nameWithType> в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="10143-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="10143-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="10143-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="10143-110">См. также</span><span class="sxs-lookup"><span data-stu-id="10143-110">See also</span></span>

- [<span data-ttu-id="10143-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="10143-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="10143-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="10143-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="10143-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="10143-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="10143-114">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="10143-114">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="10143-115">Типы значений</span><span class="sxs-lookup"><span data-stu-id="10143-115">Value Types</span></span>](value-types.md)
- [<span data-ttu-id="10143-116">Методы</span><span class="sxs-lookup"><span data-stu-id="10143-116">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="10143-117">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="10143-117">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)