---
title: "#<a name=\"undef-c-reference\"></a>undef (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#undef'
dev_langs:
- CSharp
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: 12
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
ms.openlocfilehash: acdd043535ef319f2af40c809e7fe4af612cb17d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="undef-c-reference"></a><span data-ttu-id="200a5-102">#undef (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="200a5-102">#undef (C# Reference)</span></span>
<span data-ttu-id="200a5-103">`#undef` позволяет отменить определение символа таким образом, чтобы при использовании этого символа в качестве выражения в директиве [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) возвращалось значение `false`.</span><span class="sxs-lookup"><span data-stu-id="200a5-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="200a5-104">Символ можно определить с помощью директивы [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) или параметра компилятора [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="200a5-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="200a5-105">Директива `#undef` должна находиться в файле перед использованием любых инструкций, которые также не являются директивами.</span><span class="sxs-lookup"><span data-stu-id="200a5-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="200a5-106">Пример</span><span class="sxs-lookup"><span data-stu-id="200a5-106">Example</span></span>  
  
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
  
 <span data-ttu-id="200a5-107">**DEBUG не определено**</span><span class="sxs-lookup"><span data-stu-id="200a5-107">**DEBUG is not defined**</span></span>   
## <a name="see-also"></a><span data-ttu-id="200a5-108">См. также</span><span class="sxs-lookup"><span data-stu-id="200a5-108">See Also</span></span>  
 <span data-ttu-id="200a5-109">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="200a5-109">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="200a5-110">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="200a5-110">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="200a5-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="200a5-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

