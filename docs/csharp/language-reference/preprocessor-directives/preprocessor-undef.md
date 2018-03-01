---
title: "#undef (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e7a3c162c0ecb8bb39cc13a34dcd15fa3ce96ebb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="undef-c-reference"></a><span data-ttu-id="a91db-102">#undef (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a91db-102">#undef (C# Reference)</span></span>
<span data-ttu-id="a91db-103">`#undef` позволяет отменить определение символа таким образом, чтобы при использовании этого символа в качестве выражения в директиве [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) возвращалось значение `false`.</span><span class="sxs-lookup"><span data-stu-id="a91db-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="a91db-104">Символ можно определить с помощью директивы [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) или параметра компилятора [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a91db-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="a91db-105">Директива `#undef` должна находиться в файле перед использованием любых инструкций, которые также не являются директивами.</span><span class="sxs-lookup"><span data-stu-id="a91db-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a91db-106">Пример</span><span class="sxs-lookup"><span data-stu-id="a91db-106">Example</span></span>  
  
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
  
 <span data-ttu-id="a91db-107">**DEBUG не определено**</span><span class="sxs-lookup"><span data-stu-id="a91db-107">**DEBUG is not defined**</span></span>  
## <a name="see-also"></a><span data-ttu-id="a91db-108">См. также</span><span class="sxs-lookup"><span data-stu-id="a91db-108">See Also</span></span>  
 [<span data-ttu-id="a91db-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a91db-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a91db-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a91db-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a91db-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="a91db-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
