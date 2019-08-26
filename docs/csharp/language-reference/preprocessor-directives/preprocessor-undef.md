---
title: '#undef. Справочник по C#'
ms.custom: seodec18
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: fdf22e90be766e87e823a7f8cc27ea00c17d2bb5
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605584"
---
# <a name="undef-c-reference"></a><span data-ttu-id="dd659-102">#undef (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="dd659-102">#undef (C# Reference)</span></span>
<span data-ttu-id="dd659-103">`#undef` позволяет отменить определение символа таким образом, чтобы при использовании этого символа в качестве выражения в директиве [#if](./preprocessor-if.md) возвращалось значение `false`.</span><span class="sxs-lookup"><span data-stu-id="dd659-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="dd659-104">Символ можно определить с помощью директивы [#define](./preprocessor-define.md) или параметра компилятора [-define](../compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="dd659-104">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="dd659-105">Директива `#undef` должна находиться в файле перед использованием любых инструкций, которые также не являются директивами.</span><span class="sxs-lookup"><span data-stu-id="dd659-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd659-106">Пример</span><span class="sxs-lookup"><span data-stu-id="dd659-106">Example</span></span>  

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

<span data-ttu-id="dd659-107">**DEBUG не определено**</span><span class="sxs-lookup"><span data-stu-id="dd659-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="dd659-108">См. также</span><span class="sxs-lookup"><span data-stu-id="dd659-108">See also</span></span>

- [<span data-ttu-id="dd659-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="dd659-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dd659-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="dd659-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dd659-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="dd659-111">C# Preprocessor Directives</span></span>](./index.md)
