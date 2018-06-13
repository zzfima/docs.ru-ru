---
title: '#undef (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 870b78580e5350f06fae33f2ac107dc3968b2c6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273414"
---
# <a name="undef-c-reference"></a><span data-ttu-id="febd0-102">#undef (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="febd0-102">#undef (C# Reference)</span></span>
<span data-ttu-id="febd0-103">`#undef` позволяет отменить определение символа таким образом, чтобы при использовании этого символа в качестве выражения в директиве [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) возвращалось значение `false`.</span><span class="sxs-lookup"><span data-stu-id="febd0-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="febd0-104">Символ можно определить с помощью директивы [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) или параметра компилятора [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="febd0-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="febd0-105">Директива `#undef` должна находиться в файле перед использованием любых инструкций, которые также не являются директивами.</span><span class="sxs-lookup"><span data-stu-id="febd0-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="febd0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="febd0-106">Example</span></span>  
  
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
  
 <span data-ttu-id="febd0-107">**DEBUG не определено**</span><span class="sxs-lookup"><span data-stu-id="febd0-107">**DEBUG is not defined**</span></span>  
## <a name="see-also"></a><span data-ttu-id="febd0-108">См. также</span><span class="sxs-lookup"><span data-stu-id="febd0-108">See Also</span></span>  
 [<span data-ttu-id="febd0-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="febd0-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="febd0-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="febd0-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="febd0-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="febd0-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
