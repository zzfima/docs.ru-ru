---
title: "Директивы препроцессора C#"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6378c8df794a4ee75e7b5ca283b18b228ba46383
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="e0ae6-102">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="e0ae6-102">C# preprocessor directives</span></span>
<span data-ttu-id="e0ae6-103">В этом разделе содержатся сведения о следующих директивах препроцессора C#:</span><span class="sxs-lookup"><span data-stu-id="e0ae6-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="e0ae6-104">#if</span><span class="sxs-lookup"><span data-stu-id="e0ae6-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
- [<span data-ttu-id="e0ae6-105">#else</span><span class="sxs-lookup"><span data-stu-id="e0ae6-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)
- [<span data-ttu-id="e0ae6-106">#elif</span><span class="sxs-lookup"><span data-stu-id="e0ae6-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)
- [<span data-ttu-id="e0ae6-107">#endif</span><span class="sxs-lookup"><span data-stu-id="e0ae6-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)
- [<span data-ttu-id="e0ae6-108">#define</span><span class="sxs-lookup"><span data-stu-id="e0ae6-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)
- [<span data-ttu-id="e0ae6-109">#undef</span><span class="sxs-lookup"><span data-stu-id="e0ae6-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="e0ae6-110">#warning</span><span class="sxs-lookup"><span data-stu-id="e0ae6-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)
- [<span data-ttu-id="e0ae6-111">#error</span><span class="sxs-lookup"><span data-stu-id="e0ae6-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)
- [<span data-ttu-id="e0ae6-112">#line</span><span class="sxs-lookup"><span data-stu-id="e0ae6-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)
- [<span data-ttu-id="e0ae6-113">#region</span><span class="sxs-lookup"><span data-stu-id="e0ae6-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)
- [<span data-ttu-id="e0ae6-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="e0ae6-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)
- [<span data-ttu-id="e0ae6-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="e0ae6-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)
- [<span data-ttu-id="e0ae6-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="e0ae6-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="e0ae6-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="e0ae6-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

<span data-ttu-id="e0ae6-118">Дополнительные сведения и примеры см. в разделах по каждой из этих директив.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="e0ae6-119">Хотя у компилятора нет отдельного препроцессора, директивы, описанные в этом разделе, обрабатываются так, как если бы он был.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="e0ae6-120">Они используются в условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="e0ae6-121">В отличие от директив C и C++ вы не можете использовать их для создания макросов.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="e0ae6-122">Директива препроцессора должна быть единственной инструкцией в строке.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0ae6-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e0ae6-123">See also</span></span>
 [<span data-ttu-id="e0ae6-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e0ae6-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e0ae6-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e0ae6-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
