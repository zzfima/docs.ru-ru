---
title: "void (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- void_CSharpKeyword
- void
dev_langs:
- CSharp
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 15
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
ms.openlocfilehash: d1bd7ece5ce3b558c616a4eb3a4668c3c13eb1cb
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="void-c-reference"></a><span data-ttu-id="1a400-102">void (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1a400-102">void (C# Reference)</span></span>
<span data-ttu-id="1a400-103">При использовании в качестве типа возвращаемого значения для метода ключевое слово `void` указывает, что метод не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="1a400-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="1a400-104">Ключевое слово `void` не допускается в списке параметров метода.</span><span class="sxs-lookup"><span data-stu-id="1a400-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="1a400-105">Не принимающий параметров и не возвращающий значений метод объявляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1a400-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="1a400-106">Ключевое слово `void` также используется в небезопасном контексте для объявления указателя на неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="1a400-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="1a400-107">Дополнительные сведения см. в разделе [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="1a400-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="1a400-108">`void` — это псевдоним для типа <xref:System.Void?displayProperty=fullName> в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a400-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=fullName> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1a400-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1a400-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1a400-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1a400-110">See also</span></span>
 <span data-ttu-id="1a400-111">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a400-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1a400-112">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a400-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1a400-113">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a400-113">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="1a400-114">[Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="1a400-114">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="1a400-115">[Типы значений](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="1a400-115">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="1a400-116">[Методы](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="1a400-116">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 [<span data-ttu-id="1a400-117">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="1a400-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)

