---
title: '#undef. Справочник по C#'
ms.custom: seodec18
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 0dedd1480dae15d2c04b47cee132ab3227098f56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739038"
---
# <a name="undef-c-reference"></a><span data-ttu-id="e350f-102">#undef (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e350f-102">#undef (C# Reference)</span></span>
<span data-ttu-id="e350f-103">`#undef` позволяет отменить определение символа таким образом, чтобы при использовании этого символа в качестве выражения в директиве [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) возвращалось значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e350f-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="e350f-104">Символ можно определить с помощью директивы [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) или параметра компилятора [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e350f-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="e350f-105">Директива `#undef` должна находиться в файле перед использованием любых инструкций, которые также не являются директивами.</span><span class="sxs-lookup"><span data-stu-id="e350f-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e350f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="e350f-106">Example</span></span>  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

<span data-ttu-id="e350f-107">**DEBUG не определено**</span><span class="sxs-lookup"><span data-stu-id="e350f-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="e350f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e350f-108">See also</span></span>

- [<span data-ttu-id="e350f-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e350f-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="e350f-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e350f-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e350f-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="e350f-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
