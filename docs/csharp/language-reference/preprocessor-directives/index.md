---
title: "Директивы препроцессора C#"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.preprocessor
dev_langs:
- CSharp
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
caps.latest.revision: 13
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
ms.openlocfilehash: 91bb2daefbc677fad8a3dd93b37aac996234d48c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="e45df-102">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="e45df-102">C# Preprocessor Directives</span></span>
<span data-ttu-id="e45df-103">В этом разделе содержатся сведения о следующих директивах препроцессора C#.</span><span class="sxs-lookup"><span data-stu-id="e45df-103">This section contains information about the following C# preprocessor directives.</span></span>  
  
 [<span data-ttu-id="e45df-104">#if</span><span class="sxs-lookup"><span data-stu-id="e45df-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)  
  
 [<span data-ttu-id="e45df-105">#else</span><span class="sxs-lookup"><span data-stu-id="e45df-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)  
  
 [<span data-ttu-id="e45df-106">#elif</span><span class="sxs-lookup"><span data-stu-id="e45df-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)  
  
 [<span data-ttu-id="e45df-107">#endif</span><span class="sxs-lookup"><span data-stu-id="e45df-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)  
  
 [<span data-ttu-id="e45df-108">#define</span><span class="sxs-lookup"><span data-stu-id="e45df-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)  
  
 [<span data-ttu-id="e45df-109">#undef</span><span class="sxs-lookup"><span data-stu-id="e45df-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)  
  
 [<span data-ttu-id="e45df-110">#warning</span><span class="sxs-lookup"><span data-stu-id="e45df-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)  
  
 [<span data-ttu-id="e45df-111">#error</span><span class="sxs-lookup"><span data-stu-id="e45df-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)  
  
 [<span data-ttu-id="e45df-112">#line</span><span class="sxs-lookup"><span data-stu-id="e45df-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)  
  
 [<span data-ttu-id="e45df-113">#region</span><span class="sxs-lookup"><span data-stu-id="e45df-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)  
  
 [<span data-ttu-id="e45df-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="e45df-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)  
  
 [<span data-ttu-id="e45df-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="e45df-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)  
  
 [<span data-ttu-id="e45df-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="e45df-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="e45df-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="e45df-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
 <span data-ttu-id="e45df-118">Дополнительные сведения и примеры см. в разделах по каждой из этих директив.</span><span class="sxs-lookup"><span data-stu-id="e45df-118">See the individual topics for more information and examples.</span></span>  
  
 <span data-ttu-id="e45df-119">Хотя у компилятора нет отдельного препроцессора, директивы, описанные в этом разделе, обрабатываются так, как если бы он был.</span><span class="sxs-lookup"><span data-stu-id="e45df-119">Although the compiler does not have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="e45df-120">Они используются в условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="e45df-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="e45df-121">В отличие от директив C и C++ вы не можете использовать их для создания макросов.</span><span class="sxs-lookup"><span data-stu-id="e45df-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>  
  
 <span data-ttu-id="e45df-122">Директива препроцессора должна быть единственной инструкцией в строке.</span><span class="sxs-lookup"><span data-stu-id="e45df-122">A preprocessor directive must be the only instruction on a line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e45df-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e45df-123">See Also</span></span>  
 <span data-ttu-id="e45df-124">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e45df-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="e45df-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e45df-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

